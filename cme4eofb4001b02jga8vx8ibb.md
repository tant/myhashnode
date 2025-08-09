---
title: "Hành trình chế tác AI Agent từ dữ liệu"
datePublished: Sat Aug 09 2025 15:24:41 GMT+0000 (Coordinated Universal Time)
cuid: cme4eofb4001b02jga8vx8ibb
slug: hanh-trinh-che-tac-ai-agent-tu-du-lieu
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/DwPLi_mvKpw/upload/6c4baad4f0ed560439a6fd72c6e77aa0.jpeg
tags: ai-agents, chunking, rag

---

Trong thế giới trí tuệ nhân tạo, có một câu chuyện ngụ ngôn hiện đại về một nghệ nhân mộc AI tên là Bách. Anh có một tham vọng lớn: chế tác "Linh Mai", một con búp bê gỗ AI thông thái, có khả năng thấu hiểu toàn bộ thư viện số tiếng Việt—từ những tác phẩm văn học kinh điển, các tài liệu kỹ thuật phức tạp, cho đến những kho trữ văn bản đồ sộ.

Nhưng Bách nhanh chóng đối mặt với một sự thật phũ phàng. Bộ não của Linh Mai, dù mạnh mẽ đến đâu, cũng có một giới hạn gọi là "cửa sổ ngữ cảnh" (context window). Giống như một người chỉ có thể tập trung vào một vài trang sách cùng lúc, mô hình ngôn ngữ (LLM) không thể "đọc" toàn bộ thư viện trong một lần. Đây là nút thắt cổ chai cơ bản ngăn cản AI tiếp cận tri thức vô hạn.

Để giải quyết vấn đề này, Bách phải trở thành một nghệ nhân điêu khắc dữ liệu. Anh cần một kỹ thuật gọi là "chunking"—nghệ thuật đẽo gọt những "khúc gỗ thô" của văn bản lớn thành những "linh kiện tinh xảo" của thông tin, vừa đủ nhỏ để xử lý, vừa đủ lớn để chứa đựng ngữ cảnh trọn vẹn. Chất lượng của quá trình "chế tác" này sẽ quyết định trí tuệ của Linh Mai. Một chiến lược tốt sẽ tăng cường độ chính xác và giảm nhiễu; một chiến lược tồi sẽ tạo ra những mảnh vỡ ngữ cảnh và những câu trả lời vô nghĩa. Quy tắc vàng là: nếu một đoạn văn bản có ý nghĩa với con người khi đứng một mình, nó cũng sẽ có ý nghĩa với mô hình ngôn ngữ.

Hành trình của Bách đi tìm kỹ thuật chunking hoàn hảo chính là hành trình mà bất kỳ nhà phát triển AI nào cũng phải trải qua. Hãy cùng theo chân anh khám phá thế giới phức tạp và đầy hấp dẫn này.

### **Chương 1: Những lát cắt đầu tiên của người học việc**

Bách bắt đầu với những phương pháp trực quan nhất, phản ánh những kỹ thuật chunking cơ bản và phổ biến nhất.

**Lát cắt "thô bạo": fixed-size chunking**

Phương pháp đầu tiên của Bách là fixed-size chunking (chia theo kích thước cố định). Anh coi các tài liệu như một tấm ván dài và dùng cưa cắt chúng thành những đoạn có kích thước bằng nhau, dựa trên số lượng ký tự hoặc token. Đây là điểm khởi đầu đơn giản và phổ biến nhất vì chi phí tính toán thấp và dễ triển khai.

Nhưng vấn đề nhanh chóng xuất hiện. Phương pháp này hoàn toàn "mù" trước nội dung và cấu trúc của văn bản. Nó có thể cắt đôi một câu, thậm chí một từ. Các chunk kết quả thường rời rạc về mặt ngữ nghĩa, làm mất đi bối cảnh và làm tê liệt hệ thống truy xuất thông tin.

