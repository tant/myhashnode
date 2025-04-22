---
title: "Cài erpnext 14 lên ubuntu server"
datePublished: Tue Nov 15 2022 12:10:56 GMT+0000 (Coordinated Universal Time)
cuid: clai6b3ke000008l38wnqc8qu
slug: cai-erpnext-14-len-ubuntu-server
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1669043268312/yTTN22VqR.png
tags: erp

---

Bài này để lưu lại cách cài erpnext v14 vào giữa tháng 11/2022. Mình viết theo từng gói cài một lượt trên một cái ubuntu server cài theo kiểu minimal (chỉ cài thêm nala) để tiện copy paste thôi chứ không giúp hiểu hệ thống. Để ý version của mọi thứ phải match thì khả năng mới không gặp issue

Tiện đây nhắc luôn là version 13 sẽ là lựa chọn tối ưu hơn để học vì khi cài bạn sẽ không thấy nhiều warning hay error xuất hiện như version 14. Mọi thứ đều giống trừ việc bạn sẽ dùng nodejs phiên bản 14 (v14.21.1) và sau khi cài xong thì nhớ update Snyk cli cái nha (thời điểm giữa tháng 11)

## (Tùy chọn) dùng một user khác để cài trong môi trường Production
Nếu như cài cho môi trường Production thì nên thực hiện bước này, còn không thì bỏ qua 
```
sudo adduser [tên user]
sudo usermod -aG sudo [tên user]
su - [tên user]
```
## Cài package cần thiết 
Đây là các gói cần dùng và có thể cài nhanh bằng apt (không cần chỉnh sửa)
```
sudo nala install -y nano git python3-dev python3-setuptools  python3-pip python3-venv redis-server cron nginx xvfb libfontconfig wkhtmltopdf apt-transport-https curl libmysqlclient-dev 
``` 
- python 3.10 : 3.10.6-1~22.04
- nano
- git
- python3-dev: 3.10.6-1~22.04
- python3-setuptools : 59.6.0-1.2
- python3-pip : 22.0.2+dfsg-1
- python3-venv : 3.10.6-1~22.04
- redis-server: 5:6.0.16-1ubuntu1
- cron : 3.0pl1-137ubuntu3
- nginx : 1.18.0-6ubuntu14.3
- xvfb : 2:21.1.3-2ubuntu2.2
- libfontconfig 
- wkhtmltopdf: 0.12.6-2
- libmysqlclient-dev (thử thay mysql-common) : 8.0.31-0ubuntu0.22.04.1
- apt-transport-https : 2.4.8
- curl : 7.81.0-1ubuntu1.6

## Cài nodejs 16.18.1 và yarn
Cài nvm (0.39.2) bằng lệnh dưới
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
```
Sau khi chạy xong thì đóng terminal mở lại để nạp lại PATH hoặc chạy lệnh source ./.bashrc (nếu đang dùng bash). Đảm bảo thấy nvm -v chạy 
```
nvm install v16.18.1
```
Lệnh này sẽ cài nodejs cùng với npm đi kèm nhưng bạn sẽ nâng npm (9.1.1) lên luôn chứ không lát lại thấy warning xong cài yarn luôn
```
npm install -g npm@latest
npm install -g yarn
```

## Cài MariaDB 10.9 (1:10.9.4+maria~ubu2204)
Dùng link https://downloads.mariadb.org/mariadb/repositories/#mirror=piconets để chọn nhưng đừng xài cái của việt nam nha, bị thiếu release báo lỗi hơi phiền. Và nhớ dùng bản 10.9 vì bản 10.10 bị lỗi setting mà không biết sửa sao.

Hoặc xài lệnh bên dưới luôn để set source
```
sudo curl -o /etc/apt/trusted.gpg.d/mariadb_release_signing_key.asc 'https://mariadb.org/mariadb_release_signing_key.asc'
sudo sh -c "echo 'deb https://mirrors.xtom.com/mariadb/repo/10.9/ubuntu jammy main' >>/etc/apt/sources.list"
```
Sau đó cài bình thường 
```
sudo nala update
sudo nala install -y mariadb-server
```
Xong thiết lập mariadb, ở bước này nhớ ghi xuống mật khẩu để lát nữa khỏi lộn
```
sudo mysql_secure_installation
```
Rồi thì sửa lại file config để support Unicode
```
sudo nano /etc/mysql/my.cnf
```
Thêm đoạn này vào cuối file
```
[mysqld]
character-set-client-handshake = FALSE
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci

