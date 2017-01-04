<link href="markdown.css" rel="stylesheet"></link>

<h4> Contacts </h4>

Use the /contacts resource to update the associated billing and service contact information of a customer (active, inactive, cancelled).

### **URI**

- /api/v1/customers/{eZpayID}/contacts

**Current Service Usage**

1.	CAAG uses this api to update the billing and service contact information of a customer on the call


  **Source:** CAAG
  **Target:** MAS and MDM

---

### **Methods**
- POST

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	request_tracking_id	|	String	|	Unique tracking identifier	|
|	contacts	|	object: array of contacts	|	Contains customer billing and service address and contact information	|
|	type	|	String	|	Defines contact type 'billing'	|
|	name	|	String	|	Name of the customer	|
|	work_phone_extension	|	String	|	Extension of the work phone number of the customer	|
|	work_phone	|	String	|	Work phone number of the customer	|
|	mobile_phone	|	String	|	Mobile phone number of the customer	|
|	fax	|	String	|	Fax number of the customer	|
|	email	|	String	|	Email Id of the customer	|
|	organization_name	|	String	|	Name of the Customer’s Organization	|
|	type	|	String	|	Defines contact type ‘service’	|
|	name	|	String	|	Name of the customer	|
|	work_phone_extension	|	String	|	Extension of the work phone number of the customer	|
|	work_phone	|	String	|	Work phone number of the customer	|
|	mobile_phone	|	String	|	Mobile phone number of the customer	|
|	fax	|	String	|	Fax number of the customer	|
|	email	|	String	|	Email Id of the customer	|
|	organization_name	|	String	|	Name of the Customer’s Organization	|


---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	request_tracking_id	|	String	|	Unique tracking identifier passed in the request Headers by source	|
|	status	|	String	|	"‘Success’ or ‘Failure’
Success – Transaction executed successfully without any failures
Failure – Transaction failed due to some reasons that will be provided in error in response
"	|
|	error	|	object: array of error	|	Contains error details in case of failures	|
|	     code	|	String	|	Error code of the error message	|
|	     message	|	String	|	Error Description (like Service error)	|
|	  errors	|	object: array of errors	|	Contains error description in case of failures	|
|	   message	|	String	|	Actual error message of transaction that had failed	|




---

### **Sample Request**
```
/api/v1/customers/000010000005008/contacts

```

---
### **Headers**

Accept = application/json
Request-Tracking-Id=67865456
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId= CAAG_302 (QA Environment)
Content-Type = application/json

---

### **Sample Request**

```
{
	"contacts": [{
		"type": "billing",
		"work_phone": "9147212006",
		"work_phone_extension": "2006",
		"organization_name": "APPLE BANK FOR SAVINGS",
		"email": "IDZAFEROVIC@APPLE-BANK.COM",
		"name": "John Smith",
		"mobile_phone": "9147212006",
		"fax": "9147212006"
	}, {
		"type": "service",
		"work_phone": "9147212006",
		"work_phone_extension": "2006",
		"organization_name": "APPLE BANK FOR SAVINGS",
		"name": "John Smith",
		"mobile_phone": "9147212006",
		"fax": "9147212006"
	}]
}

```
### **Sample Success  Response:**
```
{
    "status": "Success",
    "request_tracking_id": "756345"
}


```

### **Sample Failure  Response:**
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
---
