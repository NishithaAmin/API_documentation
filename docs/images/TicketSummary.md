<link href="markdown.css" rel="stylesheet"></link>

<h4>Tickets Summary  </h4>

Use this call to get tickets summary of a customer for a given date range.

### **URI**

 /customers/<customerId>/tickets?fromDate=<yyyy-MM-dd>&toDate=<yyyy-MM-dd>

---

### **Methods**
 GET

---

### **Summary   Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
| customerId           | Number    | Unique Id assigned to customer.   |
| fromDate           | Date    | Start date of the ticket details. |
| toDate           | Date    | End date of the ticket details. |

---

### **Sample Request**
```
https://api.wm.com/v1/customers/37583215008/tickets?fromDate=2011-01-01&toDate=2016-01-01


```

---

### **Summary  Response**
Returns tickets summary for the given date range.

---

### **Sample Response**

```
{
   "request_tracking_id": "123",
   "tickets":    [
            {
         "id": "897067",
         "status": "CLOSED",
         "load_type": "COU",
         "load_description": "COURTESY SRVC (NON-CHARGEABLE)",
         "dispatch_date_time": "10/22/12 11:08:00",
         "created_date_time": "10/22/12 11:08:00",
         "services_info": [{"code": "96S"}]
      },
            {
         "id": "161906",
         "status": "CLOSED",
         "load_type": "NOT",
         "load_description": "NOTE TO DRIVER",
         "dispatch_date_time": "05/14/13 09:18:00",
         "created_date_time": "05/15/13 09:18:00",
         "services_info": [{"code": "96S"}]
      },
            {
         "id": "863674",
         "status": "CLOSED",
         "load_type": "REM",
         "load_description": "REMOVAL (NON-CHARGEABLE)",
         "dispatch_date_time": "01/02/15 10:50:00",
         "created_date_time": "11/17/14 10:50:00",
         "services_info": [{"code": "96S"}]
      }
   ]
}
```

---

### [**Field Definitions**](Disposal_Tickets_summary_api_Field_Definitions.html)
