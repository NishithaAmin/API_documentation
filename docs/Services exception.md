<link href="markdown.css" rel="stylesheet"></link>

<h4> Service exceptions </h4>

Use the /services/exceptions resource to retrieve past service exceptions of a customer, based on the number of days passed. If number of days is not passed, then the service will retrieve services exceptions for 60 days by default. Provide customerId and no of days in the endpoint

### **URI**

- /api/v1/customers/{customerId}/services/exceptions

**Current Service Usage**

1.	eBiz uses this api to get past service exceptions for a customer from OCS for a specified number of days


  **Source:** OCS

---

### **Methods**
- GET

---

### **Details Request**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	customerId	|	Number	|	Unique customer Id for which service details needs to be retrieved	|
|	numberOfDays	|	Number	|	No of days for which service exceptions must be retrieved.	|



---

### **Details Response**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	Id	|	Number	|	Unique Id assigned to an exception	|
|	exception_info	|	Object	|	Contains exception details	|
|	driver_name	|	String	|	Name of the driver	|
|	container_status	|	String	|	Gives information about status of container	|
|	exception_code	|	String	|	Exception code	|
|	driver_comments	|	String	|	Driver comments	|
|	dispatcher_comments	|	String	|	Comments entered by Dispatcher	|
|	image_location	|	String	|	URL for the image	|
|	number_of_containers	|	Number	|	Quantity of containers	|
|	image_id	|	Number	|	ID of the image	|
|	image_time_stamp	|	String	|	Time when image was taken	|




---

### **Sample Request**
```
/api/v1/customers/000038513663009/services/exceptions?numberOfDays=30

```

---
### **Headers**

Headers: Request-Tracking-Id=12345 Authorization=Basic b2NzdXNlcjpvY3N1c2Vy
ProfileId=eBiz_217



---

### **Sample Response**

```
{
	"request_tracking_id": "324342",
	"services": [{
		"id": "000000001",
		"exception_info": {
			"id": "00000041441359231315",
			"driver_name": "Alegria, Mauricio ",
			"container_status": "CONFIRMED NEGATIVE",
			"exception_code": "Inaccessible / Stuck due to Weather",
			"driver_comments": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc volutpat dapibus ligula ut interdum.",
			"dispatcher_comments": "yes this can be closed",
			"image_location": "http://ocsqa.wm.com/HOCimages/DAimages/20150904/00000041441359231315.jpg",
			"number_of_containers": "1",
			"image_id": "1115224",
			"image_time_stamp": "04-SEP-15"
		}
	}, {
		"id": "000000001",
		"exception_info": {
			"id": "00000041441359231316",
			"driver_name": "Alegria, Mauricio ",
			"container_status": "CONFIRMED NEGATIVE",
			"exception_code": "Inaccessible / Stuck due to Weather",
			"driver_comments": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc volutpat dapibus ligula ut interdum.",
			"dispatcher_comments": "yes this can be closed",
			"image_location": "http://ocsqa.wm.com/HOCimages/DAimages/20150904/00000041441359231316.jpg",
			"number_of_containers": "1",
			"image_id": "1115226",
			"image_time_stamp": "05-SEP-15"
		}
	}],
	"metadata": [{
		"totalCount": "2"
	}]
}

```

---
