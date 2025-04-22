---
title: "Giờ chạy sai khi dual boot windows và linux"
datePublished: Mon Sep 25 2023 12:16:48 GMT+0000 (Coordinated Universal Time)
cuid: clmyus4k7000309ibb4lf9i2o
slug: gio-chay-sai-khi-dual-boot-windows-va-linux
tags: dual-booting

---

Tự nhiên có dư máy tôi quyết định cài thử dual boot xem sao để trải nghiệm môi trường phát triển hai bên cùng lúc xem sao. Đến giờ này, tháng 3/2023 mà mình vẫn cảm giác docker trên windows thuận tiện hơn vì cứ chạy trên linux là bị dính tới phân quyền.

Một cái máy chạy hai hệ điều hành khác biệt như linux và windows có chút trục trặc như giờ trên máy bị đổi khi mình chuyển từ OS này sang OS kia. Bình thường mình cũng chả quan tâm lắm cho tới khi phải cài wsl trên windows để code và một số tool không chạy như apt.

Cốt lõi vấn đề là đồng hồ trong BIOS của máy bị hai hệ điều hành can thiệp khác nhau. Linux thì dùng giờ UTC cho nên khi boot vào thì linux sẽ đổi giờ BIOS thành giờ UTC. Sau đó đến Windows đang dùng múi giờ +7 (timezone VN) cho nên lại lệch giờ.

Cách xử lý tốt nhất là vào Linux chỉnh lại dùng local time thay vì sys time(giờ UTC) bằng cách vào terminal

```bash
sudo timedatectl set-local rtc 1
```

Nếu muốn thay đổi lại như cũ thì thay số 1 bằng số 0 thôi.