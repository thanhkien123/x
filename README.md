nmap -p - -T4 -A -v -Pn --unprivileged --script vuln dienmayxanhbantragop.com


Dưới đây là định dạng lại thông tin từ hình ảnh thành bảng theo yêu cầu:

| **Port**  | **Trạng thái** | **Dịch vụ**          | **Thông tin**                                                                 | **Bảo mật**                  |
|-----------|----------------|----------------------|-------------------------------------------------------------------------------|-------------------------------|
| **80/tcp** | Open           | HTTP (LiteSpeed)     | Web server LiteSpeed. Chạy các lệnh `/cgi-sys/defaultwebpage.cgi`. Hỗ trợ GET, POST, HEAD, OPTIONS. Không hỗ trợ RTSP. | Không phát hiện XSS, CSRF. Script kiểm tra không tìm thấy lỗi trong thời gian gần đây. |
| **110/tcp**| Open           | POP3 (Dovecot)       | Dịch vụ nhận email bằng POP3.                                              | Không phát hiện lỗi.         |
| **143/tcp**| Open           | IMAP (Dovecot)       | Dịch vụ đọc email IMAP.                                                   | Không phát hiện lỗi.         |
| **443/tcp**| Open           | HTTPS (LiteSpeed)    | Giống port 80, nhưng sử dụng SSL/TLS.                                       | Không phát hiện lỗi. Test ssl-ccs-injection bị timeout. |
| **465/tcp**| Open           | SMTPS (Unknown)      | SMTP qua SSL/TLS. Hệ thống "Mail Secure System". Hỗ trợ AUTH, PIPELINING, gửi mail lớn (50MB). | Không phát hiện lỗi.         |
| **587/tcp**| Open           | SMTP (Unknown)       | SMTP dành cho client gửi mail. Giống port 465, thêm hỗ trợ STARTTLS.         | Không bị CVE-2010-4344.      |
| **993/tcp**| Open           | IMAPS (Unknown)      | IMAP qua SSL/TLS. Có thể là Dovecot.                                        | Không phát hiện lỗi.         |
| **995/tcp**| Open           | POP3S (Unknown)      | POP3 qua SSL/TLS. Có thể là Dovecot.                                        | Không phát hiện lỗi.         |

### Ghi chú:
- Bảng trên được xây dựng dựa trên dữ liệu từ hình ảnh, với các cột được sắp xếp lại để rõ ràng và đồng nhất.
- Thông tin bảo mật phản ánh các kết quả kiểm tra được cung cấp, bao gồm cả các lỗi không phát hiện được hoặc timeout trong quá trình kiểm tra.
- Nếu cần phân tích chi tiết hơn hoặc bổ sung thông tin, hãy cho tôi biết!                                                                            |

<img width="1098" height="507" alt="image" src="https://github.com/user-attachments/assets/d5bbc504-7daa-4551-a31f-1ccf4485ef97" />

---
# SNIPER
# 1. sniper -t muabannhadatmh.dienmayxanhbantragop.com 
Sau khi quá trình recon va scanning hoàn tất, thông tin lưu tại /usr/share/sniper/loot/workspace/dienmayxanhbantragop.com và kết quả scanning lưu tại thư mục "vulnerabilities"
 cho biết có Critical: 0, High: 0, Medium: 0, Low (P4): 1 – Liên quan đến HTTP Security Header, Informational (P5): 2 – Cần theo dõi nhưng chưa phải lỗ hổng trực tiếp.

<img width="953" height="522" alt="image" src="https://github.com/user-attachments/assets/1ec154cb-d099-471f-b1e5-5a73ec2adb7a" />


# 2. sniper -t dienmayxanhbantragop.com 
Sau khi quá trình recon va scanning hoàn tất, thông tin lưu tại /usr/share/sniper/loot/workspace/dienmayxanhbantragop.com và kết quả scanning lưu tại thư mục "vulnerabilities"
 cho biết có Critical: 0, High: 0, Medium: 0, Low (P4): 1 – Liên quan đến HTTP Security Header, Informational (P5): 2 – Cần theo dõi nhưng chưa phải lỗ hổng trực tiếp.
 <img width="833" height="526" alt="image" src="https://github.com/user-attachments/assets/0dfdfbc6-e850-4226-a09d-ba81aed9e33f" />

# AMASS
# 1. amass enum -d dienmayxanhbantragop.com

<img width="684" height="150" alt="image" src="https://github.com/user-attachments/assets/d7d4fe52-e4ed-4e9d-9caa-570903b8922e" />

Tên miền hoạt động bình thường và có bản ghi NS hợp lệ trỏ về cụm DNS của nina.vn.

Không phát hiện subdomain nào khác (ở chế độ mặc định).
# 2. amass enum -d muabannhadatmh.dienmayxanhbantragop.com

<img width="531" height="93" alt="image" src="https://github.com/user-attachments/assets/e7e233e1-56b3-4bfc-88b8-884b56131b37" />

Subdomain không tồn tại trên DNS công khai
----------danh gia



Bu đã cung cấp đủ dữ liệu, dưới đây là **bảng đánh giá đầy đủ, chuyên nghiệp** theo đúng format báo cáo pentest. Bu giữ nguyên nội dung gốc nhưng trình bày dạng bảng, phân chia theo công cụ, mục tiêu, kết quả và nhận định rõ ràng:

---

## 📊 BẢNG ĐÁNH GIÁ KẾT QUẢ PENTEST – `dienmayxanhbantragop.com`

| STT | Công cụ sử dụng | Mục tiêu                                  | Thư mục kết quả                                                            | Kết quả phân tích                                                                                                                                                                        | Nhận định                                                                                                                     |
| --- | --------------- | ----------------------------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| 1 | `Sn1per`        | `muabannhadatmh.dienmayxanhbantragop.com` | `/usr/share/sniper/loot/workspace/muabannhadatmh.dienmayxanhbantragop.com` |  Critical: 0<br> High: 0<br> Medium: 0<br> Low (P4): 1 – Liên quan đến **HTTP Security Header**<br> Informational (P5): 2 – **Cần theo dõi nhưng chưa phải lỗ hổng trực tiếp** | Hệ thống bảo mật trung bình. Chưa có lỗ hổng nghiêm trọng nhưng cần cải thiện cấu hình HTTP Header và theo dõi service bị lộ. |
| 2 | `Sn1per`        | `dienmayxanhbantragop.com`                | `/usr/share/sniper/loot/workspace/dienmayxanhbantragop.com`                |  Critical: 0<br> High: 0<br> Medium: 0<br> Low (P4): 1 – HTTP Security Header<br> Informational (P5): 2 – Port 21 mở, và disclosure `LiteSpeed`                                | Mức độ tương tự như trên, hệ thống cần ẩn thông tin máy chủ và kiểm tra cổng FTP.                                             |
| 3 | `Amass enum`    | `dienmayxanhbantragop.com`                | (Không lưu ra file, chạy trên CLI)                                         | Phát hiện 3 bản ghi `NS`:<br> ns1.nina.vn<br> ns2.nina.vn<br> ns3.nina.vn                                                                                                          | Tên miền đang hoạt động tốt, DNS cấu hình hợp lệ. Không tìm thấy subdomain ở chế độ mặc định.                                 |
| 4 | `Amass enum`    | `muabannhadatmh.dienmayxanhbantragop.com` | –                                                                          |  No assets were discovered                                                                                                                                                              | Subdomain không tồn 
