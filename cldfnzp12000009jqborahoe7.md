---
title: "Wi-Fi là gì"
datePublished: Sat Jan 28 2023 08:01:45 GMT+0000 (Coordinated Universal Time)
cuid: cldfnzp12000009jqborahoe7
slug: wi-fi-la-gi
tags: network, wifi, wireless-network

---

Wi-Fi là một bộ các giao thức mạng không dây dựa trên bộ tiêu chuẩn 802.11 của IEEE cho phép các thiết bị kết nối không dây với nhau bằng sóng điện từ

Hiểu đơn giản thì nó cho phép kết nối các thiết không cần dùng dây nối như là mạng có dây và Wi-Fi chỉ là một phần mở rộng của mạng có dây đã phổ biến từ đầu

Mọi người hay dùng lẫn lộn các khái niệm "mạng không dây", Wi-Fi, wireless, wireless network... hay wifi cũng không có vấn đề gì

Bài viết này giải thích một số khái niệm cơ bản giúp bạn nắm bắt mạng không dây, có cái để chém với mọi người hay đơn giản biết một số vấn đề, giới hạn của mạng không dây.

Việc truyền dữ liệu không dây là phát minh từ rất lâu khi con người bắt đầu phát hiện và tìm hiểu về sóng điện từ. Radio FM, AM dùng để truyền âm thanh ở tần số tính bằng Hz, KHz, MHz, nhưng ở tần số thấp còn mạng không dây truyền dữ liệu bằng sóng điện từ ở những tần số rất cao, tính bằng GHz

Hiện tại ở thời điểm bài viết này đầu năm 2023 thì Wi-Fi dùng các dải băng tầng 2.4Ghz, 5GHz, 6GHz và 60GHz, trong đó 60GHz ít phổ biến.

## Tần số

Bạn chỉ cần để ý giá trị tần số ở những nơi có ghi chữ Hz, GHz đồng thời nhớ các điều sau:

* Giá trị tần số tỉ lệ nghịch với tính xuyên thấu và khoảng cách . Như sóng FM và AM có thể phát cho cả thành phố và xuyên qua đường hầm được nhưng sóng wifi có thể gặp khó khăn với 1 vài bức tường và chỉ phát ở phạm vi nhỏ
    
* Giá trị tần số tỉ lệ thuận với dữ liệu có thể mang theo. Đó là lý do Wi-Fi ở tần số cao thì truyền càng được nhiều dữ liệu
    

## Power và ăng ten

Bạn sẽ thấy con số này ở giá trị là w hay là dbm là độ mạnh gốc tín hiệu được truyền vào dây dẫn tín hiệu đến ăng ten

Ăngten sẽ khuyếch đại tín hiệu và điều chỉnh hình, hướng sóng để truyền đi và chịu trách nhiệm cả việc lắng nghe tín hiệu nhận được. Ăngten có nhiều thông số nhưng chỉ cần nắm độ lợi thể hiện là dBi và hướng sóng là đủ rồi

* Power càng lớn thì khả năng truyền xa và rộng hơn
    
* Thiết bị wifi bị giới hạn power ở mức thấp phù hợp
    
* Ăng ten chỉ có cái phù hợp chứ không có cái tốt nhất
    

## Phần cứng và các tên gọi

Các thành phần, phần cứng được mô tà ở đây kèm cả các từ tiếng anh giúp cho bạn nắm bắt các bài viết tiếng anh.

Mạng không dây thì luôn phải có thu và phát và trong lúc hoạt động thì thiết bị sẽ luân phiên vừa thu vừa phát tương ứng với lúc gửi và nhận dữ liệu. Tuy nhiên thực tế thì bộ phát hay được nghĩ là access point còn bộ thu thì được nghĩ là client hay station.

* Bộ phát (broadcaster)
    
* Bộ thu (receiver)
    

Dữ liệu truyền trong không khí không có giới hạn truyền nhận nào nên chỉ cần có thiết bị phù hợp là có thể thu được tín hiệu và dữ liệu

