# visualping

Publisher: Splunk Community <br>
Connector Version: 2.0.0 <br>
Product Vendor: visualping <br>
Product Name: visualping <br>
Minimum Product Version: 4.9.39220

The visualping app is a convenient tool to monitor websites changes

### Configuration variables

This table lists the configuration variables required to operate visualping. These variables are specified when configuring a visualping asset in Splunk SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**username** | required | string | User name to authenticate using HTTP Basic Authentication |
**password** | required | password | Password to authenticate using HTTP Basic Authentication |
**base_url** | required | string | The base URL for visualping |
**verify_server_cert** | optional | boolean | Verify the Visualping server certificate |

### Supported Actions

[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration <br>
[list jobs](#action-list-jobs) - List visualping jobs <br>
[show result](#action-show-result) - Show the last result of a specific job <br>
[get images](#action-get-images) - Get the images from the last run of a specific job

## action: 'test connectivity'

Validate the asset configuration for connectivity using supplied configuration

Type: **test** <br>
Read only: **True**

#### Action Parameters

No parameters are required for this action

#### Action Output

No Output

## action: 'list jobs'

List visualping jobs

Type: **investigate** <br>
Read only: **True**

List all your VisualPing jobs, sorted by the job status.

#### Action Parameters

No parameters are required for this action

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.data.\*.jobs.active.\*.id | string | `visualping job id` | bd84977cdd2b45c |
action_result.data.\*.jobs.active.\*.url | string | `url` | https://example.com/ |
action_result.data.\*.jobs.active.\*.mode | string | | WEB |
action_result.data.\*.jobs.active.\*.runs | string | | 3 |
action_result.data.\*.jobs.active.\*.jobid | string | | 3003726 |
action_result.data.\*.jobs.active.\*.created | string | | 2020-12-21 15:27:48 |
action_result.data.\*.jobs.active.\*.favicon | string | | metadata/\_vol_9/\_data_924/924307/401942541602d03c6b7e3794d9cbb2f0.png |
action_result.data.\*.jobs.active.\*.trigger | string | | 1 |
action_result.data.\*.jobs.active.\*.interval | string | | 1440 |
action_result.data.\*.jobs.active.\*.last_run | string | | 2020-12-23 16:30:19 |
action_result.data.\*.jobs.active.\*.description | string | | Entry-Specific-Rule |
action_result.data.\*.success | boolean | | True False |
action_result.status | string | | success failed |
action_result.message | string | | Example message |
action_result.summary.active_jobs.\*.id | string | `visualping job id` | bd84977cdd2b45c |
action_result.summary.active_jobs.\*.url | string | `url` | https://example.com/ |
action_result.summary.active_jobs.\*.mode | string | | WEB |
action_result.summary.active_jobs.\*.runs | string | | 3 |
action_result.summary.active_jobs.\*.jobid | string | | 3003726 |
action_result.summary.active_jobs.\*.created | string | | 2020-12-21 15:27:48 |
action_result.summary.active_jobs.\*.favicon | string | | metadata/\_vol_9/\_data_924/924307/401942541602d03c6b7e3794d9cbb2f0.png |
action_result.summary.active_jobs.\*.trigger | string | | 1 |
action_result.summary.active_jobs.\*.interval | string | | 1440 |
action_result.summary.active_jobs.\*.last_run | string | | 2020-12-23 16:30:19 |
action_result.summary.active_jobs.\*.description | string | | Entry-Specific-Rule |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'show result'

Show the last result of a specific job

Type: **investigate** <br>
Read only: **True**

Show the details of the last run of a specific visualping job, including a percent difference.

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** | required | ID of the job | string | `visualping job id` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.id | string | `visualping job id` | 3941f47390034e8 |
action_result.data.\*.id | string | `visualping job id` | 3941f47390034e8 |
action_result.data.\*.url | string | `url` | https://example.com/ |
action_result.data.\*.jobid | string | | 2969557 |
action_result.data.\*.interval | string | | 1440 |
action_result.data.\*.lastcheck | string | | 2020-12-23 01:28:27 |
action_result.data.\*.description | string | | Example description |
action_result.data.\*.PercentDifference | string | | 0.03 |
action_result.status | string | | success failed |
action_result.message | string | | Example message |
action_result.summary.url | string | `url` | https://example.com/ |
action_result.summary.lastCheck | string | | 2020-12-23 01:28:27 |
action_result.summary.description | string | | Example description |
action_result.summary.percentDifference | string | | 0.03 |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'get images'

Get the images from the last run of a specific job

Type: **investigate** <br>
Read only: **True**

Get the images from the last run of a specific job, including the previous image and the difference.

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** | required | ID of the job | string | `visualping job id` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.id | string | `visualping job id` | 3941f47390034e8 |
action_result.data.\*.job_id | string | `visualping job id` | 3941f47390034e8 |
action_result.data.\*.created | string | | 2021-01-01 02:33:29 |
action_result.data.\*.image_diff | string | `url` | https://example.com/2969557_1609464809592_diff.png |
action_result.data.\*.image_previous | string | `url` | https://example.com/2969557_1609374975789.png |
action_result.status | string | | success failed |
action_result.message | string | | Example message |
action_result.summary.created | string | | 2021-01-01 02:33:29 |
action_result.summary.image_diff | string | `url` | https://example.com/2969557_1609464809592_diff.png |
action_result.summary.image_previous | string | `url` | https://example.com/2969557_1609374975789.png |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

______________________________________________________________________

Auto-generated Splunk SOAR Connector documentation.

Copyright 2026 Splunk Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
