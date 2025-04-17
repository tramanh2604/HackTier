# Reflected XSS - Easy Labs (PortSwigger)

## Lab 1: Reflected XSS into HTML context with nothing encoded
### Steps
- Search box hiện ngay đầu trang web
- Nhập payload `<script>alert(1)</script>` vào search box.
- Nhấn submit để kiểm tra XSS.

### Findings
- Payload: `<script>alert(1)</script>`
- Result: Pop-up alert "1" => Xác nhận XSS vuln, không cần mã hóa input.
![Lab 1 - Result](images/xss_reflected_html_noencode.PNG)

## Impact (Common for all Easy labs)
- Có thể trộm cookie hoặc thực thi mã độc JS.

## Recommendations (Common for all Easy labs)
- Lọc input (`<`, `>`).
