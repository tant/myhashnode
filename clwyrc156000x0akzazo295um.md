---
title: "Tài liệu kế hoạch phần mềm"
datePublished: Mon Jun 03 2024 09:17:21 GMT+0000 (Coordinated Universal Time)
cuid: clwyrc156000x0akzazo295um
slug: tai-lieu-ke-hoach-phan-mem
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/wusOJ-2uY6w/upload/57be0f848f98a2c21ff1511320d1fa6b.jpeg
tags: project-management

---

Một trong những vấn đề phức tạp nhất trong phát triển phần mềm là đội lập trình đồng ý phát triển một thứ mà họ không biết gì về nó hoặc là chưa biết rõ ràng. Gần đây phong trào startup với sự hào hứng và hi vọng thành công cũng tạo thêm nhiều động lực cho việc phát triển sản phẩm mà không có nhiều kế hoạch và chuẩn bị

Đầu tiên phải chắc chắn rằng viết phần mềm không có dễ dàng vì mắc tiền, tốn thời gian và mạo hiểm. Để có cơ hội thành công bạn phải có

* Kiểu giao tiếp rõ ràng.
    
* Kế hoạch chi tiết
    
* Tài liệu hóa về các mong đợi và các vấn đề khác
    

Từ năm 2001, phương thức Agile đề xuất một ý tưởng khác với truyền thống là việc lên kế hoạch, thực hiện, kiểm tra thực hiện cùng một lúc. Phương thức này làm giảm rủi ro và cho phép thay đổi phần mềm khi cần bằng các iteration. Nó đề xuất bạn lên kế hoạch liên tục chứ không phải là lên kế hoạch một lần duy nhất.

Lên kế hoạch phần mềm có thể hiểu là tài liệu hóa phần mềm (documetation) vì tài liệu là nơi software thành hình. Từ một ứng dụng chỉ có cái tên được phân rã ra thành hệ thống với nhiều business logic, mô tả (spec), luồng (user flow)...

Tài liệu này phải trả lời được 2 vấn đề

* Sản phẩm sẽ giống như thế nào? Product documentation
    
* Làm thế nào để chúng ta xây được nó? Process documentation
    

## Product documentation

Nếu hiểu hệ thống là một loạt các tính năng giúp cho user đạt được mong muốn của mình thì chúng ta có tài liệu

* **Functional requirements**: một user có thể xem được trạng thái đơn hàng ở màn hình chính.
    
* **Non-functional requirement**: hệ thống sẽ phải chạy được với 100.000 user cùng một lúc.
    

Phải để ý là không chỉ có user mà stakeholder cũng có mong đợi và tài liệu này sẽ chuyển các mong đợi đó thành thứ mà developer có thể hiểu để làm. Đây là tài liệu đầu tiên phải làm

Các tính năng chủ yếu đến từ user và trải nghiệm của user quyết định thành công hay thất bại của sản phẩm nên cần có **UX documentation** gồm user personas --&gt; user scenarios --&gt; user stories. Các tài liệu này sẽ hỗ trợ nghiên cứu để xây dựng prototype, wireframe và journey maps.

Về phần công nghệ đầu tiên phải kể đến **Architecture design document**. Tài liệu này do kiến trúc sư hệ thống làm ra để mô tả các thành phần của hệ thống và cách chúng nói chuyện với nhau

Tiếp đến là **Testing documentation** gồm test plan, test cases

## Process documentation

Đầu tiên là các kế hoạch hay **roadmap**

* Strategy roadmap: high level goal và rough delivery estimate
    
* Technology roadmap: low level goals và due date
    
* Release plan: strict deadline cho tính năng nào được golive
    

Sau đó là **metric** cho phép phản hồi công việc được tiến hành nhanh và hiệu quả thế nào ví dụ trong agile

* WIP có velocity, sprint burndown, release burndown.
    
* Process health and bottleneck có cycle time, cumulative flow, flow efficiency
    
* Code quality có code average, automation vs manual tests, code churn, MCC
    

Tiếp theo là **standards và guideline** cho phép tạo ra các mã nguồn thống nhất

Còn nhiều tài liệu khác nữa phát sinh theo dự án và đặc thù sản phẩm tuy nhiên để hoàn thành việc lên kế hoạch kĩ càng sản phẩm thì các tài liệu bên dưới là cần thiết và đầy để để bắt đầu và cần được bổ sung, cập nhật liên tục qua các iteration

## Project documentation

* Product document
    
    * Functional Req
        
    * NFR
        
    * UX documentation
        
    * Architecture design document
        
    * Testing documentation
        
* Process documentation
    
    * Roadmaps
        
    * Metrics
        
    * Standards và guidelines