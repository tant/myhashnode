---
title: "Mọi thứ đều bắt đầu từ firebase"
datePublished: Sun Nov 20 2022 11:23:03 GMT+0000 (Coordinated Universal Time)
cuid: clap9ssds000808l8gim52h8y
slug: moi-thu-deu-bat-dau-tu-firebase
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1669040794349/u4v3kf2v-.png

---

# Firebase sẵn sàng rồi làm gì làm

## Tạo firebase project 
Vào console.firebase.google.com chọn Add project rồi làm theo wizard của firebase. Theo suy nghĩ của mình thì cứ enable hết lên thử xài cho biết.

- Enable Google Analytics (chọn tạo tài khoản mới )

## Enable Authentication
Trong mục category bên trái chọn Build/Authentication/Sign-in method, 

Vào enable Anonymous và Email Authentication

Cho dù app của bạn dự tính sẽ dùng tài khoản để authen thì cũng nên enable Anonymous vì mình sẽ cho user vào app trải nghiệm trước khi login. Tài khoản Anonymous cho phép chúng ta quản lý state/tracking... của user trước khi họ sign in bằng account của họ

## Create database
Cũng trong category bên trái chọn Build/Firestore Database. Sau đó chọn Create database rồi cứ theo wizard của firestore
- Lưu ý chọn Cloud Firestore location cho gần nơi các user của app là tốt nhất, hiện giờ thấy chắc phải chọn Singapore

## Set Default GCP resource location 
Bên trái, trên, chổ Project Overview có cái bánh răng, click vào chọn Project settings
Tìm Default GCP resource location click vào cây bút rồi click vào Done ở màn hình popup lên thôi vì mình đã chọn firestore location rồi nên nó fixed luôn không thay đổi được nữa

Tuy nhiên không làm bước này thì lúc flutterflow apply rule hay manage content sẽ bị lỗi

## Thêm quyền cho flutterflow
 