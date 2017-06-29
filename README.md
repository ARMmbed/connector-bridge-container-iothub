mbed Device Connector integration bridge image importer for Microsoft IoTHub 

6/29/2017: property editor updates 

6/27/2017: Minor updates 

6/20/2017: Cleanups, updates to properties editor and overall structure

Container Bridge Instance Installation:

1). Clone this repo into a Linux instance that supports docker images

2). cd into the cloned repo and run: ./run-reload-bridge.sh

Once the container instance is live, you must configure the bridge and bind it between your mbed Connector account and your IoTHub Account in Azure. 

1). Please go to your Azure dashboard and create an IoTHub instance. Note your IoTHub name.

2). Please create a SAS Token for your IoTHub Owner ... Make the token good for awhile... 
    Reference: https://azure.microsoft.com/en-us/documentation/articles/iot-hub-sas-tokens/

3). Next go to https://connector.mbed.com and create your mbed Connector Account

4). Once your Connector account is created, you need to "Access Keys" to create an API Key/Token

Now that you have your:

    - IoTHub Name

    - IoTHub Owner SAS Token generated for a suitable length of time

    - Connector API Key/Token generated

Go to:  https://[[your containers public IP address]]:8234

    - username: "admin" (no quotes)

    - password: "admin" (no quotes)

Enter each of IoTHub name, SAS Token, and Connector API Token

    - Please press "SAVE" after *each* is entered... 

    - After all 3 are entered and saved, press "RESTART"

Your Connector bridge should now be configured and operational. 

Copyright 2017. ARM Ltd. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License. 
