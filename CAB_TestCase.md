|**Test Scenario ID**|**Test Scenario Name**|**Test Case ID**|**Test Type**|
| :-: | :-: | :-: | :-: |
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_01|Positive|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_02|Positive|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_03|Negative|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_04|Negative|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_05|Boundary|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_06|Boundary|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_07|Empty|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_08|Empty|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_09|Format|
|TS\_CAB\_01|Đăng ký & Xác thực|TC01\_10|Format|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_01|Positive|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_02|Positive|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_03|Negative|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_04|Negative|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_05|Boundary|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_06|Boundary|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_07|Empty|
|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_08|Empty|



|TS\_CAB\_02|Đặt xe & Điều phối|TC02\_09|Format|
| :- | :- | :- | :- |
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_01|Positive|
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_02|Positive|
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_03|Negative|
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_04|Negative|
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_05|Boundary|
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_06|Boundary|
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_07|Empty|
|TS\_CAB\_03|Thực hiện chuyến đi|TC03\_08|Format|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_01|Positive|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_02|Positive|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_03|Negative|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_04|Negative|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_05|Boundary|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_06|Boundary|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_07|Empty|
|TS\_CAB\_04|Thanh toán & Tính cước|TC04\_08|Format|
|TS\_CAB\_05|Quản trị hệ thống|TC05\_01|Positive|
|TS\_CAB\_05|Quản trị hệ thống|TC05\_02|Positive|
|TS\_CAB\_05|Quản trị hệ thống|TC05\_03|Negative|
|TS\_CAB\_05|Quản trị hệ thống|TC05\_04|Boundary|



|TS\_CAB\_05|Quản trị hệ thống|TC05\_05|Empty|
| :- | :- | :- | :- |
|TS\_CAB\_05|Quản trị hệ thống|TC05\_06|Format|



|**Test Case Description**|**Input Data**|
| :-: | :-: |
|Khách hàng đăng ký tài khoản thành công với thông tin hợp lệ|SĐT: 0912345678, Pass: Abc@1234, Tên: Nguyễn Văn A|
|Tài xế đăng nhập thành công|SĐT: 0987654321, Pass: Driver@123|
|Đăng nhập sai mật khẩu|SĐT: 0912345678, Pass: SaiPass123|
|Đăng ký với SĐT đã tồn tại|SĐT: 0912345678 (đã dùng)|
|Đăng ký với SĐT đúng 10 số (biên chuẩn)|SĐT: 0123456789|
|Đăng ký với Mật khẩu vừa đủ 8 ký tự (biên dưới)|Pass: 12345678|
|Bỏ trống trường Số điện thoại khi Đăng ký|SĐT: [Rỗng]|
|Bỏ trống Mật khẩu khi Đăng nhập|Pass: [Rỗng]|
|Đăng ký với SĐT chứa chữ cái|SĐT: 0912abc456|
|Đăng ký với Email sai định dạng (tùy chọn)|Email: test\_email.com|
|Khách hàng đặt xe thành công và có tài xế nhận chuyến|Đón: A, Đến: B, Loại xe: 4 chỗ|
|Chuyển tài xế khác tự động khi tài xế 1 từ chối|Tài xế 1 từ chối|
|Không tìm thấy tài xế khả dụng (hết xe)|Khu vực không có xe|
|Tài xế đang Offline nhưng nhận được chuyến|Tài xế chọn Offline|
|Đặt xe với khoảng cách quá ngắn (trùng điểm)|Đón = Đến|
|Thời gian chờ tài xế phản hồi hết hạn (timeout)|Chờ 30s|
|Không nhập điểm đến|Đón: A, Đến: [Rỗng]|
|Không chọn loại xe|Loại xe: [Rỗng]|



