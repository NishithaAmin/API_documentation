<link href="markdown.css" rel="stylesheet"></link>

<h4> Geocode Address </h4>

### **Description**
Use this API to get geographic coordinates for a given address along with GIS score and Locator name

**a.**	Choose BestMatch in requestSubject  to get  exact match for a given address

         <ns11:msgRequest>
            <ns11:requestSubject>BestMatch</ns11:requestSubject>
            <ns11:requestingByTypeCd>Address</ns11:requestingByTypeCd>
         </ns11:msgRequest>

**b.**	Choose Candidates in requestSubject to get array of geocoded address in proximity

           <ns11:msgRequest>
            <ns11:requestSubject>Candidates</ns11:requestSubject>
            <ns11:requestingByTypeCd>Address</ns11:requestingByTypeCd>
         </ns11:msgRequest

  ---

### **Current Service Usage**
**a.**	MDM uses this api to geocode all new address coming from MAS to MDM

**b.**	OCS uses this api for dispatchers and drivers to plot customer on the graph

**c.**	AMP use this api for pricing analysts to calculate price based on location

---

### **Source**
 GIS

---
### **Parameters**
Pass the following parameters in the request.

| Parameter    |Type | Description                              |
| -------------	|----------------|-----------------------------------------------------------------|
|	premiseAddr	|	object	|	Geocoded address	|
|	latitude	|	decimal	|	Latitude of candidate point	|
|	longitude	|	decimal	|	Longitude of candidate point	|
|	GISScore	|	decimal	|	A value assigned to all potential candidates of an address match.  The match score is based on how location found in the reference data matches with the address searched.	|
|	GISLocatorName	|	string	|	Sorted in order of individual locators in the composite locator with the most accurate locator first and the least accurate last.  For U.S.:	a) US_RoofTop,b) US_Streets,c) US_ZIP4,d) US_Zipcode,e) US_CityState.  For Canada:a) CAN_Streets,b)CAN_StreetName,c) CAN_Postcode,d) CAN_CityProv Possible Values:CoreLogicParce USAAddr_Points USAStreet_Addr USAZIP4 USAZipcode USACityState CANStreet_Addr CANStreet_Name CANPostalCode CANCityProv CityState
|	GISMatchTypeCd	|	string	|	The corresponding address or street in the reference data for the candidate point.	|
|	sideOfStreet	|	string	|	The side of the street to which the candidate has been matched: Left (L) or Right (R)	|
|	segmentID	|	integer	|	Unique road identifier	|

---

### **Mapping Specification**
https://drive.google.com/open?id=0B74bBg69IFsQbnU0WFYtS3F3Nlk



---

### **Sample Request/Response for Candidates**

**Request:**
```
<env:Envelope xmlns:env="http://www.w3.org/2003/05/soap-envelope" xmlns:soapenc="http://www.w3.org/2003/05/soap-encoding" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <env:Header/>
   <env:Body>
      <ns8:geocodeAddress xmlns:ns10="EsbMsgHeader" xmlns:ns11="MsgRequest" xmlns:ns5="EsbStatus" xmlns:ns6="GblAddr" xmlns:ns7="GblLkup" xmlns:ns8="http://esb.wm.com/service/geocodeAddress" xmlns:ns9="EsbProviderError">
         <ns10:msgHeader>
            <ns10:actionCd>Request</ns10:actionCd>
            <ns10:source>
               <ns10:msgSourceCd>eRL</ns10:msgSourceCd>
                </ns10:source>
         </ns10:msgHeader>
         <ns11:msgRequest>
            <ns11:requestSubject>Candidates</ns11:requestSubject>
            <ns11:requestingByTypeCd>Address</ns11:requestingByTypeCd>
         </ns11:msgRequest>
         <ns6:addressIn>
            <ns6:premiseAddr>
               <ns6:streetTxt1>354 MOUNT GRETNA RD</ns6:streetTxt1>
               <ns6:crossStreetName></ns6:crossStreetName>
               <ns6:cityName>ELIZABETHTOWN</ns6:cityName>
               <ns6:countryCd>US</ns6:countryCd>
               <ns6:otherAddress>
                  <ns6:geoDivisionName>PA</ns6:geoDivisionName>
                  <ns6:otherCountryZip>17022</ns6:otherCountryZip>
               </ns6:otherAddress>
            </ns6:premiseAddr>
         </ns6:addressIn>
      </ns8:geocodeAddress>
   </env:Body>
</env:Envelope>


```

