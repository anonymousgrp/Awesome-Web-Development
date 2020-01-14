##### <center> Soap </center>

SOAP stands for Simple Object Access Protocol.SOAP requires transmitting data in XML, but as it is protocol agnostic it can use HTTP, SMTP, or anything else to negotiate and send messages requests.

Example:

```Xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:hs="http://www.holidaywebservice.com/HolidayService_v2/">
    <soapenv:Body>
        <hs:GetHolidaysAvailable>
            <hs:countryCode>UnitedStates</hs:countryCode>
        </hs:GetHolidaysAvailable>
    </soapenv:Body>
</soapenv:Envelope>
```

##### <center> Rest </center>

REST stands for Representational State Transfer. RESTful APIs give a client access to a representation of the state of a desired resource. When called, the server will transfer the representation to the client.
In order to make a request the server needs two things from the client: an endpoint, and a an operation. Endpoints serve as an identifier for the desired resource- the URL(Uniform Resource Locator!) of where to find it. Operations takes the shape of an HTTP method like GET, PUT, POST, or DELETE.

Example:
```Json
[{
    "id": 1,
    "name": "Leanne Graham",
    "username": "Bret",
    "email": "Sincere@april.biz",
    "address": {
        "street": "Kulas Light",
        "suite": "Apt. 556",
        "city": "Gwenborough",
        "zipcode": "92998-3874",
        "geo": {
            "lat": "-37.3159",
            "lng": "81.1496"
        }
    },
    "phone": "1-770-736-8031 x56442",
    "website": "hildegard.org",
    "company": {
        "name": "Romaguera-Crona",
        "catchPhrase": "Multi-layered client-server neural-net",
        "bs": "harness real-time e-markets"
    }
}]
```
##### <center> GraphQl </center>
Most of us have been creating and using REST APIs for a long time now. In the past few years people started talking about GraphQL as “Rest 2.0.” What’s with all the excitement, how is GraphQL even different than rest?
GraphQL was created by Facebook back in 2012 to support their mobile application infrastructure and then open sourced in 2015. It is a data fetching specification that also functions as an API query language (GraphQL).
Data fetching is often called out as the biggest improvement of GraphQL over REST. In a normal REST API, retrieving data from a server may require hitting more than one endpoint with requests. GraphQL reduces points of access to data on the server to a single endpoint. Because of this one request is enough to get both our resource as well as related resources.

Query Example:
~~~Graphql
{
  products(id: "7") {
    name
    price
    category {
      name
    }
    vendor {
      name
    }
  }
}
~~~