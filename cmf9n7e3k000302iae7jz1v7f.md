---
title: "Hành trình xây dựng trợ lý AI"
datePublished: Sun Sep 07 2025 12:01:56 GMT+0000 (Coordinated Universal Time)
cuid: cmf9n7e3k000302iae7jz1v7f
slug: hanh-trinh-xay-dung-tro-ly-ai
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/Y_LgXwQEx2c/upload/9938767a88418267e7b0f0cc59dccdc1.jpeg
tags: ai-for-business, ai-misconceptions

---

**Nhân vật:**

* **Anh Minh:** CEO của FutureCorp, một nhà lãnh đạo tài năng, đầy nhiệt huyết nhưng không chuyên sâu về kỹ thuật AI.
    
* **Chị An:** Chuyên gia tư vấn AI, người có kinh nghiệm thực chiến trong việc triển khai các giải pháp dữ liệu và AI cho doanh nghiệp.
    

#### **Màn 1: Giấc mơ lớn**

Trong phòng họp sang trọng của FutureCorp, anh Minh trình bày slide cuối cùng với một biểu đồ tăng trưởng dốc đứng. "Và đây," anh tuyên bố hùng hồn, "là tương lai của chúng ta: 'Minh Tuệ', một AI Agent sẽ thay đổi toàn bộ ngành dịch vụ khách hàng. Nó sẽ hiểu mọi tài liệu, quy trình của công ty và trả lời khách hàng ngay lập tức."

Anh quay sang chị An, chuyên gia tư vấn. "Chúng ta sẽ bắt đầu **train con agent** này ngay lập tức. Tôi muốn nó học hết 5 năm dữ liệu của FutureCorp."

Chị An mỉm cười, một nụ cười của người đã nghe câu chuyện này nhiều lần. "Cảm ơn anh Minh, tầm nhìn của anh rất tuyệt vời. Tuy nhiên, để hiện thực hóa nó, chúng ta cần làm rõ một vài khái niệm đầu tiên. Thực ra, chúng ta không 'train một agent'."

Anh Minh hơi ngạc nhiên. "Ý cô là sao? Chẳng phải cứ đưa dữ liệu vào là AI nó học à?"

"Không hẳn ạ," chị An giải thích. "Một **agent** về bản chất là một chương trình phần mềm, một đoạn code có logic. Chúng ta chỉ có thể *cập nhật* code đó. Thứ chúng ta thực sự 'train' là **mô hình AI (model)**, có thể coi là bộ não của agent. Quá trình 'train' đó không phải là việc biên dịch code, mà là một công đoạn kỹ thuật cực kỳ phức tạp."

Chị An phác thảo lên bảng: "Chúng ta phải thu thập hàng terabyte dữ liệu, làm sạch, gán nhãn, sau đó dùng những dàn máy GPU đắt tiền chạy hàng tuần, thậm chí hàng tháng. Đầu ra của quá trình đó là một 'model' – một file chứa hàng tỷ con số gọi là tham số. File này không tự chạy được, nó cần một chương trình thông dịch đặc biệt như `Ollama` hay `vllm` để hoạt động."

Anh Minh gật gù, bắt đầu hình dung ra bức tranh lớn hơn. "Ra vậy. Giống như ChatGPT mà mọi người hay dùng, nó không chỉ là cái mô hình GPT-4, mà là cả một hệ thống website, ứng dụng phức tạp bao quanh?"

"Chính xác! Đó là một **ứng dụng AI** hoàn chỉnh," chị An khẳng định. "Và 'Minh Tuệ' của chúng ta cũng sẽ là một ứng dụng như vậy."

#### **Màn 2: Ảo tưởng về dữ liệu**

"Tuyệt vời!" Anh Minh hào hứng trở lại. "Vậy chúng ta cứ đưa hết tài liệu của công ty vào cho nó đọc. Tôi có sẵn một ổ cứng 10TB đây."

Chị An lại nhẹ nhàng can thiệp. "Đây là một hiểu lầm phổ biến khác, thưa anh. Việc 'bổ sung dữ liệu' cho AI không đơn giản là 'copy-paste'. Chúng ta sẽ dùng một kỹ thuật gọi là **RAG** (Retrieval-Augmented Generation)."

"Nó hoạt động thế này," chị tiếp tục vẽ lên bảng. "Đầu tiên, chúng ta băm nhỏ 10TB tài liệu của anh thành hàng triệu đoạn văn ngắn (chunks). Mỗi đoạn được một mô hình khác chuyển hóa thành một **vector** - một dãy số đại diện cho ý nghĩa của nó. Tất cả các vector này được lưu trong một cơ sở dữ liệu đặc biệt."

"Khi khách hàng hỏi một câu, câu hỏi đó cũng được chuyển thành một vector. Hệ thống sẽ tìm trong cơ sở dữ liệu xem vector nào giống với vector câu hỏi nhất, rồi lấy ra những đoạn văn bản gốc tương ứng. Cuối cùng, nó đưa những đoạn văn bản đó làm 'tài liệu tham khảo' cho mô hình AI để tạo ra câu trả lời. Mô hình AI của chúng ta không 'đọc' hết 10TB, mà nó chỉ đọc vài đoạn văn có liên quan nhất tại thời điểm được hỏi."

