# Bài 3 : Quản lý rủi ro khi mất thiết bị xác thực
## Báo cáo phân tích IPO
Iput( Mã dự phòng)
backup code chuỗi ký tự ngẫu nhiên ( thường 8-10 mã mỗi mã sử dụng một lần ) được hệ thống cung cấp và người dùng bắt buộc phải lưu trữ ngoại tuyến an toàn ngay tại thời điểm thiết lập MFA ban đầu
Process (quy trình xử lý)
1. Xác thực
- đăng nhập xác thực bằng backup code 
2. Hủy mã cũ 
- vào IAM hủy kích hoạt MFA cũ 
3. Cấp mã mới 
- cấp phát và kích hoạt thiết bị MFA mới : sử dụng ứng dụng Google Authenticator trên điện thoại mới quét mã QR hiển thị trên AWS.nhập hai mã OTP liên tiếp để kích hoạt 
Output (hệ thống an toàn)
Thu hồi quyền truy cập của thiết bị mất, khôi phục toàn bộ quyền quản trị AWS an toàn tuyệt đối.
## lý do không được lưu Backup Codes dưới dạng ảnh trong thư viện điện thoại
- mất thiết bị: kẻ xấu nhặt được điện thoại có thể vào thư viện nhập mã truy cập vào hệ thống 
- đồng bộ đám mây: ảnh tự động đẩy lên icloud hoặc google photos, nếu tài khoảnn cloud bị lộ, mã bảo mật sẽ bị lộ
- cấp quyền app lạ : các app lạ cấp quyền truy cập thư viện có thể quét lấy dữ liệu nhảy cảm và mã bảo mật 


