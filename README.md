# JKFramework

JKFramework is an end-end Java development framework that enables faster and effiecent software development. It is consists of the following sub-projects:
- **JKFramework-Core**:
It is a set of libraries, utilities, and API's that could help developers with small tasks such as Configurations, Context, Exception Handling, Logging, I/O, and many other. 

- **JKFramework-Data** 
  It is a **zero-config** Data Access API that enables the best of JDBC and JPA, with a unified configuration, elegant API, without intesnive features around these API's including logging, auditing, timing, and monitoring. 
  
- **JKFramework-Web**
Its is a project that enables _zero-config_ setup for _Java JakartaEE 10  Web Apps on Tomcat_, that consists of all the needed dependecies and configurations of Faces 4 (JSF), PrimeFaces 12, CDI 4 (Weld), in addition of a set of Listeners and Fliters that enables that enables many features such as automatic confguration detections, logging initializations, and proper bootstraping and shutting-down which enables a clean appraoch of hot deployment.     

- **JKFramework-Embedded**
Is a _zero_config_ wrapper of Tomcat Embedded web server that contains some utilities and enhancements, it enables faster software development by elemianting the need of confguring and running external web server to develope Java Web Applications (JSF, JSP or, Servlets) and Microservice. 

- **JKFramework-Service**
It is a_ zero_config_ project that enables a faster approach towrd JakartaEE 10 microserivces development, it consists of all the needed depedenceis, configurations, and proper listeners and filters to have a reliable software development such as exception handlers and context sycnrhozniation.   

- **JKFramework-ServiceClient**
It is a project that helps Java developers calls microservice in an effiecent approach that includes. proper configutaiton, timing, exception handling, unified logging, and others.  

- **JKFramework-WebStack**
It is a _zero-config_ project that enables Java software developers to build end-end Java web applications that communicates with databases or microservices with .

In addition, it contains the following maven parent projects that enables faster projects setup:
- **JK-App**
Parent project that include all the needed configuration of maven projects such as JDK17+, exclusions, dependecies, version files, and others. 

- **JK-App-Web**
In addition of the features of of JK-App, it contains the needed depdencies of webapp development. 

- **JK-App-WebStack**
In addition of the features of JK-App-WebApp, it consists of the needed depecnceis of accessing database and microserices. 
