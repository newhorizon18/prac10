# Experiment No. 10

## Title: Program on Implicit and Explicit Objects in JSP

## 1. Program Code

### A. Implicit Objects in JSP

**File Name: implicitDemo.jsp**

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>

<!DOCTYPE html>
<html>
<head>
    <title>Implicit Objects Demo</title>
</head>

<body>

    <h2>JSP Implicit Objects Example</h2>

    <p>
        <b>Request Parameter:</b>
        <%= request.getParameter("username") %>
    </p>

    <p>
        <b>Session ID:</b>
        <%= session.getId() %>
    </p>

    <p>
        <b>Application Context Path:</b>
        <%= application.getContextPath() %>
    </p>

    <p>
        <b>Server Info:</b>
        <%= config.getServletContext().getServerInfo() %>
    </p>

    <p>
        <b>Writer Output using out:</b>
        <% out.println("Hello from 'out' implicit object!"); %>
    </p>

</body>
</html>
```

### Output

Example output when the username is `Amit`:

```text
JSP Implicit Objects Example

Request Parameter: Amit

Session ID: [Generated Session ID]

Application Context Path: /JSPObjectsDemo

Server Info: Apache Tomcat

Writer Output using out: Hello from 'out' implicit object!
```

---

### B. Explicit Objects in JSP

**File Name: explicitDemo.jsp**

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>

<!DOCTYPE html>
<html>
<head>
    <title>Explicit Objects Demo</title>
</head>

<body>

    <h2>JSP Explicit Objects Example</h2>

    <%
        // Explicitly creating objects
        String user = request.getParameter("username");
        java.util.Date today = new java.util.Date();
    %>

    <p>
        <b>User Name:</b>
        <%= user %>
    </p>

    <p>
        <b>Current Date & Time:</b>
        <%= today %>
    </p>

</body>
</html>
```

### Output

Example output:

```text
JSP Explicit Objects Example

User Name: Amit

Current Date & Time: [Current Date and Time]
```

**Note:** Session ID, server information, and date/time may vary depending on the server and execution time.

---

## 2. Aim

To study and implement implicit and explicit objects in JSP to retrieve user information, manage sessions, access application details, and display dynamic content.

## 3. Theory

JSP (JavaServer Pages) is a Java technology used to create dynamic web pages.

### A. Implicit Objects

Implicit objects are predefined objects provided by JSP. They can be used directly without creating them.

- **request:** Retrieves information sent by the client.
- **response:** Sends responses to the client.
- **session:** Stores user information across multiple requests.
- **application:** Provides information about the web application.
- **out:** Displays output in the browser.
- **config:** Provides servlet configuration information.
- **pageContext:** Provides access to JSP page-related information.
- **page:** Refers to the current JSP page.
- **exception:** Provides exception information on error pages.

### B. Explicit Objects

Explicit objects are objects created by the programmer using Java code.

- They are declared or initialized manually.
- They are used to perform specific operations.
- They can store and process information.
- The `new` keyword is commonly used to create objects.

**Example:**

```java
java.util.Date today = new java.util.Date();
```

This creates a Date object to obtain the current date and time.

## 4. Steps to Execute

1. Open Eclipse IDE or another JSP-supported Java development environment.
2. Create a Dynamic Web Project.
3. Configure an Apache Tomcat server.
4. Create two JSP files:
   - `implicitDemo.jsp`
   - `explicitDemo.jsp`
5. Add the corresponding JSP code.
6. Save both files.
7. Run the project using the Tomcat server.
8. Open the JSP pages in a web browser.
9. Observe the output.

**Example URLs:**

```text
http://localhost:8080/JSPObjectsDemo/implicitDemo.jsp?username=Amit
```

```text
http://localhost:8080/JSPObjectsDemo/explicitDemo.jsp?username=Amit
```

Replace `JSPObjectsDemo` with your project's actual context path.

## 5. Conclusion

Thus, implicit and explicit objects in JSP were successfully studied and implemented.

Implicit objects provide predefined functionality, while explicit objects are created by the programmer to perform specific operations in a web application.
