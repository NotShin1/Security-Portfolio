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



