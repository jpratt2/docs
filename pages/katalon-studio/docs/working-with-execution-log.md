---
title: "View and Customize Execution Log"
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/working-with-execution-log.html
redirect_from:
    - "/katalon-studio/docs/working-with-execution-log/"
    - "/display/KD/View+Execution+Log/"
    - "/display/KD/View%20Execution%20Log/"
    - "/x/6ANO/"
    - "/katalon-studio/docs/view-execution-log/"
    - "/katalon-studio/tutorials/viewing_execution_logs.html"
    - "/katalon-studio/docs/view-execution-log.html"
description:
---
> Starting from Katalon Studio version 5.9.

Viewing execution log is the very first approach when troubleshooting automation test execution. The key information in the log can quickly help project teams pinpoint root causes of any issues. Katalon Studio execution logs are optimized to provide such information so that you can have a comprehensive view of the tests run.

## View Execution Log

Once your test cases/test suites finish execution, you can review the results on the **Log Viewer** views.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/view-execution-log/image2017-6-30-213A253A13.png)

Using the filter options, you can specify what type of logs to be displayed:

| Filter | Description |
| --- | --- |
| All | Show all the log messages. |
| Info | Show only the log messages for information/reference. |
| Passed | Show only the log messages indicating that a step is successfully executed. |
| Failed | Show only the log messages indicating that a test step is failed to execute. |
| Error | Show only the log messages indicating that some error has occurred at a given step. |
| Warning | Show only the log messages indicating that a test step is failed but accepted as warning. |
| Not Run | Show only the log messages indicating that a test step is skipped. |

### Tabular view vs. Tree View

The **Log Viewer** can be viewed in different modes: **tabular** view and **tree** view. You can switch to tree view by selecting the **Tree View** toggle as illustrated below:

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/view-execution-log/image2017-6-30-213A263A35.png)

The **Tree View** display logs in a structural way that relates to how the test case/test suite organized. Additionally, users can now navigate to the respective step by selecting from the context menu as showed below:

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/view-execution-log/image2017-6-23-153A553A57.png)

### Scroll Lock

While the test is being executed, the **Log Viewer** will be updated with real-time log messages, where the most recent log message is shown at the bottom of the view. Therefore, the **Log Viewer** is kept scrolling down during the test execution. However, users may want to keep the **Log Viewer** standing still so that they can verify certain log message. In order to stop this scrolling behavior, you can select **Scroll Lock**.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/view-execution-log/image2017-6-30-213A273A35.png)

## Customize Console Log

### Execution Progress Debugger

Katalon Studio execution log displays full details of actions that are performed during the test run to help you debug better. The test log contains all relevant information about the test run. Full test step statements and desired capabilities information are also included. Log levels are ANSI color-coded for different kind of levels: INFO, DEBUG, WARING, ERROR for an easier view of the execution log, as shown in the screenshot below.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/new-log.png)

In Log Viewer, the Status Bar helps you quickly get the status of the recent tests run. When there are FAILED or ERROR tests from a current job, the status bar has the RED color to indicate such, and GREEN color for tests run with PASSED status. (For Windows only)

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/new-status-bar.png)

### Extensive logs for Web Service testing

Sending and receiving Web Service can be a troublesome task due to many factors involved from both client’s and server’s sides.  Since version 5.9, Katalon Studio has included the HAR file in Web Service execution’s log. The HAR file contains low-level data to quickly help you identify the key performance problems with Web services.
Upon sending requests, a relative .har file will be recorded and made accessible from execution logs. The physical file is stored directly on the current executed machine.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/har-log.png)

If you execute Web Service Suites, these .har files are stored in the requests\main folder under the generated report folders.

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/har-location.png)

Using the .har file in services analyzer such as https://toolbox.googleapps.com/apps/har_analyzer/  will provide quality insights about the Web Service request and response. This will help the project team quickly identify key issues and efficiently allocate resources to address the issue. Some issues that can be identified include:

- Performance issues: slow page load, timeout when performing a certain task, ...

- Page rendering issues: incorrect page format, missing information, ...

### Logs Configuration

The deepest level of logs called TRACE. Use TRACE level when you need more logs details than DEBUG level, which is used by default. You can also lessen the logs details by using INFO level.

In case you want to change the log’s level of one or multiple packages, this setting is located and stored in Include > Config > log.properties file

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/log-properties.png)

By uncommenting logging.level.com.kms=TRACE line, the differences are noticeable

**Before**

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/before-trace.png)

**After**

![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/after-trace.png)

### Log executed test steps

Starting from **Katalon Studio version 7.0**, an option to disable *Log executed test steps* is available in **Project Settings > Executions**. By enabling or disabling this option, you can decide whether the logs include executed test steps or not.

**Enabled**
![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/enabled.png)

**Disabled**
![](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/working-with-execution-log/disabled.png)

### Summary

- Katalon Studio execution logs are enhanced for better debugging process and observation of execution progress.

- Logs level can be configured directly from `log.properties` file.

- `.har` file is generated and stored in Web Service request logs. It can be used to analyze and troubleshoot performance or connection issues (if any).

- Logs can be set to include or exclude the executed test steps.
