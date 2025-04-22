---
title: "Làm sao để code sạch"
datePublished: Thu Oct 27 2022 04:06:42 GMT+0000 (Coordinated Universal Time)
cuid: cl9qjn6ns000809l50xhwa82h
slug: lam-sao-de-code-sach
tags: coding

---

Tuần trước gặp một ca khó, anh sếp dẫn theo bạn head IT để trình bày về tình trạng phần mềm hiện tại xem có thể làm gì được không. Bạn IT liên tục nói rất nhiều chữ “code sạch” với ngụ ý là bạn yêu cầu nhà cung cấp code from scratch không dùng bất kì một library hay framework nào !!!??. Sau khi xem xét sơ bộ xong tôi kẹt luôn giữa ngã 3 ở chuyện khuyên nên bỏ cái code hiện tại và làm lại từ đầu với các nền tảng vững chắc an toàn hơn hoặc cố đấm ăn xôi phát triển tiếp dựa trên codebase hiện tại.

Nhưng đó là chuyện của tương lai và bài viết này chỉ để giúp hiểu đúng chút thế nào là code sạch hay clean code một cách đúng đắn.

Nếu bạn chịu khó google, bạn sẽ có rất nhiều bài viết, clip, thậm chí nhiều sách nói về code sạch hay các nội dung tương tự vì đây là cái việc nói hoài không hết. Tôi sẽ để dành cho bạn tận hưởng theo cách của mình và chỉ cung cấp thêm quan điểm của chính mình về việc này

Bản chất của code sạch không đơn thuần là việc NÊN sử dụng các thư viện hay framework nào mà chính là bạn viết code sao cho dễ duy trì, nâng cấp hơn sau này thôi. Muốn vậy bạn phải đảm bảo làm sao cho người tiếp quản hoặc chính bạn vài tháng sau, có thể hiểu được bạn đã viết được gì dễ dàng, chính xác, nhanh chóng. Do đó, việc sử dụng thư viện, framework phần nào cũng giúp cho code của bạn sạch hơn ở hai lý do:

* Nó đóng gói lại những phần code đã viết rất tốt, đã được test kĩ và verify với rất nhiều ứng dụng và ở nhiều hoàn cảnh do nhiều người nên bạn không cần quan tâm xuống chi tiết nó viết sao mà vẫn chạy đúng và an toàn
    
* Nó áp bạn vào những kiểu viết phổ biến, giúp cho các lập trình viên dễ hiểu và gần nhau hơn vì cứ tin tôi đi là viết không ai đọc nổi thì chả mấy ai dám tham gia vào viết chung với bạn nhất là trong giới opensource
    

Tuy nhiên code sạch hay không chủ yếu vẫn nằm ở từng dòng hay từng khối code của bạn nên mình đề xuất vài nguyên tắc sau

## Mỗi dòng một việc

Đây là cái dễ phạm phải nhất bắt nguồn từ ý tưởng cho rằng viết ngắn dễ đọc dễ nắm hơn viết dài. Ý tưởng này không sai nhưng lại thường hay được dùng sai

Ví dụ đây là kiểu viết một dòng

```python
x, y = 2, 7
```

Còn đây là kiểu viết hai dòng

```python
x = 2
y = 7
```

Bạn sẽ tự có khẩu vị của mình nhưng nếu tuyển lập trình viên tôi sẽ tuyển người viết kiểu sau nha.

Ví dụ set giá trị của biến ở trên đơn giản để giải thích nên viết mỗi dòng một việc. Nhưng thực tế bạn sẽ gặp các ca rất rất khó, với những kiểu viết mới (thường trong các ngôn ngữ lập trình hiện đại) như sau

```python
map(lambda x: x.split('=')[1], s.split('?')[1].split('&')[-3:])
```

Đây là nỗi đau của mình khi chuyển đổi từ các ngôn ngữ cao tuổi như C/C++, Basic… qua javascript. Cho nên nguyên tắc nguyên tắc thứ hai bên dưới có phạm vi ứng dụng cao hơn

## Mỗi dòng nên có ít hơn 6 thứ (khái niệm, đối tượng)

Quay lại với dòng code trên, ai học xong lập trình python cơ bản đều biết các thứ trong đó

1. map : chạy một hàm với một loạt giá trị tham số
    
2. lamda: viết hàm inline
    
3. .split : tách chuỗi
    
4. biến x
    
