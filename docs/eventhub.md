### Event Hub API
The WM Event Hub stores business events from any system that is currently integrated with it.  The following API methods are available to consume data from the Event Hub.

_Note: For the following API, the date parameters should be in this format:_ `YYYY-MM-ddTHH:mm:ss`


---

### Get all events
This API lists all events in the Event Hub

```
http://eventhub.wm.com:3000/api/v1/customers/services/events
```

---

### Get event by EventID
Retrieve a single event using the EventID.
```
http://eventhub.wm.com:3000/api/v1/customers/services/events/<eventId>
```

---

### Get events by CustomerID, ServiceID,  and EventID
```
http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/<serviceId>/events/<eventId>
```

---





By Customer ID : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/events
By Customer ID DateRange : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/events?startDate=<date>&endDate=<date>

By CustomerID EventType : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/events?eventType=<eventType>
By CustomerID EventType DateRange : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/events?eventType=<eventType>&startDate=<date>&endDate=<date>

By CustomerIDServiceID : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/<serviceId>/events
By CustomerIDServiceID DateRange : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/<serviceId>/events?startDate=<date>&endDate=<date>

By CustomerIDServiceIDEventType : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/<serviceId>/events?eventType=<eventType>
By CustomerIDServiceIDEventType DateRange : http://eventhub.wm.com:3000/api/v1/customers/<customerId>/services/<serviceId>/events?eventType=<eventType>&startDate=<date>&endDate=<date>

The argument page=<pageNumber> should be passed to move to required page
