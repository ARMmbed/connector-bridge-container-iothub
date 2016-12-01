mbed Device Connector integration bridge image importer for Microsoft IoTHub 

Original Date: April 22, 2016

    4/22/2016: Initial checkin. Added configurator supporting url-unsafe values

    4/26/2016: Updated with latest bridge runtime. Bi-directional support enabled. CoAP get() fixes/enablement.


    5/03/2016: Updated with latest changes from bridge source... bug fixes.

    5/06/2016: Updated with latest changes from bridge source... bug fixes.

    5/13/2016: Updated with latest changes from bridge source... bug fixes. Support for put async replies.

    5/17/2016: Updated with latest bridge. Support for device attribute flow into cloud device description. JSON type parsing fixes.

    5/26/2016: Updated with latest bridge. JSON type parsing fixes.

    5/27/2016: Updated with latest bridge. Enabled REST versioning support

    6/11/2016: Updated with latest bridge.

    6/29/2016: Updated with latest bridge.

    8/13/2016: Updated with latest bridge.

    8/14/2016: Updated with latest bridge.

    8/16/2016: Updated with latest bridge. Bridge now optionally supports long polling.

    8/23/2016: Updated with latest bridge.

    8/24/2016: Updated with latest bridge.

    8/31/2016: Updated with latest bridge. Minor fix to CoAP responses where "verb" key is now "coap_verb" key - aligns with request payload structure.

    9/13/2016: Updated with latest bridge.

    9/20/2016: Updated with latest bridge.

    11/3/2016: Updated with latest bridge.

    11/9/2016: Updated with latest bridge.

    11/12/2016: Updated with latest bridge.

    11/13/2016: Updated with latest bridge.

Container Bridge source (Apache 2.0 licensed - Enjoy!): https://github.com/ARMmbed/connector-bridge.git


Container Bridge Instance Installation:

1). Clone this repo into a Linux instance that supports docker images

2). cd into the cloned repo and run: ./run-reload-bridge.sh

If Starting on a non-Azure Container Instance: 

3). Note the public IP address of your linux runtime - update "start-bridge.sh" and replace "192.168.1.230" with yours

4). invoke: ./start-bridge.sh

If Starting on an Azure Container Instance:

3). invoke ./start-bridge-azure.sh

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

Your IoTHub-Connector bridge should now be configured and operational. 

For your mbed endpoint, you can clone and build (via yotta) this: https://github.com/ARMmbed/mbed-ethernet-sample

    - This sample assumes you are using the NXP K64F + mbed Application Shield

Additionally, I have a sample Java application that can receive and respond to IoTHub messages via the Microsoft IoTHub Service SDK. The project can be found here: https://github.com/ARMmbed/iot-event-hub-responder 

Enjoy!

Copyright 2015. ARM Ltd. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License. 
