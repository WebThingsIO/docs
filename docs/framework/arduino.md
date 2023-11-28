# webthing-arduino

## Installation

### Arduino IDE

Add the `webthing` and `ArduinoJson` libraries to your project.

### PlatformIO

Add the `webthing-arduino` and `ArduinoJson` libraries to your project.

## Example

```


#define LARGE_JSON_BUFFERS 1

    #include <Arduino.h>
    #include <Thing.h>
    #include <WebThingAdapter.h>

    #ifdef ESP32
    #include <analogWrite.h>
    #endif

    const char *ssid = "......";
    const char *password = "..........";

    #if defined(LED_BUILTIN)
    const int lampPin = LED_BUILTIN;
    #else
    const int lampPin = 13; // manually configure LED pin
    #endif

    ThingActionObject *action_generator(DynamicJsonDocument *);

    WebThingAdapter *adapter;

    const char *lampTypes[] = {"OnOffSwitch", "Light", nullptr};
    ThingDevice lamp("urn:dev:ops:my-lamp-1234", "My Lamp", lampTypes);

    ThingProperty lampOn("on", "Whether the lamp is turned on", BOOLEAN,
                     "OnOffProperty");
    ThingProperty lampLevel("brightness", "The level of light from 0-100", INTEGER,
                        "BrightnessProperty");

    StaticJsonDocument<256> fadeInput;
    JsonObject fadeInputObj = fadeInput.to<JsonObject>();
    ThingAction fade("fade", "Fade", "Fade the lamp to a given level",
                 "FadeAction", &fadeInputObj, action_generator);
    ThingEvent overheated("overheated",
                      "The lamp has exceeded its safe operating temperature",
                      NUMBER, "OverheatedEvent");

    bool lastOn = true;

    void setup(void) {
    pinMode(lampPin, OUTPUT);
    digitalWrite(lampPin, HIGH);
    Serial.begin(115200);
    Serial.println("");
    Serial.print("Connecting to \"");
    Serial.print(ssid);
    Serial.println("\"");
    #if defined(ESP8266) || defined(ESP32)
    WiFi.mode(WIFI_STA);
    #endif
    WiFi.begin(ssid, password);
    Serial.println("");

    // Wait for connection
    while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
    }

    Serial.println("");
    Serial.print("Connected to ");
    Serial.println(ssid);
    Serial.print("IP address: ");
    Serial.println(WiFi.localIP());
    adapter = new WebThingAdapter("led-lamp", WiFi.localIP());

    lamp.description = "A web connected lamp";

    lampOn.title = "On/Off";
    lamp.addProperty(&lampOn);

    lampLevel.title = "Brightness";
    lampLevel.minimum = 0;
    lampLevel.maximum = 100;
    lampLevel.unit = "percent";
    lamp.addProperty(&lampLevel);

    fadeInputObj["type"] = "object";
    JsonObject fadeInputProperties =
      fadeInputObj.createNestedObject("properties");
    JsonObject brightnessInput =
      fadeInputProperties.createNestedObject("brightness");
    brightnessInput["type"] = "integer";
    brightnessInput["minimum"] = 0;
    brightnessInput["maximum"] = 100;
    brightnessInput["unit"] = "percent";
    JsonObject durationInput =
      fadeInputProperties.createNestedObject("duration");
    durationInput["type"] = "integer";
    durationInput["minimum"] = 1;
    durationInput["unit"] = "milliseconds";
    lamp.addAction(&fade);

    overheated.unit = "degree celsius";
    lamp.addEvent(&overheated);

    adapter->addDevice(&lamp);
    adapter->begin();

    Serial.println("HTTP server started");
    Serial.print("http://");
    Serial.print(WiFi.localIP());
    Serial.print("/things/");
    Serial.println(lamp.id);

    #ifdef analogWriteRange
    analogWriteRange(255);
    #endif

    // set initial values
    ThingPropertyValue initialOn = {.boolean = true};
    lampOn.setValue(initialOn);
    (void)lampOn.changedValueOrNull();

    ThingPropertyValue initialLevel = {.integer = 50};
    lampLevel.setValue(initialLevel);
    (void)lampLevel.changedValueOrNull();

    analogWrite(lampPin, 128);

    randomSeed(analogRead(0));
    }

    void loop(void) {
    adapter->update();
    bool on = lampOn.getValue().boolean;
    if (on) {
    int level = map(lampLevel.getValue().number, 0, 100, 255, 0);
    analogWrite(lampPin, level);
    } else {
    analogWrite(lampPin, 255);
    }

    if (lastOn != on) {
    lastOn = on;
    }
    }

    void do_fade(const JsonVariant &input) {
    JsonObject inputObj = input.as<JsonObject>();
    long long int duration = inputObj["duration"];
    long long int brightness = inputObj["brightness"];

    delay(duration);

    ThingDataValue value = {.integer = brightness};
    lampLevel.setValue(value);
    int level = map(brightness, 0, 100, 255, 0);
    analogWrite(lampPin, level);

    ThingDataValue val;
    val.number = 102;
    ThingEventObject *ev = new ThingEventObject("overheated", NUMBER, val);
    lamp.queueEventObject(ev);
    }

    ThingActionObject *action_generator(DynamicJsonDocument *input) {
    return new ThingActionObject("fade", input, do_fade, nullptr);
    }


```