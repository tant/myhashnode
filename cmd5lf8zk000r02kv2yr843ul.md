---
title: "Host web trên vercel"
datePublished: Wed Jul 16 2025 06:41:34 GMT+0000 (Coordinated Universal Time)
cuid: cmd5lf8zk000r02kv2yr843ul
slug: host-web-tren-vercel
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/zs98a0DtKL4/upload/a863978ad0ab40b2f93d9c4e669972f1.jpeg

---

Khi chọn domain cho vercel bạn có 2 lựa chọn

1. Chọn url chính là www hay là non www
    
2. Chọn kiểu redirect nào
    

Hãy xem xét vấn đề này với quan điểm của SEO và cụ thể là công cụ google search console nha.

# URL chính

Về mặt SEO thì www hay non-www đều không có khác biệt cũng như có sự ưu tiên gì đặc biệt. Nhưng về mặt kỹ thuật thì nên chọn www cho phiên bản canonical hơn.

Điều quan trọng nhất là sự nhất quán, tất cả các thiết lập của bạn cần phải dùng một url thôi, đừng lẫn lộn hai cái mặc dù sau khi thiết lập redirect xong thì url nào cũng hoạt động

Việc sử dụng www còn cung cấp một sự linh hoạt do www là một sub domain nên dễ xử lý hơn các kĩ thuật liên quan như cdn và hosting và cookie mà không ảnh hưởng tới các tên subdomain khác.

Nếu bạn sử dụng root (non-www) thì tuy tên miền ngắn hơn nhưng lại khó quản lý hơn do thiết lập sẽ ảnh hưởng tới tất cả các subdomain

# Kiểu Redirect

Có 4 code là 301, 302, 307 và 308 thì trong đó hãy quên 302 và 207 vì đây là redirect tạm thời và Google sẽ cập nhật tất cả các index phù hợp.

Vậy chỉ còn 301 và 308 thì 301 là lựa chọn tốt nhất vì nó là tiêu chuẩn đã vận hành từ trước đến nay và trường hợp các webite landing page, ưu tiên SEO thì 301 cho an toàn. 308 sẽ dùng cho các API hay web service tốt hơn