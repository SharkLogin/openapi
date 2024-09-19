### Function Overview

Our API can assist users in programmatically reading and writing environment configuration information, starting and closing browsers, querying environments, and other basic API functions. It can also be used in conjunction with automation frameworks such as Selenium and Puppeter to automate browser operations.

### Usage

- Check that the API interface status in the profiles -> settings button is normal. The current version API interface address is:` http://localhost:50213/ `The default port number is' 50213 ', based on the address seen in the settings.
- Use scripts or HTTP request tools to call local API interfaces, supporting programmatic operations such as starting/closing browsers.
- The parameter types of API interfaces are all strings, and the content format of POST is JSON. Non essential parameters are optional and can be left blank.
- Access frequency control, all interfaces have access frequency control, and each interface can request a maximum of once per second.

