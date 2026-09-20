# Danh sách kịch bản kiểm thử (Test Cases) - CAB System

**Dự án:** Nền tảng đặt xe (CAB System)
**Tổng số Test Cases:** Tối đa 20 Test Cases tiêu biểu
**Phân loại:** Positive, Negative, Boundary, Empty, Format

---

## Bảng Chi Tiết Test Cases

| Test Scenario ID | Test Scenario Name | Test Case ID | Test Type | Test Case Description | Input Data | Steps to Execute | Expected Result | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TS_CAB_01** | **Đăng ký & Xác thực** | TC01_01 | Positive | Khách hàng đăng ký tài khoản thành công với thông tin hợp lệ | SĐT: 0912345678, Pass: Abc@1234, Tên: Nguyễn Văn A | 1. Mở màn hình Đăng ký<br>2. Nhập thông tin hợp lệ<br>3. Nhấn Đăng ký | Tài khoản được tạo, chuyển hướng đến màn hình chính | High |
| **TS_CAB_01** | **Đăng ký & Xác thực** | TC01_02 | Positive | Tài xế đăng nhập thành công | SĐT: 0987654321, Pass: Driver@123 | 1. Mở màn hình Đăng nhập<br>2. Nhập SĐT và Pass<br>3. Nhấn Đăng nhập | Đăng nhập thành công, vào giao diện dành cho tài xế | High |
| **TS_CAB_01** | **Đăng ký & Xác thực** | TC01_03 | Negative | Đăng nhập sai mật khẩu | SĐT: 0912345678, Pass: SaiPass123 | 1. Mở màn hình Đăng nhập<br>2. Nhập SĐT và Pass sai<br>3. Nhấn Đăng nhập | Hiển thị lỗi: "Số điện thoại hoặc mật khẩu không chính xác" | High |
| **TS_CAB_01** | **Đăng ký & Xác thực** | TC01_04 | Boundary | Đăng ký với SĐT đúng 10 số (biên chuẩn) | SĐT: 0123456789 | 1. Nhập SĐT 10 số<br>2. Nhấn Đăng ký | Hệ thống chấp nhận SĐT | Medium |
| **TS_CAB_01** | **Đăng ký & Xác thực** | TC01_05 | Empty | Bỏ trống trường Số điện thoại khi Đăng ký | SĐT: [Rỗng] | 1. Để trống SĐT<br>2. Nhấn Đăng ký | Hiển thị lỗi bắt buộc nhập SĐT | High |
| **TS_CAB_01** | **Đăng ký & Xác thực** | TC01_06 | Format | Đăng ký với SĐT chứa chữ cái | SĐT: 0912abc456 | 1. Nhập SĐT có chữ cái<br>2. Nhấn Đăng ký | Hiển thị lỗi: "Số điện thoại chỉ được chứa các chữ số" | Medium |
| **TS_CAB_02** | **Đặt xe & Điều phối** | TC02_01 | Positive | Khách hàng đặt xe thành công và có tài xế nhận chuyến | Đón: A, Đến: B, Loại xe: 4 chỗ | 1. Nhập điểm đón, đến<br>2. Chọn loại xe<br>3. Nhấn Đặt xe | Hệ thống tìm và gán tài xế, hiển thị thông tin tài xế cho khách | High |
| **TS_CAB_02** | **Đặt xe & Điều phối** | TC02_02 | Negative | Không tìm thấy tài xế khả dụng (hết xe) | Khu vực không có xe | 1. Khách đặt xe | Hiển thị lỗi: "Không có tài xế nào xung quanh. Vui lòng thử lại sau" | High |
| **TS_CAB_02** | **Đặt xe & Điều phối** | TC02_03 | Boundary | Thời gian chờ tài xế phản hồi hết hạn (timeout) | Chờ 30s | 1. Phát chuyến cho TX<br>2. TX không thao tác trong 30s | Hệ thống tự động chuyển chuyến cho tài xế khác | Medium |
| **TS_CAB_02** | **Đặt xe & Điều phối** | TC02_04 | Empty | Không nhập điểm đến | Đón: A, Đến: [Rỗng] | 1. Để trống điểm đến<br>2. Bấm Đặt xe | Nút Đặt xe bị vô hiệu hóa hoặc báo lỗi yêu cầu nhập điểm đến | High |
| **TS_CAB_02** | **Đặt xe & Điều phối** | TC02_05 | Format | Nhập tọa độ điểm đón bị lỗi định dạng | Lat/Lng không hợp lệ | 1. Mô phỏng API truyền sai tọa độ | Hệ thống không tính khoảng cách, báo lỗi không xác định được vị trí | Medium |
| **TS_CAB_03** | **Thực hiện chuyến đi** | TC03_01 | Positive | Tài xế cập nhật trạng thái "Đã đến điểm đón" | Chuyến đang thực hiện | 1. TX đến nơi<br>2. Bấm "Đã đến" | Trạng thái chuyến đi cập nhật, khách nhận được thông báo | High |
| **TS_CAB_03** | **Thực hiện chuyến đi** | TC03_02 | Negative | Khách hàng hủy chuyến khi tài xế đã đón khách | Trạng thái: Đang di chuyển | 1. Khách tìm nút Hủy chuyến | Nút Hủy chuyến bị vô hiệu hóa hoặc tính phí phạt | Medium |
| **TS_CAB_03** | **Thực hiện chuyến đi** | TC03_03 | Boundary | Đánh giá tài xế 5 sao (biên trên) | Rate: 5 sao | 1. Chuyến hoàn thành<br>2. Chọn 5 sao | Hệ thống ghi nhận 5 sao | Low |
| **TS_CAB_03** | **Thực hiện chuyến đi** | TC03_04 | Empty | Gửi đánh giá nhưng bỏ trống số sao | Rate: [Rỗng] | 1. Không chọn sao<br>2. Bấm Gửi đánh giá | Báo lỗi yêu cầu chọn ít nhất 1 sao | Low |
| **TS_CAB_04** | **Thanh toán & Tính cước**| TC04_01 | Positive | Thanh toán bằng Tiền mặt thành công | PTTT: Tiền mặt | 1. Chuyến hoàn thành<br>2. Khách trả tiền mặt<br>3. TX xác nhận | Giao dịch thành công, cập nhật doanh thu | High |
| **TS_CAB_04** | **Thanh toán & Tính cước**| TC04_02 | Negative | Thanh toán điện tử thất bại do không đủ số dư | Số dư ví < Cước phí | 1. Hệ thống trừ tiền điện tử | Báo lỗi giao dịch thất bại, yêu cầu chọn PTTT khác | High |
| **TS_CAB_04** | **Thanh toán & Tính cước**| TC04_03 | Format | Thêm thẻ mới với số CVV sai định dạng | CVV: 12A | 1. Nhập thông tin thẻ có CVV chữ<br>2. Lưu | Báo lỗi CVV chỉ gồm 3-4 chữ số | Medium |
| **TS_CAB_05** | **Quản trị hệ thống** | TC05_01 | Positive | Admin khóa tài khoản tài xế vi phạm | ID Tài xế: X | 1. Tìm tài xế X<br>2. Bấm Khóa tài khoản | Tài xế X không thể đăng nhập hoặc nhận chuyến | High |
| **TS_CAB_05** | **Quản trị hệ thống** | TC05_02 | Negative | Nhân viên không có quyền thử truy cập báo cáo | Role: Staff | 1. Staff đăng nhập<br>2. Vào Báo cáo | Báo lỗi "Không có quyền truy cập" (Access Denied) | High |