<link href="markdown.css" rel="stylesheet"></link>

<h4>Ticket Details </h4>

Use this call to get ticket details for the specific ticketId

### **URI**

- /customers/<customerId>/tickets/<ticketId>

---

### **Methods**
 - GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
| customerId           | Number    | Unique Id assigned to customer.   |
| ticketId           | Number    | Id that uniquely identifies each ticket. |

---

### **Sample Request**
```
https://api.wm.com/v1/customers/90226605006/tickets/782186


```

---

### **Details Response**
Returns tickets object with the ticket details.

---

### **Sample Response**

```


{  
   "tickets":[  
      {  
         "id":"782186",
         "status":"VOID",
         "load_type":"REM",
         "dispatch_date_time":"09/26/14 13:09:00",
         "load_description":"REMOVAL (NON-CHARGEABLE)",
         "created_by":"ACHAVE1",
         "created_date_time":"09/16/14 13:09:00",
         "generate_ticket":"N",
         "complaint":"N",
         "comments":"",
         "closed_date_time":"09/19/14 00:00:00",
         "closed_by":"VMORA1",
         "completion_code":"",
         "completed_description":"null",
         "requested_by":"RMC - 8662 Voided By VMORA1",
         "audit_info":{  
            "logged_date_time":"09/16/14 13:09:00"
         },
         "services_info":[  
            {  
               "code":"96S",
               "description":"",
               "quantity":"1.00",
               "cost":"12.99",
               "special_description":""
            }
         ]
      }
   ]
}
```

---

### [**Field Definitions**](Disposal_Tickets_summary_api_Field_Definitions.html)
