---
title: "Một số mẹo với WSL để có nhiều không gian đĩa hơn"
seoTitle: "wsl"
seoDescription: "Giảm kích thước wsl"
datePublished: Fri Nov 08 2024 08:52:36 GMT+0000 (Coordinated Universal Time)
cuid: cm38i0sru000109ldb6bscjwy
slug: mot-so-meo-voi-wsl
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/-blDs_-gLzE/upload/b8d87744820b6d33aac02f154b8bd769.jpeg
tags: wsl, wsl-2

---

Qua một thời gian tự nhiên bạn thấy hết ổ cứng mặc dù không cảm thấy mình làm gì nhiều. Đây là lúc kiểm soát các hệ thống con của mình và đầu tiên là WSL

Bạn luôn có thể truy cập được các file ở trong WSL từ File Explorer của Windows với đường dẫn như sau:

```plaintext
\\wsl$
```

Thường bạn chỉ cần một cái linux cũng đủ mọi việc rồi nhưng thỉnh thoảng cũng tò mò cài thêm. Vì vậy hãy kiểm tra xem mình có quên cái nào không bằng lệnh

```plaintext
 wsl -l -v
```

Bạn có thể dễ dàng uninstall trực tiếp một distrubution ở trên Windows

hyper-v dễ dàng tăng kích thước ổ cứng WSL nhưng lại không có thu hồi nên bình thường thì nó cứ to ra. Bạn có thể tìm ra nó bằng cách vào Powershell, gõ lệnh cd phối hợp với phím Tab để đến được thư mục cần với đường dẫn tương tự như sau

```plaintext
cd C:\Users\[tên username]\AppData\Local\Packages\[tên của linux]\LocalState\
ví dụ vầy:

    Directory: C:\Users\tantran\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu22.04LTS_79rhkp1fndgsc\LocalState

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           11/8/2024    15:51    96224673792 ext4.vhdx
```

Sau đó bạn sẽ chạy lệnh để dồn lại như sau.

```plaintext
optimize-VHD -Path .\ext4.vhdx -Mode Full
```

Nếu may mắn tự nhiên lòi ra mấy Gb trống

Hoặc trước đó bạn có thể kiểm tra xem cái thư mục home của mình có đang có gì nhiều quá có thể xóa không

```plaintext
ncdu ~/
Có thể bạn phải cài ncdu bằng lệnh sudo apt install ncdu trước
```

Bạn sẽ ngạc nhiên về thư mục .local, .cache và .npm lắm nếu như làm các dự án xài npm như mình.