Anh Minh thắc mắc: "Vậy vector chỉ dùng để tìm kiếm thôi à? Tôi cứ nghĩ AI nói chuyện với nhau bằng vector."

Chị An bật cười. "Không đâu ạ. Vector là các dãy số vô hồn. Các hệ thống phần mềm, dù là AI hay không, giao tiếp với nhau qua **API**, và dữ liệu được truyền đi dưới dạng **JSON** – một định dạng văn bản có cấu trúc mà con người và máy đều đọc được."

"Thế tại sao chúng ta không **fine-tune** mô hình với dữ liệu của tôi để nó 'biết' luôn mọi thứ mà không cần tìm kiếm?" anh Minh hỏi, sử dụng một thuật ngữ anh mới nghe được.

"Một câu hỏi rất hay," chị An ghi nhận. "Đây là điểm khác biệt cốt lõi. Hãy tưởng tượng mô hình AI là một sinh viên xuất sắc. **Fine-tuning** giống như anh dạy cho cậu sinh viên đó *cách viết báo cáo theo mẫu của công ty*. Nó thay đổi *hành vi và phong cách*. Còn **RAG** là anh đưa cho cậu ấy *toàn bộ thư viện tài liệu của công ty* để tra cứu khi cần. Để cập nhật kiến thức liên tục, việc đưa sách mới vào thư viện (RAG) hiệu quả hơn nhiều việc dạy lại từ đầu (fine-tuning)."

#### **Màn 3: Những sự thật "đau lòng"**

Sáu tháng sau, phiên bản đầu tiên của "Minh Tuệ" ra đời. Anh Minh rất phấn khởi, nhưng cũng sớm đối mặt với những vấn đề không lường trước.

"An này, sao tháng này hóa đơn đám mây cao thế?" anh Minh hỏi trong một cuộc họp. "Chúng ta mới chỉ có vài trăm người dùng thử thôi mà."

Chị An mở trang tổng quan chi phí. "Đó là **chi phí inference**, thưa anh. Chi phí cho mỗi lần AI tạo ra câu trả lời. Giống như tiền xăng xe vậy, đi càng nhiều càng tốn. Cuộc trò chuyện càng dài, AI càng phải xử lý nhiều ngữ cảnh, chi phí cho mỗi lượt trả lời càng tăng."

Một tuần sau, anh Minh lại gọi cho chị An, giọng có vẻ bực bội. "Tôi vừa nói chuyện với 'Minh Tuệ' về chính sách A, năm phút sau hỏi lại, nó lại trả lời như chưa từng nghe thấy gì cả. Nó bị 'mất trí nhớ' à?"

"Anh nói đúng rồi đấy ạ," chị An bình tĩnh đáp. "Mô hình **LLM vốn không có trí nhớ (stateless)**. Mỗi lần anh gửi một tin nhắn, ứng dụng của chúng ta phải 'nhắc bài' cho nó bằng cách gửi kèm toàn bộ lịch sử cuộc trò chuyện. Nếu cuộc trò chuyện quá dài, vượt qua 'cửa sổ ngữ cảnh' của nó, nó sẽ quên mất những gì đã nói ở đầu."

Cuối tháng, đội ngũ tập hợp để đánh giá dự án. Anh Minh hỏi câu quan trọng nhất: "Vậy rốt cuộc, 'Minh Tuệ' của chúng ta hoạt động có tốt không?"

Cả phòng im lặng. Một kỹ sư lên tiếng: "Em thử vài câu thì thấy ổn ạ." Một nhân viên khác xen vào: "Nhưng em hỏi về sản phẩm X thì nó lại trả lời sai."

Chị An đứng lên. "Đây chính là thử thách lớn nhất trong mọi dự án AI: **Đánh giá chất lượng (Evaluation)**. Chúng ta không thể dựa vào 'cảm giác' được. Để biết nó có 'tốt' hay không, chúng ta phải xây dựng một bộ gồm hàng nghìn câu hỏi kiểm thử, với câu trả lời chuẩn, và chạy tự động mỗi khi có thay đổi. Chỉ khi đó chúng ta mới có thể tự tin nói rằng hệ thống đang tốt lên hay tệ đi."

#### **Màn kết: Tầm nhìn thực tế**

Anh Minh ngả người ra ghế, nhìn những ghi chú chằng chịt trên bảng trắng. Giấc mơ ban đầu của anh về một cỗ máy thần kỳ đã được thay thế bằng một sự thấu hiểu sâu sắc hơn. Xây dựng một ứng dụng AI không phải là phép thuật, mà là một hành trình kỹ thuật đầy thách thức, đòi hỏi sự tỉ mỉ trong xử lý dữ liệu, sự thông minh trong kiến trúc hệ thống và sự nghiêm ngặt trong khâu kiểm thử.

"Cảm ơn chị, An," anh Minh chân thành nói. "Giờ thì tôi đã hiểu. 'Minh Tuệ' không phải là một sản phẩm, mà là một quá trình. Một quá trình mà chúng ta phải liên tục xây dựng, đo lường và cải tiến."

Hành trình của FutureCorp và "Minh Tuệ" chỉ mới bắt đầu, nhưng giờ đây, họ đã bước đi trên một con đường vững chắc, được soi sáng bởi sự thật, chứ không phải bởi những lầm tưởng.