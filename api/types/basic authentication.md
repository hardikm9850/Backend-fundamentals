In this method, client credentials, consisting of a username and password pair, are passed to the API server in a field in the HTTP header. The server then verifies these credentials before granting access to protected resources. Although Basic Auth is straightforward to implement, it is less secure compared to more advanced methods since it involves transmitting credentials in an encoded, but not encrypted, format. It is often used in cases where simplicity is paramount, or High security levels are not required.

![basic-authentication](https://github.com/user-attachments/assets/e4cb91d7-8118-4d62-8930-8f2678b14ad5)