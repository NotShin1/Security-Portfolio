## Lab description:

<img width="1376" height="893" alt="image" src="https://github.com/user-attachments/assets/69de88cf-698e-4ac7-bf0a-7aed64758b1e" />

This lab's email change functionality is vulnerable to CSRF. It uses tokens to try to prevent CSRF attacks, but they aren't fully integrated into the site's session handling system.

## Solution:

<img width="1912" height="760" alt="image" src="https://github.com/user-attachments/assets/1cacac49-2971-4981-b30a-48ea50cdfcc2" />

Login as `wiener` user:

<img width="1916" height="761" alt="image" src="https://github.com/user-attachments/assets/065bb4f8-13f1-4185-838c-a8aae7a08d29" />

Then turn on the intercept and observe the request:

<img width="1606" height="657" alt="image" src="https://github.com/user-attachments/assets/4fd78d34-1baa-4cd4-8c4a-fa3ebd8c3289" />

We must pay attention that the POST request has cookie, csrfkey and token:

<img width="1142" height="554" alt="image" src="https://github.com/user-attachments/assets/f1cebc52-0992-45bd-9d07-dd0261c45c68" />

Send it to repeater and drop the request

Now, login as `Carlos` and use the change email function, turn on intercept and observe again:

<img width="1595" height="699" alt="image" src="https://github.com/user-attachments/assets/a9e55600-025c-4dd6-a5ef-66038e298994" />

We try it, replace the csrf token and cookie from the previous POST request:




