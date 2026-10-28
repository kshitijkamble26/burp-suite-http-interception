
Burp Suite HTTP Request and Response Interception
Aim

To configure Burp Suite Proxy to intercept HTTP requests and responses, modify an intercepted request parameter, and observe the server response using an authorized test application.

Requirements
Burp Suite Community Edition
A web browser
An authorized practice application, such as OWASP Juice Shop running locally
Permission to test the application
Procedure
1. Configure the browser
Open Burp Suite.
Select Proxy → Proxy settings.
Check that the local proxy listener is enabled, commonly at 127.0.0.1:8080.
Configure the browser to use 127.0.0.1:8080 as its HTTP proxy.
For HTTPS testing, configure Burp's CA certificate in a dedicated test browser profile.
2. Intercept an HTTP request
Open Burp Suite and select Proxy → Intercept.
Turn interception on.
Visit the authorized test application in the configured browser.
Observe the intercepted request in Burp Suite.
3. Modify a request parameter
Find a harmless parameter in a request to the test application.
Change its value to another valid test value.
Click Forward to send the modified request.
Observe the resulting page or application behavior.

Example of a harmless test parameter:

Before: GET /search?q=apple HTTP/1.1

After: GET /search?q=orange HTTP/1.1

Use this example only with an application that supports the indicated route and parameter.

4. Observe the server response
Open Proxy → Intercept and observe the response if response interception is enabled and supported by the current Burp workflow.
Alternatively, use Proxy → HTTP history to inspect the request and its corresponding response.
Compare the status code, response headers, and response body before and after changing the parameter.
5. Record observations
Original request parameter:
Modified request parameter:
HTTP status code:
Observed response:
Difference in application behavior:
Result

Burp Suite was configured to intercept HTTP traffic. A request parameter was modified in an authorized test application, and the corresponding server response was inspected.
