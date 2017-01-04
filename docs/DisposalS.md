<link href="markdown.css" rel="stylesheet"></link>

 <h4> Disposal Ticket </h4>

### **URI**

- /customers/<customerId>/tickets?ticket_type=disposal&fromDate=<yyyy-MM-dd>&toDate=<yyyy-MM-dd>

---

### **Methods**
- GET


---

### **Summary Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
| customerId           | Number    | Unique Id assigned to customer.   |
| fromDate           | Date    | Start date of the ticket details. |
| toDate           | Date    | End date of the ticket details.  |
---

### **Sample Request**
```
https://api.wm.com/v1/customers/144931293002/tickets?ticket_type=disposal&fromDate=2016-03-01&toDate=2016-03-16

```

---

### **Summary Response**
Returns tickets object, total count and tickets for the given date range.

---

### **Sample Response**

```
{
  "request_tracking_id": "23402739423",
  "tickets": [
    {
      "id": "33",
      "date": "2016-03-02 14:30:58.0",
      "status": "Completed",
      "amount": "1047.57",
      "site_name": "Argo Rail Yard"
    }
  ],
  "metadata": [
    {
      "totalCount": "1"
    }
  ]
}
```

---

### [**Field Definitions**](Disposal_Tickets_summary_api_Field_Definitions.html)
