## API - Application Program Interface

Interface is all around us. Everything that we see around is made up of so many interfaces that makes our job easy. For example, a simple radio has so many buttons (interface) that allows us to change the volumes, tune into different channel and much more. A mobile phone, computers have GUI (Graphical User Interface). A programming framework/libraries have interface that allows us to set various properties/ custom desing a specific task as we desire.

An Interface hides what is under the hood. For example, if a web developer wants a button, she/he can just use the required single or two lines of code and implement it without knowing what is going under the hood.

An interface defines ways for us to interact/communicate with the object(physical or software). Interfaces abstract away the implementation.

While the UI(User Interface) is made for the User of an Application, an API is made for the Application Programmer to use and then extend their applications

API - is a contract of source. It defines how it is expected to be used and also defines what you can expect to be received from using it. It is created to give access to data and provide abstraction of the implementation (how it is doing what it is doing)

Safe to assume when you hear the word API, it means 'web based API' though there are many other APIs

A programming language is an API that abstracts all the low level bit by bit operation on the instruction. For example, if you want to create a string from lowercase to uppercase, you just have to call the respective API method (upper()) and that will do the work for you. This method abstracts the low level implementation part.

Frameworks allow you to extend what is already given to your own desire.

Broweser implements so many web APIs so that when we host a site, it is able to get all the necessary information.

APIs - 1. Local APIs, 2. Remote APIs

## Remote API:

- A TV remote is an example of a remote API. We can access the TV's various interfaces or Settings using the TV Remote's various Interfaces(Buttons). Basically we can control an application using remote API (TV Remotes, Drone Remotes, Changing Traffic Board Messages from a computer, controlling a robot(wireless), etc,...). Google Drives, Google Clouds, etc,... are also an example of Remote APIs.
- Since Remote APIs remove the limitations of the local machine, we can have enormous computaional capabilities (fast responses). These are the reasons that allows us to access various and specific information from in the web (web APIs are remote as well)
- We use REST -> Representational State Transfer, to access information from web. (abstraction). It is a Web Service API.
- Other RemoteAPIs -> GraphQL, SOAP, RPC,...

REST sits on top of web technology.

## How web works and web terminologies (HTTP):

- Browser -> Web Client (we use browser to connect to a server). We connect to the server by putting an address in the search bar. This address is called "Universal Resource Locator(URL) / Universal Resource Identifier(URI)'
- http - Hyper Text Transfer protocol
- https - Hyper Text Transfer protocol Secure
- URI/URL has a Scheme Portion which has either http/https protocol
- https/http is a little lower than an API
- http/https -> defines how to communicate with the with the server and client
- Browser creates a http/https request for you by using a particular https/http words/request methods: GET, PUT, POST, HEAD, DELETE, PATCH, OPTIONS
- GET: Clarifies that it will only receive data and will not modify anything in the server.
- POST: used to post data to the server
- The http request from the client is transfered to the server; the server does the job and sends back the result to the client (browser). The most important part of the response is the body - in case of webpage, it contains the HTML code.
  -Hyper Text Markup Language -> the first two words, 'Hyper Text', which means linking to something else. When this link is clicked, a HTTP request is sent and the necessary output is displayed after getting a response from the server.
- HTTP is a 'STATELESS' protocal; meaning that once the request receives a response, its job is finished. If we want to maintain a state, then we/client have to manage that itself and sent it up with each new request.

The stuffs after the question mark(?) in the URL is one way to pass the information about the request.

Another common way to pass the information about the request is using the key and value pairs called 'Headers'. Both requests and responses have headers and is used to communicate what is further wanted by the client. Using headers, we can add each and every info that we need (content Lang, content type,...)

The Response also has headers. These headers have status codes that convey informations about what happended in the server.

# REST:

REST sits top of all the web technologies. Hence it will leverage the use of all of these to benefit us.

Applications that meet the REST architecture are considered to be 'RESTful'

Here are the guiding architectural constraints required for an API to be considered RESTful:

1. Client-Server architecture
2. Statelessness
3. Layered System
4. Cacheability
5. Uniform desing
6. Code on Demand

# How the REST API sits on top of the web?

The client makes a request to the server. The client in this case is going to be your program running in your browser and will probably using some frameworks or libraries to create the request. The protocol used is "HTTP" and is stateless: which means the server wont remember anything about the particular client. So, if we want to the server to remember some details like login info etc, then we have to send those appropriate keys in the header of each and every HTTP request.

Everything is a Resource. It is an object. For example, in a book website, we see a list of books which is a resource. When we click on a book, we see additional informations about the book and again that is also a resource. When we click on the author of the book, we see all the books written by that particular author and again it is a collection of resources. So, we can use 'resource' to pretty much anything.

A like button on a photo is a resource, a comment section is a resource. So, almost everything we want to buld can be expressed as a resources/collections.

Most of what we want our application to do the resources / collections can be expressed with the acronym 'CRUD' (Create, Read, Update, Delete)

When we want to perform a 'Read' action, the REST API sends a GET request and the server responds with the data that has headers and the body. And the body is called as JSON these days because of the format of the data present inside it.

JSON - JavaScript Object Notation

JSON provides a great way to structure and nest your data. Every programming language tries to turn the JSON data to the native format of that particular language.

If JSON is not our priority, then we can specify the type of Data format in the request.

The HTTP Verbs - GET, POST, PUT, PATCH, DELETE - are used by the REST API to state the intention of the request.

(The HTTP Verb Usage and the equivalent CRUD Abbreviation)

- GET - Retrieves the Data - Read
- POST - puts the data - Create
- PATCH - updates the data - Update
- PUT - updates the data - Update
- DELETE - Removes the data - Delete

We can play with any application that exposes their API. Using that, we can even integrate those applications with our own applications

- SDK - Software Delevopment Kit -> it gives an API that wraps around around other APIs and it will feel native to your programming language. This is also called as 'Helper Libraries'

Whenevr a JSON is returned in REST, it is also cached in the server side so, the result is not rendered everytime a request is made. That is why when the same request is made twice, the response is so quick than the first request-response.

We can send API requests using using either Terminal using the 'curl' language or we can use 'Postman' App.

We dont want to make requests whose response are of big sizes. it sounds like the job of client side caching.

In postman, if the request was made once and again, the same request is made, then an actual request is not made to the server, but to the local machine, where the cached data is stored. By using 'if-Modified-since' key and the last modified date as the value to that key, in the header, we will receive a 304 Status which says "Not Modified" from the specified time and date. This proves the Cacheing of the REST API.

Using HTTP's caching mechanisms like 'Last-Modified' and 'e' tags, RESTful API should support Caching. Comes in Handy when we need to prevent making unneeded requests

HTTP Requests is all we need to interact with the REST APIs

