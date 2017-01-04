<link href="markdown.css" rel="stylesheet"></link>

<h4> Service exceptions </h4>

Use the /cleanse resource to validate the email id of a user using Melissadata. Melissadata is global email cleanser. It will respond with status code like unknown/valid/invalid/corrected

1.	If there is at least one Unknown code API sends status as 'unknown' to customer
2.	If there is at least one Invalid code then API sends status as 'invalid' to customer
3.	If there is no Invalid code and there is at least one Corrected code then API sends status as 'corrected' to customer
4.	If there is no Invalid code and all codes are Valid API sends status as 'valid' to customer

### **URI**

- /api/v1/ emails/{emailID}/cleanse

**Current Service Usage**

1.	eBiz, CAAG, SalesForce and MAS uses this API to validate the email of a customer.

  **Source:** Melissadata

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	emailID	|	String	|	Email Id of the customer that needs to be validated by Melissadata|




---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	status	|	String	|	Status to be sent to customer post validation based on the scenarios listed above	|
|	email	|	String	|	Contains exception details	|
|	reason	|	Object	|	Contains details about code and message returned by Melissadata	|
|	code	|	String	|	Status code sent by Melissadata	|
|	message	|	String	|	Message that describes the status code	|





---

### **Sample Request**
```
/api/v1/emails/agokhale@wm.com/cleanse

```

---
### **Headers**

Request-Tracking-Id=12345
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=eBiz_227




---

### **Sample Response**

```
{
    "request_tracking_id": "123",
    "status": "valid",
    "email":" agokhale@wm.com",
    "reason": [{
        "code": "Valid Email",
        "message": "This email was confirmed to be a valid email"
    }, {
        "code": "Verify (Precision: Real-time Mailbox Result)",
        "message": "The mailbox validation was performed in real-time"
    }]
}

```

---
