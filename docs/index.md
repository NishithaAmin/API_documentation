# ![wmlogo][wmlogo] API Documentation

### Overview

Welcome to Waste Management REST API reference. Listed in these pages are the API that is currently publicly available for our customers to consume. Use the navigation bar on the left to explore the API.

Please contact us through **apiaccess@wm.com** to obtain access to the API or if you have any questions, with a brief description of your need or issue

---

### Getting started
To use the WM  API, Please contact us through **apiaccess@wm.com** to obtain access

---

### Base URL

Waste Management supports two environments for REST APIs Test and Production



| Enviroment    |Description | EndPoint                              |
| -------------	|----------------|-----------------------------------------------------------------|
| Test           | Test. Use your test credentials to generate an access token to make calls to the Sandbox URIs.    | **https://apitest.wm.com/v1**  |
| Production           | Test. Use your test credentials to generate an access token to make calls to the Sandbox URIs.    |  **https://api.wm.com/v1** |

---
### Version

- v1

---
### Authentication & Headers

For each API call the following headers need to be set:



-	**Authorization:** Bearer `<JWT token>`. **Required** (will be provided by WM)
-	**Request-Tracking-Id:** Unique identifier for each request. **Required**
-	**ClientId:** will be provided by WM. **Required**
-	**Accept:** Set to application/json or application/xml. Default is application/json. **Optional**

---

### Try out
You can test the API using the `curl` application or other api testing and browser based tools like postman available for free.
<div class="shell-wrap">
  <p class="shell-top-bar">/Users/apiDeveloper/Documents/help/</p>
  <ul class="shell-body">
    <li>cd&nbsp;/Users/apiDeveloper/Documents/help/</li>
    <li>curl&nbsp;https://apitest.wm.com/v1/test/helloworld</li>
  </ul>
</div>

---

## API


[wmlogo]: ./images/wmlogo.png "Waste Management Logo"
