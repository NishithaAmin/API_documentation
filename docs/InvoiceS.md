<link href="markdown.css" rel="stylesheet"></link>

<h4> Invoice Summary </h4>

Use this call to get invoice summary of a customer for a given date range.

### **URI**

- /customers/<customerId>/invoices?fromDate=<yyyy-MM-dd>&toDate=<yyyy-MM-dd>

---

### **Methods**
- GET

---

### **Summary Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
| customerId           | Number    | Unique Id assigned to customer.   |
| fromDate           | Date    | Start date of the invoice  details. |
| toDate           | Date    | End date of the invoice  details.  |
---

### **Sample Request**
```
https://api.wm.com/v1/customers/45684712009/invoices?fromDate=2016-01-01&toDate=2016-04-01

```

---

### **Summary Responce**
Returns invoice summary of the customer for the given date range.

---

### **Sample Responce**

```
{
   "currency": "USD",
   "balances":    [
            {
         "type": "Current",
         "date": "2016-05-03",
         "amount": "0.0"
      },
            {
         "type": "30Day",
         "date": "2016-04-03",
         "amount": "0.0"
      },
            {
         "type": "60Day",
         "date": "2016-03-04",
         "amount": "0.0"
      },
            {
         "type": "90Day",
         "date": "2016-02-03",
         "amount": "0.0"
      },
            {
         "type": "120Day",
         "date": "2016-01-04",
         "amount": "0.0"
      },
            {
         "type": "Future",
         "date": "null",
         "amount": "0.0"
      },
            {
         "type": "Total",
         "date": "null",
         "amount": "0.0"
      }
   ],
   "invoices": [   {
      "id": "1067800",
      "date": "2016-01-01",
      "amount": "247.74",
      "payment_info":       {
         "amount": "null",
         "date": "null",
         "reference_number": "RECUR-AMEX          "
      },
      "balance_amount": "null"
   }]
}
```

---

### [**Field Definitions**](Disposal_Tickets_summary_api_Field_Definitions.html)
