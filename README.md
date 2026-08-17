# 23632471_TranTuongVy_cabsystem
## Bước 1: Tìm hiểu nghiệp vụ của hệ thống
1.	Vấn đề hiện tại là gì?
-	Phân công tài xế chủ yếu được thực hiện thủ công
-	Khách hàng khó theo dõi trạng thái chuyến đi
-	Thông tin thanh toán chưa được quản lý tập trung
-	Bộ phận vận hành gặp khó khăn khi muốn mở rộng hệ thống
-	Ban lãnh đạo mong muốn xây dựng một nền tảng CAB mới có khả năng phục vụ số lượng lớn khách hàng và tài xế, đồng thời có thể phát triển thêm các tính năng trong tương lai.
2.	Mục tiêu?
- Số hóa quy trình đặt xe từ lúc khách hàng tạo yêu cầu đến khi hoàn thành chuyến.
- Tự động hóa việc tìm kiếm và phân công tài xế.
- Cho phép khách hàng theo dõi trạng thái chuyến đi.
- Hỗ trợ tính cước và thanh toán bằng tiền mặt hoặc phương thức điện tử.
- Quản lý tập trung thông tin khách hàng, tài xế, phương tiện, chuyến đi và giao dịch.
- Hỗ trợ nhân viên vận hành theo dõi và xử lý các chuyến đi.
- Cung cấp báo cáo về chuyến đi, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế.
- Đảm bảo hệ thống ổn định, bảo mật và có khả năng mở rộng khi số lượng khách hàng/tài xế tăng.
3.	Lý do gì phải xây dựng hệ thống?
-	Công ty ABC là một doanh nghiệp cung cấp dịch vụ đặt xe trực tuyến. Hiện tại khách hàng có thể liên hệ với tổng đài hoặc sử dụng một ứng dụng đơn giản để yêu cầu xe.
4.	Ai là người tham gia và sử dụng hệ thống?
- Khách hàng:	Đăng ký, đăng nhập, đặt xe, theo dõi chuyến đi, xem lịch sử, thanh toán và đánh giá tài xế
- Tài xế:	Quản lý hồ sơ/phương tiện, nhận hoặc từ chối chuyến, cập nhật trạng thái chuyến và vị trí
- Nhân viên vận hành:	Quản lý khách hàng, tài xế, phương tiện, chuyến đi; theo dõi và xử lý các trường hợp lỗi
- Ban lãnh đạo:	Xem báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế
- Nhà cung cấp thanh toán bên ngoài:	Tham gia xử lý các giao dịch thanh toán điện tử
- Nhà cung cấp dịch vụ thông báo:	Hỗ trợ gửi thông báo cho khách hàng và tài xế
5.	Hệ thống mới mang lại giá trị kinh doanh gì?
- Khách hàng:	Đặt xe thuận tiện, biết tài xế nào nhận chuyến, theo dõi chuyến và thanh toán dễ dàng
- Tài xế:	Nhận chuyến phù hợp, cập nhật trạng thái và quản lý thông tin cá nhân/phương tiện
- Nhân viên vận hành:	Quản lý tập trung khách hàng, tài xế, phương tiện và chuyến đi
- Ban lãnh đạo:	Có dữ liệu và báo cáo để đánh giá doanh thu, hoạt động và hiệu quả tài xế
- Doanh nghiệp:	Giảm thao tác thủ công, tăng khả năng mở rộng và phát triển thêm dịch vụ

## Bước 2: Xác định Stakeholder và Vai trò

| STT | Stakeholder | Vai trò |
|:---:|---|---|
| 1 | **Khách hàng** | Người sử dụng dịch vụ đặt xe |
| 2 | **Tài xế** | Người thực hiện chuyến xe |
| 3 | **Nhân viên vận hành** | Quản lý và hỗ trợ hoạt động hệ thống | 
| 4 | **Ban lãnh đạo** | Quản lý và theo dõi hoạt động kinh doanh | 
| 5 | **Nhà cung cấp thanh toán** | Hệ thống bên ngoài hỗ trợ thanh toán | 
| 6 | **Nhà cung cấp thông báo** | Hệ thống bên ngoài hỗ trợ gửi thông báo | 

