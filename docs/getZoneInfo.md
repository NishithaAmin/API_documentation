<link href="markdown.css" rel="stylesheet"></link>

<h4> Geocode Address </h4>

### **Description**
Use this API to get the zone information, distance to travel and travel time between the customer service address and the nearest landfill.

**a.**		Choose Intersect in requestSubject  to get  all the zones into which the customer latitude and longitude falls

<MsgRequest:msgRequest>     
<MsgRequest:requestSubject>Intersect</MsgRequest:requestSubject>
<MsgRequest:requestingByTypeCd>Coordinate</MsgRequest:requestingByTypeCd>
<MsgRequest:parm>
   <MsgRequest:parmName>X-Coord</MsgRequest:parmName>
   <MsgRequest:parmValue></MsgRequest:parmValue>
</MsgRequest:parm>
<MsgRequest:parm>
   <MsgRequest:parmName>Y-Coord</MsgRequest:parmName>
   <MsgRequest:parmValue></MsgRequest:parmValue>
</MsgRequest:parm>
</MsgRequest:msgRequest>


**b.**	Choose Travel in requestSubject to get the total distance and the total travel time between the customer address and nearest landfill

<MsgRequest:msgRequest>     
<MsgRequest:requestSubject>Travel</MsgRequest:requestSubject>
<MsgRequest:requestingByTypeCd>Coordinate</MsgRequest:requestingByTypeCd>
<MsgRequest:parm>
 <MsgRequest:parmName>OriginLong</MsgRequest:parmName>
 <MsgRequest:parmValue></MsgRequest:parmValue>
</MsgRequest:parm>
<MsgRequest:parm>
 <MsgRequest:parmName>OriginLat</MsgRequest:parmName>
 <MsgRequest:parmValue></MsgRequest:parmValue>
</MsgRequest:parm>
<MsgRequest:parm>
 <MsgRequest:parmName>DestLong</MsgRequest:parmName>
 <MsgRequest:parmValue></MsgRequest:parmValue>
</MsgRequest:parm>
<MsgRequest:parm>
<MsgRequest:parmName>DestLat</MsgRequest:parmName>
        		<MsgRequest:parmValue></MsgRequest:parmValue>
    	</MsgRequest:parm>
</MsgRequest:msgRequest>    



  ---

### **Current Service Usage**
**a.**	AMP and Siebel uses this api to get all the zones into which the customer latitude and longitude falls
**b.**	AMP and Siebel use this api to get the total distance and the total travel time between the customer address and nearest landfill


---

### **Source**
 GIS

---
### **Parameters**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	requestSubject	|	String	|	Intersect or Travel	|
|	requestingByTypeCd	|	String	|	Coordinate	|
|	X-Coord	|	decimal	|	Latitude of customer point	|
|	Y-Coord	|	decimal	|	Longitude of customer point	|
|	OriginLat	|	decimal	|	Latitude of customer point	|
|	OriginLat	|	decimal	|	Longitude of customer point	|
|	DestLong	|	decimal	|	Latitude of nearest landfill	|
|	DestLat	|	decimal	|	Longitude of nearest landfill	|


---
###**Response Parameters:**
| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	name	|	String	|	Intersect or Travel	|
|	lobLvl2ID	|	String	|	Coordinate	|
|	hieLvlName	|	decimal	|	Latitude of customer point	|
|	hieLvlID	|	decimal	|	Longitude of customer point	|
|	entVehicleTypeID	|	decimal	|	Latitude of customer point	|
|	wasteStreamCd	|	decimal	|	Longitude of customer point	|
|	totalTimeMin	|	decimal	|	Latitude of nearest landfill	|
---
---
