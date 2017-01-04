<link href="markdown.css" rel="stylesheet"></link>

<h4> Tickets </h4>

Use the /tickets resource to post the resume service tickets to MAS for cut-off customers. This api creates service request for future date to resume the service for a cut-off customer. Data will be posted to MAS to create a resume service request. Provide customer id in the endpoint


### **URI**

- /api/v1/customers/{customerId}/tickets

**Current Service Usage**

1.	Siebel uses this api to create resume service request in MAS

  **Source:** MDM

---

### **Methods**
- POST

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customer_id	|	Number	|	Unique customer Id for which resume service request needs to be created	|
|	reason_code	|	String	|	Reason code	|
|	reason	|	String	|	Description of the reason code	|
|	dispatch_date_time	|	String	|	Date and time indicates when the request needs to be served.	|
|	service	|	Object	|	Service details	|
|	id	|	String	|	Service Id	|
|	code	|	String	|	Service code	|
|	description	|	String	|	Description of the service	|
|	requestor_info	|	Object	|	Requestor details	|
|	name	|	String	|	Service requestor’s name	|
|	phone	|	Number	|	Service requestor’s phone	|
|	email	|	String	|	Service requestor’s email id	|
|	assigned_to_user	|	String	|	User assigned	|

---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	status	|	String	|	Transaction status	|
|	transaction_id	|	Number	|	Unique Transaction ID	|

---

### **Sample Request**
```
/api/v1/customers/104127993008/tickets

```

---
### **Headers**

Request-Tracking-Id=456
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=Siebel_201

---

### **Sample Response**

```
{
	"profiles": [{
		"id": "104127993008^26984565|E",
		"paperless_invoice": "true",
		"auto_pay": "true",
		"auto_pay_owner": "true",
		"registered_code": "R",
		"logon_status": "S",
		"first_name": "KAREN",
		"last_name": "HAIN",
		"email": "14828PAGEPARK.COM",
		"last_login_date": "2014-05-21T15:41:52.000-05:00"
	}]
}



```

---
