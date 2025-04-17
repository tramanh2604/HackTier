# Reflected XSS - HTML Tags Context - Easy Labs (PortSwigger)

## Lab 1: Reflected XSS into HTML context with nothing encoded
### Steps
- Search box hiện ngay đầu trang web
- Nhập payload `<script>alert(1)</script>` vào search box.
- Nhấn submit để kiểm tra XSS.

### Findings
- Payload: `<script>alert(1)</script>`
- Result: Pop-up alert "1" => Xác nhận XSS vuln, không cần mã hóa input.
![Lab 1 - Result](images/xss_reflected_html_noencode.PNG)

## Lab 2: Stored XSS into HTML context with nothing encoded
### Steps
- Ấn vào post bất kỳ trên blog, kéo xuống cuối bài viết để tìm comment form.
- Nhập payload `<img src=x onerror=alert(1)>`
- Nhấn submit để gửi comment và reload page để kiểm tra lỗi Stored XSS.

### Findings
- Payload: `<img src=x onerror=alert(1)>`
- Result: Pop-up alert"1" sau khi reload => Xác nhận lỗi Stored XSS .
![Lab 2 - Result](images/stored_xss_html_tags_easy.PNG)

## Impact (Common for all Easy labs)
- Có thể trộm cookie hoặc thực thi mã độc JS.

## Recommendations (Common for all Easy labs)
- Lọc input (`<`, `>`).
