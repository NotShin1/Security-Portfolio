## Lab Description :
<img width="1380" height="647" alt="Screenshot 2025-11-11 113629" src="https://github.com/user-attachments/assets/7fcfe548-4754-48ed-bca9-7893139f7ec6" />

## Solution :
This lab has a stock feature with fetches data from an internal server, when we use this to check the stock:

<img width="1901" height="917" alt="Screenshot 2025-11-11 114326" src="https://github.com/user-attachments/assets/3c0067f4-ca88-439e-9c22-4bf73bb05338" />

The HTTP Request will return like:
```
stockApi=http://stock.weliketoshop.net:8080/product/stock/check?productId=2&storeId=2
```


<img width="673" height="503" alt="Screenshot 2025-11-11 114405" src="https://github.com/user-attachments/assets/3684ba7d-68ca-4c23-9e2f-65769cb34d70" />

We try to redirect the API to the admin panel from localhost:
```
stockApi=http://localhost/admin
```

<img width="650" height="496" alt="Screenshot 2025-11-11 114449" src="https://github.com/user-attachments/assets/0c7f0873-07c9-496c-9673-3742ccdae0ef" />

The server will response:

<img width="660" height="563" alt="Screenshot 2025-11-11 115127" src="https://github.com/user-attachments/assets/751b2300-2748-4f23-b744-fe8ea5cf2784" />

We successfully accessed the admin control panel
Then, we use the delete parameter to delete user ```Carlos```:

<img width="1324" height="507" alt="Screenshot 2025-11-11 114603" src="https://github.com/user-attachments/assets/0614e98c-b752-4b60-9a54-c5ee0dab4b13" />

The server will response successfully
The lab has been solved

<img width="654" height="569" alt="Screenshot 2025-11-11 115340" src="https://github.com/user-attachments/assets/29ec61cd-4dea-4638-9f1c-0d0e49cd00b6" />