5. biến s
    
6. chuỗi ‘=’
    
7. chuỗi ‘?’
    
8. chuỗi ‘&’
    
9. \[1\]: là phần tử thứ hai trong list (python tính 0)
    
10. \[-3:\] là ba phần tử cuối cùng trong list
    

Tuy nhiên để nạp và diễn dịch 10 thứ cùng lúc như vầy não không thể đáp ứng nổi. Thật sự nếu bạn biết python bạn đọc xong cái này có thể hiểu được nó chạy ra sao không?

Felienne Hermans trong cuốn [*The Programmer’s Brain*](https://www.manning.com/books/the-programmers-brain?utm_source=somacdivad&utm_medium=affiliate&utm_campaign=book_hermans2_programmers_12_8_20&a_aid=somacdivad&a_bid=d7c7c538) đề cập não chỉ xử lý được tối đa 6 thứ thôi cho nên chúng ta tốt hơn nên chia nhỏ code này ra thành nhiều dòng

## Khi code bạn có dấu hiệu rối hãy chia nhỏ ra

Dùng các biến trung gian, đặt tên có ý nghĩa sẽ giúp rất nhiều cho lập trình viên khác duy trì code của bạn và phát triển nó thêm. Cũng với câu lệnh trên có thể chia nó ra như sau

```python
query_params = s.split('?')[1].split('&')[-3:]
map(lambda x: x.split('=')[1], query_params)
```

Với dụng ý tôi sẽ tách các params ra trước rồi tôi làm gì đó tiếp theo. Hay nhiều dòng hơn nữa như bên dưới là sẽ lấy nguyên cụm query ra trước, sau đó tách ra các param

```python
url_query_string = s.split('?')[1]
query_params = url_query_string.split('&')[-3:]
map(lambda x: x.split('=')[1], query_params)
```

Hoặc là đưa khối code vào các hàm vừa tái sử dụng được vừa dễ kiểm soát chất lượng như sau

```python
def query_params(url):
    return url.split('?')[1].split('&')[-3:]

map(lambda x: x.split('=')[1], query_params(s))
```

Hay kiểu này

```python
def query_params(url):
    query_string = url.split('?')[1]
    return query_string.split('&')[-3:]
    
map(lambda x: x.split('=')[1], query_params(s))
```

Bạn có cảm giác là nắm được nhiều thông tin hơn về khối lệnh này không? Cho dù bạn không thật sự giỏi python hay có cái đầu nhanh nhạy như những lập trình viên khác. Hãy dùng cách này thật nhiều nha và nó sẽ giúp cho thế giới có nhiều phần mềm tốt hơn

Tuy nhiên những giải pháp này vẫn còn chưa tối ưu do vẫn có nhiều hơn 6 thứ một dòng. Bạn có cách nào xử lý khác không? Gợi ý là bạn phải tìm cách hiểu được lệnh này làm gì rồi sau đó viết lại một cách hoàn toàn khác theo các nguyên tắc trên

## Comment, comment và comment

Tôi rất khổ sở phải đọc code không có comment nào. Nó gây thách thức cho cả những lập trình viên nhiều kinh nghiệm nhất cho nên trừ phi tích tụ nghiệp là đam mê của bạn, hãy cố gắng comment code của mình chu đáo một chút để tích đức nha.

Ví dụ tôi thích viết kiểu kia 1 dòng để thể hiện trình độ thông thạo ngôn ngữ của mình vẫn không sao nếu tôi có thể thêm cái comment như sau

```python
# Lấy ra các giá trị tham số trong url
# giả sử s = "https://example.com/path/to/page?name=ferret&color=purple"
# thì sẽ trả về ferret và purple
values = map(lambda x: x.split('=')[1], s.split('?')[1].split('&')[-3:])
print(list(values))
```

Mô tả input và output của một đoạn code cũng rất có giá trị rồi nhưng tốt hơn nữa bạn nên thêm vào giải thuật của đoạn đó

Dĩ nhiên tốt nhất vẫn là kiểu viết các dòng lệnh đơn giản hơn và từ đó cũng tiết kiệm được công sức comment, chỉ comment cho từng khối code hay các dòng quá phức tạp, cốt lõi của đoạn.

Tuy nhiên cho dù vậy, giải pháp ở đây không phải là giải pháp tối ưu mà bạn nên code cho vấn đề này vì bạn đang phát minh lại bánh xe. Chưa kể là bạn chưa nắm hết mọi ngóc ngách, tình huống làm cho solution của bạn sai và tạo nên bug vì vậy lời khuyên là tận dụng các thư viện có sẵn hơn là tự code

## Hãy dùng thư viện, framework khi có thể

Khi có một nhiệm vụ bạn có hai lựa chọn (không tính việc thuê ai khác code dùm cho nha)

* Tự nghĩ giải pháp/giải thuật xong code theo hướng của của mình.
    
* Bỏ thời gian ra tìm hiểu thư viện của người ta đã viết và dùng nó
    

Rõ ràng cách nào cũng tốn thời gian, khi bạn không bỏ thời gian tìm hiểu thư viện thì bạn phải ngồi nghĩ solution mà nhiều lúc tự nghĩ ra lại nhanh hơn. Tuy nhiên bạn phải để ý là:

* Thư viện sẽ được cập nhật, tối ưu liên tục hơn code của bạn và tuổi đời của nó cũng lâu hơn, va vấp nhiều rồi nên trừ phi bạn là thần đồng còn lại code của bạn gần như thua của người ta
    
* Thay vì ngồi nghĩ solution thì bạn chỉ cần tập trung vào cách sử dụng hơn và giao trứng cho người ta (người ta là ác hay không ác sẽ nằm trong bài viết khác về lựa chọn thư viện/framework)
    

Với yêu cầu như trên là muốn lấy các giá trị tham số trong url, và viết theo kiểu trên thì tôi gặp vấn đề với url như sau

```plaintext
url = "https://example.com/path/to/page?name=ferret&color=purple&color=brown"
```

Vì thiết kế của url query cho phép mình truyền nhiều giá trị vào một param nên khi giải pháp của tôi có thể gặp vấn đề. Nếu tôi dùng thư viện thì lại không sao như đoạn dưới

```plaintext
>>> from urllib.parse import urlparse
>>> from urllib.parse import parse_qs
>>> url = "https://example.com/path/to/page?name=ferret&color=purple"
>>> parsed_url = urlparse(url)
>>> print(parsed_url)
ParseResult(scheme='https', netloc='example.com', path='/path/to/page', params='', query='name=ferret&color=purple', fragment='')
>>> cv = parse_qs(parsed_url.query)
>>> print(cv)
{'name': ['ferret'], 'color': ['purple']}
>>> print(type(cv))
<class 'dict'>
>>> print(cv.values())
dict_values([['ferret'], ['purple']])
```

Ý nghĩa ở đây là bạn sẽ thấy người ta viết phần này rất tốt rồi, value của một param được trả về là một list cho nên chấp hết các tình huống và bạn có một cái dict để làm việc của mình rồi muốn sao cũng được.

Còn cách cũ thì bạn sẽ gặp vấn đề với output ra cần phải xử lý thêm.

### Mẹo tăng tốc, code nhanh hơn người khác

Khi bạn gặp một task cần xử lý, tốt nhất hãy google ví dụ như cùng yêu cầu trên thay vì ngồi nghĩ solutions thì tôi sẽ google câu “python get param values from url string”

Các lập trình viên trên thế giới sẽ chia sẻ cách họ đã/sẽ làm cái này như thế nào. Tuy nhiên hãy ưu tiên chọn những cách nào sử dụng thư viện có sẵn của python trước. Sau đó hãy chọn những cách viết các lệnh, nếu là các lệnh phức tạp thì hãy đảm bảo nó đúng ý mình.

Đừng vội vã copy đoạn code đó và tích hợp vào code của mình mà hãy

* Tìm cách hiểu người ta viết gì
    
* Đọc thêm 1 chút về nhận xét của người khác về giải pháp đó trong reply đó
    
* Tham khảo thêm các giải pháp đề xuất khác bên dưới vì không hẳn cái nào được vote nhiều nhất là ngon nhất với mình
    

Thời gian này bỏ ra không phí đâu nhất là khi bạn có thể sử dụng thư viện có sẵn để giải quyết vấn đề. Sau đó bạn cứ thế dùng tiếp các thư viện đó mà không cần duy trì code cũ của mình (nhất là nó không phải là best code của thần đồng viết)

Và hãy tham gia trả lời câu hỏi của người khác khi có dịp. Đó là con đường để viết code giỏi hơn mà còn giúp đỡ được cộng đồng