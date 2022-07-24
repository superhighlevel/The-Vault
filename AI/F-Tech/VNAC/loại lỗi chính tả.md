---
aliases: Vietnamese
tag: AI, NLP, VNAC
date: 04-06-2022
---
### Loại lỗi chính tả
- Lỗi [[Chính tả]] thuần
	- Lỗi viết hoa: 
		- Viết hoa sai quy định chính tả: Lão hạc --> Lão Hạc
		- Viết hoa tùy tiện: Tôi Là một người Mẫu --> Tôi là một người mẫu
	- Lỗi viết tắt:
		- Viết tắt sai quy định chính tả: đ/c, T.N.V.N --> ĐC, TNVN (đồng chí, thanh niên Việt Nam)
		- Viết tắt tùy tiện: phg pháp: Phương pháp, tình thg: tình thương,..
	- Lỗi dùng số và chữ biểu thị số:
		- Lẫn lộn hai loại số: nhẫm lần giữa: số thường và số la mã: Đồng 2 --> Đồng II
		- Lẫn lộn số và chữ biểu thị số: Ngày 8, tháng hai; 1 cuộc sống; cuộc gặp gỡ thứ I,… Theo quy định chính tả, phải viết: Ngày 8, tháng 2; một cuộc sống; cuộc gặp gỡ thứ nhất,…
	- [[Lỗi chính tả âm vị]]: 
		- [[Lỗi chính tả âm vị siêu đoạn tính]]: Lảng mạng, nỗi bật, (khác) hẵn, vội vả, chán nãn, diển đạt,...
		- [[Lỗi chính tả âm vị đoạn tính]]: 
			- [[Ghi sai phụ âm đầu]]: l/đ: long lanh/đong đanh, đung đưa/lung lưa, ...
			- [[Ghi sai âm đệm]]: đấy/đáy, sân trường/sơn trường,...
			- [[Ghi sai âm chính]]: /â/ơ/a/: xâm lược/xơm được,...; iu/êu/ iêu: nâng niu/nâng niêu, tiềm ẩn/tìm ẩn; giữa o/oo - ô/ôô: không thấy --> khôông tháy, ...
			- [[Ghi sai phụ âm cuối /bán nguyên âm cuối]]: 
				- Thứ nhất, các từ kết thúc bằng các phụ âm: /p, t, c, k, i, y/. Ví dụ: tuổi tác/tuổi tát, thân thuộc/thân thuận, mặt chị đỏ lên/mặc chị đỏ đên,...
				- Thứ hai, các từ kết thúc bằng các phụ âm: /m, n, ŋ, nh/. Ví dụ: quãng đời/quãnh đời/quáng đời, ghẻ lạnh/ghẻ lạng, Xuân Quỳnh/Xuân Quyền,...
- Lỗi ngữ pháp
#### Guide line
1. Không quan tâm chữ hoa chữ thường
#### Các trường hợp lỗi trong tập dữ liệu cụ thể
1. Đúng dấu chính tả toàn bộ
2. Không dấu toàn bộ câu
3. Có dấu nhưng sai chính tả toàn bộ câu
4. 20-80% số tự trong câu sai chính tả rời vào một hoặc tất cả các trường hợp sau:
	1. Sai thanh điệu: Ngang, huyền, sắc, hỏi, ngã, nặng
	2. Lỗi phụ âm đầu: ch - tr, h - th, s - x, gi - d - r, n - l, đ - l - d, v - d, c - k - q, r - l, nh -ngh
	3. lỗi phần âm:
		1. Âm đệm
		2. Âm chính
		3. âm cuối
5. 20-40% các từ trong câu bị lỗi chính tả do đánh văn bản
	1. Thêm ngẫu nhiên các từ sau vào cuối mỗi từ: f, s, r, x, j
	2. Thêm ngẫu nhiên các từ sau vào mỗi các từ dưới đây:
		1. o: ô, oo, ơ, ow
		2. a: â, aa, ă, aw
		3. u: ư, uw,
		4. i: y,
		5. e: ê, ee
6. 30-50% các từ bị thêm nhiễu: Thêm bất ngẫu nhiên 1-3 ký tự vào từ
7. 
### Các phương án sửa lỗi
#### Thêm
Ví dụ ta có một câu: Minh muốn hóa hữu cơ; muốn gì ở "Hóa hữu cơ", phải thêm một từ nào đó ở đây để bổ sung ý nghĩa của câu. 
Mình muốn [MASK] hóa hữu cơ. --> Mình muốn biết về hóa hữu cơ.
[MASK] : 1 or N word? 
#### Sửa
#### Xóa