# Bài 2 : Chuỗi tấn công từ mật khẩu bị rò rỉ
## 1. cơ chế tấn công Domino
khi bạn dùng chung mật khẩu "123456" cho mọi tài khoản . Khi một web nhỏ bị hack, chuỗi sụp đỗ điẽn ra qua 4 bước 
1. Rò rỉ dữ liệu: hacker chiếm CSDL, thu được căp mật khẩu và email
2. thử mật khẩu tự động: hacker dùng bot tự động thử ngay cặp email và mật khẩu này lên các dịch vụ lớn như gmail, facebook, github
3. chiêm " mắt xích trung tâm" hacker đăng nhập thành cong gmail . từ gmail, có thể yêu cầu đổi lại mật khẩu cho mọi tài khoản khác 
4. hiệu ứng domino : toàn bộ các tài khoản lớn lần lượt sụp đổ. hacker đổi thông tin khôi phục, khóa quyền truy cập của nạn nhân và chiếm đoạt hoàn toàn dữ liệu
## 2. so sánh mật khẩn cảm tính và mật khẩu do máy tính sinh ra 
| tiêu chí | mật khẩu cảm tính (do con người tạo) |mật khẩu máy tính sinh ra |
|:--|:--:|--:|
| đặc điểm| thường ngắn, dùng thông tin cá nhân, từ có nghĩa hoặc từ dễ nhớ| chuỗi dài 16-32+ ký tự ,kết hợp ngẫy nhiên chữ hoa chữ thường |
| độ hỗn loạn| rất thấp|rất cao|
| khả năng chống tấn công | dễ dàng bị vô hiệu hóa bởi các hình thức Dictionary Attack| miễn nhiễm với các kiể tấn công|
| thời gian bẻ khóa| chỉ mất vài mili giây đến vài giây| có thể mất hàng triệu đến hàng tỉ năm với công nghệ máy tính hiện tại |
- mật khẩu cảm tính yếu vì chúng có tính dự đoán dựa trên tâm lý và thói quen con người 
- mật khẩu do máy tính tạo ra đạ độ ngẫu nhiên an toàn , buộc hacker phải thử toàn bôh không gian khóa với chi phí tính toán không ngừng 
## 3. mã hóa AES-256
AES-256 là chuẩn mã hóa đối xứng hàng đầu thế giới được chính phủ và tổ chức tài chính sử dụng để bảo vệ dữ liệu tối mật 
không gian khóa 256-bit: số lượng khóa có thể có 2^256 ~=1,15.10^77 khả năng
tính an toàn thực tế : Ngay cả khi dùng toàn bộ siêu máy tính mạnh nhất thế giới hiện nay để thử brute-force, cũng phải mất billions năm để giải mã một dữ liệu mã hóa bằng AES-256.
## 4. Tại sao lưu trên Password Manager an toàn hơn ghi chép thủ công?
Bảo mật dữ liệu: Password Manager mã hóa mãnh liệt bằng AES-256; ghi chép thủ công lưu dạng text thô, dễ bị đọc lén.

Quyền riêng tư : Chỉ bạn giữ chìa khóa mở kho Password Manager; ghi chép thủ công không có lớp bảo vệ thực sự.

Quản lý mật khẩu: Password Manager tự sinh và nhớ vô số mật khẩu siêu mạnh; ghi chép thủ công khiến bạn lười, hay chọn mật khẩu ngắn/dễ đoán.

Chống lừa đảo (Phishing): Password Manager chỉ tự động điền trên web chính chủ; ghi chép thủ công dễ khiến bạn gõ nhầm vào web giả.

Cơ động & Tiện lợi: Password Manager tự động điền cực nhanh trên mọi thiết bị; ghi chép thủ công tốn công tra cứu và gõ tay.

Trải nghiệm sử dụng: Password Manager loại bỏ nguy cơ quên mật khẩu; ghi chép thủ công dễ thất lạc sổ sách hoặc mất file note.