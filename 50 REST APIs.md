###  APIs  

● An API (Application Programming Interface) is a software interface that allows two applications to communicate with each other.

● APIs are essential not just for network automation, but for all kinds of applications.

● In SDN architecture, APIs are used to communicate between apps and the SDN controller (via the NBI), and between the SDN controller and the network devices (via the SBI).

● The NBI typically uses REST APIs.

● NETCONF and RESTCONF are popular southbound APIs.  
![1445-08-10 22_21_57-Day 61 Slides - REST APIs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7c03bb5d-0ddb-4263-96c8-1a9155c33dbb)  
<br>


###  CRUD (Create, Read, Update, Delete)  

![1445-08-10 22_22_55-Day 61 Slides - REST APIs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/fca77a04-8198-446b-a0b4-a66809020419)  
<br>


###  HTTP Response  

Here are some examples of each HTTP Response class:  
● **1xx** Informational  
→**102 Processing** indicates that the server has received the request and is processing it, but the response is not yet available.

● **2xx** Successful  
→**200 OK** indicates that the request succeeded.  
→**201 Created** indicates that the request succeeded and a new resource was created (ie. in response to POST)

● **3xx** Redirection  
→**301 Moved Permanently** indicates that the requested resource has been moved, and the server indicates its new location.

● **4xx** Client Error  
→**401 Unauthorized** means the client must authenticate to get a response.  
→**404 Not Found** means the requested resource was not found.

● **5xx** Server Error  
→**500 Internal Server Error** means the server encountered something unexpected that it doesn’t know how to handle.  
<br>  


###  REST  

● **REST** (Representational State Transfer) **APIs** (aka **REST-based APIs** or **RESTful APIs**) are APIs that follow the REST architecture.  
→REST isn’t a specific API. Instead, it describes a set of rules about how the API should work.

● The six constraints of RESTful architecture are:  
→ Uniform Interface  
→ Client-server  
→ Stateless  
→ Cacheable or non-cacheable  
→ Layered system  
→ Code-on-demand (optional)

● For applications to communicate over a network, networking protocols must be used to facilitate those communications.  
→For REST APIs, HTTP(S) is the most common choice.  
![1445-08-10 22_27_34-Day 61 Slides - REST APIs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/a727fead-96c3-480d-8847-1e0678a4d9d8)
