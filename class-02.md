What is http
Hypertext transfer protocol (the web)
when item searched in the address bar
	URL converted into an IP address when
IP address
like an individual mailbox for an address on the internet
URL (uniform resourcec locator)
four parts to the url
protocol (http)
IP address (192.168.1.1) where the server lives on the web
Port (:80) listening channel that speaks http to handle those incoming requests
resource (piano.html) the actual html file for the browser 

HTTP Verbs are certain functions built into http
get and post are two that would be used  to perform sign up actions for our webpage

How HTTP requests work
-understanding requests 
what is a requerst?
	a way to exchange data between a client and a server
client sends request
server responds to the request
Each request gets sent to a specific URL
Message returned from the server is called the response. 
data can be sent in URL parameters like /api?data=value
data can also be sent to the server via form data
data can be sent to the server in JSON format
data cant be sent and recieved as files--must tell server the type of file to expect
data can be sent as XML 

--components of a request
Methods
making a request to a server will be done using methods
traveling to a website will usually be using a get request from the server 
Data
Headers
	additional information about the request like the meta data
Authentication
	can be included in data or headers
	usually have a token that verifies who you are when hitting an api
--components of a response
Data 
	will be a response in similar fashion that the request was made 
Status code
	status code will come with the response
Headers
	popular type of header is to be given the data type of the data response
--Status codes 
1XX- information status code
2XX- success for your request
 	sometimes will have a ewrror in the body respionse which means the response and what not worked but how you requested it was wrong
3XX- Redirect
4XX- client error
	send a request to a url that doesnt exist, you'll gety a 404
	means the the client made a mistake, not the server
5XX- server error 

Tips fgor sending requextss
requests are blocking ---program will wait for the response from that request before the rest of the app continues
Requests can be generic-- make it so the function calls that hit endpoints are generic enough to write minimal code if you have to switch to a new api

HOW DNS WORKS
A URL is typed into the browser, hit enter and there is a new request generated for the broswer, browser checks its cache for the website if Its not there it asks the OS .
If the OS doesnt know of the website it puts the resolver to work it looks for the domain name within its cache.
If domain is not in resolver's cache the resolver goes to the :root directory.
If the root directory doesnt know it directs the resolver to the Top Level Domain server (.com, .org, .gov, etc). 
While in search of the domain name's corresponding IP address the resolver saves the top level domain given to it by the root. 
There are a total iof 13 Root Servers 
On our quest to find the IP address the resolver ends up in the .com top level domain which turns out not to know exactly what the IP address is however it recognizes the name servers that act to serve that particular website (which is stored for later in the cache)
These 4 servers are reffered to as the authoritative name servers for that domain
The domain registrar keeps track of all the websites 
Authoritative name servers provide answers to DNS queries: websites, email etc.. 
They hold all the real website code, good to have backups in case of failure. Location comes into play when talking about load times. Its ideal to be close to the nearest DNS
This is what gives the resolver our IP address for the requested webpage 
Review:
Root points to the .com server
The Top Level Domain server points to  the authoritative name servers addresses.
That server then responds with the IP address for our requested webpage. 

What is a Rest API?
Application program interface
Can think of them as a contract between one piece orf software to another
ktichen is the server, waitor is the api. The api goes back and forth with the data from on software to another. (sever and client)
Shapes are the api standard for making a request. They have to be structured in a certain way, same goes for responses we can abstract out and shape our data. 
Rest-- representational state transfer
relies on a statelss client server proptocl almost always HTTP

There are different methods of making requests to a server in HTTP
Get: retrieve data from a specified ressource 
POST: submit data to be processed to a specified resource
PUT: update a specified resource
	send some sort of parameter for that specific resource 
DELETE: deletes specified resource 
	others
Head: same as get but does not reutrn body
OPTIONS: returns the supported HTTP methods
PATCH: Update partial resources
Endpoints
The URI that the requests are sent to.
Endpoints can have the same URI but different functionality by calling different http methods on that specific endpoint. 

Authentication
Some apis require authentication to use, free or paid
OAUTH is a type of authorization

First example is sending the token inside the header
curl -H "Authorization: token OAUTH-TOKEN" https://api/github.com

Second example is as a parameter in the URI
curl https://api.github.com/?access_token=OAUTH-TOKEN

 SEnd a generated cleint id and client secret as a parameter 
cuurl 'https://api.github.com/users/whatever?client_id=xxxx&client_secret=yyyy'
