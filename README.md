# Performance Testing with Apache JMeter & BlazeMeter

Welcome to the **Performance Testing** project repository. This repository contains scenarios and scripts for performance testing using Apache JMeter, assisted by the BlazeMeter extension for recording scenarios.

## Table of Contents
1. [What is Apache JMeter?](#1-what-is-apache-jmeter)
2. [What is the BlazeMeter Plugin?](#2-what-is-the-blazemeter-plugin)
3. [Performance Testing Scenario](#3-performance-testing-scenario)
4. [Step-by-Step Guide](#4-step-by-step-guide)
   - [Step 1: Prepare BlazeMeter Plugin](#step-1-prepare-blazemeter-plugin)
   - [Step 2: Recording Configuration](#step-2-recording-configuration)
   - [Step 3: BlazeMeter Login](#step-3-blazemeter-login)
   - [Step 4: Start Recording](#step-4-start-recording)
   - [Step 5: Login & Navigation Phase](#step-5-login--navigation-phase)
   - [Step 6: Data Input Actions (Add & Edit)](#step-6-data-input-actions-add--edit)
   - [Step 7: Stop & Export to JMX](#step-7-stop--export-to-jmx)
   - [Step 8: Open File in Apache JMeter](#step-8-open-file-in-apache-jmeter)
   - [Step 9: Review Scenarios & Grouping](#step-9-review-scenarios--grouping)
   - [Step 10: Setting Timers & User Load](#step-10-setting-timers--user-load)
   - [Step 11: Adding Listeners (Test Results)](#step-11-adding-listeners-test-results)
5. [Download Apache JMeter](#5-download-apache-jmeter)

---

## 1. What is Apache JMeter?

**Apache JMeter** is a Java-based open-source software that is very important for **load testing**. This tool can simulate a large group of users accessing and sending requests to a target server at the same time.

Using JMeter, we can:
- Measure system performance and load (such as response time and throughput).
- Identify bottlenecks.
- Test system scalability and weaknesses before the application is launched to production.

## 2. What is the BlazeMeter Plugin?

The **BlazeMeter Chrome Extension** is a tool used to record browser activities and automatically convert them into JMeter scripts (.jmx).

In this project, BlazeMeter is used to:
- Speed up the test script creation process without writing every request manually.
- Accurately capture user workflows (such as login, menu navigation, and data input).
- Provide flexibility in organizing scenarios before exporting to JMeter.

## 3. Performance Testing Scenario

This repository contains scenarios and scripts for **Stress Testing** using Apache JMeter. The main goal of Stress Testing is to test and determine the upper limits of system performance, stability, and reliability when pushed with high load.

## 4. Step-by-Step Guide

Here is a step-by-step guide to the testing process with more detailed explanations:

### Step 1: Prepare BlazeMeter Plugin
Use the BlazeMeter extension on Chrome as the starting point for recording scenarios. Make sure the extension is installed and you have logged in so that the JMX export feature is accessible with full functionality.
![BlazeMeter Plugin](ss/1-blazemeter-plugin.jpg)

### Step 2: Recording Configuration
Before recording, set the BlazeMeter configuration, such as disabling the browser cache. This is important so the test simulation represents a new user experience without saved data, making the results more accurate.
![Setting Recording](ss/2-blazemeter-plugin-setting-recording-disable-cache-ajaz-request-.jpg)

### Step 3: BlazeMeter Login
Ensure you are logged into your BlazeMeter account to gain access to download recordings in .jmx format. An authenticated account allows the plugin to process script conversion in the cloud with more complete metadata.
![Sign In](ss/3-blazemeter-plugin-sigin.jpg)

### Step 4: Start Recording
Click the 'Record' button to start capturing network activity in the browser. Run your navigation scenario on the target application as usual; every HTTP request and sent parameter will be automatically recorded by the plugin.
![Start Record](ss/4-blazemeter-plugin-record-start.jpg)

### Step 5: Login & Navigation Phase
Perform the login process to record the application's authentication flow, then continue navigation to main features like the Customer menu. This step forms the main transaction framework that will be load-tested in JMeter later.
![Step Login](ss/4-blazemeter-plugin-record-step-login.jpg)
![Step Pelanggan](ss/5-blazemeter-plugin-record-step-pelanggan.jpg)

### Step 6: Data Input Actions (Add & Edit)
Record data transaction activities such as adding new records or editing existing ones. Measuring performance during database write operations is crucial in Stress Testing to find potential bottlenecks on the server side.
![Tambah Pelanggan](ss/6-blazemeter-plugin-record-step-pelanggan-tambah.jpg)
![Edit Pelanggan](ss/6-blazemeter-plugin-record-step-pelanggan-edit.jpg)

### Step 7: Stop & Export to JMX
Once the scenario is complete, stop the recording and select the export option to '.jmx' format. BlazeMeter will reorganize the activity log into an organized XML structure ready to be opened directly using Apache JMeter.
![Stop & Export](ss/7-blazemeter-plugin-record-export-to-jmx.jpg)
![Select JMX](ss/8-blazemeter-plugin-record-export-to-jmx-2.jpg)
![Export Process](ss/9-blazemeter-plugin-record-export-to-jmx-3.jpg)
![Save File](ss/10-blazemeter-plugin-record-export-to-jmx-4.jpg)

### Step 8: Open File in Apache JMeter
Open the main Apache JMeter application and load the JMX file you downloaded earlier. JMeter will display the Test Plan, which already includes HTTP Request Defaults, Header Manager, and Cookie Manager automatically from the recording.
![Apache JMeter](ss/11-apache-jmeter.jpg)

### Step 9: Review Scenarios & Grouping
Review the list of recorded endpoints in JMeter's navigation panel and ensure they are grouped correctly. You can disable irrelevant requests (like external trackers) to focus on testing the internal server.
![Grouping Endpoint](ss/12-apache-jmeter-all-endpoint-terrecord-dan-terkelompokan.jpg)

### Step 10: Setting Timers & User Load
Set the number of Threads (users) and the Ramp-up period to simulate the desired load. Add a 'Timer' to provide delays between requests so the simulation traffic pattern better resembles real user behavior in a production environment.
![Setting Timer](ss/13-apache-jmeter-setting-timmer.jpg)
![Setting Timer 2](ss/15-apache-jmeter-setting-timmer-2.jpg)

### Step 11: Adding Listeners (Test Results)
Add 'Listener' components like 'Aggregate Report' to view performance statistics such as Response Time and Throughput. Use this data to analyze system stability and determine the maximum capacity of your application.
![Setting Listener](ss/14-apache-jmeter-setting-listener-aggreate-view-listener.jpg)

## 5. Download Apache JMeter

You can download the latest version of Apache JMeter through the following official link:
[Download Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi)
