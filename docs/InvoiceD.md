<link href="markdown.css" rel="stylesheet"></link>

<h4> Invoice Details </h4>

Use this call to get invoice details for the specific invoiceId

### **URI**

- /customers/<customerId>/invoices/<invoiceId>

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
| customerId           | Number    | Unique Id assigned to customer.   |
| invoiceId           | Number    | Id that uniquely identifies each invoice. |

---

### **Sample Request**
```
https://api.wm.com/v1/customers/000021700264005/invoices/101625

```

---

### **Details  Responce**
Returns invoice object with all the invoice details.

---

### **Sample Responce**

```
{"invoices": [
      {
      "id": "101625",
      "type": "4",
      "description": "FINANCE CHARGE",
      "date": "01/01/09",
      "amount": "5.41",
      "due_date": "01/01/09",
      "period": "200812"
   },
      {
      "id": "101625",
      "type": "3",
      "description": "ADJUSTMENT",
      "date": "10/18/12",
      "amount": "4.51",
      "due_date": "10/18/12",
      "period": "201210"
   },
      {
      "id": "101625",
      "type": "3",
      "description": "ADJUSTMENT",
      "date": "03/18/14",
      "amount": "0.90",
      "due_date": "03/18/14",
      "period": "201403"
   },
      {
      "id": "101625",
      "type": "3",
      "description": "ADJUSTMENT",
      "date": "04/07/14",
      "amount": "0.90",
      "due_date": "04/07/14",
      "period": "201404"
   }
]}
```

---

### [**Field Definitions**](Disposal_Tickets_summary_api_Field_Definitions.html)