**Response:**

```
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"/>
   <SOAP-ENV:Body>
      <ser-root:geocodeAddressResponse xmlns:ser-root="http://esb.wm.com/service/geocodeAddress">
         <EsbStatus:status xmlns:EsbStatus="EsbStatus">
            <EsbStatus:statusCd>SUCCESS</EsbStatus:statusCd>
         </EsbStatus:status>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>354 MOUNT GRETNA Road</GblAddr:streetTxt1>
               <GblAddr:cityName>ELIZABETHTOWN</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.167724999999997</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.605222999999995</GblLkup:longitude>
               <GblAddr:GISScore>100</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>PointAddress</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>CoreLogicParce</GblAddr:GISLocatorName>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>354 Mount Gretna Rd</GblAddr:streetTxt1>
               <GblAddr:cityName>Mt Joy Twp</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.16742</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.604810999999998</GblLkup:longitude>
               <GblAddr:GISScore>93.099999999999994</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>PointAddress</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>NAV_Point_Addr</GblAddr:GISLocatorName>
               <GblAddr:sideOfStreet>L</GblAddr:sideOfStreet>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>354 Mt Gretna Rd</GblAddr:streetTxt1>
               <GblAddr:cityName>Mt Joy Twp</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.16742</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.604810999999998</GblLkup:longitude>
               <GblAddr:GISScore>93.099999999999994</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>PointAddress</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>NAV_Point_Addr</GblAddr:GISLocatorName>
               <GblAddr:sideOfStreet>L</GblAddr:sideOfStreet>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>354 Mount Gretna Rd</GblAddr:streetTxt1>
               <GblAddr:cityName>Mt Joy Twp</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.167552999999998</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.604761999999994</GblLkup:longitude>
               <GblAddr:GISScore>93.099999999999994</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>StreetAddress</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>NAV_Street_Add</GblAddr:GISLocatorName>
               <GblAddr:sideOfStreet>L</GblAddr:sideOfStreet>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>354 Mt Gretna Rd</GblAddr:streetTxt1>
               <GblAddr:cityName>Mt Joy Twp</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.167552999999998</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.604761999999994</GblLkup:longitude>
               <GblAddr:GISScore>93.099999999999994</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>StreetAddress</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>NAV_Street_Add</GblAddr:GISLocatorName>
               <GblAddr:sideOfStreet>L</GblAddr:sideOfStreet>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>355 Mount Gretna Rd</GblAddr:streetTxt1>
               <GblAddr:cityName>Mt Joy Twp</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.167538</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.604590999999999</GblLkup:longitude>
               <GblAddr:GISScore>72.099999999999994</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>StreetAddress</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>NAV_Street_Add</GblAddr:GISLocatorName>
               <GblAddr:sideOfStreet>R</GblAddr:sideOfStreet>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>355 Mt Gretna Rd</GblAddr:streetTxt1>
               <GblAddr:cityName>Mt Joy Twp</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.167538</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.604590999999999</GblLkup:longitude>
               <GblAddr:GISScore>72.099999999999994</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>StreetAddress</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>NAV_Street_Add</GblAddr:GISLocatorName>
               <GblAddr:sideOfStreet>R</GblAddr:sideOfStreet>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.219057999999997</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.655192</GblLkup:longitude>
               <GblAddr:GISScore>100</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>Postal</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>USAZipcode</GblAddr:GISLocatorName>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:otherCountryZip>17022</GblAddr:otherCountryZip>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.159343999999997</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.615829000000005</GblLkup:longitude>
               <GblAddr:GISScore>100</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>Postal</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>USAZipcode</GblAddr:GISLocatorName>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:cityName>Elizabethtown</GblAddr:cityName>
               <GblAddr:countryCd>US</GblAddr:countryCd>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.153250999999997</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.598975999999993</GblLkup:longitude>
               <GblAddr:GISScore>100</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>City</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>USACityState</GblAddr:GISLocatorName>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:cityName>Elizabethtown</GblAddr:cityName>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.153337000000001</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.599058999999997</GblLkup:longitude>
               <GblAddr:GISScore>100</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>City</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>Others.Map_USA_CTY_ST</GblAddr:GISLocatorName>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:cityName>Elizabethtown</GblAddr:cityName>
               <GblAddr:otherAddress>
                  <GblAddr:geoDivisionName>PA</GblAddr:geoDivisionName>
               </GblAddr:otherAddress>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.153337000000001</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.599057000000002</GblLkup:longitude>
               <GblAddr:GISScore>100</GblAddr:GISScore>
               <GblAddr:GISMatchTypeCd>City</GblAddr:GISMatchTypeCd>
               <GblAddr:GISLocatorName>Others.Map_USA_TWN_ST</GblAddr:GISLocatorName>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
      </ser-root:geocodeAddressResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>


```