``` mermaid
quadrantChart
    title Stakeholder Matrix - CAB System
    x-axis "Mức độ quan tâm thấp" --> "Mức độ quan tâm cao"
    y-axis "Mức độ ảnh hưởng thấp" --> "Mức độ ảnh hưởng cao"
    quadrant-1 "Quản lý chặt chẽ"
    quadrant-2 "Giữ hài lòng"
    quadrant-3 "Theo dõi"
    quadrant-4 "Giữ thông tin"
    
    "Ban lãnh đạo": [0.85, 0.90]
    "Nhân viên vận hành": [0.90, 0.80]
    "Khách hàng": [0.95, 0.65]
    "Tài xế": [0.90, 0.60]
    "Nhà cung cấp thanh toán": [0.55, 0.70]
    "Nhà cung cấp thông báo": [0.45, 0.45]
  ```
## Bước 3: Mục đích của nghiệp vụ

| STT | Nghiệp vụ | Mục đích |
|:---:|---|---|
| 1 | **Quản lý tài khoản khách hàng** | Cho phép khách hàng đăng ký, đăng nhập và cập nhật thông tin cá nhân để sử dụng hệ thống |
| 2 | **Đặt xe** | Cho phép khách hàng nhập điểm đón, điểm đến, chọn loại xe và gửi yêu cầu đặt xe |
| 3 | **Tìm kiếm & phân công tài xế** | Tự động tìm tài xế phù hợp dựa trên vị trí, trạng thái sẵn sàng và tiêu chí vận hành |
| 4 | **Quản lý chuyến đi** | Theo dõi và cập nhật trạng thái chuyến từ lúc tài xế nhận chuyến đến khi hoàn thành |
| 5 | **Tính cước** | Xác định số tiền khách hàng phải trả dựa trên loại dịch vụ và thông tin chuyến đi |
| 6 | **Thanh toán** | Cho phép khách hàng thanh toán bằng tiền mặt hoặc phương thức điện tử |
| 7 | **Quản lý thông báo** | Thông báo cho khách hàng và tài xế về các sự kiện liên quan đến chuyến đi và thanh toán |
| 8 | **Quản lý khách hàng, tài xế & phương tiện** | Hỗ trợ nhân viên vận hành quản lý thông tin và trạng thái của các đối tượng trong hệ thống |
| 9 | **Xử lý sự cố chuyến đi** | Hỗ trợ nhân viên vận hành kiểm tra và xử lý các trường hợp chuyến đi bị lỗi |
| 10 | **Tra cứu giao dịch & lịch sử** | Cho phép tra cứu lịch sử chuyến đi và lịch sử giao dịch phục vụ quản lý |
| 11 | **Đánh giá tài xế** | Cho phép khách hàng đánh giá tài xế sau khi chuyến đi hoàn thành |
| 12 | **Báo cáo hoạt động** | Cung cấp dữ liệu về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế |

## Bước 4: Xác định phạm vi dự án

> **Thời gian thực hiện: 7 tuần**

| STT | Module | Phạm vi chính | Mức độ |
|:---:|---|---|:---:|
| 1 | **Quản lý khách hàng** | Đăng ký, đăng nhập, quản lý thông tin, lịch sử chuyến | Bắt buộc |
| 2 | **Quản lý tài xế** | Hồ sơ, phương tiện, trạng thái hoạt động | Bắt buộc |
| 3 | **Đặt xe** | Điểm đón, điểm đến, loại xe, tạo yêu cầu | Bắt buộc |
| 4 | **Tìm & phân công tài xế** | Tìm tài xế phù hợp và xử lý từ chối | Bắt buộc |
| 5 | **Quản lý chuyến đi** | Cập nhật và theo dõi trạng thái chuyến | Bắt buộc |
| 6 | **Tính cước & thanh toán** | Tính tiền, tiền mặt, thanh toán điện tử | Bắt buộc |
| 7 | **Thông báo** | Thông báo cho khách hàng và tài xế | Bắt buộc |
| 8 | **Quản lý vận hành** | Quản lý khách hàng, tài xế, phương tiện, chuyến đi | Bắt buộc |
| 9 | **Báo cáo** | Chuyến, doanh thu, hoàn thành, hủy, hiệu quả tài xế | Cơ bản |
| 10 | **Đánh giá tài xế** | Khách hàng đánh giá sau chuyến | Cơ bản |

### Tiến độ 7 tuần

| Tuần | Nội dung |
|:---:|---|
| 1 | Phân tích yêu cầu & thiết kế phạm vi |
| 2 | Quản lý khách hàng |
| 3 | Quản lý tài xế |
| 4 | Đặt xe & tìm tài xế |
| 5 | Quản lý chuyến & tính cước |
| 6 | Thanh toán, thông báo & quản lý vận hành |
| 7 | Tích hợp, kiểm thử & hoàn thiện |

## Bước 5: Chuyển các yêu cầu đó thành yêu cầu nghiệp vụ

