# Changelog Alensy EMS

## 0.7.0 - 18/8/02021

### Added
- used for new features.

### Changed
- used for changes in existing functionality.

### Deprecated
- used for soon-to-be removed features.

### Removed
- used for now removed features.

### Fixed
- used for any bug fixes.

### Security
- used in case of vulnerabilities.

### Known Issues
-  used in case any known issue going in the release

### Limitation
-  used any limitation of the project/project in the current release

## 0.6.1 - 17/08/2021

### Changed
- Change sending of BlackList Grey List text to numbers over Local MQTT.
- Don't send TimeStamp if the device is not active.

## 0.6.0 - 09/07/2021

### Added
- Getting Alert Settings and Model's Library information from SpokeZone using User Credentials.
- Generating Email Alert Notification for parameters going beyond defined limited.
- Sending Grey-List and Black-List Error Notification through Email Alert.
- Sending Grey-List and Black-List Status to local MQTT and SpokeZone Broker.
- Sending status updates to local MQTT Broker to display at the local portal.

### Improved
- Filtering IoT Service messages using Display parameters before sending.

### Fixed
- Debug app sends the logs after Shutting down the EMS app.
- Error in Read Scheduler Service after black list of a device.

### Known issues
- EMS app stops the communication when debugging is enabled, and the debug app is closed Not disabled (closed the debug terminal).
- EMS Stop updating the logs.
- Debug app connection error: Failed to deserialize.

## 0.5.0 - 08/06/2021

### Added
- Unit Tests for Data Processing Service and Database Access Layer.
- Capability to add variations to parsed values, if the simulation is enabled.
- Sending updates to local MQTT Broker to display at the local portal.

### Improved
- Reduced the computation of the parsing process of DB Update.
- Improved IoT Service Response.

### Fixed
- Segmentation Fault in Modbus Interface causing application to stop.
- Corrected 32bit Register parsing.

### Known issues
- Debug app sends the logs after Shutting down the EMS app.
- EMS app stops the communication when debugging is enabled, and the debug app is closed Not disabled (closed the debug terminal).
- EMS Stop updating the logs.
- Debug app connection error: Failed to deserialize.

## 0.4.0 - 30/04/2021

### Added
- MongoDB Replica Set with the capability to generate operations log (oplog).
- Watcher Implemented on Replica Set oplog to detect changes in the MongoDB.
- MQTT Service which handles local MQTT Client to communicate with other applications and services inside Odroid/Linux.

### Improved
- Changed communication between EMS Application and Debug Application from TCP Socket to MQTT.
- Improved IoT Service functionality by getting SpokeZone Credentials from Environmental Variables.
- Improved the functionality of ModbusInterface to Peek the Queue and then dequeue after executing the request.
- Improved the Queue functionality to restrict it from having duplicate messages. Implemented for queue entering ModbusInterface.
- Enhanced Data Processing Service functionality to differentiate between the devices with the same address but on different Modbus Interface.
- Improved Logging Information for a better understanding of the logs.

### Fixed
- Excessive logging by prioritizing the logging information.
- MongoDB couldn't connect to the server that caused connection refusal.
- MongoDB Replica Set does not start automatically on reboot.
- Debug app is showing -ive wait time while sending debug log message to Alensy EMS app.
- Alensy EMS enable debug timeout.

### Known issues
- Debug app connection error: Failed to deserialize.
- Debug app sends the logs after Shutting down EMS app.
- EMS app stops the communication when debugging is enabled, and the debug app is closed Not disabled (closed the debug terminal).
- EMS Stop updating the logs.
- Segmentation Fault in Modbus Interface.
 
## 0.3.0 - 02/03/2021

### Added
- Added support for multiple Modbus RTU via serial port. [AE-184]

### Fixed
- When EMS Alensy app is not running, Debug app does not run.
- Stop allowing reading negative or out of range baudrate.
- Calculating the number of registers to read for Modbus message block in DBM parser.
- Failed to store default baudrate value when overridebaudrate is false.
- Error occurs while trying to update database when modbus message cycle time of all messages are set to zero.
- Set modbus response timeout interval to atleast 500ms.

### Known Issues
- Modbus error: Bus contention (Response comes after timeout)
- Application crashes due to too much file logging which consumes all of the odroid's memory.

## 0.2.0 - 03/02/2021

### Added
- Added operating modes in Alensy EMS App
- Debug app for debugging Alensy EMS App
	- Reading log files based on date time filter
	- Filtering logs based on Modbus request/response messages
	- Printing logs on console
	- Getting Alensy EMS App operating mode
- Timeout for debug mode in Alensy EMS App
- Limited FIFO Queues Size. 
	- Wrapped C# “ConcurrentQueues” class into our own class named “MessageQueue”.
- Automatic Serial Port Detection 
	- Detects closest named available serial port in case of unavailability of actual serial port.
- Modified read scheduler to schedule all the ready messages in single iteration.
- Error handling due to bus contention
	- Validate by matching device's address and function code of the request and response message.
- BugFix: Modbus interface:: Buffers and pointers where not cleared in case of timeout.
- BugFix: Modbus simulator:: Added validation for Modbus register csv file.
- Unit tests:
	- DbmParser 
	- EmsParser
- Added Retry Mechanism in Modbus Interface
- Added Dynamic Response Timeout
- Modified DataParsing for MultiChannel Device Support
- Added Data Processing Service.
- Added MongoDB Database.
- Added IoT Service, Which sends Data from database to SpokeZone.
- Added SpokeSettings.json, settings for communication with SpokeZone MQTT Broker.


## 0.1.0 - 26/12/2020

### Added
- Classes for infrastructure which will be used to store JSON and DBM files data
- EMS Parser which parses Arch JSON file
- DBM Parser which parses Device DBM files
- Read Scheduler which schedules Read request messages for devices
- Modbus interface for modbus RTU communication
- Modbus device simulator to simulate a Modbus device
- added appsettings.json for configuration
- Injected Ilogger powered by serilog