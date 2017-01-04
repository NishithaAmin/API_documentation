<link href="markdown.css" rel="stylesheet"></link>

<h4> Search </h4>

Use the /search resource to retrieve customer details based on search criteria provided. This api provides service and billing contact details for the customer. Elastic Search provides the contact details for query parameters passed. Provide search parameters carrying address fields in the endpoint


### **URI**

- /api/v1/customers/search

**Current Service Usage**

1.	Genesys uses this api to get contact details for the customer from Elastic Search

  **Source:** Elastic Search

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	query	|	String	|	Contact details such as phone number, street, city, state etc. passed as a string separated by space.|




---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customers	|	Object	|	Contains customer details such as customer id, LOB, status and contact details for both billing and service	|
|	id	|	Number	|	Customer ID	|
|	status	|	String	|	Status of customer(active/inactive)	|
|	line_of_business	|	String	|	LOB such as RESIDENTIAL, COMMERCIAL, ROLLOFF	|
|	account_type	|	String	|	Type of account	|
|	contacts	|	Object	|	Contains customer contact details for service and billing	|
|	type	|	String	|	Contact type can be service  or billing	|
|	organization_name	|	String	|	Name of the organization	|
|	name	|	String	|	Name of the customer	|
|	home_phone	|	String	|	Residential contact number	|
|	email	|	String	|	Email Id of the customer	|
|	address	|	String	|	Customer address	|
|	street	|	Object	|	Street details	|
|	city	|	Number	|	City	|
|	state	|	String	|	State	|
|	postal_code	|	String	|	Zip code	|
|	country	|	String	|	Country	|

---

### **Sample Request**
```
/api/v1/customers/search?query=8147740365 PA 16417

```

---
### **Headers**

Request-Tracking-Id=12345
Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=Genesys_203


---

### **Sample Response**

```
{
	"request_tracking_id": "12345",
	"customers": [{
		"id": "000149245562005",
		"status": "ACTIVE",
		"category": "FRAN/MUNI",
		"line_of_business": "RESIDENTIAL",
		"account_type": "child",
		"contacts": [{
			"type": "service",
			"organization_name": "GANDLEY, ROBERT AND JULIE",
			"name": "GANDLEY, ROBERT AND JULIE LAST",
			"home_phone": "8147740365",
			"email": "rgandley@mijb.com",
			"address": {
				"street": "47 S PARK ROW",
				"city": "GIRARD",
				"state": "PA",
				"postal_code": "16417-1629",
				"country": "US"
			}
		}, {
			"type": "billing",
			"organization_name": "GANDLEY, ROBERT AND JULIE",
			"name": "GANDLEY, ROBERT AND JULIE LAST",
			"home_phone": "8147740365",
			"email": "rgandley@mijb.com",
			"address": {
				"street": "47 S PARK ROW",
				"city": "GIRARD",
				"state": "PA",
				"country": "US",
				"postal_code": "16417-1629"
			}
		}],
		"wm_metadata": {
			"library": "192A",
			"company_code": "794",
			"mas_account_number": "794-1305056"
		}
	}],
	"metadata": {
		"totalCount": "1"
	}
}


```

---
