<link href="markdown.css" rel="stylesheet"></link>

<h4> billcycles </h4>

Use the /billcycles resource to get the bill cycle code details for a library suffix.

### **URI**

- /api/v1/libraries/{libraryId}/billcycles

**Current Service Usage**

1. WM.com uses this service to get customer’s bill cycle details from MAS


  **Source:** MAS

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	{libraryId}	|	String	|	library suffix|

---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customerId	|	String	|	Unique Id assigned to a customer	|
|	request_tracking_id	|	String	|	Unique tracking identifier	|
|	contacts	|	object: array of contacts	|	Contains customer billing address and contact information	|
|	type	|	String	|	Defines contact type 'billing'	|
|	name	|	String	|	Name of the customer	|
|	first_name	|	String	|	First name of the customer	|
|	middle_name	|	String	|	Middle name of the customer	|
|	last_name	|	String	|	Last name of the customer	|
|	land_line	|	String	|	Land line of the customer	|
|	work_phone	|	String	|	Work phone number of the customer	|
|	mobile_phone	|	String	|	Mobile phone number of the customer	|
|	fax	|	String	|	Fax number of the customer	|
|	email	|	String	|	Email Id of the customer	|
|	address	|	object	|	Contains data about the customer address	|
|	street	|	String	|	Street name	|
|	city	|	String	|	City name	|
|	country	|	String	|	Country code	|
|	province	|	String	|	Cananda state name	|
|	postal_code	|	String	|	Cananda postal code	|
|	state	|	String	|	US state name	|
|	zip	|	String	|	US postal code	|
|	zip4		String	|	4 digit extension postal code for US addresses	|
|	metadata		object	|	Contains WM specific data	|
|	cleansed		String	|	Defines the address validation status	|
|	status		String	|	‘Success’ or ‘Failure’ Success – Transaction executed successfully without any failures Failure – Transaction failed due to some reasons that will be provided in error in response	|
|	error		object: array of error	|	Contains error details in case of failures	|
|	     code		String	|	Error code of the error message	|
|	     message		String	|	Error Description (like Service error)	|
|	  errors		object: array of errors	|	Contains error description in case of failures	|
|	   message		String	|	Actual error message of transaction that had failed	|



---

### **Sample Request**
```
/api/v1/libraries/113A/billcycles

```

---
### **Headers**

Request-Tracking-Id=56756
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=eBiz_327

---

### **Sample  Success Response**

