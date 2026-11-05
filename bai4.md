# Bài 4 : Rủi ro đánh cắp mật khẩu từ trình duyệt
## bảng so sánh google chrome password manager và bitwarden password manager 
| Tiêu chí so sánh | Google password manager | Bitwarden password manager|
|:--:|:--:|:--:|
| Khả năng chống Infostealer| Yếu: Lưu trữ mật khẩu trong tệp cơ sở dữ liệu cục bộ (Login Data). Các dòng mã độc Infostealer dễ dàng trích xuất và giải mã thông qua cơ chế DPAPI của hệ điều hành|Mạnh: Dữ liệu được mã hóa đầu cuối (E2EE) AES-256. Mật khẩu không nằm dạng thuần túy trên đĩa cứng; mã độc không thể đọc trực tiếp nếu không có Master Password|
|Zero-Knowledge Architecture|Không: Google lưu trữ khóa giải mã và một phần dữ liệu dưới dạng có thể truy cập qua tài khoản Google cá nhân, tiềm ẩn rủi ro khi tài khoản chính bị xâm phạm.|Có: Máy chủ Bitwarden hoàn toàn không biết Master Password hay dữ liệu gốc của bạn. Toàn bộ quá trình mã hóa/giải mã diễn ra cục bộ trên thiết bị (Client-side).|
|Đồng bộ chéo nền tảng (Cross-platform)|Tốt trong hệ sinh thái Google/Chrome, nhưng hạn chế và kém bảo mật khi đồng bộ ra ngoài các trình duyệt hoặc hệ điều hành khác.|Xuất sắc: Hỗ trợ đa nền tảng (Windows, macOS, Linux, iOS, Android, các trình duyệt chính) với giao thức đồng bộ bảo mật đồng nhất.|
## Lập luận vì sao Bitwarden thắng thế về mặt bảo mật dù tốn thêm thao tác nhập Master password 
- kháng mã độc Infostealer tận gốc 
Chrome: Lưu mật khẩu trong tệp Login Data dạng dễ bị mã độc (RedLine, Lumma...) khai thác hệ thống để giải mã và trích xuất toàn bộ trong vài giây mà không cần hỏi lại người dùng.

Bitwarden: Dữ liệu mã hóa chuẩn AES-256 cục bộ. Máy tính nhiễm mã độc cũng chỉ lấy được chuỗi mã hóa vô nghĩa vì khóa giải mã phụ thuộc vào Master Password (không lưu trên máy).

- Kiến trúc Zero-Knowledge:
Máy chủ Bitwarden hoàn toàn mù dữ liệu—chính nhà cung cấp dịch vụ cũng không thể đọc hay can thiệp vào mật khẩu của bạn.

- Kiểm soát phiên làm việc an toàn:
Cho phép cấu hình tự động khóa két sắt (Auto-lock) khi không sử dụng, trong khi Chrome luôn mở khóa sẵn theo phiên trình duyệt, dễ bị lợi dụng khi máy bị bỏ ngỏ.
