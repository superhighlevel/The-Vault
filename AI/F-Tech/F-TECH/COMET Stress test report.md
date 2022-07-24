

--- 
Abstract

Author

Lê Văn Hiếu ([levanhieu231@gmail.com](mailto:levanhieu231@gmail.com)) 

Period

18/4/2022 - 19/04/2022

---
### Tổng quan.
Với việc dự án F-School đã có những tiến triển tốt trong thời gian qua. Team đã thành công trong việc tạo ra được một hệ thống trả lời câu hỏi liên lý thuyết quan tới các môn học bao gồm Toán, Lý, Hóa, KHTN. Việc đánh giá và kiểm nghiệm mô hình trước khi triển khai vào sản phẩm thực tế là điều cần thiết. Do đó, các thành viên trong nhóm dự án VA [[F-School]] đã thực hiện kết nối mô hình với với [[F-Work]] là [[COMET]] để tiến hành kiểm tra mô hình bằng tay.
Trong quá trình đánh giá mô hình, tôi nhân thấy mô hình cấn được thực hiện một bài kiểm tra hiệu năng hệ thống. Bài kiểm tra này liên quan tới tốc độ xử lý câu hỏi, phản hồi của hệ thống. Bài kiểm tra này sẽ kiểm tra xem hệ thống sẽ xử lý như thế nào trước các tính huống như sau:
- Nhiều người đồng thời nhắn tín, hỏi COMET cùng một lúc.
- 1 người hỏi rất nhiều câu hỏi cùng một lúc với tần suất cao.
- Có người cố ý phá hoại hệ thống bằng cách gửi rất nhiều gói tin, hay ở đây là tin nhắn tới hệ thống.
- Các trường hợp liên quan nhưng không thể để cập tới ở đây
Việc kiểm tra các trường hợp trên sẽ giúp ta có cái hình tổng quan về tính năng cũng như là hiệu năng của hệ thống. Răng, hệ thống có thể chịu được tần suất gửi tin nhắn liên tục với độ ổn định cao hay không.
Lưu ý, bài kiểm tra này không đánh giá độ chính xác của mô hình.
### Cách thức tiến hành.
Cách thức tiến hành kiểm tra hệ thống khá đơn gian bao gồm các bước như sau:
1. Chuẩn bị bộ câu hỏi(có nghĩa hoặc vô nghĩa)
2. Lấy câu hỏi từ bộ câu hỏi trên và gửi tin nhắn đến [[COMET]] trong [[F-Work]]
3. Lặp lại bược 2 với tần suất cao theo ý người kiểm tra (1 câu hỏi trên 1->5 giây)
4. Dừng lại khi đạt số vòng lặp hay theo lệnh của người kiểm tra.
### Đánh giá
Sau khi tiên tiến hanh bài kiểm tra trên. Ta có được một số đánh giá như sau:
1. Thời gian phản hồi trung bình từ khoảnh khắc gửi tin nhắn đến lúc COMET đưa ra câu trả lời là: 3-4 giây.
2. Với tộc độ hỏi khoảng 4-5 giây/câu hỏi thì việc test diễn ra bình thường.
3. Ta có thể đặt rất nhiều câu hỏi cho COMET cùng một lúc và COMET sẽ trả lời dần. Khi hỏi với tốc độ 3 giây/câu hỏi thì bot không thể trả lời các câu hỏi ngay mà sẽ trả lời dần. Khi đó, dưa vào cảm quan, bot đã để câu hỏi vào một hàng đợi, và tiến hành trả lời dần các câu hỏi đó cho đến khi hết câu hỏi. 
4. Người dùng khác sẽ đợi lâu hơn khi đặt câu hỏi: Khi COMET đang trả lời các câu hỏi trong hàng đợi(3.), thì các người dùng khác nhắn tin vào COMET trong giời gian chạy bài kiểm tra sẽ có thời gian chờ để có câu hỏi lâu hơn đáng kể. Thời gian chờ nói trên nhanh nhất là trên 10 giây, lâu hơn là trên 25 giây so với thời gian đợi trung bình là 3-4 giây(1.)
5. Trong quá trình kiểm tra, nhận thầy rằng khi số lượng câu hỏi đã được hỏi lớn, trong trường hợp này là trên 150 câu. Thì F-work phải sử dụng nhiều CPU và RAM để lưu lại các câu hỏi - trả lời trước. Khi đó việc truy cập vào COMET trở nên tốn thời gian, mất khoảng 8-10 giây để vào, trong khi các kênh khác chỉ mất 1-3 giây. Tuy nhiên việc này chi diễn ra trên một session, sau khi tắt hoàn toàn F-work và mở lại thì hiện tượng này biến mất.
6. Một điểm bất thường khác trong quá trình kiểm tra là, vì lý do nào đó mà COMET trả lời nhiều hơn số câu hỏi mà mình đã hỏi. Và COMET tự động nhắn câu trả lời trong khi mình không hề đặt câu hỏi.![[FWork_naMn68hMpr.png]]
### Đề xuất.
- Nên có một hàm để kiểm tra tốc độ gửi tin nhắn từ người dùng đến COMET nói riêng và đến các kênh khác nói chung của F-work để tránh tình trạng để tránh nguy cơ bị hack, hoặc khi đưa lên product sẽ tránh được DDOS. (2, 3, 4, 5)
- Nên cải thiện tốc độ trả lời của Mô hình hiện tại. Hiện mô hình chỉ có thể chịu được 1 câu hỏi mỗi 3-4 giây(1.)
- Nên đưa tốc độ trả lời câu hỏi trở thành một tiêu chí để đánh giá mô hình. Một mô hình có độ chính xác cao (94%) nhưng cho tốc độ trả lời 4s/q thì việc áp dụng trong thực tế là bất khả thi. Để xuất tốc độ trả lời câu hỏi ở mức baseline là 1 câu hỏi trên giây
- Nên giới hạn lại số lượng load tin nhắn trong khi thực hiện 1 session. (5.)

