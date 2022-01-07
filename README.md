[comment]: # "Auto-generated SOAR connector documentation"
# visualping

Publisher: Splunk Community  
Connector Version: 1\.0\.1  
Product Vendor: visualping  
Product Name: visualping  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.9\.39220  

The visualping app is a convenient tool to monitor websites changes

[comment]: # " File: readme.md"
[comment]: # "    Copyright (c) 2021 Splunk Inc."
[comment]: # ""
[comment]: # "    Licensed under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0.txt)"
[comment]: # ""
Uses for visualping users include:

-   Competitive website and activities
-   Pricing and special offers changes
-   Job offers from their most coveted companies
-   Google search rankings
-   Newsfeeds and alerts
-   Changes in government regulations and legislations
-   New documentation from insurance and financial companies
-   General automation purposes
-   App version update monitoring


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a visualping asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**username** |  required  | string | User name to authenticate using HTTP Basic Authentication
**password** |  required  | password | Password to authenticate using HTTP Basic Authentication
**base\_url** |  required  | string | The base URL for visualping

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[list jobs](#action-list-jobs) - List visualping jobs  
[show result](#action-show-result) - Show the last result of a specific job  
[get images](#action-get-images) - Get the images from the last run of a specific job  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'list jobs'
List visualping jobs

Type: **investigate**  
Read only: **True**

List all your VisualPing jobs, sorted by the job status\.

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.jobs\.active\.\*\.id | string |  `visualping job id` 
action\_result\.data\.\*\.jobs\.active\.\*\.url | string |  `url` 
action\_result\.data\.\*\.jobs\.active\.\*\.mode | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.runs | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.jobid | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.created | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.favicon | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.trigger | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.interval | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.last\_run | string | 
action\_result\.data\.\*\.jobs\.active\.\*\.description | string | 
action\_result\.data\.\*\.success | boolean | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.active\_jobs\.\*\.id | string |  `visualping job id` 
action\_result\.summary\.active\_jobs\.\*\.url | string |  `url` 
action\_result\.summary\.active\_jobs\.\*\.mode | string | 
action\_result\.summary\.active\_jobs\.\*\.runs | string | 
action\_result\.summary\.active\_jobs\.\*\.jobid | string | 
action\_result\.summary\.active\_jobs\.\*\.created | string | 
action\_result\.summary\.active\_jobs\.\*\.favicon | string | 
action\_result\.summary\.active\_jobs\.\*\.trigger | string | 
action\_result\.summary\.active\_jobs\.\*\.interval | string | 
action\_result\.summary\.active\_jobs\.\*\.last\_run | string | 
action\_result\.summary\.active\_jobs\.\*\.description | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'show result'
Show the last result of a specific job

Type: **investigate**  
Read only: **True**

Show the details of the last run of a specific visualping job, including a percent difference\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | ID of the job | string |  `visualping job id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.id | string |  `visualping job id` 
action\_result\.data\.\*\.id | string |  `visualping job id` 
action\_result\.data\.\*\.url | string |  `url` 
action\_result\.data\.\*\.jobid | string | 
action\_result\.data\.\*\.interval | string | 
action\_result\.data\.\*\.lastcheck | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.PercentDifference | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.url | string |  `url` 
action\_result\.summary\.lastCheck | string | 
action\_result\.summary\.description | string | 
action\_result\.summary\.percentDifference | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get images'
Get the images from the last run of a specific job

Type: **investigate**  
Read only: **True**

Get the images from the last run of a specific job, including the previous image and the difference\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | ID of the job | string |  `visualping job id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.id | string |  `visualping job id` 
action\_result\.data\.\*\.job\_id | string |  `visualping job id` 
action\_result\.data\.\*\.created | string | 
action\_result\.data\.\*\.image\_diff | string |  `url` 
action\_result\.data\.\*\.image\_previous | string |  `url` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.created | string | 
action\_result\.summary\.image\_diff | string |  `url` 
action\_result\.summary\.image\_previous | string |  `url` 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 