Để khắc phục, Bách sử dụng chunk\_overlap (phần chồng lấn), trong đó phần cuối của chunk trước được lặp lại ở đầu chunk sau. Nó hoạt động như một vùng đệm an toàn, đảm bảo các ý tưởng bị chia cắt có cơ hội được kết nối lại. Một tỷ lệ chồng lấn phổ biến là 10-20%.

Tuy nhiên, Bách lại đối mặt với một tình thế tiến thoái lưỡng nan khác: chọn chunk\_size (kích thước chunk) phù hợp. Các chunk nhỏ (100-300 token) giúp truy xuất nhanh hơn nhưng có thể chia cắt thông tin quan trọng. Các chunk lớn hơn (500-1000 token) giữ lại nhiều ngữ cảnh hơn nhưng lại chậm hơn và có thể làm loãng thông tin cụ thể cần cho một truy vấn. Điểm khởi đầu hợp lý thường là khoảng 100-200 từ.

Sức mạnh lớn nhất của fixed-size chunking—sự đơn giản—cũng chính là điểm yếu chí mạng của nó. Đó là một cái bẫy ngọt ngào. Nó giải quyết được bài toán tức thời là làm cho văn bản vừa với cửa sổ ngữ cảnh, nhưng lại tạo ra một vấn đề ngầm nguy hiểm hơn ở phía sau: chất lượng truy xuất thông tin kém.

**Lát cắt "ngữ pháp": sentence splitting**

Rút kinh nghiệm, Bách quyết định tôn trọng đơn vị cơ bản của ý nghĩa: câu. Anh sử dụng các thư viện như nltk hoặc spacy để chia văn bản theo ranh giới câu (dấu chấm, dấu hỏi, v.v.). Điều này đảm bảo mỗi chunk ít nhất là một ý tưởng hoàn chỉnh.

Nhưng anh sớm nhận ra việc tách câu không hề đơn giản. Vô số trường hợp ngoại lệ xuất hiện: các từ viết tắt ("Mr. Smith," "U.S.A."), số thập phân, và các dấu câu phức tạp có thể đánh lừa các bộ tách ngây thơ. Điều này cho thấy sự cần thiết của các bộ tokenizer tinh vi, đã được huấn luyện như punkt của nltk.

Dù đã cải tiến, phương pháp này lại nảy sinh những thách thức mới. Độ dài câu rất khác nhau, dẫn đến kích thước chunk không đồng đều và có thể làm mất cân bằng khi truy xuất. Quan trọng hơn, một câu đơn lẻ thường thiếu bối cảnh rộng lớn để trả lời một câu hỏi phức tạp. Linh Mai có thể trả lời "Token là gì?" nhưng lại bó tay với câu "Hãy giải thích tác động của tokenization đến hiệu suất của RAG."

### **Chương 2: Tay nghề của người thợ lành nghề**

Bách tiến lên một bậc, từ các quy tắc đơn giản đến các chiến lược tôn trọng cấu trúc bên trong của tài liệu.

**Phương pháp "phân tầng": recursive character text splitting**

Bách khám phá ra recursive character text splitting (chia văn bản đệ quy theo ký tự), một chiến lược mặc định thanh lịch và mạnh mẽ hơn. Kỹ thuật này cố gắng chia văn bản bằng một danh sách các dấu phân tách được ưu tiên, thường là

`"\n\n","\n"," ",""`

(dấu xuống dòng kép, dấu xuống dòng đơn, dấu cách, và ký tự rỗng).

Đầu tiên, nó cố gắng chia theo đoạn văn (\\n\\n). Nếu một đoạn văn vẫn quá lớn, nó sẽ đệ quy tự gọi chính nó trên chunk đó, lần này thử chia theo dòng (\\n), sau đó là dấu cách, và cuối cùng, như một phương án cuối cùng, là chia theo từng ký tự.

