Spring Security 4 Custom Login Form Annotation+XML Example
---------------------------------------------------------
This post shows you creating custom login form in Spring Security 4 and integrate it in Spring MVC web application.

In Spring Security 4 Hello World Annotation+xml example, we have seen the default login form provided by Spring Security in case we don’t specify one. In this post, we will create our own Custom login form.

Basically, the idea is, in Security Configuration, attach a call to loginPage(URL) function with formLogin() like shown below

.and().formLogin().loginPage("/login")
And then, Map this ‘/login’ URL in your Spring MVC Controller which will return the login view defined by you. Now, on login attempt, the specified login view will be displayed.Rest of the login functionality remains same.

Below provided is complete example for this scenario.

Following technologies being used:
--------------------------------
- Spring 4.1.6.RELEASE
- Spring Security 4.0.1.RELEASE
- Maven 3
- JDK 1.8
- Tomcat 8.0.21
- Eclipse JUNO Service Release 2 / STS



Run the application
---------------------
Open browser and goto 
http://localhost:8080/SpringSecurityCusotmLoginFormAnnotationExample/
http://localhost:8080/SpringSecurityCusotmLoginFormAnnotationExample/admin

Reference:-
-----------
http://websystique.com/spring-security/spring-security-4-custom-login-form-annotation-example/