---

### **Sample Request/Response for BestMatch**

**Request:**
```
<env:Envelope xmlns:env="http://www.w3.org/2003/05/soap-envelope" xmlns:soapenc="http://www.w3.org/2003/05/soap-encoding" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <env:Header/>
   <env:Body>
      <ns8:geocodeAddress xmlns:ns10="EsbMsgHeader" xmlns:ns11="MsgRequest" xmlns:ns5="EsbStatus" xmlns:ns6="GblAddr" xmlns:ns7="GblLkup" xmlns:ns8="http://esb.wm.com/service/geocodeAddress" xmlns:ns9="EsbProviderError">
         <ns10:msgHeader>
            <ns10:actionCd>Request</ns10:actionCd>
            <ns10:source>
               <ns10:msgSourceCd>eRL</ns10:msgSourceCd>
                </ns10:source>
         </ns10:msgHeader>
         <ns11:msgRequest>
            <ns11:requestSubject>BestMatch</ns11:requestSubject>
            <ns11:requestingByTypeCd>Address</ns11:requestingByTypeCd>
         </ns11:msgRequest>
         <ns6:addressIn>
            <ns6:premiseAddr>
               <ns6:streetTxt1>354 MOUNT GRETNA RD</ns6:streetTxt1>
               <ns6:crossStreetName></ns6:crossStreetName>
               <ns6:cityName>ELIZABETHTOWN</ns6:cityName>
               <ns6:countryCd>US</ns6:countryCd>
               <ns6:otherAddress>
                  <ns6:geoDivisionName>PA</ns6:geoDivisionName>
                  <ns6:otherCountryZip>17022</ns6:otherCountryZip>
               </ns6:otherAddress>
            </ns6:premiseAddr>
         </ns6:addressIn>
      </ns8:geocodeAddress>
   </env:Body>
</env:Envelope>


```

**Response:**
```
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <SOAP-ENV:Header xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"/>
   <SOAP-ENV:Body>
      <ser-root:geocodeAddressResponse xmlns:ser-root="http://esb.wm.com/service/geocodeAddress">
         <EsbStatus:status xmlns:EsbStatus="EsbStatus">
            <EsbStatus:statusCd>SUCCESS</EsbStatus:statusCd>
         </EsbStatus:status>
         <GblAddr:addressOut xmlns:GblAddr="GblAddr">
            <GblAddr:premiseAddr>
               <GblAddr:streetTxt1>354 MOUNT GRETNA Road, ELIZABETHTOWN, PA, 17022</GblAddr:streetTxt1>
            </GblAddr:premiseAddr>
            <GblAddr:coordinateAddr>
               <GblLkup:latitude xmlns:GblLkup="GblLkup">40.167724999999997</GblLkup:latitude>
               <GblLkup:longitude xmlns:GblLkup="GblLkup">-76.605222999999995</GblLkup:longitude>
               <GblAddr:GISStatusCd>Match</GblAddr:GISStatusCd>
               <GblAddr:GISScore>100</GblAddr:GISScore>
               <GblAddr:GISLocatorName>CoreLogicParce</GblAddr:GISLocatorName>
            </GblAddr:coordinateAddr>
         </GblAddr:addressOut>
      </ser-root:geocodeAddressResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


---