|Nhập tọa độ điểm đón bị lỗi định dạng|Lat/Lng không hợp lệ|
| :- | :- |
|Tài xế cập nhật trạng thái "Đã đến điểm đón"|Chuyến đang thực hiện|
|Tài xế cập nhật trạng thái "Hoàn thành chuyến"|Chuyến đang di chuyển|
|Tài xế bấm "Hoàn thành" khi chưa bấm "Bắt đầu"|Trạng thái: Đang chờ|
|Khách hàng hủy chuyến khi tài xế đã đón khách|Trạng thái: Đang di chuyển|
|Đánh giá tài xế 5 sao (biên trên)|Rate: 5 sao|
|Đánh giá tài xế 1 sao (biên dưới)|Rate: 1 sao|
|Gửi đánh giá nhưng bỏ trống số sao|Rate: [Rỗng]|
|Nhập ghi chú chứa ký tự đặc biệt không hợp lệ|Ghi chú: <script>alert(1)</script>|
|Thanh toán bằng Tiền mặt thành công|PTTT: Tiền mặt|
|Thanh toán qua Ví điện tử thành công|PTTT: Ví điện tử|
|Thanh toán điện tử thất bại do không đủ số dư|Số dư ví < Cước phí|
|Thanh toán qua thẻ thất bại do thẻ hết hạn|Thẻ hết hạn|
|Thanh toán chuyến đi có cước phí tối thiểu|Khoảng cách rất ngắn|
|Thanh toán với số tiền lớn bất thường (cảnh báo)|Cước phí > 5.000.000đ|
|Không có phương thức thanh toán nào được liên kết|PTTT: [Rỗng]|
|Thêm thẻ mới với số CVV sai định dạng|CVV: 12A|
|Admin xem báo cáo doanh thu theo ngày|Lọc ngày: Hôm nay|
|Admin khóa tài khoản tài xế vi phạm|ID Tài xế: X|
|Nhân viên không có quyền (Staff) thử truy cập báo cáo tài chính|Role: Staff|
|Xuất báo cáo dữ liệu trong 1 năm (khối lượng lớn)|Từ 01/01 đến 31/12|



|Lọc tìm kiếm chuyến đi bỏ trống từ khóa|Keyword: [Rỗng]|
| :- | :- |
|Tìm kiếm theo ID chuyến đi bằng chữ cái|ID: ChuyenDi123|



|**Steps to Execute**|**Expected Result**|**Priority**|
| :-: | :-: | :-: |
|<p>1\. Mở màn hình Đăng ký</p><p>2\. Nhập thông tin hợp lệ</p><p>3\. Nhấn Đăng ký</p>|Tài khoản được tạo, chuyển hướng đến màn hình chính|**High**|
|<p>1\. Mở màn hình Đăng nhập</p><p>2\. Nhập SĐT và Pass</p><p>3\. Nhấn Đăng nhập</p>|Đăng nhập thành công, vào giao diện dành cho tài xế|**High**|
|<p>1\. Mở màn hình Đăng nhập</p><p>2\. Nhập SĐT và Pass sai</p><p>3\. Nhấn Đăng nhập</p>|Hiển thị lỗi: "Số điện thoại hoặc mật khẩu không chính xác"|**High**|
|<p>1\. Mở màn hình Đăng ký</p><p>2\. Nhập SĐT đã tồn tại</p><p>3\. Nhấn Đăng ký</p>|Hiển thị lỗi: "Số điện thoại này đã được đăng ký"|**Medium**|
|<p>1\. Nhập SĐT 10 số</p><p>2\. Nhấn Đăng ký</p>|Hệ thống chấp nhận SĐT|**Medium**|
|<p>1\. Nhập mật khẩu 8 ký tự</p><p>2\. Nhấn Đăng ký</p>|Hệ thống chấp nhận mật khẩu (nếu rule >= 8)|**Medium**|
|<p>1\. Để trống SĐT</p><p>2\. Nhấn Đăng ký</p>|Hiển thị lỗi bắt buộc nhập SĐT|**High**|
|<p>1\. Nhập SĐT, bỏ trống Pass</p><p>2\. Nhấn Đăng nhập</p>|Hiển thị lỗi bắt buộc nhập Mật khẩu|**High**|
|<p>1\. Nhập SĐT có chữ cái</p><p>2\. Nhấn Đăng ký</p>|Hiển thị lỗi: "Số điện thoại chỉ được chứa các chữ số"|**Medium**|
|<p>1\. Nhập Email thiếu @</p><p>2\. Nhấn Lưu</p>|Hiển thị lỗi: "Email không hợp lệ"|**Low**|
|<p>1\. Nhập điểm đón, đến</p><p>2\. Chọn loại xe</p><p>3\. Nhấn Đặt xe</p>|Hệ thống tìm và gán tài xế, hiển thị thông tin tài xế cho khách|**High**|
|<p>1\. Khách đặt xe</p><p>2\. TX1 từ chối</p>|Hệ thống tự động phát chuyến cho TX2 gần đó|**High**|
|1\. Khách đặt xe|Hiển thị lỗi: "Không có tài xế nào xung quanh. Vui lòng thử lại sau"|**High**|
|<p>1\. TX chuyển Offline</p><p>2\. Có khách đặt xe</p>|Hệ thống không phát chuyến cho tài xế này|**High**|
|1\. Nhập điểm đón trùng điểm đến|Hiển thị lỗi hoặc áp dụng cước phí tối thiểu|**Medium**|
|<p>1\. Phát chuyến cho TX</p><p>2\. TX không thao tác trong 30s</p>|Hệ thống tự động chuyển chuyến cho tài xế khác|**Medium**|
|<p>1\. Để trống điểm đến</p><p>2\. Bấm Đặt xe</p>|Nút Đặt xe bị vô hiệu hóa hoặc báo lỗi yêu cầu nhập điểm đến|**High**|
|<p>1\. Nhập điểm đón, đến</p><p>2\. Không chọn loại xe</p>|Báo lỗi yêu cầu chọn loại xe|**High**|



