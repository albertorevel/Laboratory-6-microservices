# Laboratory 6 - microservices
## The two microservices are running and registered

The account microservice dashboard:
![AccountsService](https://github.com/albertorevel/Laboratory-6-microservices/blob/master/images/lab6-accounts.PNG?raw=true)

The web microservice dashboard:
![WebService](https://github.com/albertorevel/Laboratory-6-microservices/blob/master/images/lab6-web.PNG?raw=true)

## The service registration service has the two microservices registered
Both services are registered:
![WebRegister](https://github.com/albertorevel/Laboratory-6-microservices/blob/master/images/lab6-registry.PNG?raw=true)

## A second account microservice is running in the port 4444 and it is registered
The other account service dashborad:
![SecondAccountService](https://github.com/albertorevel/Laboratory-6-microservices/blob/master/images/lab6-accounts2.PNG?raw=true)

## A brief report describing what happens when you kill the microservice with port 2222. 
##### Can the web service provide information about the accounts? Why?

When you kill the accounts microservice which is running on the port 2222, the web microservice can't do any operation and shows an error message. This error message is the error response from the server, it has an 500 response status (Internal Server Error). We can see the cause, who contains "... I/O error on GET request for "http://ACCOUNTS-SERVICE/......."". This is a normal response: the killed account microservice can't be reached.

![ErrorService](https://github.com/albertorevel/Laboratory-6-microservices/blob/master/images/lab6-web-error.PNG?raw=true)

After some seconds, the web microservice finds the other accounts microservice registered at port 4444 because it's also registered, and continues working normally with it.

