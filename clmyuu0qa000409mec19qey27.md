---
title: "UAT - User Acceptance Test"
datePublished: Mon Sep 25 2023 12:18:16 GMT+0000 (Coordinated Universal Time)
cuid: clmyuu0qa000409mec19qey27
slug: uat-user-acceptance-test
tags: testing

---

Đây là một bước nghiệm thu tiêu chuẩn mà dự án phần mềm nào cũng có. Tuy nhiên cách tiến hành lại được làm sơ sài và theo hiểu biết của từng PM và thậm chí của tester nên bài viết này tổng kết lại những điểm cốt yếu để có một UAT hiệu quả và cách phản hồi lại kết quả nghiệm thu

## Mục tiêu của UAT

Rõ ràng đây là phép test nhằm giúp cho công ty/khách hàng xác nhận sản phẩm, dịch vụ kết quả chạy được cho người sử dụng và cụ thể như sau

* Xác nhận là sản phẩm, dịch vụ, quy trình tạo ra chạy như mong đợi trong môi trường thật
    
* Liệt kê những vấn đề còn tồn đọng cần xử lý để có thể xác nhận dự án được hoàn thành
    

UAT phải giả lập các điều kiện thực tế, cho nên khi tính năng đó đã hoạt động thì mọi người có thể tự tin hơn về việc sản phẩm sẽ chạy ổn khi nó được tung ra thị trường/go live/launch. Nó cho phép đội dự án thu thập những thông tin chi tiết hơn về cách người dùng tương tác với sản phẩm. UAT giúp trả lời những câu hỏi ngoài tính năng thiết kế như

* User có nhận ra tính năng và dùng chúng không?
    
* Cách họ tương tác với nó
    
* User mất bao nhiêu thời gian để tương tác
    
* Họ có nắm bắt được hết tính năng không
    
* Sản phẩm này có tiếp cận được tất cả mọi người không
    

UAT còn có thể dùng để thu thập những trải nghiệm của user với sản phẩm qua đó đội dự án có thể nắm bắt được những cảm xúc sản phẩm tạo nên, những thông điệp nó truyền tải và những diện mạo nó đang thể hiện…

## Phương thức làm UAT tốt nhất

Để đạt các mục tiêu tiêu trên UAT phải được tiến hành một cách cẩn trọng chu đáo. Các best practices này sẽ giúp bạn thực hiện một UAT hiệu quả

### Định nghĩa và ghi xuống Acceptance criteria

AC là những tiêu chuẩn hay yêu cầu đặt trước dành cho sản phẩm. Viết xuống những yêu cầu này cho những mục mà bạn muốn test.

Ví dụ nếu dự án có tính năng là tạo ra sổ tay nhân viên cho các nhân viên thì tiêu chuẩn nghiệm thu là sổ tay phải là file pdf có thể truy cập được bằng điện thoại hay máy tính

### Tạo ra test case cho mỗi mục cần test

Một TC là một loạt các bước và kết quả mong đợi sau từng bước. Nó thường gồm một loạt các hoạt động user có thể làm để xác nhận sản phẩm hoạt động theo đúng cách nó được kì vọng.

Cũng theo ví dụ trên thì sẽ có 1 TC là user click vào sổ tay thì sẽ truy cập được mà không gặp lỗi lầm gì

### Lựa chọn user cẩn thận

Phải là những người sau này thực tế dùng sản phẩm

### Viết kịch bản UAT dựa trên user story

Kịch bản này sẽ giao cho user trong khi thực hiện test. User story là một cái giải thích không chính thức chung chung cho một tính năng được viết theo góc nhìn của user. Cũng ở ví dụ trên một US: Là một nhân viên mới, tôi muốn dùng sổ tay để dễ dàng tìm kiếm chính sách nghỉ phép và chia sẻ nó với mọi người qua mail

### Trao đổi với user trước và cho họ biết cần trông đợi gì

Nếu bạn có cơ hội làm việc với user trước, thì chắc chắn sẽ có ít câu hỏi, vấn đề hay sự trì trệ trong quáy trình UAT

### Chuẩn bị trước môi trường test cho UAT

Phải test thử trước môi trường này và cung cấp đầu đủ thông tin, truy cập cho user

### Cung cấp hướng dẫn step by step để giúp user đi qua quá trình test

Cái này rất có ích với user để có những hướng dẫn rõ ràng, dễ theo giúp họ tập trung sự chú ý vào đúng chổ cần thiết. Bạn có thể làm cái hướng dẫn này và gửi mọi người từ trước

### Ghi xuống các thông tin phát sinh và thu thập tất cả issue được phát hiện

Dùng excel hay gì cũng được nhưng giờ thường là dùng các hệ thống bug tracking hơn. Quan trọng là nó phải phân loại được issue nằm ở đâu kèm theo các ý kiến của user về mức độ ưu tiên. Nó sẽ giúp đội dự án bố trí ưu tiên fix cái nào trước cái nào sau

## Quản lý kết quả UAT

User cung cấp phản hồi khi thực hiện UAT và nói chung cũng rất đa dạng từ tích cực cho tới tiêu cực và có cả đúng lẫn sai từ comment, bug reports, change request… Cho nên team dự án cần phải phân tích liên tục và quản lý danh sách chỉ giữ lại hai thứ

* Bug/Issue: Nó có thể là vấn đề kĩ thuật, hay những vấn đề khác và bạn sẽ theo dõi nó trên hệ thống, xếp độ ưu tiên cao để xử lý.
    
* Change request: Đây là các ý tưởng xuất hiện và đề xuất cải tiến sau khi sử dụng tính năng. Bạn cũng cần quản lý và xếp độ ưu tiên cho chúng. Cái này có thể phải có phê duyệt từ stakeholder để thực hiện và có thể phải điều chỉnh project timeline để hoàn thành
    

## Lời cuối

UAT là một công cụ mạnh mẽ để đảm bảo đầu ra của dự án đúng yêu cầu và thành công. PM nhớ dành thời gian cho UAT và cả thời gian để giải quyết phát sinh