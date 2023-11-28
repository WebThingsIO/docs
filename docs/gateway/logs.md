# Logs

The logging screen can be used to log values of properties over time and visualise that information on a graph.

To navigate to the logs screen, choose the "Logs" option from the main menu.

![Screenshot of the main menu with the "Logs" option selected](images/main_menu-logs.png)

## Add Log

To add a log, click the "+" button at the bottom right of the screen.

![Screenshot of the empty logs screen](images/logs_screen-empty.png)

You will then see the new log screen.

1. Choose a device whose property you would like to log
2. Choose a numerical or boolean property you would like to log
3. Choose how long you would like to retain logged data for before it is automatically deleted
4. Click the "Save" button

![Screenshot of the new log screen with dropdowns for device and property name, and a number field and unit dropdown for the retention period](images/new_log.png)

You will then be navigated to the view logs screen, with an empty graph representing the log you just created.

![Screenshot of the logs screen with one graph representing the log that was created](images/view_logs.png)

**⚠️ Warning:** If saving logs to an SD card (e.g. on a Raspberry Pi), writing large quantities of data can shorten the life of your memory card.

## View Logs

To view an individual log full screen, click its title from the view logs screen.

![Screenshot of a collection of graphs representing logs](images/view_logs-multiple_logs.png)

The data in the log is represented as a line graph. You can set the timescale of the graph to "minute", "hour", "day" or "week" depending on the duration you'd like to view at any one time. You can then scroll through the logged data using the scrollbar at the bottom.

![Screenshot of a line graph of a numerical property over time](images/view_log-populated.png)

Both numerical and boolean (true/false) types of property can be logged.

The x axis will show the timescale, and the y axis will show the range and unit of the values.

Logs are updated in real time, which you will notice when viewing the "Minute" time resolution because the graph will animate across the screen.

![Screenshot of a line graph of a boolean property over time](images/view_log-boolean.png)

**💡 Tip:** You can hover over a data point to view its exact timestamp and value.

## Remove Log

To remove a log, from the view log screen click the overflow menu at the bottom right of the screen and click the "Remove" option.

![Screenshot of the log overflow menu with the "Remove" option selected](images/remove_log_option.png)

You will then be shown a confirmation dialog which will confirm that you want to permanently delete the log.

**⚠️ Warning:** Removing a log will also permanently delete all of its data.

![Screenshot of the remove log confirmation dialog](images/remove_log-confirm.png)
