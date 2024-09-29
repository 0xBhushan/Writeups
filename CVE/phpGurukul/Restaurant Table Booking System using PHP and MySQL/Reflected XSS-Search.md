## Vulnerability Description

Reflected Cross-Site Scripting (XSS) vulnerability was found in the //check-status.phptus.php of the 	Restaurant Table Booking System using PHP and MySQL V. This vulnerability allows remote attackers to execute arbitrary scripts via the searchkey parameter in a POST HTTP request.

| Field                                   | Details                                                                                              |
|-----------------------------------------|------------------------------------------------------------------------------------------------------|
| Affected Vendor                         | PHPGurukul                                                                                           |
| Affected Product Name                   |Restaurant Table Booking System using PHP and MySQL                               |
| Product Official Website URL            | [https://phpgurukul.com/restaurant-table-booking-system-using-php-and-mysql/](https://phpgurukul.com/restaurant-table-booking-system-using-php-and-mysql/) |
| Affected Components                     | - Version: V 1.0 <br>- Affected Code File: /check-status.php <br>- Affected Parameter: searchdata <br>- Method: POST |

## Steps to Reproduce:

**Step 1:** Click on Check Booking Status

![image-1](https://github.com/user-attachments/assets/c7a5b565-59c3-4519-8e16-72699ca2e9db)

**Step 2:** In search bar, provide values ```<script>alert(1)</script>``` and enable burpsuite to confirm the parameter.

![image-4](https://github.com/user-attachments/assets/25ea8958-473a-4152-9b1a-57bc6f159682)

**Step 3:** Observe that the payload is the ```searchdata``` parameter. Now proceed to forward the request.

![image-2](https://github.com/user-attachments/assets/580b875b-e945-421f-8080-14188b9d5608)

Step 4: After forwarding the request, observe in the browser that the payload is executed, resulting in a popup.

![image-3](https://github.com/user-attachments/assets/1fe6bc0d-ad8d-471e-a2d5-913c29852112)



## Mitigation/recommendations
- https://portswigger.net/web-security/cross-site-scripting
- https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html