```
{
    "request_tracking_id": "756345",
    "billcycles": [
        {
            "code": "BCA",
            "description": "BROKER CM MONTHLY ADVANCE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "BOR",
            "description": "BROKER RO MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "CMA",
            "description": "CM MONTHLY ADVANCE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "CMR",
            "description": "CM MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "MTR",
            "description": "RO MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "NCA",
            "description": "NATIONAL CM MONTHLY ADVANCE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "NOR",
            "description": "NATIONAL RO MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "OBR",
            "description": "RO TWICE MONTHLY ARREARS",
            "frequency_code": "B",
            "frequnecy": "2/ Times//Month",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "OMR",
            "description": "RO MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "RMR",
            "description": "RS MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "RQ1",
            "description": "RS QUARTERLY ADVANCE 1,4,7,10",
            "frequency_code": "Q",
            "frequnecy": "Quarterly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "RQ2",
            "description": "RS QUARTERLY ADVANCE 2,5,8,11",
            "frequency_code": "Q",
            "frequnecy": "Quarterly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "RQ3",
            "description": "RS QUARTERLY ADVANCE 3,6,9,12",
            "frequency_code": "Q",
            "frequnecy": "Quarterly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R11",
            "description": "RS ANNUAL ADVANCE 11",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "RMA",
            "description": "RS MONTHLY ADVANCE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "CQA",
            "description": "CM QUARTERLY ADVANCE",
            "frequency_code": "Q",
            "frequnecy": "Quarterly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "RSA",
            "description": "RS SEMI-ANNUAL ADVANCE 1,7",
            "frequency_code": "S",
            "frequnecy": "Semi/ Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R01",
            "description": "RS ANNUAL ADVANCE 1",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R02",
            "description": "RS ANNUAL ADVANCE 2",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R03",
            "description": "RS ANNUAL ADVANCE 3",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R04",
            "description": "RS ANNUAL ADVANCE 4",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R05",
            "description": "RS ANNUAL ADVANCE 5",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R06",
            "description": "RS ANNUAL ADVANCE 6",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R07",
            "description": "RS ANNUAL ADVANCE 7",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R08",
            "description": "RS ANNUAL ADVANCE 8",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R09",
            "description": "RS ANNUAL ADVANCE 9",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R10",
            "description": "RS ANNUAL ADVANCE 10",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "R12",
            "description": "RS ANNUAL ADVANCE 12",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "BCR",
            "description": "BROKER CM MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "C01",
            "description": "CM ANNUAL ADVANCE 1",
            "frequency_code": "A",
            "frequnecy": "Annual",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "MTA",
            "description": "RO MONTHLY ADVANCE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "MMR",
            "description": "MASTER MONTHLY BILLING CYCLE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "M",
            "line_of_business": "Master"
        },
        {
            "code": "OWR",
            "description": "RO WEEKLY ARREARS",
            "frequency_code": "W",
            "frequnecy": "Weekly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "ACA",
            "description": "CONTRACT CM MONTHLY ADVANCE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "ACR",
            "description": "CONTRACT CM MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "ARA",
            "description": "CONTRACT RS MONTHLY ADVANCE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "ARR",
            "description": "CONTRACT RS MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "ABR",
            "description": "CONTRACT RO TWICE MNTHLY",
            "frequency_code": "B",
            "frequnecy": "2/ Times//Month",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "AOR",
            "description": "CONTRACT RO MONTHLY ARREARS",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "RK1",
            "description": "RESI CYCLE FOR 3041.2",
            "frequency_code": "Q",
            "frequnecy": "Quarterly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "CK1",
            "description": "COMM CYCLE FOR 3041.2",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        },
        {
            "code": "OK1",
            "description": "ROLLOFF CYCLE FOR 3041.2",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "MK1",
            "description": "MASTER CYCLE FOR 3041.2",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "M",
            "line_of_business": "Master"
        },
        {
            "code": "TS1",
            "description": "RS MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "TS2",
            "description": "RS MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "TS3",
            "description": "RS MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "TS4",
            "description": "RS MON ADV ISSUE DATE",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "RO1",
            "description": "RO MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "RO5",
            "description": "RO TEST",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "OO1",
            "description": "RO MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "DO1",
            "description": "DEV RO BILLING",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "S1",
            "description": "SUM RO MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "Z1",
            "description": "SUMIT RO MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "Z2",
            "description": "RO SUMI MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "O",
            "line_of_business": "Roll Off"
        },
        {
            "code": "Z3",
            "description": "SUMIT RES MON ADV",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "LF1",
            "description": "LATE FEE KT TEST",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "1",
            "advance_arrears": "Advance",
            "line_of_business_code": "R",
            "line_of_business": "Residential"
        },
        {
            "code": "AB1",
            "description": "AB1 RMO CHARGE TEST",
            "frequency_code": "M",
            "frequnecy": "Monthly",
            "advance_arrears_code": "2",
            "advance_arrears": "Arrears",
            "line_of_business_code": "C",
            "line_of_business": "Commercial"
        }
    ]
}


```
### **Sample Failure Response:**
```
{
    "error": {
        "code": "500",
        "message": "Service Error",
        "errors": [
            {
                "message": "Source not configured"
            }
        ]
    },
    "request_tracking_id": "3432273233"
}


```

### **Empty Response - No Content:**

```
***************** HTTP Status Code ***************
status: 204 No Content
```
###**Error Response - Not Modified:**

```
***************** HTTP Status Code ***************
status: 304 Not Modified
```
###**Error Response - Not Found:**
```

{
  "error": {
    "code": "404",
    "message": "Not Found",
    "errors": [
      {
        "message": "Invalid Resource"
      }
    ]
  },
  "request_tracking_id": "123"
}

***************** HTTP Status Code ***************
status: 404 Not found
```

###**Error Response - Method Not Allowed:**

```
***************** HTTP Status Code ***************
status: 405 Method Not Allowed

Error Response - Validation Error:

{
  "error": {
    "code": "422",
    "message": "Validation Error",
    "errors": [
      {
        "message": "ClientId\/ProfileId - Header is a required field"
      }
    ]
  },
  "request_tracking_id": "123"
}

***************** HTTP Status Code ***************
status: 422 Validation Error
```
###**Error Response - Service Error:**
```

{
  "error": {
    "code": "500",
    "message": "Internal Server Error",
    "errors": [
      {
        "message": "Source not configured"
      }
    ]
  },
  "request_tracking_id": "123"
}
***************** HTTP Status Code ***************
status: 500 Service Error
```
---
