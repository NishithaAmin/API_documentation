<link href="markdown.css" rel="stylesheet"></link>

<h4> Get Customer Profile Info </h4>

### **Description**
Use this API to get the profile information for a given customer ID and gets the below information:
    Auto Pay flag for Billing
    Paperless Flag for receiving Invoices
    Customer Last Name
    Customer First Name
    Customer Email Address
    Customer Last Login Date and Time into WM.com
    Customer logon status into WM.com.


---

### **Current Service Usage**



---

### **Source**
 MDM

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
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:wm="http://esb.wm.com/wm_businessservices.customerService.webServices:getCustomerProfileInfo" xmlns:esb="EsbMsgHeader" xmlns:cus="CustomerProfile">
   <soapenv:Header/>
   <soapenv:Body>
      <wm:getCustomerProfileInfo>
         <esb:msgHeader>
            <esb:actionCd>Request</esb:actionCd>
            <esb:requestTypeCd>OnlnEnroll</esb:requestTypeCd>
            <esb:transactionID>829064</esb:transactionID>
            <esb:source>
               <esb:msgSourceCd>Siebel</esb:msgSourceCd>
               <esb:requestedEnv>QA</esb:requestedEnv>
            </esb:source>
         </esb:msgHeader>
         <CustomerProfile>
            <cus:id>100670912008</cus:id>
         </CustomerProfile>
      </wm:getCustomerProfileInfo>
   </soapenv:Body>
</soapenv:Envelope>




```

**Response:**

```
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
      <ser-root:getCustomerProfileInfoResponse xmlns:ser-root="http://esb.wm.com/wm_businessservices.customerService.webServices:getCustomerProfileInfo">
         <EsbStatus:status xmlns:EsbStatus="EsbStatus">
            <EsbStatus:statusCd>SUCCESS</EsbStatus:statusCd>
         </EsbStatus:status>
         <CustomerProfile>
            <CustomerProfile:id xmlns:CustomerProfile="CustomerProfile">100670912008^118144|E</CustomerProfile:id>
            <CustomerProfile:userAccount xmlns:CustomerProfile="CustomerProfile">
               <CustomerProfile:paperlessInvoiceFlg>true</CustomerProfile:paperlessInvoiceFlg>
               <CustomerProfile:autoPayOwnerFlg>true</CustomerProfile:autoPayOwnerFlg>
               <CustomerProfile:registeredCd>R</CustomerProfile:registeredCd>
               <CustomerProfile:WMLogonStatus>Y</CustomerProfile:WMLogonStatus>
               <CustomerProfile:firstName>KAREN</CustomerProfile:firstName>
               <CustomerProfile:lastName>HAIN</CustomerProfile:lastName>
               <CustomerProfile:eMailAddress>MOMBEAR70@VERIZON.NET</CustomerProfile:eMailAddress>
               <CustomerProfile:lastLoginDT>2014-05-21T15:41:52.000-05:00</CustomerProfile:lastLoginDT>
            </CustomerProfile:userAccount>
         </CustomerProfile>
      </ser-root:getCustomerProfileInfoResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>


```


---
