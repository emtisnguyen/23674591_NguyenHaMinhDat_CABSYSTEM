# Danh sách kịch bản kiểm thử (Test Cases) - CAB System

Dự án: Nền tảng đặt xe (CAB System)
Tổng số Test Cases: 20

---

## TS_CAB_01: Đăng ký & Xác thực (Authentication & Registration)

| TC ID | Test Type | Test Case / Mô tả | Dữ liệu đầu vào (Input) | Các bước thực hiện (Steps) | Kết quả kỳ vọng (Expected Result) | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC01** | Positive | Khách hàng đăng ký tài khoản thành công | Họ tên, SĐT hợp lệ, Email, Mật khẩu chuẩn | 1. Nhập đủ thông tin hợp lệ<br>2. Nhấn "Đăng ký" | Hệ thống tạo tài khoản thành công và chuyển đến màn hình đăng nhập. | **High** |
| **TC02** | Negative | Đăng nhập với mật khẩu sai | SĐT: `0901234567`<br>Mật khẩu: `SaiMatKhau` | 1. Nhập SĐT đã đăng ký<br>2. Nhập sai mật khẩu<br>3. Nhấn "Đăng nhập" | Hệ thống báo lỗi: "Tên đăng nhập hoặc mật khẩu không chính xác". | **High** |
| **TC03** | Empty | Bỏ trống các trường bắt buộc khi đăng ký | Họ tên: `[Rỗng]`<br>SĐT: `[Rỗng]` | 1. Mở màn hình đăng ký<br>2. Để trống form<br>3. Nhấn "Đăng ký" | Báo lỗi ngay tại các trường bắt buộc: "Thông tin này không được để trống". Nút Đăng ký bị vô hiệu. | **High** |
| **TC04** | Format | Nhập Email sai định dạng cấu trúc | Email: `khachhang.com` hoặc `khachhang@` | 1. Nhập email thiếu `@` hoặc domain<br>2. Nhấn "Đăng ký" | Hệ thống báo lỗi "Định dạng Email không chính xác (vd: abc@domain.com)". | **Medium** |

---

## TS_CAB_02: Yêu cầu Đặt xe & Điều phối (Booking & Dispatch)

| TC ID | Test Type | Test Case / Mô tả | Dữ liệu đầu vào (Input) | Các bước thực hiện (Steps) | Kết quả kỳ vọng (Expected Result) | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC05** | Positive | Đặt xe thành công (Happy Path) | Điểm đón: A<br>Điểm đến: B<br>Loại xe: 4 chỗ | 1. Nhập A và B<br>2. Bấm đặt xe<br>3. Có tài xế online gần đó nhận | Hệ thống tính đúng tiền, tìm thấy tài xế và gửi thông báo "Tài xế Nguyễn Văn A đang đến". | **High** |
| **TC06** | Negative | Không có tài xế nào khả dụng xung quanh | Vị trí đón không có tài xế online | 1. Nhập lộ trình<br>2. Bấm Đặt xe<br>3. Đợi hết timeout tìm kiếm | Hiển thị thông báo: "Hiện không tìm thấy tài xế xung quanh, vui lòng thử lại sau". | **High** |
| **TC07** | Boundary | Nhập Điểm đón và Điểm đến trùng nhau | Điểm đón: `123 Lê Lợi`<br>Điểm đến: `123 Lê Lợi` | 1. Nhập điểm đón trùng điểm đến (Khoảng cách = 0)<br>2. Bấm Đặt xe | Hệ thống cảnh báo: "Điểm đến phải khác điểm đón" hoặc tính cước tối thiểu. | **Medium** |
| **TC08** | Empty | Để trống điểm đón / điểm đến | Điểm đón: `[Rỗng]`<br>Điểm đến: `[Rỗng]` | 1. Mở app đặt xe<br>2. Không chọn vị trí<br>3. Bấm Đặt xe | Hệ thống chặn thao tác, hiển thị popup: "Vui lòng chọn điểm đón và điểm đến". | **High** |

---

## TS_CAB_03: Thực hiện chuyến đi & Cập nhật trạng thái (Trip Execution)

