## Path Traversal - Lab 1: File Path Traversal, Simple Case

### Objective
In this lab, we exploit a path traversal vulnerability to access sensitive files on the server.

### Steps

1. **Understanding the Vulnerability**
   - The application allows unsanitized user input to access files on the server.

2. **Exploit the Vulnerability**
   - We utilize the `loadImage` function in the HTML, which processes file paths without proper validation.
   - By manipulating the file path, we request the `/etc/passwd` file, which is a common target for path traversal attacks.

3. **Payload Example**
   ```http
   GET /loadImage?filename=../../../../etc/passwd HTTP/1.1
   Host: vulnerable-website.com
