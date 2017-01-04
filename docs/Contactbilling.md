<link href="markdown.css" rel="stylesheet"></link>

<h4> Contacts Billing </h4>

Use the /contacts/billing resource to retrieve the billing address and associated contact information of a customer (active, inactive, cancelled).

### **URI**

- /api/v1/customers/{eZpayID}/contacts/billing

**Current Service Usage**

1.	WaterField IVR uses this api to get the billing zip code to verify customer on the call


  **Source:** MDM

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	{eZpayID}	|	String	|	Unique Id assigned to a customer, to fetch the billing address and associated contact information  of this customer|

---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customerId	|	String	|	Unique Id assigned to a customer	|
|	request_tracking_id	|	String	|	Unique tracking identifier	|
|	contacts	|	object: array of contacts	|	Contains customer billing address and contact information	|
|	type	|	String	|	Defines contact type 'billing'	|
|	name	|	String	|	Name of the customer	|
|	first_name	|	String	|	First name of the customer	|
|	middle_name	|	String	|	Middle name of the customer	|
|	last_name	|	String	|	Last name of the customer	|
|	land_line	|	String	|	Land line of the customer	|
|	work_phone	|	String	|	Work phone number of the customer	|
|	mobile_phone	|	String	|	Mobile phone number of the customer	|
|	fax	|	String	|	Fax number of the customer	|
|	email	|	String	|	Email Id of the customer	|
|	address	|	object	|	Contains data about the customer address	|
|	street	|	String	|	Street name	|
|	city	|	String	|	City name	|
|	country	|	String	|	Country code	|
|	province	|	String	|	Cananda state name	|
|	postal_code	|	String	|	Cananda postal code	|
|	state	|	String	|	US state name	|
|	zip	|	String	|	US postal code	|
|	zip4		String	|	4 digit extension postal code for US addresses	|
|	metadata		object	|	Contains WM specific data	|
|	cleansed		String	|	Defines the address validation status	|
|	status		String	|	‘Success’ or ‘Failure’ Success – Transaction executed successfully without any failures Failure – Transaction failed due to some reasons that will be provided in error in response	|
|	error		object: array of error	|	Contains error details in case of failures	|
|	     code		String	|	Error code of the error message	|
|	     message		String	|	Error Description (like Service error)	|
|	  errors		object: array of errors	|	Contains error description in case of failures	|
|	   message		String	|	Actual error message of transaction that had failed	|



---

### **Sample Request**
```
/api/v1/customers/000010000005008/contacts/billing

```

---
### **Headers**

Request-Tracking-Id=8678789
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId= WaterField_312 (QA Environment)

---

### **Sample  Success Response**

```
{
    "request_tracking_id": "8678789",
    "contacts": [
        {
            "type": "billing",
            "name": "CHEN, JACKSON",
            "first_name": "JACKSON",
            "middle_name": " ",
            "last_name": "CHEN",
            "work_phone": "9147212006",
            "mobile_phone": "9147212006",
            "fax": "9147212006",
            "email": "IDZAFEROVIC@APPLE-BANK.COM",
            "address": {
                "street": "2633 LOUISE AVE",
                "city": "ARCADIA",
                "country": "US",
                "state": "CA",
                "zip": "91006",
                "zip4": "5128",
                "longitude": "-118.029523",
                "latitude": "34.107976",
                "metadata": {
                    "cleansed": "true"
                }
            }
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
---
