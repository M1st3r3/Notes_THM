
![[Pasted image 20231106235618.png]]
**Example Request:  
```http
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/

```

### HTTP Method

**GET Request**
This is used for getting information from a web server.  

**POST Request**
This is used for submitting data to the web server and potentially creating new records  

**PUT Request**
This is used for submitting data to a web server to update information

**DELETE Request**  
This is used for deleting information/records from a web server.

### 5 category of  Code Response

		100 -199 = Information Response
		200 - 299 = Success
		300 - 399 = Redirection
		400 - 499 = Client Error
		500 - 599 = Server Errors

### Most Common Code
|   |   |
|---|---|
|**200 - OK**|The request was completed successfully.|
|**201 - Created**|A resource has been created (for example a new user or new blog post).|
|**301 - Moved Permanently**|This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead.|
|**302 - Found**|Similar to the above permanent redirect, but as the name suggests, this is only a temporary change and it may change again in the near future.|
|**400 - Bad Request**|This tells the browser that something was either wrong or missing in their request. This could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didn't send.|
|**401 - Not Authorised**|You are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password.|
|**403 - Forbidden**|You do not have permission to view this resource whether you are logged in or not.|
|**405 - Method Not Allowed**|The resource does not allow this method request, for example, you send a GET request to the resource /create-account when it was expecting a POST request instead.|
|**404 - Page Not Found**|The page/resource you requested does not exist.|
|**500 - Internal Service Error**|The server has encountered some kind of error with your request that it doesn't know how to handle properly.|
|**503 - Service Unavailable**|This server cannot handle your request as it's either overloaded or down for maintenance.|

### Request Header
- Headers are additional pieces of information sent to web servers when making HTTP requests.
- While not strictly required, headers are essential for proper website functionality and data transmission.

 **Common Request Headers** 
1. **Host Header**
   - Sent from the client (e.g., browser) to the server.
   - Specifies the desired website when a server hosts multiple sites.
   - Ensures you receive the intended website instead of the default.

2. **User-Agent Header**
   - Communicates the client's browser software and version.
   - Helps the server format the website for the specific browser.
   - Supports browser-specific HTML, JavaScript, and CSS features.

3. **Content-Length Header**
   - Used when sending data to a web server (e.g., form submissions).
   - Informs the server about the expected data size, preventing data loss.

4. **Accept-Encoding Header**
   - Indicates the browser's supported compression methods.
   - Enables the server to send smaller, compressed data over the internet.

5. **Cookie Header**
   - Sends data to the server for user information storage (see cookies task for details).

**Common Response Headers
1. **Set-Cookie Header**
   - Returned from the server to the client after a request.
   - Contains information for storing cookies that are sent back on subsequent requests (see cookies task for details).

2. **Cache-Control Header**
   - Specifies how long the content should be stored in the browser's cache before re-requesting.
   - Helps optimize website performance by reducing redundant requests.

3. **Content-Type Header**
   - Informs the client about the type of data being returned (e.g., HTML, CSS, JavaScript, images, PDF, video).
   - Allows the browser to process the data appropriately.

4. **Content-Encoding Header**
   - Indicates the compression method used to reduce data size during transmission over the internet.

### Cookies
![[Pasted image 20231107001303.png]]

