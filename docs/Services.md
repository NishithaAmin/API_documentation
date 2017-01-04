<link href="markdown.css" rel="stylesheet"></link>

<h4> Service </h4>

Use the /services resource to retrieve all the services (active, inactive, cancelled etc) for all lines of businesses (Roll Off, Commercial and Residential) of a customer. If a line of business is specified in the parameter, the api returns the services only for that LOB.

### **URI**

- /api/v1/customers/{customerId}/services

**Current Service Usage**

1.	eBiz uses this api to get services for a customer from CCDB for a specified line of business
2.	Bernallilo uses this api to get services for a customer from MAS for a specified line of business


  **Source:** MAS & CCDB

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customerId	|	Number	|	Unique customer Id for which service details needs to be retrieved	|
|	lineofbusiness	|	String	|	Line of business such as RESIDENTIAL/COMMERCIAL/ROLLOFF	|
|	status	|	String	|	To fetch Active/Inactive services as requested by user	|


---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	Id	|	Number	|	MAS service line ID	|
|	status	|	String	|	Status of the service (Active or Inactive)	|
|	occurs	|	String	|	Occurrence of the services	|
|	taxable	|	String	|	Flag to decide if the service is taxable or not	|
|	type_code	|	String	|	Type code of the service	|
|	enterprise_catalog	|	Object	|	Contains enterprise details	|
|	Id	|	Number	|	Unique Id assigned to a enterprise catalog	|
|	name	|	String	|	Name of the enterprise catalog	|
|	description	|	String	|	Description of the enterprise catalog	|
|	sub_category	|	String	|	Sub category value	|
|	category	|	String	|	Catalog category	|
|	line_of_business	|	String	|	Line of business against which service has been created	|
|	material	|	Object	|	Contains material details associated with service	|
|	Id	|	Number	|	Unique Id assigned to a material	|
|	code	|	String	|	Material code	|
|	name	|	String	|	Name of the material	|
|	special_handling	|	String	|	Flag that indicates if special handling is needed	|
|	manifest	|	String	|	Flag that decides if manifest or not	|
|	equipment	|	Object	|	Contains equipment details	|
|	Id	|	String	|	Unique Id assigned to an equipment	|
|	name	|	String	|	Name of the equipment	|
|	description	|	String	|	Description of the equipment	|
|	volume	|	Number	|	Volume of the equipment	|
|	uom	|	String	|	Unit of measure	|
|	count	|	Number	|	Number of equipment	|
|	pricing	|	Object	|	Contains pricing details	|
|	summary_pricing	|	String	|	Flag to indicate if summary pricing is needed	|
|	extended_cost_amount	|	Number	|	Cost amount extended	|
|	currency_code	|	String	|	Currency	|
|	disposal_rate_type	|	String	|	Type of disposal rate	|
|	disposal_rate_amount	|	Number	|	Amount of disposal rate	|
|	uom	|	String	|	Unit of measure	|
|	wm_metadata	|	Object	|	Contains metadata details	|
|	service_code	|	String	|	Service code	|
|	service_cycle_code	|	String	|	Service cycle code	|



---

### **Sample Request**
```
/api/v1/customers/129653423004/services?line_of_business=RESIDENTIAL&status=Active

```

---
### **Headers**

Request-Tracking-Id=12345
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=eBiz_216


---

### **Sample Response**

```
{
	"request_tracking_id": "312",
	"services": [{
		"id": "1",
		"status": "Active",
		"occurs": "On Call",
		"taxable": "true",
		"type_code": "T",
		"enterprise_catalog": {
			"id": "2321",
			"name": "COLL_RO:HAUL uses RO with 30O for MSIN",
			"description": "Hauling - 30 Yard Open Top for MSW Industrial",
			"sub_category": "HAUL",
			"category": "COLL",
			"line_of_business": "COLL_RO"
		},
		"material": {
			"id": "169",
			"code": "MSIN",
			"name": "MSW Industrial",
			"special_handling": "false",
			"manifest": "false"
		},
		"equipment": {
			"id": "30O",
			"name": "30 Yard Open Top",
			"description": "null",
			"volume": "30",
			"uom": "YD3",
			"count": "1"
		},
		"pricing": {
			"summary_pricing": "true",
			"extended_cost_amount": "133.63",
			"currency_code": "USD",
			"disposal_rate_type": "R",
			"disposal_rate_amount": "133.63",
			"uom": "EA"
		},
		"wm_metadata": {
			"service_code": "30O",
			"service_cycle_code": "OMR"
		}
	}]
}

```

---