* Không mã hóa (open network): dữ liệu không mã hóa, khi thu được thì có thể đọc hiểu
    
* Mã hóa (secure network): dữ liệu được mã hóa bằng các thuật toán mã hóa TKIP AES... và phải có mã khóa mới hiểu được dữ liệu
    

Các kết nối trong Wi-Fi sẽ có nhiều mô hình

* Infrastructure mode: Một thành phần chính (thường gọi là Wireless Access Point/WAP/AP hoặc hay gặp hơn là wifi router...) và nhiều trạm con kết nối vào (station, client. device hay máy tính, laptop...) nối vào
    
* Hiếm gặp là ad-hoc mode: Gồm có hai trạm nối trực tiếp với nhau để trao đổi dữ liệu
    
* Lưu ý là các thành phần này đều có ăngten, nếu bạn không thấy không có nghĩa là nó không có mà thường được giấu bên trong
    

## Các tiêu chuẩn

Các thiết bị phát sóng đều phải tuân theo quy chuẩn của nhà nước vì nhiều lý do nên các nhà sản xuất cũng thiết kế và sản xuất thiết bị Wi-Fi đáp ứng quy định.

Ngoài ra để đảm bảo cho các thiết bị có thể hoạt động chung với nhau thì IEEE đã thiết lập rất nhiều mô tả giao thức để các nhà sản xuất định hướng sản xuất sản phẩm có thể hoạt động chung với nhau.

Từ 1999, có các tiêu chuẩn chính đã được xây dựng theo thứ tự là 802.11b, 802.11a, 802.11g, 802.11n, 802.11ac, and 802.11ax và sắp có 802.11axe. Các tiêu chuẩn này có điểm là

* Tương thích ngược cao cho phép các thiết bị cũ vẫn dùng được với các thiết bị mới ra sau này (trừ phi khác tần số). Tuy nhiên không nên cố gắng xài lệch nhau quá xa vì tính hiệu quả, sẽ giải thích sau ở phần lưu ý
    
* Các chuẩn mới sẽ có tốc độ cao hơn và dĩ nhiên mắc hơn
    

Người viết từng làm việc rất nhiều với 802.11n và 802.11ac nhưng vẫn không hiểu tại sao IEEE và Wi-Fi lại dùng mấy cái tên khó nhớ như vậy. May mắn là từ 2018, họ đã quyết định dùng một cách đặt tên dễ nhớ hơn theo số như Wi-Fi 6 là thế hệ thứ 6 tương ứng với 802.11ax là chuẩn phổ biến hiện tại (cho dù Wi-Fi 6E đã ra thị trường nhiều tương đối và cuối 2023 có thể sẽ có Wi-Fi 7)

Cách đặt tên này giúp cho bạn thoải mái khỏi phải suy nghĩ xem 11n với 11ac cái nào ngon hơn mà chỉ cần chọn cái số to hơn hay có chữ E (extention) với ý nghĩa mở rộng

Và trên một số client (thường là điện thoại) khi kết nối Wi-Fi sẽ thấy con số xuất hiện giúp bạn biết mình đang hoạt động theo chuẩn nào

Hiện nay các chuẩn đầu tiên gần như biến mất 802.11b, 802.11a, and 802.11g ở các nơi công cộng. Nếu máy của bạn hơi cũ thì hãy cân nhắc mua cái adapter mới để truy cập mạng không dây nhanh hơn như cái adapter 11n bây giờ dưới 200k rồi.

Một số điều cần lưu ý

* Để đảm bảo tương thích ngược, chuẩn chậm nhất của thiết bị chậm nhất sẽ được dùng. Ví dụ router Wi-Fi 6 kết nối với client Wi-Fi 5 thì chỉ có thể dùng chuẩn Wi-Fi 5
    
* Trong thực tế cho dù ít nhiễu vì các mạng wifi khác, tốc độ chỉ được khoảng 2/3 lý thuyết là mừng rồi vì có rất nhiều yếu tố ảnh hưởng.
    
