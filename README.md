x.tìm subdomainb:https://github.com/findomain/findomain
```apt update
git clone https://github.com/findomain/findomain.git
cd findomain
cargo build --release
sudo cp target/release/findomain /usr/bin/
findomain
findomain -t dienmayxanhbantragop.com
```
<img width="845" height="736" alt="image" src="https://github.com/user-attachments/assets/6a7e56d4-24b0-4a10-9f04-0dd872ff801a" />

-> truy vấn qua nhiều API như: Archive.org, CertSpotter, Sublist3r, CrT.sh, Threatcrowd, AnubisDB, Threatminer, Urlscan.io và tìm thấy 8 subdomain gồm: webmail.dienmayxanhbantragop.com	Dịch vụ email
cpanel.dienmayxanhbantragop.com, mail.dienmayxanhbantragop.com, autodiscover.dienmayxanhbantragop.com, sieuthixedapdien.dienmayxanhbantragop.com, muabanhadathm.dienmayxanhbantragop.com, webdisk.dienmayxanhbantragop.com, linkhiensi.vn.dienmayxanhbantragop.com.

---

# 3.4.2 : Wayback Machine robots.txt directory
```
git clone https://github.com/NTKien-ptitt/Exploit-_Paths_Website.git
 python3 ./Robot_Arrchive_Web.py dienmayxanhbantragop.com
```

<img width="1083" height="241" alt="image" src="https://github.com/user-attachments/assets/b42cb90f-7130-47d7-a3ce-713f2e391f45" />

-> đang kiểm tra robots.txt của website này trên Wayback Machine (web.archive.org) để tìm các đường dẫn mà có thể đã từng bị chặn hoặc được liệt kê trong quá khứ.hai đường dẫn đã từng xuất hiện trong file robots.txt là dienmayxanhbantragop.com/administrator/ dienmayxanhbantragop.com/cgi-bin/
---

---
# 4.4 Osmedeus
GitHub: https://github.com/j3ssie/Osmedeus
```
bash <(curl -fsSL https://raw.githubusercontent.com/osmedeus/osmedeus-base/master/install.sh)
go install -v github.com/j3ssie/osmedeus@latest

osmedeus scan -f vuln -t example.com           # Scan lỗ hổng
osmedeus scan -f extensive -t example.com      # Quét sâu và toàn diện
```

