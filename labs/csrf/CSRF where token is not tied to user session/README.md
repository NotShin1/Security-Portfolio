## Lab Description:

<img width="1385" height="889" alt="Screenshot 2025-11-14 101621" src="https://github.com/user-attachments/assets/00755c86-f2fc-4a44-8920-b1f5e2038593" />

## Solution:

We suppose that ```wiener``` user is victim and ```carlos``` is attacker, we login as ```carlos```:

<img width="1901" height="914" alt="image" src="https://github.com/user-attachments/assets/9fc418a2-a56f-4659-99b1-eb25bd561e19" />

Next, we use the update email function to change our email:


<img width="1898" height="907" alt="Screenshot 2025-11-14 102230" src="https://github.com/user-attachments/assets/5c7dea40-bf68-47ae-88f3-f2104d4be89e" />


The POST Request is:

<img width="1248" height="877" alt="image" src="https://github.com/user-attachments/assets/c677d323-c6fb-488c-a205-a8e73e35910b" />


We get carlos's csrf token: ```csrf=Z1XQXXKzWHgL3BEkfB2Ndt2PNB3lqIGT```:

Now, we login as ```wiener```:

<img width="1900" height="734" alt="image" src="https://github.com/user-attachments/assets/26614853-5f8e-4530-90df-f3896481438c" />

And use the email change function:

<img width="1919" height="929" alt="image" src="https://github.com/user-attachments/assets/f0585880-9449-4687-8009-762202d469c3" />

We get wiener's csrf token: ```csrf=KCTCKdwbrN0ZP5BivIjV2VC2N9Bah3Sq```

What if we use carlos's csrf token instead wiener's token? I change the email and use carlos's csrf token for ```wiener``` account:

<img width="1912" height="777" alt="image" src="https://github.com/user-attachments/assets/3e243eef-fa0a-4009-9301-e19ee5bcb181" />

The server's response is ```"Invalid CSRF token"```:

We try again, now we login as ```wiener```, turn on the intercept and we can see a POST request:
<img width="1919" height="905" alt="image" src="https://github.com/user-attachments/assets/b33ca701-a9cf-4ab2-bae4-a3944e3777fc" />

We drop it now, then login as carlos and do this again:
<img width="1919" height="763" alt="image" src="https://github.com/user-attachments/assets/95752c2a-6e86-4a69-9109-d384a8fb4c80" />

We send this POST request to Repeater and go to ```wiener``` again:

We use the carlos's token and fill it in a wiener's POST request:

<img width="1912" height="784" alt="Screenshot 2025-11-14 113857" src="https://github.com/user-attachments/assets/98ea2773-208d-452c-a0a0-abc7ea0cc852" />

<img width="1913" height="912" alt="Screenshot 2025-11-14 113919" src="https://github.com/user-attachments/assets/78c8ec6b-11d0-40f0-8c76-d2bc96d5dbbb" />


Forward the request, and now wiener's email has been changed:

<img width="1903" height="731" alt="image" src="https://github.com/user-attachments/assets/0b540452-a874-4ffe-8078-038eaba47cdc" />

We know that if we use another csrf token from another account, the request has successful, now be generate a fresh one and store in the exploit server:

I use the CSRF PoC generator:

<img width="1027" height="851" alt="image" src="https://github.com/user-attachments/assets/cf8ae5eb-6893-4ee8-926e-f7f516199c45" />


Go to exploit server:

<img width="1906" height="802" alt="image" src="https://github.com/user-attachments/assets/133365d5-23b0-4f2b-bae3-24b773ec4122" />

But we need a new csrf token that has not been use, so we use intercept and get a fresh one: ```r5DgDvuOUCEFSObkLVETZRaPzyGKukvk```


<img width="1903" height="755" alt="image" src="https://github.com/user-attachments/assets/b072f49b-b6f9-48dd-8fd4-1a3f0c9f6263" />

Click deliver exploit to victim:

<img width="1909" height="834" alt="image" src="https://github.com/user-attachments/assets/1944c86d-b369-4f48-8c75-b460dd788220" />

### The lab has been solved 
