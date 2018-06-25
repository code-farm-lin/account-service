# Simple Bank Account and transaction management Application

##Initial functional requirement 

 
## Assumptions
As it is a bank transaction and account maintainance application. The following assumptions
has been made to justify the design decision.


Followings are my assumptions of what is important to teh system.  
1) The first assumption is that it is critical to be able handle high volume of transactions at the same time. the 
system should be able to handle high throughput
2) it is important that transaction records will not be lost without a trace. As 
a result, it requires a very reliable system and fault tolerance.
3) In addition, the system should be highly scalable as with the trend of online payments,
there will be increase volume of transactions. 
4) fast time to Market 


The following are in lower priority than the above. 
1) low latency, for example the transaction must be executed within a nano or milisecond.
2) development cost  
3) the data can be eventually consistent. 

## Initial System Design
 
 The initial system design is to build a green field application using MicroService. The 
 advantage of this choice is that the system can is highly scalable and able to handle high through put. 
 
 On the downside is that the system can be very complex which include the complete CI/CD and monitoring system. In addition, 
 the system cost is high.
 
 For this exercise, I impelement 3 micro-services using spring boot. The main technologies I used are:
 1) Spring boots
 2) in memory Mongo DB
 3) Spring WebFlux
 4) Swagger for API documentation
 
 ## Instruction to run the application
 
 1) checkout the customer-service application from github
 2) run maven command: mvn spring-boot:run
 3) the account service api will be available under http://localhost:8080/
 
 The initial prototyping phase is focus on 2 APIs listed below for the account service. The transaction service will 
 provide another endpoints for account transactions. 
 
 1) accept a request to open accounts of existing customers. API will do the following:
    - Accepts the user request with sufficient information to open an account
    - Create a transaction for the user if initial credit is not zero
    - Invalid request will send back to the user if customer does not exist within the system
    - The authentication and authorisation should be implemented. However, due to the time constraint, 
    it will be implemented in the next iteration
 2) output the user information showing Name, Surname, balance,and transactions of the accounts.
 API documentation can be checked at the following URL (http://localhost:8080/swagger-ui.html#/) once you have it up and running.  
  
 
 Please Note that this is initial prototyping stage, there are some development items still required to be completed such as
 exception and error status handling, security and messaging service between transaction service and account service. 
 
