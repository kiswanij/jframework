# JKFramework

JKFramework is an end-end Java development framework that enables faster and efficient software development. It is consists of the following sub-projects:
- [**JKFramework-Core**](components/jkframework-core.md):
It is a set of libraries, utilities, and API's that could help developers with small tasks such as Configurations, Context, Exception Handling, Logging, I/O, and many other. 

- **JKFramework-Data** 
  It is a **zero-config** Data Access API that enables the best of JDBC and JPA, with a unified configuration, elegant API, without intensive features around these API's including logging, auditing, timing, and monitoring. 
  
- **JKFramework-Web**
Its is a project that enables _zero-config_ setup for _Java JakartaEE 10  Web Apps on Tomcat_, that consists of all the needed dependencies and configurations of Faces 4 (JSF), PrimeFaces 12, CDI 4 (Weld), in addition of a set of Listeners and Filters that enables that enables many features such as automatic configuration detections, logging initializations, and proper bootstraping and shutting-down which enables a clean approach of hot deployment.     

- **JKFramework-Embedded**
Is a _zero_config_ wrapper of Tomcat Embedded web server that contains some utilities and enhancements, it enables faster software development by eliminating the need of configuring and running external web server to develop Java Web Applications (JSF, JSP or, Servlets) and Microservice. 

- **JKFramework-Service**
It is a_ zero_config_ project that enables a faster approach toward JakartaEE 10 microservices development, it consists of all the needed dependencies, configurations, and proper listeners and filters to have a reliable software development such as exception handlers and context synchronization.   

- **JKFramework-ServiceClient**
It is a project that helps Java developers calls microservice in an efficient approach that includes. proper configuration, timing, exception handling, unified logging, and others.  

- **JKFramework-WebStack**
It is a _zero-config_ project that enables Java software developers to build end-end Java web applications that communicates with databases or microservices with .

In addition, it contains the following maven parent projects that enables faster projects setup:
- **JK-App**
Parent project that include all the needed configuration of maven projects such as JDK17+, exclusions, dependencies, version files, and others. 

- **JK-App-Web**
In addition of the features of of JK-App, it contains the needed dependencies of webapp development. 

- **JK-App-WebStack**
In addition of the features of JK-App-WebApp, it consists of the needed dependencies of accessing database and microservices.