Ưu điểm chính là bản chất phân cấp của nó. Nó cố gắng giữ các đơn vị ngữ nghĩa liên quan nhất (đoạn văn, sau đó là câu) lại với nhau càng lâu càng tốt, chỉ phá vỡ chúng khi thực sự cần thiết để đáp ứng ràng buộc về chunk\_size. Điều này làm cho nó vượt trội hơn hẳn so với fixed-size chunking đối với văn bản phi cấu trúc thông thường.

**Tôn trọng "bản thiết kế": structural chunking**

Bách nhận ra rằng đối với các tài liệu có cấu trúc rõ ràng, cách tốt nhất là tôn trọng ý đồ của tác giả hoặc nhà thiết kế ban đầu.

**Markdown chunking:** Đối với các tài liệu kỹ thuật được viết bằng markdown, Bách sử dụng markdown chunking. Công cụ này chia tài liệu dựa trên hệ thống tiêu đề (ví dụ: # H1, ## H2). Nội dung dưới mỗi tiêu đề được nhóm lại với nhau, và chính tiêu đề đó được lưu dưới dạng siêu dữ liệu (metadata). Siêu dữ liệu này cung cấp ngữ cảnh cực kỳ quan trọng. Một chunk văn bản không còn chỉ là một chuỗi ký tự; nó là "nội dung thuộc mục 'Triển khai' của chương 'Recursive chunking'". Anh cũng có thể kết hợp phương pháp này với chia đệ quy để có được hiệu quả tốt nhất.

**Layout-aware chunking:** Thách thức lớn nhất của Bách là các tài liệu pdf lịch sử được quét và các báo cáo tài chính có bố cục phức tạp với bảng biểu, hình ảnh và văn bản nhiều cột. Các công cụ trích xuất văn bản thông thường sẽ làm xáo trộn thông tin này. Anh tìm đến layout-aware chunking (chia theo bố cục) bằng các công cụ như document ai của Google hoặc amazon textract. Các công cụ này không chỉ đọc văn bản; chúng phân tích bố cục trực quan của tài liệu, xác định các yếu tố như tiêu đề, đoạn văn, danh sách và bảng biểu. Các chunk được tạo ra từ chính các yếu tố bố cục này. Một bảng được giữ nguyên vẹn như một chunk có cấu trúc, thay vì một chuỗi văn bản lộn xộn. Điều này cải thiện đáng kể sự mạch lạc về ngữ nghĩa cho các tài liệu có cấu trúc trực quan.

Bước chuyển từ chia đệ quy sang chia theo cấu trúc đánh dấu một sự thay đổi cơ bản trong nhận thức của Bách. Anh không còn xem nội dung như một dòng dữ liệu đơn thuần để phân đoạn, mà xem tài liệu như một đối tượng có cấu trúc với logic và hệ thống phân cấp riêng. Điều này có nghĩa là hệ thống xử lý dữ liệu cho Linh Mai không thể là một khối đồng nhất. Nó phải có khả năng xác định loại tài liệu và gửi nó đến chiến lược chunking phù hợp. Một tệp .md sẽ đến bộ chia markdown, một tệp .pdf đến bộ phân tích bố cục. Việc này làm tăng độ phức tạp của kiến trúc nhưng mang lại lợi ích to lớn về chất lượng truy xuất.

### **Chương 3: Cái nhìn thấu suốt của bậc thầy**

Hệ thống của Bách giờ đã mạnh mẽ, nhưng vẫn còn một điểm yếu: những đoạn văn dài hoặc các phần thảo luận về nhiều chủ đề khác nhau một cách tinh vi. Các phương pháp hiện tại không thể "nhìn thấy" những thay đổi ngữ nghĩa bên trong này.

**Đọc "linh hồn" của văn bản: semantic chunking**

Bách bước vào thế giới của semantic chunking (chia theo ngữ nghĩa). Kỹ thuật này vượt qua các quy tắc cấu trúc và sử dụng chính ý nghĩa của văn bản để tìm điểm chia. Quá trình này thường bao gồm:

1. Chia văn bản thành các câu riêng lẻ.
    
2. Tạo một vector embedding (một biểu diễn số của ý nghĩa) cho mỗi câu.
    
3. Tính toán độ tương đồng cosine (khoảng cách) giữa các embedding của các câu liền kề.
    
4. Xác định các "điểm gãy" (breakpoint) nơi điểm tương đồng giảm mạnh, cho thấy sự thay đổi chủ đề. Văn bản sau đó được chia tại các điểm này.
    

Ý tưởng cốt lõi là nhóm các câu có liên quan về mặt ngữ nghĩa, tạo ra các chunk chặt chẽ về chủ đề và giàu ngữ cảnh. Về lý thuyết, đây là phương pháp chunking chính xác nhất.

Tuy nhiên, với sự cẩn trọng của một nghệ nhân, Bách tìm hiểu sâu hơn và phát hiện ra một ngã rẽ bất ngờ trong các phương pháp. Mặc dù vượt trội về mặt khái niệm, semantic chunking lại tốn kém về mặt tính toán. Nó đòi hỏi một bước embedding toàn bộ các câu chỉ để quyết định nơi chia. Các bài báo học thuật gần đây cho thấy chi phí cao này không phải lúc nào cũng được bù đắp bằng sự cải thiện hiệu suất nhất quán. Trong một số thử nghiệm thực tế, fixed-size chunking đơn giản hơn lại hoạt động tốt hơn.

Điều này tạo ra một nghịch lý: phương pháp được thiết kế để chính xác nhất có thể thất bại trong các tác vụ đòi hỏi sự chính xác. Bài học quan trọng cho Bách là anh không thể mặc định "tinh xảo hơn là tốt hơn". Anh phải xây dựng một quy trình đánh giá mạnh mẽ cho hệ thống RAG của riêng mình, thử nghiệm các chiến lược chunking khác nhau trên dữ liệu của anh và với các truy vấn người dùng dự kiến của anh để xem điều gì thực sự hiệu quả. Việc lựa chọn chiến lược chunking là một câu hỏi thực nghiệm, không phải là một câu hỏi lý thuyết.

### **Chương 4: Nước cờ của bậc thầy**

Bách đã đến biên giới cuối cùng của chunking, nơi anh không còn ra lệnh cho máy móc phải chia như thế nào, mà thay vào đó, hỏi ý kiến của nó.

**AI với vai trò chiến lược gia: agentic chunking**

Agentic chunking (chia theo tác tử) là chiến lược tiên tiến và thử nghiệm nhất. Nó sử dụng chính LLM như một tác tử (agent) thông minh để quyết định cách chia một tài liệu. Quá trình này thường bao gồm:

* **Propositionizing** (tạo mệnh đề): LLM đầu tiên phân rã văn bản nguồn thành một loạt các "mệnh đề"—những câu phát biểu độc lập, đơn lẻ. Ví dụ, "RAG kết hợp truy xuất và sinh văn bản" trở thành một mệnh đề.
    
* **Agentic grouping** (nhóm theo tác tử): Một tác tử dựa trên LLM sau đó phân tích các mệnh đề này. Nó quyết định xem một mệnh đề mới có thuộc về chunk hiện tại hay không, hay nó đại diện cho một sự thay đổi chủ đề cần bắt đầu một chunk mới. Nó giống như một người đang đọc và quyết định, "Được rồi, phần tiếp theo là một ý mới, mình sẽ bắt đầu một đoạn mới ở đây."
    

Phương pháp này mô phỏng tư duy của con người trong quá trình chunking. Nó linh hoạt, bảo toàn ngữ cảnh và thậm chí có thể làm giàu các chunk bằng siêu dữ liệu như tóm tắt hoặc tiêu đề do chính tác tử tạo ra. Đây là đỉnh cao của sự mạch lạc ngữ nghĩa. Tuy nhiên, Bách nhận ra đây là một chiến lược "cấp 5" có lý do của nó. Nó mang tính thử nghiệm cao, cực kỳ tốn kém về mặt tính toán và phức tạp để triển khai. Nó đại diện cho tương lai nhưng có thể chưa thực tế cho hầu hết các hệ thống sản xuất ngày nay.

### **Kết luận: Hộp đồ nghề của nghệ nhân - Chọn đúng dụng cụ**

Hành trình của Bách đã kết thúc. Anh không tìm thấy một "dụng cụ vạn năng" duy nhất cho việc chunking. Thay vào đó, anh đã xây dựng được một hộp đồ nghề đa năng. Trí tuệ mà anh có được không nằm ở việc biết phương pháp tốt nhất duy nhất, mà là biết chọn phương pháp nào cho một nhiệm vụ nhất định.

Sự lựa chọn phụ thuộc vào một phương trình nhiều biến số:

* **Bản chất dữ liệu:** Có cấu trúc (markdown, pdf có bảng) hay phi cấu trúc (văn bản thuần)?
    
* **Mô hình embedding:** Khả năng và giới hạn cửa sổ ngữ cảnh của nó là gì?
    
* **Truy vấn người dùng:** Ngắn và cụ thể hay dài và phức tạp?
    
* **Ứng dụng:** Dùng cho hỏi-đáp, tóm tắt, hay một quy trình tác tử?
    
* **Nguồn lực:** Các ràng buộc về ngân sách và độ trễ là gì?
    

Để hệ thống hóa kiến thức của mình, Bách tạo ra một bảng so sánh cuối cùng. Đây là công cụ tối thượng, chắt lọc toàn bộ phân tích phức tạp thành một hướng dẫn tham khảo duy nhất, dễ dàng và thiết thực.

### **Bảng Hướng Dẫn So Sánh Các Chiến Lược Chunking**

<table><tbody><tr><td colspan="1" rowspan="1"><p><strong>Chiến Lược</strong></p></td><td colspan="1" rowspan="1"><p><strong>Cơ Chế Cốt Lõi</strong></p></td><td colspan="1" rowspan="1"><p><strong>Ưu Điểm Chính</strong></p></td><td colspan="1" rowspan="1"><p><strong>Nhược Điểm Chính</strong></p></td><td colspan="1" rowspan="1"><p><strong>Trường Hợp Sử Dụng Lý Tưởng</strong></p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Fixed-size</strong></p></td><td colspan="1" rowspan="1"><p>Chia văn bản thành các chunk có số lượng ký tự/token cố định.</p></td><td colspan="1" rowspan="1"><p>Đơn giản, nhanh, có thể dự đoán, chi phí tính toán thấp.</p></td><td colspan="1" rowspan="1"><p>Bỏ qua ngữ cảnh ngữ nghĩa, thường phá vỡ câu và ý tưởng, dẫn đến chất lượng truy xuất kém.</p></td><td colspan="1" rowspan="1"><p>Văn bản đồng nhất, phi cấu trúc, nơi tốc độ quan trọng hơn độ chính xác (ví dụ: log đơn giản). Một phương pháp cơ sở nhanh chóng.</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Sentence splitting</strong></p></td><td colspan="1" rowspan="1"><p>Chia văn bản dựa trên các dấu kết thúc câu.</p></td><td colspan="1" rowspan="1"><p>Đảm bảo mỗi chunk là một ý tưởng hoàn chỉnh. Mạch lạc hơn về mặt ngữ nghĩa so với fixed-size.</p></td><td colspan="1" rowspan="1"><p>Kích thước chunk không nhất quán. Một câu đơn lẻ thường thiếu ngữ cảnh đủ cho các truy vấn phức tạp.</p></td><td colspan="1" rowspan="1"><p>Nội dung dạng ngắn hoặc dữ liệu hội thoại nơi các câu riêng lẻ mang ý nghĩa quan trọng.</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Recursive character</strong></p></td><td colspan="1" rowspan="1"><p>Chia văn bản theo tầng bậc bằng một danh sách các dấu phân tách được ưu tiên (ví dụ: đoạn, dòng, từ).</p></td><td colspan="1" rowspan="1"><p>Cân bằng tuyệt vời giữa hiệu suất và sự gắn kết ngữ nghĩa. Cố gắng giữ các văn bản liên quan lại với nhau. Là lựa chọn mặc định mạnh mẽ cho văn bản chung.</p></td><td colspan="1" rowspan="1"><p>Vẫn có thể dẫn đến các lần chia tùy tiện nếu văn bản thiếu cấu trúc rõ ràng và kích thước chunk nhỏ.</p></td><td colspan="1" rowspan="1"><p>Phương pháp nên dùng cho hầu hết các tài liệu văn bản phi cấu trúc (ví dụ: bài báo, báo cáo).</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Structural (markdown / layout-aware)</strong></p></td><td colspan="1" rowspan="1"><p>Chia văn bản dựa trên cấu trúc sẵn có của tài liệu (ví dụ: tiêu đề markdown, bảng biểu pdf, danh sách).</p></td><td colspan="1" rowspan="1"><p>Độ trung thực cao nhất với cấu trúc của tài liệu gốc. Bảo tồn hoàn hảo ngữ cảnh logic và trực quan.</p></td><td colspan="1" rowspan="1"><p>Yêu cầu các bộ phân tích chuyên dụng. Chỉ áp dụng cho các tài liệu có cấu trúc rõ ràng, máy có thể đọc được.</p></td><td colspan="1" rowspan="1"><p>Các tài liệu có cấu trúc cao như tài liệu kỹ thuật (markdown) hoặc các tệp pdf phức tạp (layout-aware).</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Semantic</strong></p></td><td colspan="1" rowspan="1"><p>Sử dụng embedding câu để tìm các "điểm gãy" nơi chủ đề hoặc ý nghĩa của văn bản thay đổi.</p></td><td colspan="1" rowspan="1"><p>Tạo ra các chunk rất mạch lạc, giàu ngữ cảnh dựa trên ý nghĩa, không phải quy tắc. Thích ứng với nội dung của văn bản.</p></td><td colspan="1" rowspan="1"><p>Tốn kém về mặt tính toán. Các nghiên cứu gần đây cho thấy lợi ích về hiệu suất có thể không tương xứng với chi phí trong mọi trường hợp.</p></td><td colspan="1" rowspan="1"><p>Văn bản dày đặc, dạng dài với các thay đổi chủ đề tinh vi, nơi sự mạch lạc ngữ nghĩa tối đa là quan trọng và chi phí không phải là rào cản lớn.</p></td></tr><tr><td colspan="1" rowspan="1"><p><strong>Agentic</strong></p></td><td colspan="1" rowspan="1"><p>Sử dụng một tác tử LLM để phân tích văn bản, trích xuất các mệnh đề và quyết định ranh giới chunk.</p></td><td colspan="1" rowspan="1"><p>Phương pháp nhận biết ngữ cảnh và "thông minh" nhất. Mô phỏng tư duy giống con người để tạo ra các chunk tối ưu.</p></td><td colspan="1" rowspan="1"><p>Mang tính thử nghiệm cao, chi phí tính toán và độ trễ cực cao, phức tạp để triển khai và đưa vào sản xuất.</p></td><td colspan="1" rowspan="1"><p>Các dự án r&amp;d tiên phong; các tình huống đòi hỏi mức độ hiểu biết ngữ cảnh cao nhất tuyệt đối, bất kể chi phí.</p></td></tr></tbody></table>