[mysql]
default-character-set = utf8mb4
```
Cuối cùng restart service là xong
```
sudo service mysql restart
```
## Cài bench (5.14.4) và init một phiên bản frappe v14
Từ đoạn init bench trở đi sẽ hơi khó khăn 1 chút vì chủ yếu là sẽ get xong chạy các script rất dài, có thể can thiệp vào database nữa nên coi kĩ thông báo lỗi để làm một lần trúng luôn là tốt nhất
```
pip3 install frappe-bench
bench --version
bench init mybench --frappe-branch version-14
```
Đoạn cài bench sẽ có mấy cái warning liên quan đến honcho, chưa thấy ảnh hưởng lắm vì trong môi trường venv sẽ có bản honcho riêng
```
WARNING: The script honcho is installed in '/home/tantran/.local/bin' which is not on PATH.
```
Đoạn cài frappe sẽ có báo deprecation thì cứ kệ nha, chắc từ từ sẽ dc fix và chưa thấy ảnh hưởng
```
DEPRECATION: zxcvbn-python is being installed using the legacy 'setup.py install' method,
```
Lúc chạy yarn có một số báo lỗi
```
[4/5] Linking dependencies...
warning " > @frappe/esbuild-plugin-postcss2@0.1.3" has unmet peer dependency "less@^4.x".
warning " > @frappe/esbuild-plugin-postcss2@0.1.3" has unmet peer dependency "stylus@^0.x".
warning Workspaces can only be enabled in private projects.
```
Lúc bench build có
```
$ bench build
Assets for Release v14.15.0 don't exist
✔ Application Assets Linked
```
Cuối cùng có warn nhưng kệ luôn vì đâu có biết làm gì
```
WARN  Cannot connect to redis_cache to update assets_json
```

# Từ khúc này làm việc trong thư mục frappe bench mới tạo thôi 
Không chạy lệnh bech ở thư mục ngoài, bị lỗi ráng chịu
```
$ cd mybench/
```

# Cài erpnext v14 vào bench 
Tải erpnext 14 đó về bench nhưng trước đó nhớ cài payments nếu không sẽ báo lỗi
```
bench get-app payments
bench get-app erpnext --branch version-14
```
Lựa chọn bỏ thêm --resolve-deps cũng có thể giúp nhưng kinh nghiệm cho thấy cài tay an toàn hơn

Erpnextv13 thì không cần cài payments 

## Tạo site và nhớ update current site nha

Tạo một site theo ý bạn, giả sử là tantran.dev
```
bench new-site tantran.dev
```

Chuyển qua site này hoặc là vào thư mục con sites tạo 1 file currentsite.txt có nội dung là tên site 
```
bench use tantran.dev
```

Cài app đó vào site tantran.dev
```
bench --site tantran.dev install-app erpnext
```

Và cuối cùng là 
```
bench start
```
Lưu ý bạn hãy để thời gian lâu lâu chút để mọi thứ được chạy xong, update các kiểu rồi hẵng vào và sau đó hãy theo dõi màn hình log để phát hiện vấn đề ở đâu mà tìm cách khắc phục

## Các chú ý
### Nếu dùng máy ảo
Thêm dòng 'vm.overcommit_memory = 1' vào file  /etc/sysctl.conf
hoặc chạy lệnh 
```
sudo sysctl vm.overcommit_memory=1
```

### Rollback site
Trong quá trình setup site nếu xảy ra bất kì vấn đề gì gì bạn chỉ việc remove site bằng cách tự động như sau
```
bench drop-site tantran.dev --force 
```
Hoặc thủ công là xóa thư mục site sau đó vào mariadb xóa database đó nếu phương án tự động không thành công

### Chạy wizard setup firsttime
Lựa chọn các nước lớn, phổ biến lúc chạy wizard vì các bạn dev quên mất cấu hình Chart of accounts cho Việt Nam nên khi chạy tới bước 4 5 sẽ ra lỗi và hỏng site
Work around là chọn luôn IN luôn nhưng timezone chọn VN và tiền tệ thì chọn VND thì mọi thứ sẽ trơn tru tới cuối cùng 

### Lên pro
