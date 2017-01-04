<link href="markdown.css" rel="stylesheet"></link>

<h4>Disposal Ticket Details </h4>

### **URI**

- /customers/<customerId>/tickets/<ticketId>?ticket_type=disposal

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
https://api.wm.com/v1/customers/144931293002/tickets/33?ticket_type=disposal

```

---

### **Details Response**
Returns tickets object with all the ticket details.

---

### **Sample Responce**

```
{
  "request_tracking_id": "23402739423",
  "tickets": [
    {
      "id": "33",
      "hauling_ticket_id": "null",
      "replace_ticket_id": "null",
      "void_ticket_id": "null",
      "time_in": "2016-03-02 14:30:34.0",
      "time_out": "2016-03-02 14:30:56.0",
      "status": "Completed",
      "weight": {
        "gross": "39340",
        "tare": "12620",
        "net": "26720",
        "rounded_net": "13.36"
      },
      "scale_in": "Inbound",
      "scale_out": "Inbound",
      "swipe_card_id": "null",
      "volume": "0",
      "material_subtotal": "478.25",
      "surcharge": "552.75",
      "tax": "16.57",
      "amount": "1047.57",
      "carrier": {
        "id": "CITY OF SEATTLE",
        "description": "CITY OF SEATTLE"
      },
      "site": {
        "id": "S08510",
        "name": "Argo Rail Yard"
      },
      "destination": "null",
      "route_id": "null",
      "notes": "null",
      "seal": {
        "number_1": "789",
        "number_2": "null"
      },
      "customer": {
        "name": "SEATTLE-RABU",
        "business_name": "CITY OF SEATTLE",
        "address": {
          "street_text_1": " PO BOX 34018",
          "street_text_2": "null",
          "city": "SEATTLE",
          "country": "USA",
          "state": "WA",
          "zip": "98124",
          "zip4": "4018"
        }
      },
      "audit_info": {
        "created_by": "pos",
        "created_date_time": "2016-03-02 14:30:34.0",
        "modified_by": "pos",
        "modified_date_time": "2016-03-02 14:30:58.0"
      },

       "vehicle": {
        "number": "448",
        "description": "448",
        "driver_name": "null"
      },
      "details": [
        {
          "sequence_number": "2",
          "material_name": "null",
          "surcharge_name": "RAIL T MSW",
          "description": "RAIL BY THE TON MSW",
          "volume": "0",
          "generator_name": "null",
          "rounded_net_weight": "0",
          "billed_quantity": "13.36",
          "rate_per_unit": "22.11",
          "rate_uom": "Tons",
          "origin": {
            "id": "WA-SEATTLE",
            "description": "WA-SEATTLE"
          },
          "amount": "552.75",
          "total_tax_amount": "0",
          "total_amount": "552.75",
          "purchase_order_number": "null",
          "manifest_id": "null",
          "container_id": "null"
        },
        {
          "sequence_number": "1",
          "material_name": "MSW",
          "surcharge_name": "null",
          "description": "MSW",
          "volume": "0",
          "profile": {
            "id": "null",
            "description": "null"
          },
          "generator_name": "null",
          "rounded_net_weight": "13.36",
          "billed_quantity": "13.36",
          "rate_per_unit": "19.13",
          "rate_uom": "Tons",
          "origin": {
            "id": "WA-SEATTLE",
            "description": "WA-SEATTLE"
          },
          "amount": "478.25",
          "total_tax_amount": "16.57",
          "total_amount": "494.82",
          "purchase_order_number": "null",
          "manifest_id": "null",
          "container_id": "null",
          "tax": [
            {
              "squence_number": "1",
              "id": "8599",
              "name": "DEQ 1.24",
              "description": "DEQ CM/BU",
              "rate_uom": "Tons",
              "amount": "16.57",
              "rate": "1.24"
            }
          ]
        }
      ]
    }
  ]
}

```

---

### [**Field Definitions**](Disposal_Tickets_summary_api_Field_Definitions.html)
