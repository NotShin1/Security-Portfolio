## Lab description:

<img width="1370" height="897" alt="Screenshot 2025-11-11 130359" src="https://github.com/user-attachments/assets/337eafad-e2ef-4995-b708-543cc4abf4db" />

## Solution:
This lab has a stock check feature with fetches data from internal server

<img width="1894" height="730" alt="Screenshot 2025-11-11 131723" src="https://github.com/user-attachments/assets/183378d9-bae6-44c7-83d4-5ce79cfab610" />

We can use this to check the stock, the server will response like:

<img width="1353" height="696" alt="Screenshot 2025-11-11 131934" src="https://github.com/user-attachments/assets/5a730251-8258-4cd5-8c14-8b8dd2131f6a" />

The ```stockApi``` paremeter has a value like:
```
stockApi=http://192.168.0.1:8080/product/stock/check?productId=2&storeId=1
```

We try to redirect the API to the localhost:

<img width="1347" height="633" alt="Screenshot 2025-11-11 132148" src="https://github.com/user-attachments/assets/d33acb9e-c095-413b-a4ae-79807ad94494" />

The server return ```HTTP/2 500 Internal Server Error```

Currently, we know that the server is not returning to the localhost ip, and the lab description said that: ```To solve the lab, use the stock check functionality to scan the internal 192.168.0.X range for an admin interface on port 8080, then use it to delete the user carlos```

So we try again with the payload:
```
stockApi=http://192.168.0.1:8080/admin
```
<img width="1341" height="625" alt="Screenshot 2025-11-11 132735" src="https://github.com/user-attachments/assets/ed9d3764-48e3-4ac2-b2a0-d2f9cf2733fb" />

The server return the ```HTTP/2 400 Bad Request```

We know that the ip range is from 1 - 254, so we can use Intruder to attack the server and find out the right number for the ip address:

Send the POST Request to Intruder, then click ```Add§``` button, change the payloads to Numbers from 1 to 254:
<img width="1836" height="846" alt="Screenshot 2025-11-11 132952" src="https://github.com/user-attachments/assets/4ab0685d-4dc0-4622-a4c6-8d6c4946fdf6" />

And click the ```Start Attack```:

<img width="1895" height="815" alt="Screenshot 2025-11-11 134457" src="https://github.com/user-attachments/assets/9783eb5f-ca18-4b00-8014-b89d6f4d8862" />

We noted that the single number has been returned the status code 200:

<img width="1354" height="698" alt="Screenshot 2025-11-11 134608" src="https://github.com/user-attachments/assets/573bee8b-2295-4e0f-b0b6-7f78cf487db7" />

We successfully accessed the admin control panel:

Then, use the payload:
```
stockApi=http://192.168.0.180:8080/admin/delete?username=carlos
```

<img width="1355" height="634" alt="Screenshot 2025-11-11 134727" src="https://github.com/user-attachments/assets/803c2405-e3fc-46d2-9de1-2b32ea79debe" />

The lab has been resolved
<img width="1896" height="906" alt="Screenshot 2025-11-11 134800" src="https://github.com/user-attachments/assets/f1621281-7457-4583-9777-68c2b9583b69" />

