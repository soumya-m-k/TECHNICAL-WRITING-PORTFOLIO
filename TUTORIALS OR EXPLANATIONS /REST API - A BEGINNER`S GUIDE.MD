# REST API
REST Stands for Representational State Transfer.REST is not protocol and not a standard , It is architectural style. API which follows the REst architectural style that is REST API. It uses HTTPs protocol and provide interface between two software systems to communicate each other over internet by sharing data,functions and services.

REST API also known as RESTFull API that uses HTTP web services to communicate between client and server. REST API is usefull in web related API like most companies or organizations want to communicate to internal systems or third party applications to access data,function or services for fast and better performance 

For example : In e-commerce application companies wants internal systems to connect their customer banking details for payment because of that they use APIs instead of building from scratch and provide security tocustomer data.

# Principles of REST Architectural style and components

REST Architecture has best style for better communication because it follows six basic principles that helps to provide good interface to share data and services between client and server. these principles ensures reliability,scalability and extensibility.
<img src="https://media.licdn.com/dms/image/v2/C4D12AQHh6l0xkbhTPg/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1622931040032?e=2147483647&v=beta&t=KP6s82dMHXyOTcVsNCkKypBjIlQSWYCqI4ucfTrzTJg"  width="800" height="700">

+ **Client-Server Architect**: This principles states the client and server seperation so that each should act independent of the other.the server side and client side performace changes should not affect the other and provide same interface for different clients.

+ **Statelessness**: The communication between client and server doesn not track state of sessions because there is no continuous connection between client and server. Each request sent to the server has state of session so server doesn`t rely on state of session. which improves scalability and reliability.

+ **Uniform Interface**: All API requests for same resource should look the same, no matter where the request comes from. API should ensure that the same piece of data like name or email of user, belongs to only one URI(Uniform Resource Identifier).Resourse shouldn`t be too large but it should contain every piece of information that client needed.

+ **Layered System** : The layered system style allows an architecture to be composed of hierarchical layers by constraining component behavior. In a layered system, each component cannot see beyond the immediate layer they are interacting with.

+ **Cacheable** : The REST server can cache data to better serve the client, for example by storing the images of a site to then serve them again.

# How Rest API works
Rest APi works on client and server model through request and response cycle using http methods.

+ Client makes http request to an APi endpoint.
+ server validates the authentication and process the request and interacts with database if necessary.
+  the server sends back response and also status code. the response is in json format.

# Rest API Reference 
Rest API reference includes Resource description, endpoint and methods, parameters,request examples and response example.

1. **RESOURCE DESCRIPTION**

   Resource description is group of endpoints under the same resource. operation about user has different endpoints under same resource.

   for example of user operation in any applications.

       GET     /user/{username}    Get user by user name
   
       PUT     /user/{username}    Updated user
   
       DELETE  /user/{username}    Delete user
   
       GET     /user/login         Logs user into the system
   
       GET     /user/logout        Logs out current logged in user session
   
       POST    /user               Create user

2. **ENDPOINT AND METHODS**

   Endpoint is combination of base URL and path or specific resource that send request to access data using crud operation.

   here is example of simple book api

   `/order`

   with path parameter

   `/order/{orderId}`

   **methods**

   methods are listed next to endpoint. the methods are used to perform operations with resource.

  1. **GET**  : Retrieve all the reources.

      `GET`  /orders 

      get all the book orders.

      `GET`  /order/{orderId} 

      get a particular oeder by its id.

 2.  **POST**  : create a resource.

      `POST`  /orders

       order books you want.

 3.  **PUT** : it completely replace existing resource ot create new resource.

 4.  **PATCH** : modify or update the existing resource.

      `PATCH`  /orders/{orderId}

       update the order.

 5.  **DELETE** : delete the resource.

      `DELETE`   /orders/{orderId}

3. **PARAMETERS**

    Parameter is the variable that passed inside the API request to control the response data.

    They are three types of parameters

    + Header parameter - parameters are in the request body related to authorization.
    + path parameter - parameters are within query string before the ?.
    + query string parameter - parameter are mentioned outside the query string after the ?.

4. **REQUEST EXAMPLE**

    Request is message sent to server to access data.

    request body includes 4 key points.
   
    + headers - it includes security tokens and data format.
    + resource URL - it includes baseURL and endpoints.
    + parameters - vaiables like specific id.
    + http methods - the action to perform.

    request example always written in curl

  ` curl -I -X GET "https://api.openweathermap.org/data/2.5/surfreport?zip=95050&appid=APIKEY&units=imperial&days=2"`

5. **RESPONSE EXAMPLE**

    the response always retuns data in the form JSON and also status code.

    components of response
    + status code - three digit code stating the outcome.
    + headers - metadata containing data formats.
    + body - the actual data.

   **Status code**
     + 2xx(successful) - the request recieved and data processed successfully.
     + 3xx(redirected) - the action is needed to complete.
     + 4xx(client error) - the issue is in the request format.
     + 5xx(server error) - the server failed to fulfill the request.

   **response data**

        {
          "status": "success",
          "code": 200,
          "message": "User data retrieved successfully.",
          "data": {
          "userId": 1084,
          "name": "valentina",
          "email": "valentina.doe@example.com"
         }
       }
     

    

      

   

