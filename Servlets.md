# HTTP Servlets
## Concepts
- [HTTP](https://tools.ietf.org/html/rfc2616):
  - Version HTTP/1.1
  - [Client-server messaging](https://tools.ietf.org/html/rfc7230#section-2.1)
  - [Message Syntax](https://tools.ietf.org/html/rfc7230#section-3):
    - [Request](https://tools.ietf.org/html/rfc2616#section-5):
      - [Methods](https://tools.ietf.org/html/rfc7231#section-4): Get, Post, Put, Delete, Head, Options, Trace
      - [URI](https://tools.ietf.org/html/rfc2616#section-5.1.2)
    - [Response](https://tools.ietf.org/html/rfc2616#section-6):
      - [Status Code](https://tools.ietf.org/html/rfc2616#section-6.1.1)
    - [Headers](https://tools.ietf.org/html/rfc7230#section-3.2): [Content-Type](https://tools.ietf.org/html/rfc2616#section-14.17), [Content-Length](https://tools.ietf.org/html/rfc7230#section-3.3.2)
- Java Platform, Enterprise Edition (Java EE) 7
  - Static Web Server vs Application Server
  - Layered Architecture: Presentation, Business, Persistence
- [Servlet](https://docs.oracle.com/javaee/7/tutorial/servlets001.htm): 
  - [Reading/Writing to ServletRequest/ServletResponse](https://docs.oracle.com/javaee/7/tutorial/servlets005.htm)
  - Servlet Container (Tomcat)
  - [Servlet interface life-cycle](https://docs.oracle.com/javaee/7/tutorial/servlets002.htm)
  - [ServletContext](https://docs.oracle.com/javaee/7/tutorial/servlets008.htm) vs ServletConfig
  - Forward vs Redirect
  - Session vs Cookie
  - Deployment Descriptor:
    - `web.xml` tags: servlet-name, servlet-class, url-mapping, load-on-startup, init-param, context-param
- HTML5:
  - Elements
  - Attributes
  - DOM
  - Forms
- REST
  - Constraints
  - Expose & Consume endpoints
  - XML/JSON serialization w/ JAXB or Jackson/Gson

## Syntax
- [javax.servlet](https://docs.oracle.com/javaee/7/api/javax/servlet/package-summary.html):
  - [Servlet](https://docs.oracle.com/javaee/7/api/javax/servlet/Servlet.html): init(), service(), destroy()
  - [ServletContext](https://docs.oracle.com/javaee/7/api/javax/servlet/ServletContext.html)
  - [ServletConfig](https://docs.oracle.com/javaee/7/api/javax/servlet/ServletConfig.html): getInitParameter()
  - [GenericServlet](https://docs.oracle.com/javaee/7/api/javax/servlet/GenericServlet.html): getServletConfig(), getServletContext() 
  - [ServletRequest](https://docs.oracle.com/javaee/7/api/javax/servlet/ServletRequest.html): getAttribute(), getParameter(), getRequestDispatcher()
  - [RequestDispatcher](https://docs.oracle.com/javaee/7/api/javax/servlet/RequestDispatcher.html): forward()
  - [ServletResponse](https://docs.oracle.com/javaee/7/api/javax/servlet/ServletResponse.html)
  - [javax.servlet.annotations]:
    - [WebServlet](https://docs.oracle.com/javaee/7/api/javax/servlet/annotation/WebServlet.html)
  - [javax.servlet.http](https://docs.oracle.com/javaee/7/api/javax/servlet/http/package-summary.html):
    - [HttpServlet](https://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServlet.html): doGet(), doPost()
    - [HttpServletRequest](https://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServletRequest.html): getSession() 
    - [HttpServletResponse](https://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpServletResponse.html): setHeader(), setStatus(), sendRedirect()
    - [HttpSession](https://docs.oracle.com/javaee/7/api/javax/servlet/http/HttpSession.html) & [Cookie](https://docs.oracle.com/javaee/7/api/javax/servlet/http/Cookie.html)
    - [Cookie](https://docs.oracle.com/javaee/7/api/javax/servlet/http/Cookie.html)

# Questions
- What is a client and server? How do they communicate?
- What is HTTP? What is its role?
- What are the major HTTP actions?
- What is the structure of an HTTP request?
- What is the structure of an HTTP response?
- What are HTTP headers used for?
- What is the difference between an HTTP Get and Post?
- What is JavaEE? How does it compare with JavaSE?
- What is an Application Server?
- Describe a JavaEE program's layered architecture.
- What is a Servlet?
- What is the difference between a ServletConfig and ServletContext?
- What is a Servlet container? Which container are you familiar with?
- What is a deployment descriptor? What are its important values?
- Explain the life cycle of a servlet.
- Explain the path taken by an incoming request to a servlet.
- How do I preload a servlet?
- How do I set initial parameters for both ServletConfig and ServletContext?
- What tags are used for mapping a servlet in the web.xml?
- Explain the inheritance tree from the Servlet interface to a custom subclass of HttpServlet.
- How do I perform error handling with the deployment descriptor?
- What is the difference between a forward and a redirect? How do I send either using servlets?
- How do I get and set data in a servlet?
- What is the difference between Sessions & Cookies?

# Notes
## Tomcat Embedded API
Tomcat embed is a library that allows for programmatic configuration and deployment of an embedded server within a Java application. In the `build.gradle`:
```
implementation 'org.apache.tomcat.embed:tomcat-embed-core:<version>
```

Replace <version> with a version found on https://search.maven.org.

Then in a main method:
```java
import org.apache.catalina.Context;
import org.apache.catalina.startup.Tomcat;

import javax.servlet.http.HttpServlet;
import java.io.File;

public class App {
    public static void main(String[] args) throws Exception {
        Tomcat tomcat = new Tomcat();
        tomcat.setPort(8080);

        // Set context path and root folder
        String contextPath = "/";
        String docBase = new File(".").getAbsolutePath();

        Context context = tomcat.addContext(contextPath, docBase);

        // Declare, define, and map servlets
        HttpServlet helloServlet = new HttpServlet(){
            @Override
            protected void doGet(HttpServletRequest req, HttpServletResponse resp)
                    throws ServletException, IOException {
                PrintWriter out = resp.getWriter();
                out.write("<html><title>Example</title><body><h1>Hello, World!</h1></body></html>");
                out.close();
            }
        };

        String servletName = "HelloServlet";
        String urlPattern = "/hello";

        // Register servlets with Tomcat
        Tomcat.addServlet(context, servletName, helloServlet);
        context.addServletMappingDecoded(urlPattern, servletName);

        // Start the server
        tomcat.start();
        tomcat.getServer().await();
    }
}
```
  
This will allow you to access a simple Hello World webpage at http://localhost:8080/hello
