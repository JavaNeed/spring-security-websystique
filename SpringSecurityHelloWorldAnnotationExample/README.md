Spring Security 4 Hello World Annotation+XML Example
---------------------------------------------------

This tutorial demonstrates Spring Security 4 usage to secure a Spring MVC web application, securing URL access with authentication. We will use classic Hello World example to learn Spring Security 4 basics. This post uses Spring Annotation based configuration for Servlet 3.0 containers [thus no web.xml] and also shows corresponding XML based Security configuration for side-by-side comparison where applicable.

Following technologies being used:
--------------------------------
- Spring 4.1.6.RELEASE
- Spring Security 4.0.1.RELEASE
- Maven 3
- JDK 1.8
- Tomcat 8.0.21
- Eclipse JUNO Service Release 2 / STS


First thing to notice here is the maven-war-plugin declaration. As we are using full annotation configuration, we don’t even use web.xml, so we will need to configure this plugin in order to avoid maven failure to build war package. We are using latest versions(at time of writing) of Spring and Spring Security.

Method configureGlobalSecurity in above class configures AuthenticationManagerBuilder with user credentials and allowed roles. This AuthenticationManagerBuilder creates AuthenticationManager which is responsible for processing any authentication request. Notice that in above example, we have used in-memory authentication while you are free to choose from JDBC, LDAP and other authentications.

The overridden Method Configure configures HttpSecurity which allows configuring web based security for specific http requests. By default it will be applied to all requests, but can be restricted using requestMatcher(RequestMatcher)/antMathchers or other similar methods.

In above configuration, we say that URL’s ‘/’ & ‘/home’ are not secured, anyone can access them. URL ‘/admin/**’ can only be accessed by someone who have ADMIN role. URL ‘/db/**’ can only be accessed by someone who have both ADMIN and DBA roles.

Method formLogin provides support for form based authentication and will generate a default form asking for user credentials. You are allowed to configure your own login form.We will see examples for the same in subsequent posts.

We have also used exceptionHandling().accessDeniedPage() which in this case will catch all 403 [http access denied] exceptions and display our user defined page instead of showing default HTTP 403 page [ which is not so helpful anyway].


Reference:
--------
http://websystique.com/spring-security/spring-security-4-hello-world-annotation-xml-example/


How to run ?
-------------
http://localhost:8080/SpringSecurityHelloWorldAnnotationExample/

http://localhost:8080/SpringSecurityHelloWorldAnnotationExample/login