| TC ID | Test Type | Test Case / Mô tả | Dữ liệu đầu vào (Input) | Các bước thực hiện (Steps) | Kết quả kỳ vọng (Expected Result) | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC09** | Positive | Tài xế cập nhật đúng các mốc trạng thái | Trạng thái: Đã đến -> Đã đón -> Hoàn thành | 1. Tài xế đến điểm đón, bấm "Đã đến"<br>2. Khách lên xe, bấm "Bắt đầu"<br>3. Đến nơi, bấm "Hoàn thành" | Trạng thái chuyến đi cập nhật realtime. Khách hàng nhận được thông báo tương ứng. | **High** |
| **TC10** | Negative | Chuyển cuốc cho tài xế đang ở trạng thái Offline | Trạng thái tài xế: Offline | 1. Hệ thống / Admin cố gắng ép gán chuyến cho tài xế đang nghỉ | Hệ thống từ chối điều phối và không gửi thông báo chuyến đi cho tài xế này. | **High** |
| **TC11** | Boundary | Đánh giá sao biên dưới và biên trên (1 sao, 5 sao) | Mức sao: 1 sao và 5 sao | 1. Kết thúc chuyến<br>2. Chấm 1 sao rồi đổi 5 sao<br>3. Nhấn "Gửi đánh giá" | Hệ thống lưu trữ thành công các mức giá trị biên này mà không báo lỗi logic. | **Low** |
| **TC12** | Format | Nhập Ghi chú cho tài xế vượt quá giới hạn | Chuỗi ký tự độ dài 300 ký tự (Giới hạn: 255) | 1. Ở màn hình đặt xe, nhập 300 ký tự vào ô Ghi chú<br>2. Bấm "Đặt xe" | Hệ thống chỉ cho phép nhập tối đa 255 ký tự (chặn gõ thêm) hoặc báo lỗi độ dài. | **Medium** |

---

## TS_CAB_04: Thanh toán & Tính cước (Payment & Billing)

| TC ID | Test Type | Test Case / Mô tả | Dữ liệu đầu vào (Input) | Các bước thực hiện (Steps) | Kết quả kỳ vọng (Expected Result) | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC13** | Positive | Thanh toán Ví điện tử thành công | Ví điện tử có đủ số dư | 1. Kết thúc chuyến đi<br>2. Hệ thống gọi API thanh toán qua Ví điện tử | Tiền được trừ thành công, trạng thái chuyến đổi thành "Đã thanh toán", hiển thị hóa đơn. | **High** |
| **TC14** | Negative | Thanh toán điện tử thất bại (Thẻ/Ví không đủ tiền) | Số dư Ví = 0 VNĐ | 1. Kết thúc chuyến đi<br>2. Hệ thống gọi API trừ tiền | Cổng thanh toán trả về lỗi. App thông báo: "Giao dịch thất bại, vui lòng đổi phương thức". | **High** |
| **TC15** | Empty | Bỏ trống lựa chọn phương thức thanh toán | PTTT: `[Chưa chọn]` | 1. Tại màn hình chốt đơn, không chọn PTTT<br>2. Bấm "Đặt xe" | Hệ thống yêu cầu: "Vui lòng chọn 1 phương thức thanh toán (Tiền mặt / Thẻ / Ví) trước khi đặt". | **High** |
| **TC16** | Format | Nhập sai định dạng thông tin thẻ tín dụng khi liên kết | Số thẻ: `1234abcd5678` (chứa chữ) | 1. Vào phần Liên kết thẻ<br>2. Nhập số thẻ chứa chữ cái<br>3. Bấm "Liên kết" | Báo lỗi định dạng: "Số thẻ không hợp lệ, chỉ bao gồm chữ số". | **Medium** |

---

## TS_CAB_05: Quản trị & Báo cáo (Admin & Reporting)

| TC ID | Test Type | Test Case / Mô tả | Dữ liệu đầu vào (Input) | Các bước thực hiện (Steps) | Kết quả kỳ vọng (Expected Result) | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC17** | Positive | Xem báo cáo doanh thu theo tháng | Ngày bắt đầu: `01/10/2023`<br>Ngày kết thúc: `31/10/2023` | 1. Admin vào mục Báo cáo<br>2. Chọn tháng 10/2023<br>3. Bấm "Xem thống kê" | Hiển thị chính xác tổng số chuyến, tổng doanh thu, tỷ lệ hoàn thành chuyến dạng biểu đồ. | **High** |
| **TC18** | Negative | Nhân viên cấp thấp truy cập chức năng cấm (Phân quyền) | Tài khoản: `Staff` (nhân viên thường) | 1. Đăng nhập bằng tk Staff<br>2. Dán URL trỏ tới chức năng "Xóa tài khoản tài xế" | Hệ thống chặn quyền, báo lỗi 403: "Bạn không có quyền truy cập chức năng này". | **High** |
| **TC19** | Boundary | Lọc báo cáo với Ngày bắt đầu > Ngày kết thúc | Từ ngày: `30/10/2023`<br>Đến ngày: `01/10/2023` | 1. Nhập khoảng thời gian ngược logic<br>2. Bấm "Lọc dữ liệu" | Hệ thống cảnh báo: "Ngày bắt đầu không được lớn hơn ngày kết thúc". | **Medium** |
| **TC20** | Format | Tìm kiếm thông tin bằng ký tự đặc biệt SQL Injection | Ô tìm kiếm: `' OR 1=1--` | 1. Admin vào danh sách tài xế<br>2. Gõ mã độc vào ô tìm kiếm tên/SĐT<br>3. Bấm "Tìm" | Hệ thống mã hóa (escape) chuỗi đầu vào, trả về kết quả rỗng (không tìm thấy), không bị lỗi Database. | **Low** |