----

### Client-Side Filtering

- **Execution Location**: Runs in the user's browser.
- **Data Handling**: Works with data already present on the client side.
- **Performance Impact**: Can be faster for small datasets since it doesn't require network requests.
- **Scalability**: Less scalable, struggles with large datasets.
- **Security**: Less secure, as it relies on data already available on the client side.
- **User Experience**: Offers immediate feedback and dynamic interactions without page reloads.
- **Resource Usage**: Utilizes the user's device resources (CPU, memory).
- **Examples**: JavaScript filtering, local search functionalities.

### Server-Side Filtering

- **Execution Location**: Occurs on the web server.
- **Data Handling**: Can handle large datasets and perform complex queries.
- **Performance Impact**: May be slower due to network latency, but more efficient for large datasets.
- **Scalability**: More scalable, can manage extensive data and complex filtering logic.
- **Security**: More secure, as it can validate and sanitize user inputs on the server.
- **User Experience**: May require page reloads or asynchronous requests (AJAX) for updates.
- **Resource Usage**: Utilizes server resources, offloading work from the client.
- **Examples**: Database queries, server-side search implementations.
---
### Different type of filtering

#### Extension Validation
- **File Extensions**: They are supposed to identify file contents but are easily changeable.
- **Use in Operating Systems**: Windows relies heavily on extensions; Unix-based systems use other methods.
- **Filtering Methods**:
    - **Blacklist**: List of not allowed extensions.
    - **Whitelist**: List of allowed extensions, rejecting all others.

#### File Type Filtering
- **MIME Validation**:
    - **Purpose**: Identifies file types, especially in web transfers.
    - **Format**: `<type>/<subtype>`, e.g., `image/jpeg`.
    - **Limitation**: Easy to bypass as it's based on file extension.
- **Magic Number Validation**:
    - **Purpose**: Identifies file content using specific bytes at the file's start.
    - **Usage**: Common in Unix systems.
    - **Example**: PNG files start with bytes `89 50 4E 47 0D 0A 1A 0A`.
    - **Reliability**: More accurate but not foolproof.

#### File Length Filtering
- **Purpose**: Prevents uploading of excessively large files.
- **Consideration**: Small files like shells might be filtered out if they exceed size limits.

#### File Name Filtering
- **Uniqueness**: Ensures uploaded files have unique names.
- **Sanitization**: Removes or replaces problematic characters.
- **Implication for Uploads**: Uploaded file names might differ from the original names.

#### File Content Filtering
- **Complexity**: More advanced, scans entire contents of files.
- **Purpose**: Verifies the file isn't spoofing its extension, MIME type, or Magic Number.
- **Note**: Not covered in basic filtration systems.
---

### Bypassing Client-Side Filtering

- _Turn off Javascript in your browser_ .
- _Intercept and modify the incoming page._ 
- _Intercept and modify the file upload_.
- _Send the file directly to the upload point._  `curl -X POST -F "submit:<value>" -F "<file-parameter>:@<path-to-file>" <site>`
----
Example Method 2:
When Requesting to Website Intercept Response & Completely Delete the Javascript

![[Pasted image 20231201194119.png]]
![[Pasted image 20231201194130.png]]


Example Method 3:
When intercepting the Packet -> Change MIME to [ text/x-php ]
And use the reverse Shell
![[Pasted image 20231201193107.png]]

![[Pasted image 20231201193113.png]]
![[Pasted image 20231201193118.png]]
![[Pasted image 20231201193124.png]]

---

### For Server Side filtering 
- Try different extensions for the file -> .php (php4,phtml,php5)
- Try putting the good file format before (file.jpg.php)
It really depends on the server code to Filter the files

---

### Magic Number

A **magic number** refers to a unique sequence of bytes at the beginning of a file, used to identify the file type and format. This distinctive sequence can be a specific string or numerical value and serves as a signature to enable software to determine the file's contents, independent of the file extension. Magic numbers are especially useful in systems where file extensions are not reliable for indicating file types, like in Unix-like operating systems. They facilitate programs in quickly and accurately identifying the format of a file for proper processing or display.

With ```Hexeditor``` command on linux you can modify the Hex signature of a fille
Find witch file you want to imitate : https://gist.github.com/leommoore/f9e57ba2aa4bf197ebc5?permalink_comment_id=4111195

Add random letters a the beginning ( 4 letters)

And with hexeditor change the first   letter to the signature you have found

