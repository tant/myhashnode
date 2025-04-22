---
title: "Giải quyết hàng ký gửi"
datePublished: Mon Nov 21 2022 14:11:12 GMT+0000 (Coordinated Universal Time)
cuid: claqv8w66000708l7dbawdu6q
slug: giai-quyet-hang-ky-gui
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1669040584897/3daTl9E3-.jpg
tags: erp

---

# Giao dịch ký gửi (consignment) 
Là loại giao dịch chỉ phát sinh chi phí vận chuyển nhưng không phát sinh doanh số nghĩa là bên B vận chuyển hàng vào kho bên A để bên A nhưng quyền sở hữu hàng vẫn thuộc về bên B cho tới khi bên A hoàn thành thanh toán.

Để dễ hiểu thì với giao dịch mua bán, khi A nhận 1 món hàng X giá 1 triệu thì A sẽ giảm số tiền 1 triệu để trả tiền cho B đồng thời trong kho A tăng lên 1 đơn vị hàng tồn kho và hai bên không phát sinh nợ 

Còn với giao dịch ký gửi, A nhận được 1 món hàng X trị giá 1 triệu thì A sẽ tăng 1 đơn vị hàng tồn kho lên lên và A nợ B 1 món hàng đó (hoặc 1 triệu đồng) để sau này có thể trả lại hàng hay trả lại tiền đều được.

Do vậy phải ghi nhận chính xác hàng hóa X đó cái nào là ký gửi cái nào là mua đứt để ghi nhận bút toán cho đúng.

# Tư vấn
Các hệ thống ERP tiêu chuẩn sẽ không xử lý tình huống này theo kiểu mô tả đây là một món hàng kí gửi hay đây là một món hàng mua đứt mà nhà tư vấn sẽ tạo cho A 2 kho (warehouse) là kho bình thường với kho hàng kí gửi

- Khi nhập hàng kí gửi thì món X đó được ghi nhận vào kho hàng kí gửi
- Khi nhập hàng mua đứt thì món X đó được ghi nhận vào kho hàng bình thường

Và đồng thời nhà tư vấn sẽ tạo một kho ảo (cái này rất bình thường trong erp) là gộp của các kho này lại để đếm số lượng hàng tổng hoặc thực hiện các công tác tính giá vốn, giá bán....
