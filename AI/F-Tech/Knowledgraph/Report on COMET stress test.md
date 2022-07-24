1. Bot mất khoảng 3-4 giây để trả lời
2. mình có thể đặt rất nhiều câu hỏi và nó trả lời dần
3. Khi mình đặt câu hỏi quá nhanh, nó sẽ để vào 1 hàng đợi và trả lời dần.
4. Vì một lý do nào đó mà vào [[COMET]] mất nhiều thời gian hơn các kênh khác(mất khoảng 8-10 giây để vào, trong khi các kênh khác chỉ mất 1-3 giây)
5. ?? Khi [[DDOS]], người khác có thể nhắn và có được câu trả lời không. -Không người hỏi phải chờ trên 10 giây để có câu trả lời, (15- 25 giây) với tốc độ hỏi của người khác là 1s/q
6. Mức độ Stress ntn thì khiến người khác không thể nhắn tin được. khi người hỏi với tóc độ 1 câu hỏi trên 3 giây.
7. khi hỏi với tốc độ 3 giây trên câu hỏi thì bot bắt đầu queue lại câu hỏi và trả lời dần.(2, 3)
8. với số lượng hỏi lớn thì [[F-Work]] trở nên giấy lag
9. vì lý do nào đó mà [[F-Work]] sử dụng rất nhiều [[CPU]] và [[Ram]].![[Anh.png]]
10. 8, 9 diễn ra khi hỏi quá nhiều trong 1 session.
11. Vì lý do nào đó mà [[COMET]] trả lời nhiều hơn số câu hỏi mà mình đã hỏi.
12. Với tộc độ hỏi 5s/q thì việc hỏi đạp qua lại diễn ra rất mượt mà.
13. Tốc độ xử lý của mô hình hiện tại là khá chậm, chủ yếu là do số lượng parameter của mô hình hiện tại khá cao. và có thể do delay trong hệ thống.
14. Vì một lý do nào đó mà [[COMET]] tự động nhắn câu trả lời trong khi mình không hề đặt câu hỏi, + 11![[Pasted image 20220418154132.png]]
15. Khi khối lượng chat với bot quá nhiều thì sẽ mất nhiều thời gian đợi load COMET.

Đề xuất:
- Nên có một function để kiểm tra tóc độ gửi tinh nhắn từ người dùng đến comet nói riêng và đến các kênh khác nói dung để tránh tình trạng để tránh DDOS nội bộ, hoặc khi đưa lên product. (2, 3, 4, 5, 6, 7, 8)
- Nên cải thiện tốc độ trả lời của bot. hiên tại chỉ chịu được 1 câu hỏi mỗi 4 giây (4s/q)
- Nên đưa tốc độ trả lời câu hỏi trở thành một tiêu chi để đánh giá mô hình. Một mô hình có độ chính xác 94% nhưng cho tốc độ trả lời 4s/q thì việc áp dụng trong thực tế là bất khả thi. Để xuất tốc độ trả lời câu hỏi ít nhất là 1q/s
- 8, 9, 10: Nên giới hạn lại số lượng load tin nhắn trong session.
