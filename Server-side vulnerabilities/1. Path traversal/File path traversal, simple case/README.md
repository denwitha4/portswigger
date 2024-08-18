# File path traversal, simple case
In this lab, we'll exploit a web application's lack of defenses against path traversal attacks.

## Steps

1. **Visit the Target Site**
   - Use Burp Suite to visit the target website.
   - In Burp Suite, observe the requests made by the site, noting images loaded via their file directories.
   ![File Directory Example](images/filenamenotice.png)
   - **Note:** Ensure "Images" is selected in the history filter to view these requests.
   ![Burp Suite Filter Options](images/filteroptions.png)

2. **Identify the Exploit Method**
   - Right-click the image request and send it to the Repeater. This request will be used to test the path traversal vulnerability.
   ![Send to Repeater](images/sendtorepeater.png)

3. **Modify the Request**
   - In the Repeater tab, change the file path to `../../../etc/passwd` to target the system's passwd file.
   ![Before Change](images/beforechange.png) ![After Change](images/afterchange.png)

4. **Execute the Exploit**
   - Send the modified request. If successful, you will receive the contents of the root `passwd` file.
   ![Lab Completed](images/labcompleted.png)

Congratulations, you have successfully completed the first lab in the Server-Side Vulnerabilities learning path!
