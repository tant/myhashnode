---
title: "Kế hoạch tối ưu khả năng gửi mail cho tên miền mới"
seoTitle: "Lộ trình chuẩn bị tên miền mới để gửi Email Marketing thành công"
seoDescription: "Email của bạn đang vào thư mục spam? Khám phá lộ trình làm ấm tên miền từ A-Z, giúp tăng tỷ lệ vào inbox và xây dựng uy tín cho chiến dịch email marketing."
datePublished: Sun Jul 13 2025 15:03:54 GMT+0000 (Coordinated Universal Time)
cuid: cmd1t1ope000102jvamy83zvm
slug: ke-hoach-toi-uu-kha-nang-gui-mail-cho-ten-mien-moi
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/D2TZ-ashGzc/upload/af261e2d074ce122ff072cd361c797fc.jpeg
tags: email-marketing

---

**Mục tiêu:** Xây dựng một nền tảng vững chắc và uy tín bền vững cho tên miền [`yourdomain.name`](http://yourdomain.name), đảm bảo email gửi đi có tỷ lệ vào Hộp thư đến (Inbox) cao nhất và tránh bộ lọc Spam. Kế hoạch này là một checklist chi tiết từ khâu chuẩn bị kỹ thuật ban đầu đến việc duy trì và tối ưu hóa lâu dài.

# **Giai đoạn 1: Thiết lập nền tảng kỹ thuật**

**Mục tiêu:** Khẳng định với các nhà cung cấp dịch vụ email (Google, Microsoft...) rằng [`yourdomain.name`](http://yourdomain.name) là một doanh nghiệp hợp pháp, có sự đầu tư nghiêm túc và đáng tin cậy về mặt kỹ thuật.

## **1\. Thiết lập nhận mail (qua Cloudflare Email Routing)**

* **Mục đích:** Sử dụng giải pháp miễn phí và hiệu quả để chuyển tiếp (forward) tất cả email gửi đến `@`[`yourdomain.name`](http://yourdomain.name) về một địa chỉ email cá nhân (ví dụ: [`emailcuaban@gmail.com`](mailto:emailcuaban@gmail.com)) mà không cần trả phí cho hộp thư.
    
* **Hành động cần làm:**
    
    * Đảm bảo tên miền [`yourdomain.name`](http://yourdomain.name) đang sử dụng Nameserver của Cloudflare.
        
    * Trong dashboard Cloudflare, vào mục "Email" -&gt; "Email Routing" và kích hoạt.
        
    * Xác nhận và thêm các bản ghi MX mà Cloudflare tự động đề xuất.
        
    * Tạo một quy tắc "catch-all" để chuyển tiếp *tất cả* email về địa chỉ email cá nhân của bạn.
        
* **Tiêu chí hoàn thành:** Gửi một email thử nghiệm đến [`test@yourdomain.name`](mailto:test@yourdomain.name) và nhận được email đó trong hộp thư cá nhân.
    

## **2\. Thiết lập gửi mail (qua Brevo)**

* **Mục đích:** Cấu hình Brevo để có thể gửi email marketing và email giao dịch một cách hợp lệ từ địa chỉ `@`[`yourdomain.name`](http://yourdomain.name).
    
* **Hành động cần làm:**
    
    * Trong Brevo, vào "Senders & IP" và thêm một Sender mới (ví dụ: [`tenban@yourdomain.name`](mailto:tenban@yourdomain.name)).
        
    * Kiểm tra hộp thư cá nhân để nhận email xác thực từ Brevo và click vào link.
        
    * (Tùy chọn) Vào "SMTP & API" để lấy khóa API nếu cần tích hợp gửi mail tự động.
        
* **Tiêu chí hoàn thành:** Sender trong Brevo có trạng thái "Verified".
    

## **3\. Xác thực tên miền (SPF, DKIM, DMARC)**

* **Mục đích:** Chứng minh email gửi từ Brevo thực sự là của bạn, ngăn chặn giả mạo và xây dựng lòng tin cơ bản với các bộ lọc spam.
    
* **Hành động cần làm:**
    
    * **SPF & DKIM:** Lấy giá trị từ Brevo và tạo các bản ghi `TXT` tương ứng trong DNS của bạn.
        
    * **DMARC:** Tạo bản ghi `TXT` cho `_`[`dmarc.yourdomain.name`](http://dmarc.yourdomain.name) với chính sách khởi đầu an toàn: `p=none`. Đây là chế độ giám sát, không tác động đến luồng mail.
        
* **Tiêu chí hoàn thành:** Sử dụng MXToolbox để kiểm tra, cả 3 bản ghi đều báo cáo **Pass** hoặc **Published**.
    

## **4\. Cấu hình miền Return-Path tùy chỉnh**

* **Mục đích:** Đồng bộ hóa hoàn toàn thương hiệu của bạn trong mọi khía cạnh kỹ thuật của email, tăng cường uy tín.
    
* **Hành động cần làm:**
    
    * Trong Brevo, tìm mục "White Label" hoặc "Custom Bouncing Domain".
        
    * Tạo một tên miền phụ (ví dụ: [`bounce.yourdomain.name`](http://bounce.yourdomain.name)) và thêm bản ghi DNS theo hướng dẫn.
        
* **Tiêu chí hoàn thành:** Gửi email thử nghiệm và kiểm tra header, thấy dòng `Return-Path` trỏ về [`bounce.yourdomain.name`](http://bounce.yourdomain.name).
    

# **Giai đoạn 2: Xây dựng "làm ấm" tên miền**

**Mục tiêu:** Gửi tín hiệu tích cực đến các thuật toán chống spam rằng email từ [`yourdomain.name`](http://yourdomain.name) được người nhận mong muốn và có tương tác tốt, thông qua một quá trình tăng trưởng có kiểm soát.

## **1\. Lên kế hoạch "Làm ấm"**

* **Hành động cần làm:**
    
    * **Danh sách:** Lập danh sách từ 10-15 địa chỉ email tin cậy mà bạn có toàn quyền kiểm soát (quan trọng nhất là Gmail và Outlook).
        
    * **Lịch trình:** Soạn lịch gửi tăng dần trong 2-3 tuần (ví dụ: Tuần 1: 10-20/ngày; Tuần 2: 40-50/ngày...).
        
    * **Nội dung:** Soạn 3-4 mẫu email đơn giản, có giá trị để gửi luân phiên.
        
* **Tiêu chí hoàn thành:** Có danh sách, lịch trình và nội dung sẵn sàng để bắt đầu.
    

## **2\. Thực thi & Tương tác**

* **Hành động cần làm:**
    
    * Bắt đầu gửi email theo lịch trình đã định.
        
    * Với **mỗi email nhận được** trong danh sách "làm ấm", hãy chủ động thực hiện các hành động sau: Mở email, Click vào một liên kết (nếu có), Trả lời (Reply) email, và quan trọng nhất là Đánh dấu "Không phải Spam" nếu email vô tình vào thư rác.
        
* **Tiêu chí hoàn thành:** Hoàn thành lịch trình gửi trong ít nhất 2 tuần. Tỷ lệ email vào Inbox đạt &gt;95%. Không có email nào bị tự động đánh dấu là spam trong 3 ngày cuối.
    

# **Giai đoạn 3: Duy trì & Tối ưu hóa**

**Mục tiêu:** Duy trì uy tín đã xây dựng và tối ưu hóa liên tục để đảm bảo hiệu quả lâu dài cho các chiến dịch, đồng thời tăng cường bảo mật.

## **1\. Quản lý chất lượng danh sách**

* **Hành động cần làm:** Luôn dùng Double Opt-in, dọn dẹp danh sách không tương tác định kỳ (3-6 tháng), cung cấp liên kết hủy đăng ký rõ ràng và bảo vệ biểu mẫu đăng ký bằng CAPTCHA.
    
* **Tiêu chí hoàn thành:** Tỷ lệ khiếu nại spam (Spam Complaint Rate) luôn dưới 0.1%.
    

## **2\. Tối ưu nội dung & Cấu trúc email**

* **Hành động cần làm:** Sử dụng địa chỉ Reply-to thật, cân bằng tỷ lệ văn bản/hình ảnh, tránh các yếu tố "spammy" (link rút gọn, file đính kèm, tiêu đề VIẾT HOA) và dùng mã HTML sạch.
    
* **Tiêu chí hoàn thành:** Email chuyên nghiệp, hiển thị tốt trên nhiều thiết bị.
    

## **3\. Giám sát uy tín liên tục**

* **Hành động cần làm:** Sử dụng Google Postmaster Tools, MXToolbox để theo dõi uy tín; phân tích báo cáo trong Brevo (tỷ lệ mở, click, bounce) và thực hiện A/B Testing.
    
* **Tiêu chí hoàn thành:** Nắm rõ các chỉ số hiệu suất và có kế hoạch hành động khi cần.
    

## **4\. Nâng cấp chính sách DMARC**

* **Mục đích:** Chuyển đổi chính sách DMARC từ chế độ giám sát sang chế độ bảo vệ hoàn toàn một cách an toàn, tránh chặn nhầm email hợp lệ.
    
* **Hành động cần làm:**
    
    1. **Bước 1: Giám sát với** `p=none` (2-4 tuần).
        
        * **Mục tiêu:** Thu thập dữ liệu mà không gây ảnh hưởng.
            
        * **Thực hiện:** Giữ nguyên chính sách `p=none`. Sử dụng một dịch vụ phân tích báo cáo DMARC (như Postmark, Dmarcian) để đọc các báo cáo được gửi về. Các báo cáo này sẽ cho thấy tất cả các nguồn (IP) đang gửi email nhân danh bạn và liệu chúng có vượt qua SPF/DKIM hay không.
            
    2. **Bước 2: Phân tích và Sửa lỗi.**
        
        * **Mục tiêu:** Đảm bảo tất cả các nguồn gửi hợp lệ đều được xác thực đúng.
            
        * **Thực hiện:** Dựa trên báo cáo, nếu thấy một nguồn gửi hợp lệ (ví dụ: website, CRM) bị lỗi xác thực, hãy cập nhật lại bản ghi SPF hoặc cấu hình DKIM cho nguồn đó. Lặp lại cho đến khi tất cả các nguồn hợp lệ đều báo cáo "Pass".
            
    3. **Bước 3: Nâng cấp lên** `p=quarantine` (2-4 tuần).
        
        * **Mục tiêu:** Bắt đầu cách ly các email đáng ngờ.
            
        * **Thực hiện:** Khi đã chắc chắn 100% các nguồn gửi hợp lệ đã được xác thực, hãy cập nhật bản ghi DMARC thành `p=quarantine`. Chính sách này sẽ chỉ thị cho các máy chủ nhận đưa những email không qua được xác thực vào thư mục Spam. Tiếp tục theo dõi báo cáo để đảm bảo không có email hợp lệ nào bị ảnh hưởng.
            
    4. **Bước 4: Nâng cấp lên** `p=reject`.
        
        * **Mục tiêu:** Chặn hoàn toàn email giả mạo.
            
        * **Thực hiện:** Đây là bước cuối cùng và là mức bảo vệ cao nhất. Cập nhật bản ghi DMARC thành `p=reject`. Từ thời điểm này, các email giả mạo tên miền của bạn sẽ bị từ chối thẳng thừng.
            
* **Tiêu chí hoàn thành:** Bản ghi DMARC được thiết lập ở mức `p=reject`, bảo vệ tối đa cho thương hiệu của bạn.