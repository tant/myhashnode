---
title: "Ứng dụng GPT giải quyết yêu cầu chatbot"
datePublished: Sun Jun 25 2023 08:42:09 GMT+0000 (Coordinated Universal Time)
cuid: cljb6lptz000c09icaz3qehev
slug: ung-dung-gpt-giai-quyet-yeu-cau-chatbot
tags: chatbot, gpt-4

---

Những ai từng sử dụng các giải pháp chatbot hiện tại để chăm sóc khách hàng rồi sẽ hiểu sử dụng thành thạo khó như thế nào. Đây là một ví dụ bạn phải tạo ra các ngữ cảnh, kịch bản tương ứng rất phức tạp

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687762562274/c7d35768-7413-4088-a8d5-c6220d01d01e.png align="center")

Khi chatGPT ra đời tạo một cơn lốc trên toàn thế giới về AI nhưng đa phần vẫn chỉ ở mức là vô trang web chat với em nó và thường là nhờ vả tạo ra nội dung.

Tuy nhiên ứng dụng của GPT không dừng lại ở đây, mình sẽ trình bày một tính năng thú vị mà các doanh nghiệp có thể sử dụng để tạo ra giá trị cho khách hàng cũng như nâng tầm công nghệ của mình.

# Giải pháp chatbot GPT với dữ liệu nội bộ.

Chúng ta sẽ sử dụng tính năng phân tích dữ liệu của GPT và tính năng xử lý ngôn ngữ tự nhiên để tạo ra chatbot linh hoạt và giống con người thật hơn.

Nó khác với việc sử dụng chatGPT ở điểm là chatbot của bạn sẽ trả lời được những nội dung mà doanh nghiệp bạn không public ra ngoài, và nó cũng chỉ trả lời được các nội dung liên quan trong ngữ cảnh dữ liệu của bạn. Ví dụ data đầu vào chính là nội dung nói về sản phẩm, dịch vụ của bạn, thậm chí các câu hỏi của khách hàng và câu trả lời của bạn, hay các mục FAQ, chia sẻ kinh nghiệm sản phẩm... đều có thể đưa vào để xử lý và chatbot sẽ trả lời theo hiểu biết của nó về nội dung đã phân tích, nếu không trả lời được thì sẽ trả lời không biết.

Còn với chatGPT do đã hấp thụ một lượng lớn data trên toàn thế giới nên khả năng trả lời là cao hơn cho mọi tình huống. Tuy nhiên vẫn gặp khó khăn với các dữ liệu mới và nội bộ. Vì vậy GPT phối hợp với LLM là một giải pháp hay để tạo ra các chatbot hay các công cụ truy vấn dữ liệu nội bộ bằng ngôn ngữ tự nhiên

# Demo giải pháp

Chúng tôi đưa dữ liệu từ một bài báo mới (hi vọng chatGPT chưa đọc) vào model để index và tạo các vector (link [https://vnexpress.net/thu-tuong-pham-minh-chinh-len-duong-tham-trung-quoc-4621506.html](https://vnexpress.net/thu-tuong-pham-minh-chinh-len-duong-tham-trung-quoc-4621506.html))

Đơn giản là đưa dữ liệu text vào thôi.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687681320529/5f0581e0-30d2-44e1-a9c7-c30fbaf393cb.png align="center")

Sau đó chúng tôi sẽ chạy để phân tích nội dung này (chỉ mất 1s là xong) sau đó đặt hai loại câu hỏi query và logic

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687681497060/c2895fbe-1861-450e-a733-e59bcd137496.png align="center")

Kết quả tương đối ổn với query. Thử câu khó hơn xem sao

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687681523643/699b0e1a-b5d5-4d2e-b22e-a57f95640d16.png align="center")

Có một vấn đề với chữ "tổng thống" nhưng có thể châm chước vì cái này tiếng việt với lại dính tới thể chế là ngoài ngữ cảnh rồi. Hỏi thêm chút nữa

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687681657703/010ba37c-6937-43a6-b3c7-c8d91fa136d2.png align="center")

Bạn đã không trả lời được dù mình biết bạn biết được ngày đi nhưng bạn không có dữ liệu thời tiết để trả lời

# Ứng dụng

Giải pháp này phải được xây dựng tích hợp với các điểm chạm online của doanh nghiệp để khai thác tối đa giá trị

Phải tổ chức lưu trữ lại dữ liệu hoạt động của chatbot (các câu hỏi, câu trả lời, thời gian phản hồi, người hỏi...) để bổ sung vào dữ liệu và train model tiếp tục

## Các bước tiến hành

* Khách hàng giao dữ liệu
    
* Train chatbot trên dữ liệu đó
    
* Khách hàng kiểm tra chatbot xem đúng yêu cầu chưa
    
* Tích hợp chatbot vào các hệ thống của khách hàng
    

## Giá trị

Ngắn hạn có thể chatbot không xử lý được tốt tất cả nội dung câu hỏi, nhưng qua thời gian nó sẽ trả lời tốt hơn nhiều vì có nhiều dữ liệu hơn cũng như được nâng cấp với các model mới hơn

Doanh nghiệp có thể cắt giảm được chi phí tư vấn trực tiếp cùng với các vấn đề phát sinh liên quan đến cảm xúc

Doanh nghiệp tiến xa hơn chuyển đổi số và vận dụng công nghệ cao hơn. Trường hợp cần phải gọi vốn, đặc biệt là vốn ngoại thì ứng dụng công nghệ rất có giá trong mắt nhà đầu tư

# Các giải pháp khác trên thị trường

* Copilot và Dynamics