* Băng thông thực tế được chia sẻ bởi tất cả client trong cùng mạng
    
* Mạng không dây chỉ có lợi thế về mặt tiện lợi hay bề ngoài còn mạng có dây chiến thắng tất cả các mặt còn lại
    

## Băng tần Wi-Fi và độ xa

Nhắc lại chút là tần số càng cao thì băng thông/tốc độ càng cao, tầm xa thu hẹp hơn và mức độ mất băng thông càng nhiều theo khoảng cách

* Băng tần 2.4Ghz: đạt khoảng cách khoảng 61m tuy nhiên do nhiều thiết bị khác cũng dùng băng tầng này và gây nhiễu nên về sau được dùng như một băng tầng dự phòng khi khoảng cách cần hơn là tốc độ
    
* Băng tần 5Ghz: tốc độ cao hơn 2.4GHz tuy nhiên lại bị thu hẹp khoảng cách xuống còn khoảng 50m
    
* Băng tần 6GHz: khoảng cách còn khoảng 40m tuy nhiên mới nên ít nhiễu và đạt băng thông cao nhất
    

Độ xa trong thực tế rất biến thiên vì phụ thuộc vào rất nhiều yếu tố. Trong các giải pháp dành cho gia đình hay văn phòng thì cần thiết kế ở khoảng cách nhỏ hơn lý thuyết và cân nhắc vấn đề nhiễu để đảm bảo chất lượng

## Nhiễu sóng và trở ngại

Nôm na hiểu Wi-Fi như âm thanh, có người khác nói thì tạo tiếng ồn và làm cho người khác không thể nghe được hội thoại và nếu có vật cản thì việc lắng nghe sẽ khó khăn hơn

Đối với băng tần 2.4GHz

* Những thiết bị phát sóng khác xung quanh
    
* Điện thoại không dây cùng băng tần
    
* Đèn huỳnh quang
    
* Thiết bị bluetooth (ít)
    
* Lò vi sóng
    

Đối với băng tần 5GHZ

* Những thiết bị phát sóng khác xung quanh
    
* Điện thoại không dây cùng băng tần
    
* Radar
    
* Vệ tinh
    

Các loại tường chất liệu từ xốp như vách ván gỗ mỏng cho tới đặc như bê tông dày có thể cản từ 10 tới 90% tín hiệu

## Kênh và độ rộng kênh

Mỗi kết nối không dây phải được thiết lập trên một kênh và độ rộng kênh cho biết mức độ băng thông có thể thiết lập trên đó

Độ rộng kênh có các mức độ 20, 40, 80, 160Mhz và càng rộng thì càng truyền được nhiều dữ liệu (tăng băng thông và tốc độ) nhưng lại càng dễ bị nhiễu hơn

Kênh chồng lắp với lại không bị chồng

* Để đạt được độ rộng kênh như mong muốn thì số kênh không chồng lên nhau sẽ ít đi do các kênh lân cận sẽ bị nhiễu ở độ rộng kênh ví dụ nếu dùng độ rộng 40Mhz thì chỉ có 3 kênh là 1 6 12 là 3 kênh không bị nhiễu lẫn nhau và ở băng tần 5Ghz mà sử dụng độ rộng 160MHz thì chỉ còn 2 kênh
    
* Có thể thiết lập kênh hoạt động chồng lắp lên nhau ví dụ ở độ rộng kênh 40MHz thì 1 thiết bị ở kênh 1 và 1 thiết bị ở kênh 2 vẫn hoạt động được, tuy nhiên băng thông sẽ giảm nhiều do nhiễu
    