|1\. Mô phỏng API truyền sai tọa độ|Hệ thống không tính được khoảng cách, báo lỗi không xác định được vị trí|**Medium**|
| :- | :- | :-: |
|<p>1\. TX đến nơi</p><p>2\. Bấm "Đã đến"</p>|Trạng thái chuyến đi cập nhật, khách nhận được thông báo|**High**|
|<p>1\. TX đến đích</p><p>2\. Bấm "Hoàn thành"</p>|Chuyến đi kết thúc, chuyển sang màn hình thanh toán|**High**|
|1\. TX cố gắng bấm Hoàn thành luôn|Nút "Hoàn thành" bị ẩn hoặc báo lỗi quy trình|**Medium**|
|1\. Khách tìm nút Hủy chuyến|Nút Hủy chuyến bị vô hiệu hóa hoặc tính phí phạt|**Medium**|
|<p>1\. Chuyến hoàn thành</p><p>2\. Chọn 5 sao</p>|Hệ thống ghi nhận 5 sao|**Low**|
|<p>1\. Chuyến hoàn thành</p><p>2\. Chọn 1 sao</p>|Hệ thống ghi nhận 1 sao|**Low**|
|<p>1\. Không chọn sao</p><p>2\. Bấm Gửi đánh giá</p>|Báo lỗi yêu cầu chọn ít nhất 1 sao|**Low**|
|<p>1\. Nhập script vào ô ghi chú</p><p>2\. Gửi</p>|Hệ thống lọc bỏ mã độc (sanitize) hoặc báo lỗi ký tự không hợp lệ|**Medium**|
|<p>1\. Chuyến hoàn thành</p><p>2\. Khách trả tiền mặt</p><p>3\. TX xác nhận</p>|Giao dịch thành công, cập nhật doanh thu|**High**|
|<p>1\. Chuyến hoàn thành</p><p>2\. Hệ thống trừ tiền tự động</p>|Trừ tiền thành công, gửi thông báo hóa đơn|**High**|
|1\. Hệ thống trừ tiền điện tử|Báo lỗi giao dịch thất bại, yêu cầu chọn PTTT khác|**High**|
|1\. Hệ thống trừ tiền qua thẻ|Báo lỗi thẻ không hợp lệ|**High**|
|1\. Tính cước|Hệ thống áp dụng mức giá sàn quy định (VD: 15,000đ)|**Medium**|
|1\. Hoàn thành chuyến đi dài|Có thể yêu cầu xác nhận thêm hoặc ghi log nghi ngờ|**Medium**|
|1\. Khách đặt xe trả trước qua thẻ|Báo lỗi yêu cầu thêm thẻ hoặc chọn tiền mặt|**High**|
|<p>1\. Nhập thông tin thẻ có CVV chữ</p><p>2\. Lưu</p>|Báo lỗi CVV chỉ gồm 3-4 chữ số|**Medium**|
|<p>1\. Vào Admin</p><p>2\. Chọn Báo cáo</p><p>3\. Lọc theo hôm nay</p>|Hiển thị chính xác tổng doanh thu, số chuyến|**High**|
|<p>1\. Tìm tài xế X</p><p>2\. Bấm Khóa tài khoản</p>|Tài xế X không thể đăng nhập hoặc nhận chuyến|**High**|
|<p>1\. Staff đăng nhập</p><p>2\. Vào Báo cáo tài chính</p>|Báo lỗi "Không có quyền truy cập" (Access Denied)|**High**|
|<p>1\. Chọn khoảng thời gian 1 năm</p><p>2\. Bấm Xuất Excel</p>|Hệ thống xử lý xuất file thành công (có thể mất thời gian nhưng không lỗi)|**Medium**|



|<p>1\. Bỏ trống ô tìm kiếm</p><p>2\. Bấm Tìm</p>|Hiển thị toàn bộ danh sách chuyến đi hoặc yêu cầu nhập từ khóa|**Low**|
| :- | :- | :-: |
|<p>1\. Nhập ID bằng chữ vào ô tìm kiếm số</p><p>2\. Bấm Tìm</p>|Báo lỗi "ID chuyến đi phải là số"|**Medium**|

