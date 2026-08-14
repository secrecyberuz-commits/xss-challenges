# Level 1 – Hello, World of XSS

## Zaiflik turi: Reflected XSS

Ushbu darajada source code tahlil qilinib, XSS zaifligi aniqlandi.

Payload: 

``` <script>alert("XSS")</script> ```

Payload yuborilganda, input hech qanday escaping qilinmasdan HTML kod sifatida qaytarildi. Natijada brauzer JavaScript kodini bajarib, alert("XSS") oynasini chiqardi.

![XSS Challanges](./images/01-xss.png)

# Level 2 

## Zaiflik turi: Stored XSS

Ushbu darajada source code tahlil qilinib, foydalanuvchi kiritgan ma'lumot `innerHTML` orqali sahifaga joylashtirilishi aniqlandi.

Kodning zaif qismi:

```
var html = "<blockquote>" + posts[i].message + "</blockquote>";
containerEl.innerHTML += html;
```
Bu yerda `posts[i].message` foydalanuvchi tomonidan boshqariladi va `innerHTML` orqali HTML sifatida qayta ishlanadi.

Avval ushbu payload sinab ko'rildi: 
``` <script>alert("XSS")</script> ```
<script> ishlamagani sababli onerror event handleridan foydalanildi:
``` <img src=x onerror=alert()> ```

![XSS Challanges](./images/02-xss.png)

Payload yuborilgandan keyin post saqlandi, page ga qayta kirganda "alert()" chiqdi.

# Level 3 







