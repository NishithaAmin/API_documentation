<link href="markdown.css" rel="stylesheet"></link>

<h4> Profiles </h4>

Use the /profiles resource to retrieve customer profile details for the customer id. This api provides profile details such as log in information, auto pay information etc. to the customer. MDM is the source of profile information. Provide customer id in the endpoint.


### **URI**

- /api/v1/customers/{customerId}/profiles

**Current Service Usage**

1.	Ebiz uses this api to get customer profile details from MDM

  **Source:** MDM

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customerId	|	Number	|	Unique customer Id for which profile details needs to be retrieved.|


---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	profiles	|	Object	|	Contains customer profile details such as log on information, auto pay information	|
|	id	|	String	|	Log in id	|
|	paperless_invoice	|	Boolean	|	Paperless Flag for receiving Invoices	|
|	auto_pay	|	Boolean	|	Auto Pay flag for Billing	|
|	auto_pay_owner	|	Boolean	|	Auto Pay flag for customer	|
|	registered_code	|	String	|	Registered code	|
|	logon_status	|	String	|	Customer logon status into WM.com.	|
|	first_name	|	String	|	First name of customer	|
|	last_name	|	String	|	Last name of the customer	|
|	email	|	String	|	Email id of the customer	|
|	last_login_date	|	String	|	Customer Last Login Date and Time into WM.com	|


---

### **Sample Request**
```
/api/v1/customers/104127993008/profiles

```

---
### **Headers**

Request-Tracking-Id=12345
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=eBiz_215

**Body**
{
"customer_id": "156714543005",
    "reason_code": "RES",
    "reason": "Resume Service",
    "dispatch_date_time": "2016-03-22T11:50:35.000Z",
    "service": {
        "id": 1,
        "code": "6FL",
        "description": "6 Yard FEL"
    },
    "requestor_info": {
        "name": "TESTMAN1",
        "phone": "9874564566",
        "email": "abc@wm.com"
    },
    "assigned_to_user": "CSR1"
}

---

### **Sample Response**

{
    "status":"SUCCESS",
    "transaction_id":"456"
}


```

---
