#### Webinar

[[knowledge graph]] [[QA]]
3-2022
thay vì sử dụng [[structured data]] ta sẽ dùng dạng [[knowledge-base]]
2 câu hỏi
- [[simple]]
- [[complex]] 
[[RDF]]
[[knowledge-base QA]] 


[[knowledge-base]] is trend, massive fact, find answer more quicky, accurate and efficiently.

[[SymSpell]]
normolize
VietnameseTextNormalizer

[[knowledge graph database]] 

Vấn đề:
- Xây dụng vào yếu tố kinh nghiệm
	- Đã có kinh nghiệm về [[knowledge graph]]
	- Nếu ai chưa có kiên thức sẽ mất nhiều thời gian
- không đồng bộ kiến thức.
	- Gây khó khawnh, thachs thức cho việc kiểm tra, phát hiện và chỉnh sửa nội dung
- Mục tiêu:
	- Quy trình hóa nghiệp vụ xậy dựng [[knowledge graph database]]

![[Pasted image 20220401150947.png]]

Lữu trữ độ thì dưới dạng băng

- Quy trình:
	- Phân tích nghiệp vụ
		- tìm kiếm thông tin
			- thực thể: khái niệm biểu diễn 1 [[lớp khái niệm]] trong thế giới thực
				- Trực quan: tồn Tại vật lý
				- Không trực quan: Phi vật lý
			- Thuộc tính
				- Đặc trưng của thực thể
				- có cấu trúc bên trong
				- đặc trưng của mối kết hợp nhiều nhiều
					- Có thông tin ngày mua hàng, số lượng từng đơn hàng
					- ![[Pasted image 20220401151217.png]]
				- Mối kết hợp:
					- ![[Pasted image 20220401151330.png]]
				- Bảng số
					- min, max: số lượng mối quan hệ được tham gia vào quan hệ tối thiểu và tối 
					- ![[Pasted image 20220401151448.png]]
					- ![[Pasted image 20220401151545.png]]
		- Thiết kế:
			- -mô hình thucự thể quan hệ:
			- ![[Pasted image 20220401151656.png]]
			- "Thực thể - mối kết hơp -  thực thể"
		- Lữu trữ dữ liệu:
			- đã xác định thông tin cần lưu trữ
			- Ánh xạ thông tin  ![[Pasted image 20220401151753.png]]
			- Mối kết hợp mở rộng
			- ![[Pasted image 20220401152806.png]]
			- 