Đối với băng tần 5GHz thì còn 1 vấn đề là DFS (Dynamic Frequency Selection) là một tính năng bắt buộc thiết bị hoạt động trên băng tần 5GHz phải lắng nghe xem có radar hoạt động ở cùng kênh thì sẽ phải chuyển sang kênh khác để hoạt động dành ưu tiên cho radar. Nên nếu bạn ở gần sân bay, trạm thời tiết... thì thỉnh thoảng sẽ thấy thiết bị 5Ghz của mình bị đứt kết nối một chút do chuyển kênh nhường cho thiết bị radar gần đó phát sóng

Độ rộng kênh 160Mhz có 1 giải pháp hack như trên thiết bị Netgear RAX120 là họ dùng 2 kênh có độ rộng 80MHz để giải bớt tác động của DFS tuy nhiên tốc độ sẽ không bằng giải pháp 160MHz thật

## Wi-Fi streams

Cứ hiểu đơn giản càng nhiều stream thì tốc độ càng cao. Tùy vào phần cứng, một kết nối có thể là single stream, hay dual stream (2x2) hay three-stream (3×3) và four-stream (4×4). Trong tương lai có thể sẽ có nhiều hơn

Mỗi stream đề cập ở đây được tính trên một băng tần. Một số hãng có thể ghém nhiều băng tầng và cho ra số stream nhiều hơn như 8, 12... nhưng quan trọng nhất vẫn là số stream nhỏ nhất trong kết nối sẽ được dùng. Ví dụ router hỗ trợ 4 stream nhưng adapter chỉ là 2 stream thì biết chỉ thiết lập kết nối ở 2 stream

## Băng tầng, kênh, stream

Để dễ tưởng tượng hình dung băng tần như con đường, kênh là những làn xe và stream là các xe đi trên đó. Cùng một đường thì làn xe rộng hơn có thể đi được xe to hơn. Xe to hơn thì chở được dữ liệu nhiều hơn tuy nhiên tốc độ thực tế là tốc độ của chiếc xe chậm nhất

## Sự tiến hóa của Wi-Fi và các tính năng

Để kể ngược lại từ mới tới cũ

### Wi-Fi 6E

Không phải là một thế hệ mới mà chỉ là một bản mở rộng của wifi 6, và được thương mại hóa từ 2021. Wi-Fi 6E sử dụng toàn bộ băng tầng 6GHz nên có 7 kênh (không chồng) 160MHz hay 14 kênh 80MHz.

* Tốc độ không thay đổi nhưng tầm xa thì bị giảm một chút
    
* Bắt buộc dùng WPA3 đối với các thiết bị dùng băng tầng 6GHz nhưng vẫn hỗ trợ WPA2 và WPA ở hai băng tần còn lại
    
* Đối với các mạng công cộng như ở nhà hàng, sân bay thì OWE (Opportunistic Wireless Encryption hay gọi ngắn là Enhanced Open) sẽ được sử dụng để hạn chế tấn công mạng. Tuy nhiên nếu có một thiết bị bình thường không hỗ trợ OWE kết nối thì AP đó sẽ vận hành theo kiểu Open bình thường
    

### Wi-Fi 6 (802.11ax)

Tiêu chuẩn mới và phổ biến hiện nay được thương mại hóa vào đầu 2019 hoạt động cả ở hai băng tầng 2.4 và 5GHz. Ở băng tần 5Ghz hỗ trợ 160Mhz với tốc độ một stream là 600Mbps

* Ở đầu phát, một 4x4 router có thể tạo băng thông 4800Mbps nhưng ở đầu thu chỉ có loại 2x2 adapter
    
* OFDMA là bản nâng cấp của MU-MIMO chia nhỏ các kênh ra thành các tần số khác nhau để gửi và nhận liên tục nên có băng thông tốt hơn
    
* Target Wake Time (TWT) hay wake time scheduling là tính năng tiết kiệm pin/năng lượng cho phép adapter có thể tắt một khoảng thời gian ngắn rồi mở lại khi cần
    
* WPA3 là kiểu mã hóa mới được giới thiệu từ 2018 và có thể cần phải nâng cấp firmware lên để được hỗ trợ
    

### Wi-Fi 5