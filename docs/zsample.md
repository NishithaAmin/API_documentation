<link href="markdown.css" rel="stylesheet"></link>

<h4>Services  </h4>
<div class="container">
                <div class="panel-group">
                    <a data-toggle="collapse" href="#collapse1">REST API Reference</a>
                </div>
                <div id="collapse1" class="panel-collapse collapse">
                    <div> &nbsp; Base URL</div>                     
                    <br>
                    <div>&nbsp;Versions</div>
                    <br>
                    <div>&nbsp;Authentication and Headers</div>                     
                </div>

Use this call to get services information of a customer .

### **URI**

- /customers/<customerId>/services

---

### **Methods**
- GET


---

### **Summary Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
| customerId           | Number    | Unique Id assigned to customer.   |

---

### **Sample Request**
```
https://api.wm.com/v1/customers/16906645006/services


```

---

### **Summary Response**
Returns services information of the customer.

---

### **Sample Responce**

```
{  
   "Services":[  
      {  
         "id":"96S",
         "frequency":"2",
         "occurs":" ",
         "taxable":"N",
         "auto_bill":"N",
         "enterprise_catalog":{  
            "description":""
         },
         "material":{  
            "code":"",
            "name":"null"
         },
         "pricing":{  
            "extended_cost_amount":"29.93"
         },
         "wm_metadata":{  
            "service_code":"96S",
            "service_quantity":"1.00"
         },
         "operations":[  
            {  
               "route_id":"$2AF",
               "stop_id":"815.00",
               "day_of_week":"TUESDAY  "
            },
            {  
               "route_id":"B3CA",
               "stop_id":"0.00",
               "day_of_week":"WEDNESDAY"
            }
         ]
      }
   ]
}

```

---

### [**Field Definitions**](Disposal_Tickets_summary_api_Field_Definitions.html)
