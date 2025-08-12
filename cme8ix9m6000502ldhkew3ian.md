---
title: "Đâu có dễ ăn"
datePublished: Tue Aug 12 2025 12:34:37 GMT+0000 (Coordinated Universal Time)
cuid: cme8ix9m6000502ldhkew3ian
slug: dau-co-de-an
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1755001604806/1c7b4eeb-98ce-4ce7-979a-fd19cfcace19.png
tags: bugs-and-errors

---

Hôm nay họp do chủ tịch Next điều hành, là một nhà quản lý trẻ tuổi, cực kỳ giỏi giang và nguyên tắc. Triết lý của ông là "hiệu suất tuyệt đối". Trước mỗi cuộc họp, ông yêu cầu tất cả các thành viên phải nộp toàn bộ tài liệu, báo cáo và phụ lục. Mọi thứ được đánh số, sắp xếp và đóng thành một tập hồ sơ duy nhất, không thể thay đổi. Chương trình nghị sự một khi đã chốt là bất biến. Đây chính là quá trình "build" của Next.js.

Trong cuộc họp hôm nay, có một khách mời đặc biệt: Tiến sĩ Gen, một chuyên gia ai lừng danh từ phòng thí nghiệm của google. Ông được mời đến để trình bày một giải pháp đột phá. Đi cùng ông là Express, người trợ lý trung thành nhưng có phần cổ điển, đã làm việc với ông từ rất lâu.

Chủ tịch Next bắt đầu cuộc họp: "Chào mừng tất cả mọi người. Hồ sơ cuộc họp đã được chốt. Chúng ta sẽ đi theo đúng chương trình nghị sự đã được phê duyệt."

Đến lượt Tiến sĩ Gen phát biểu, chủ tịch Next quay sang và nói: "Thưa tiến sĩ, chúng tôi rất vinh dự. Xin hãy xác nhận mọi tài liệu trình bày của ông đều đã có trong tập hồ sơ đã nộp."

Tiến sĩ Gen chuẩn bị gật đầu thì người trợ lý Express bỗng lên tiếng: "Thưa chủ tịch, mọi tài liệu chính đều đã đủ. Chỉ có một chi tiết nhỏ, đôi khi trong lúc trình bày, Tiến sĩ sẽ cần một biểu đồ minh họa mà chúng tôi không thể biết trước được. Xin cứ ghi vào biên bản là 'một biểu đồ sẽ được chỉ định sau'."

Yêu cầu này chính là dòng code `require(mod)` trong lỗi trên

Ngay lập tức, Chủ tịch Next gõ mạnh xuống bàn, vẻ mặt nghiêm lại. "Không thể được! Điều này vi phạm nghiêm trọng quy tắc của hội đồng. Chương trình nghị sự là bất biến. Không có mục nào tên là 'sẽ được chỉ định sau'. Cuộc họp không thể tiếp tục với một yêu cầu không xác định."

Ông tuyên bố: "Cuộc họp sẽ bị hoãn cho đến khi văn phòng của Tiến sĩ Gen cung cấp được danh sách chính xác của tất cả các biểu đồ cần thiết."

Thông báo lỗi `module not found` chính là biên bản hoãn họp đó. Quy trình của chủ tịch Next không thể tìm thấy "biểu đồ chưa xác định" trong tập hồ sơ đã được đóng gói sẵn của mình. Vấn đề không phải do Tiến sĩ Gen hay trợ lý Express làm sai, mà vì cách làm việc linh hoạt "đến đâu tính đến đó" của họ hoàn toàn xung đột với quy trình cứng nhắc "mọi thứ phải biết trước" của Chủ tịch Next.

Và tôi gỡ genkit ra và gọi trực tiếp API của google luôn. Dạo này trải nghiệm kém, định dùng SDK của brevo thì thấy package bị depricated rồi không xài được, nhào vô định fix luôn thì thấy các bạn xài OpenAI để gen ra nên thôi lại bỏ gọi trực tiếp API luôn. Giờ tới genkit mặc dù còn vài cách xử lý nữa nhưng thôi, lại gọi thẳng cho rồi