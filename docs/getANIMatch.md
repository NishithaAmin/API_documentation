<link href="markdown.css" rel="stylesheet"></link>

<h4> getANIMatch </h4>

### **Description**
Use this API to get customer information based on phone number

---

### **Current Service Usage**

**a.**	Genesys uses this API to provide screen pop with customer information when customer is on call with agent

---

### **Source**
 Salesforce

---
### **Parameters**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	phoneNumber	|	string	|	Phone number	|
|	referenceType	|	string	|	Lead or Opportunity	|
|	referenceID	|	string	|	Reference identification	|
|	matchStatus	|	string	|	NoMatch if phone number doesn’t exist or else Match	|
|	companyName	|	string	|	Company name	|
|	contactName	|	string	|	Contact name	|
|	leadCategory	|	string	|	Lead Category	|
|	leadSubCategory	|	string	|	Lead Subcategory	|


---

### **Mapping Specification**
https://drive.google.com/open?id=0B74bBg69IFsQN2FKVTc0bllKUE0



---

### **Sample Request/Response for Candidates**

**Request:**
```
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:wm="http://crpu385a/wm_businessservices.customerService.webServices:getANIMatch_11">
   <soapenv:Header/>
   <soapenv:Body>
      <wm:getANIMatch>
         <phoneNumber>9562405650</phoneNumber>
         <transactionID>test67</transactionID>
         <!--Optional:-->
         <requestTypeCd>PhoneNum</requestTypeCd>
         <!--Optional:-->
         <msgSourceCd>Genesys</msgSourceCd>
         <!--Optional:-->
         <msgTargetCd>SalesForce</msgTargetCd>
         <!--Optional:-->
           <requestedEnv>QA</requestedEnv>
</wm:getANIMatch>
   </soapenv:Body>
</soapenv:Envelope>



```

**Response:**

```
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ser-root:getANIMatchResponse xmlns:ser-root="http://crpu385a/wm_businessservices.customerService.webServices:getANIMatch_11">
         <phoneNumber>9562405650</phoneNumber>
         <referenceType>Lead</referenceType>
         <referenceID>00Q8000001EhYlFEAV</referenceID>
         <matchStatus>Match</matchStatus>
         <companyName>rivas company</companyName>
         <contactName>Rivas</contactName>
         <leadCategory>Marketing/Advertising</leadCategory>
         <leadSubCategory>Online Advertisement</leadSubCategory>
         <status>Success</status>
      </ser-root:getANIMatchResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


---
