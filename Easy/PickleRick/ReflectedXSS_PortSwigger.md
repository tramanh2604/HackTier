# Reflected XSS - Easy Labs (PortSwigger)

## Lab 1: Reflected XSS into HTML context with nothing encoded
- Payload: `<script>alert(1)</script>`
- Result: Pop-up alert "1" => Xác nhận XSS vuln.
![Lab 1 - Result](images/xss_reflected_html_noencode.PNG)
