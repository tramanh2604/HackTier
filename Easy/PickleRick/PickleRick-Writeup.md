![image](https://github.com/user-attachments/assets/74f32951-839c-4e1e-97f4-8d5c52381527)# Picke Rick

## Overview
- **Difficulty**: Easy
- **Platform**: TryHackMe
- **Link**: [Pickle Rick](https://tryhackme.com/room/picklerick)
- **Goal**: Tìm 3 flag thông qua web exploration và command execution.

## Steps
1. **Reconnaissance**
- Dùng `gobuster` scan target (`10.10.x.x`) để liệt kê các thư mục có tồn tại: `gobuster dir -u http://vulnnet.thm -w /usr/share/wordlists/dirb/common.txt`
![Gobuster Scan](../images/gobuster-scan.PNG)
- Phát hiện được `robots.txt` và `index.html`
  + Trong `robots.txt` tìm được password: `Wubbalubbadubdub`
    ![robots.txt](../images/robots.PNG)
  + Trong `index.html` tìm được username: `R1ckRul3s`
    ![index.html](../images/index.PNG)
    
2. **Login**:
- Truy cập `http://10.10.x.x/login.php`
![login](../images/login.PNG)
- Thử dùng username & password vừa tìm log in vào `login.php` thì thành công.
- Và thấy command pane.
![Command Pane](../images/command-pane.PNG)

3. **Flag Hunting**:
- **Flag 1**:
