# url 
- http://api.radioreference.com/soap2/?wsdl&v=latest
# portType = 
  - operation : 
```  
  <operation name="getCountryList">
    <documentation>Returns the list of countries</documentation>
    <input message="tns:getCountryListRequest"/>
    <output message="tns:getCountryListResponse"/>
  </operation>
```
# message =
  - input : 
```  
    <message name="getCountryListRequest"/>
```
  - output :
```   
    <message name="getCountryListResponse">
      <part name="return" type="tns:Countries"/>
    </message>
```
# type = 
  - Countries = 
```
    <xsd:complexType name="Countries">
      <xsd:complexContent>
        <xsd:restriction base="SOAP-ENC:Array">
        <xsd:attribute ref="SOAP-ENC:arrayType" wsdl:arrayType="tns:Country[]"/>
        </xsd:restriction>
      </xsd:complexContent>
    </xsd:complexType>
```
  - Country =
```
    <xsd:complexType name="Country">
      <xsd:all>
        <xsd:element name="coid" type="xsd:int"/>
        <xsd:element name="countryName" type="xsd:string"/>
        <xsd:element name="countryCode" type="xsd:string"/>
      </xsd:all>
    </xsd:complexType>
```
# binding
```
  <operation name="getCountryList">
    <soap:operation soapAction="http://api.radioreference.com/soap2#getCountryList" style="rpc"/>
    <input>
      <soap:body use="encoded" namespace="http://api.radioreference.com/soap2" encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"/>
    </input>
    <output>
      <soap:body use="encoded" namespace="http://api.radioreference.com/soap2" encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"/>
    </output>
  </operation>
```
 
# service
```
  <port name="RRWsdlPort" binding="tns:RRWsdlBinding">
    <soap:address location="http://api.radioreference.com/soap2/index.php"/>
  </port>
```  
