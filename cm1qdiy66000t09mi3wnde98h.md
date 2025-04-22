---
title: "Sao lưu nội bộ (local backup) vẫn hay"
datePublished: Tue Oct 01 2024 11:47:12 GMT+0000 (Coordinated Universal Time)
cuid: cm1qdiy66000t09mi3wnde98h
slug: sao-luu-noi-bo-local-backup-van-hay
tags: backup, luu-tru

---

Cloud backup hay là sao lưu qua các dịch vụ cloud quá tiện không thể chối cãi. Vậy tại sao còn luẩn quẩn với công nghệ của 10 năm trước. Và đây là các lý do..

# Cloud backup cũng không phải hay nhất

Có hơn 2 tỉ người dùng trong các dịch vụ lưu trữ và vẫn đang tăng trưởng trong ngành công nghiệp được đánh giá 200 tỉ USD này. Sự phổ cập này không phải là điều lạ vì nó quá tiện dụng và làm cuộc sống chúng ta dễ dàng hơn

Tuy nhiên có những vấn đề mà khi gặp mới biết. Đó là

* Bạn vẫn có thể mất trắng dữ liệu
    
* Bạn vẫn có thể bị hack và thất thoát dữ liệu
    
* Một ai đó có thể ngẫu nhiên truy cập dữ liệu của bạn
    
* Thỉnh thoảng bạn cũng không thể truy cập được dữ liệu
    

Nghiêm trọng nhất là một ngày đẹp trời, nhà cung cấp quyết định ngừng dịch vụ của bạn và xóa tài khoản. Thế là không cần biết ít hay nhiều, bạn chỉ còn 0 byte dữ liệu vì bạn đã giao hết cho nhà cung cấp.

Vẫn chưa hết, quyền riêng tư với dữ liệu không do bạn quản lý. Một ngày nào đó bạn nhận ra file mình đã xóa nó vẫn còn ở đó

Cuối cùng, đó là chi phí của các plan kiểu như hàng năm thì Google Drive sẽ thu $100 để lưu giữ giúp bạn 2Tb, iCloud thì sang chảnh hơn khoảng $130 cho 2Tb. Đây có thể xem là nợ vì bạn phải trả trước, và nếu bạn không trả tiền thì dữ liệu của bạn sẽ thành hư không

# Local backup cũng không bất tiện như bạn nghĩ

Nếu bạn yêu thích sự tự do có thể kiểm soát toàn bộ dữ liệu của mình và tự chịu trách nhiệm với chúng thì thật ra công nghệ đã cho phép chúng ta có thể tự sao lưu dễ dàng hơn rất nhiều so với trước và giá của thiết bị cũng rẻ hơn xưa nhiều

* Không phải nộp tiền trước đều đặn
    
* Gần như không có giới hạn lưu trữ (miễn bạn còn tiền mua ổ cứng)
    
* Tốc độ sao lưu có thể cực nhanh (bạn thấy tốc độ chép 1-2Gb một giây chưa?)
    

Và bạn sẽ có vài lựa chọn cho việc này:

## NAS (Network Attached Storage)

Đây là giải pháp lưu trữ mạng nên nếu kết hợp với một số kỹ năng thiết lập hệ thống mạng, bạn sẽ có giải pháp tương đương với cloud storage với quyền riêng tư của mình và mọi thứ do mình quyết định như dung lượng bằng cách mua thêm ổ cứng, tốc độ bằng cách chọn đường truyền mạng nhanh hơn…

Không chỉ vậy, bạn có thể tự build từ đầu hay là mua 1 giải pháp sẵn từ Synology, QNAP… hay đơn giản là tận dụng cái PC cũ của mình để thiết lập

## Ổ cứng ngoài (External Storage)

Giải pháp này cũng đa dạng từ thẻ nhớ, thanh usb, ổ cứng ngoài và cái gì cũng có giá của nó. Đánh giá nhanh các loại như sau

* Usb có tốc độ chậm nhất, do mục tiêu phục vụ của mảng này là chỉ để lưu trữ backup nên tốc độ đọc ghi chỉ tương đối. Bạn sẽ cảm thấy sống chậm khi dùng nó chép dữ liệu vào, tốc độ đọc thì đỡ hơn. Hãy chọn USB 3.0 trở lên nha, dưới đó cho dù có rẻ thì cũng không đáng
    
* Thẻ nhớ có tốc độ cao hơn nhưng phụ thuộc vào đầu đọc, các loại thẻ cao cấp có tốc độ tương đối cao. Thẻ nhớ có điểm cộng là có thể dùng cho các thiết bị khác như máy ảnh, drone, hay cái board raspberry pi của bạn
    
* Ổ cứng ngoài thì đa dạng, nó có thể là HDD dùng từ tính hồi xưa cho tới ssd với các giao thức tốc độ cao lên tới 40Gbps
    

Lưu ý là những thiết bị này có thể hư và mất dữ liệu vì thường không có phương án backup.