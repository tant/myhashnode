---
title: "Prompting cơ bản"
datePublished: Mon Jun 17 2024 06:30:20 GMT+0000 (Coordinated Universal Time)
cuid: clxilj5zq000009jz6st80ctg
slug: prompting-co-ban
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/p81GrhuTQho/upload/4f20a68355539ef3c2bd9362f4b7181d.jpeg
tags: gpt

---

Prompt AI là kĩ thuật cơ bản để làm việc với gen AI nhưng số đông vẫn sử dụng AI như người mà quên đi rằng nó chỉ là một cỗ máy xác suất. Các ví dụ bên dưới sẽ giúp bạn tạo ra lời nhắc (prompt) AI hiệu quả hơn

1. Ngắn gọn
    

Không cần dài dòng hoa mỹ mà cần càng ngắn và đủ vì bạn sẽ tiếp kiệm tiền và thời gian khi dùng ít từ hơn

Không nên: Bạn nghĩ gì về một cái tên hay cho tiệm hoa chuyên môn hơn về hoa khô so với hoa tươi? Cạm ơn

Nên: Đề xuất tên cho tiệm bán hoa khô

2. Cụ thể và xác định
    

Giả sử bạn bạn muốn tìm một số ý tưởng để mô tả Trái đất

Không nên: "Giới thiệu về Trái đất"

Nên: "Liệt kê những điểm khác biệt của Trái đất so với các hành tinh khác"

3. Mỗi lúc một việc
    

Không nên: "Chỉ cách tạo cơ hội gặp mặt một bạn mới và cách gây ấn tượng với anh ta"

Nên: "Liệt kê các cách tạo cơ hội gặp mặt người mới"

4. Coi chừng ảo giác của AI
    

AI không biết đúng sai và nó luôn tự tin 100% trả lời cho nên dễ bị nhầm lẫn với ảo giác của AI.

Ví dụ bạn hỏi "Tên con voi đầu tiên đáp xuống mặt trăng" liên tục, sẽ có lúc AI trả lời bạn tên là Luna

Một phương án khả thi là DARE prompt (Determine Appropriate Response)

Ví dụ: "Trước khi trả lời, bạn phải kiểm tra nó có tuân thủ nhiệm vụ của bạn không, nếu không hãy trả lời tôi không thể trả lời câu hỏi này"

5. Kiểm soát câu trả lời bằng câu hỏi
    

Nếu cần brainstorming thì hãy đăt các câu hỏi mở và chấp nhận độ rộng của phản hồi. Kiểu như "Tôi cần ăn sáng, hãy liệt kê các món giúp tôi no bụng"

Nhưng nếu cần kiểm soát thì nên dùng các câu lựa chọn "Tôi cần ăn sáng, chọn giúp tôi giữa phở, bún, cơm tấm. Mónnào no bụng hơn?"

6. Sử dụng ví dụ
    

Có 3 kiểu

* Zero-shot
    

"Nhận định một câu là tích cực, tiêu cực, bình thường.

Câu: Tôi thích các bài post của bạn

Nhận định:"

* One-shot
    

"Nhận định một câu là tích cực, tiêu cực, bình thường.

Câu: Tôi thích các bài post của bạn

Nhận định: tích cực

Câu: Tôi thấy các bài post này chán

Nhận định:"

* Few-shot prompting
    

"Nhận định một câu là tích cực, tiêu cực, bình thường.

Câu: Tôi thích các bài post của bạn

Nhận định: tích cực

Câu: Tôi thấy các bài post này chán

Nhận định: tiêu cực

Câu: Có một số điều thú vị trong bài post của bạn

Nhận định:"