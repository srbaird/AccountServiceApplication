# Account Service Application


This allows the [AccountServiceApp](https://github.com/srbaird/AccountServiceApp/) project to be built into an [ear](https://en.wikipedia.org/wiki/EAR_(file_format)) file and allows it to be deployed on a server which means the authentication service may be decoupled as a dependency.

___

A stand alone application may access the service through a Spring JNDI lookup.
```
	xmlns:jee="http://www.springframework.org/schema/jee"
	xsi:schemaLocation="http://www.springframework.org/schema/jee http://www.springframework.org/schema/jee/spring-jee-3.0.xsd

    <jee:remote-slsb id="accountServiceApp" business-interface="com.bac.accountservice.AccountService"
    	jndi-name="java:global/AccountServiceApplication/AccountServiceApp-1.0.0/AccountServiceApp" />
```
The JNDI name is made up from the deployed application name followed by the jar and finally the interface implementing class.

___




