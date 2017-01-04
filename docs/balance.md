<link href="markdown.css" rel="stylesheet"></link>

<h4> Customer Account Balance </h4>

Use the /balance resource to retrieve payment balance due for a customer along with last payment amount and last payment date. Provide customerId in the endpoint

### **URI**

- /api/v1/customers/{customerId}/balance

**Current Service Usage**

1.	Waterfield IVR uses this api to get amount due for a customer while customer is on call to make a payment
2.	CCT IVR uses this api to get amount due for a customer while customer is on call



  **Source:** MAS

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customerId	|	String	|	Unique Id assigned to a customer	|
|	request_tracking_id	|	String	|	Unique tracking identifier	|
|	billing_name	|	String	|	Name on billing account	|
|	ivr_fee	|	String	|	IVR  transaction fee	|
|	last_payment_amount	|	String	|	Last payment amount	|
|	last_payment_date	|	String	|	Last payment date	|
|	balance	|	Object	|	Balance object	|
|	type	|	String	|	Type of balance	|
|	amount	|	String	|	Balance amount on account	|



---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|




---

### **Sample Request**
```
/api/v1/customers/000152301242008/balance

```

---
### **Headers**

Request-Tracking-Id=12345
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=WaterField_314


---

### **Sample Response**

```
{
   "request_tracking_id": "234",
      "billing_name": "FAIRPOINT COMMUNICATIONS INC ",
      "ivr_fee": "5.0",
      "last_payment_amount": "497.7",
      "last_payment_date": "2014-09-01",
      "balance": [      {
         "type": "total",
         "amount": "30.0"
      }]
   }

```

---
