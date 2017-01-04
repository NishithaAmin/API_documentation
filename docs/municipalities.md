<link href="markdown.css" rel="stylesheet"></link>

<h4> municipalities </h4>

Use the /municipalities resource to fetch the municipalities details for the given library suffix.

### **URI**

- /api/v1/libraries/{libraryId}/municipalities

**Current Service Usage**

1.	WM.com uses this service to get municipality details like code and description from MAS


  **Source:** MAS

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	{libraryId}	|	String	|	library suffix|

---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	libraryId	|	String	|	library suffix	|
|	request_tracking_id	|	String	|	Unique tracking identifier	|
|	municipalities	|	Object: array of municipalities	|	Contains Municipality details like code and description	|
|	code	|	String	|	Municipality Code	|
|	description	|	String	|	Description of Municipality Code	|
|	status	|	String	|	‘Success’ or ‘Failure’	|
|		|		|	Success – Transaction executed successfully without any failures	|
|		|		|	Failure – Transaction failed due to some reasons that will be provided in error in response	|
|	error	|	object: array of error	|	Contains error details in case of failures	|
|	     code	|	String	|	Error code of the error message	|
|	     message	|	String	|	Error Description (like Service error)	|
|	  errors	|	object: array of errors	|	Contains error description in case of failures	|
|	   message	|	String	|	Actual error message of transaction that had failed	|




---

### **Sample Request**
```
/api/v1/libraries/113A/municipalities

```

---
### **Headers**

Request-Tracking-Id=56756
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=eBiz_327

---

### **Sample  Success Response**

```
{
    "request_tracking_id": "56756",
    "municipalities": [
        {
            "code": "AE",
            "description": "AIRELLO AQUISITION"
        },
        {
            "code": "CA",
            "description": "CASACELLI ACQUISITION"
        },
        {
            "code": "DQ",
            "description": "DO NOT USE"
        },
        {
            "code": "DW",
            "description": "DO NOT USE"
        },
        {
            "code": "JP",
            "description": "DO NOT USE"
        },
        {
            "code": "MA",
            "description": "DO NOT USE"
        },
        {
            "code": "MG",
            "description": "MARAGGIO ACQUISITION"
        },
        {
            "code": "MK",
            "description": "DO NOT USE"
        },
        {
            "code": "NH",
            "description": "DO NOT USE"
        },
        {
            "code": "NV",
            "description": "DO NOT USE"
        },
        {
            "code": "PE",
            "description": "DO NOT USE"
        },
        {
            "code": "TE",
            "description": "TEMPORARY"
        },
        {
            "code": "US",
            "description": "USA CUSTOMER"
        },
        {
            "code": "WC",
            "description": "WCI"
        },
        {
            "code": "BOS",
            "description": "BOSTON"
        },
        {
            "code": "001",
            "description": "CITY OF CHELSEA"
        },
        {
            "code": "",
            "description": "RESEARCH"
        }
    ]
}



```
### **Sample Failure Response:**
```
{
    "error": {
        "code": "500",
        "message": "Service Error",
        "errors": [
            {
                "message": "Source not configured"
            }
        ]
    },
    "request_tracking_id": "3432273233"
}



```

###**Error Response - Not Found:**
```

{
  "error": {
    "code": "404",
    "message": "Not Found",
    "errors": [
      {
        "message": "Invalid Resource"
      }
    ]
  },
  "request_tracking_id": "123"
}

***************** HTTP Status Code ***************
status: 404 Not found
```

###**Error Response - Method Not Allowed:**

```
***************** HTTP Status Code ***************
status: 405 Method Not Allowed
```
###**Error Response - Validation Error:**
```
{
  "error": {
    "code": "422",
    "message": "Validation Error",
    "errors": [
      {
        "message": "ClientId\/ProfileId - Header is a required field"
      }
    ]
  },
  "request_tracking_id": "123"
}

***************** HTTP Status Code ***************
status: 422 Validation Error
```
###**Error Response - Service Error:**
```

{
  "error": {
    "code": "500",
    "message": "Internal Server Error",
    "errors": [
      {
        "message": "Source not configured"
      }
    ]
  },
  "request_tracking_id": "123"
}
***************** HTTP Status Code ***************
status: 500 Service Error
```
---
