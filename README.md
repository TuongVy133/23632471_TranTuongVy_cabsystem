# 23632471_TranTuongVy_cabsystem
### Bước 1: Tìm hiểu nghiệp vụ của hệ thống
## 1.	Vấn đề hiện tại là gì?
-	Phân công tài xế chủ yếu được thực hiện thủ công
-	Khách hàng khó theo dõi trạng thái chuyến đi
-	Thông tin thanh toán chưa được quản lý tập trung
-	Bộ phận vận hành gặp khó khăn khi muốn mở rộng hệ thống
-	Ban lãnh đạo mong muốn xây dựng một nền tảng CAB mới có khả năng phục vụ số lượng lớn khách hàng và tài xế, đồng thời có thể phát triển thêm các tính năng trong tương lai.
## 2.	Mục tiêu?
- Số hóa quy trình đặt xe từ lúc khách hàng tạo yêu cầu đến khi hoàn thành chuyến.
- Tự động hóa việc tìm kiếm và phân công tài xế.
- Cho phép khách hàng theo dõi trạng thái chuyến đi.
- Hỗ trợ tính cước và thanh toán bằng tiền mặt hoặc phương thức điện tử.
- Quản lý tập trung thông tin khách hàng, tài xế, phương tiện, chuyến đi và giao dịch.
- Hỗ trợ nhân viên vận hành theo dõi và xử lý các chuyến đi.
- Cung cấp báo cáo về chuyến đi, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế.
- Đảm bảo hệ thống ổn định, bảo mật và có khả năng mở rộng khi số lượng khách hàng/tài xế tăng.
## 3.	Lý do gì phải xây dựng hệ thống?
-	Công ty ABC là một doanh nghiệp cung cấp dịch vụ đặt xe trực tuyến. Hiện tại khách hàng có thể liên hệ với tổng đài hoặc sử dụng một ứng dụng đơn giản để yêu cầu xe.
## 4.	Ai là người tham gia và sử dụng hệ thống?
- Khách hàng:	Đăng ký, đăng nhập, đặt xe, theo dõi chuyến đi, xem lịch sử, thanh toán và đánh giá tài xế
- Tài xế:	Quản lý hồ sơ/phương tiện, nhận hoặc từ chối chuyến, cập nhật trạng thái chuyến và vị trí
- Nhân viên vận hành:	Quản lý khách hàng, tài xế, phương tiện, chuyến đi; theo dõi và xử lý các trường hợp lỗi
- Ban lãnh đạo:	Xem báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế
- Nhà cung cấp thanh toán bên ngoài:	Tham gia xử lý các giao dịch thanh toán điện tử
- Nhà cung cấp dịch vụ thông báo:	Hỗ trợ gửi thông báo cho khách hàng và tài xế
## 5.	Hệ thống mới mang lại giá trị kinh doanh gì?
- Khách hàng:	Đặt xe thuận tiện, biết tài xế nào nhận chuyến, theo dõi chuyến và thanh toán dễ dàng
- Tài xế:	Nhận chuyến phù hợp, cập nhật trạng thái và quản lý thông tin cá nhân/phương tiện
- Nhân viên vận hành:	Quản lý tập trung khách hàng, tài xế, phương tiện và chuyến đi
- Ban lãnh đạo:	Có dữ liệu và báo cáo để đánh giá doanh thu, hoạt động và hiệu quả tài xế
- Doanh nghiệp:	Giảm thao tác thủ công, tăng khả năng mở rộng và phát triển thêm dịch vụ

### Bước 2: Xác định Stakeholder và Vai trò

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
### Bước 3: Mục đích của nghiệp vụ

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

### Bước 4: Xác định phạm vi

Hệ thống cần đảm bảo thực hiện được quy trình đặt xe cơ bản:

**Bước 1:** Khách hàng đăng nhập hệ thống.

**Bước 2:** Khách hàng nhập điểm đón và điểm đến.

**Bước 3:** Hệ thống tính và hiển thị giá cước.

**Bước 4:** Khách hàng xác nhận đặt xe.

**Bước 5:** Hệ thống tìm tài xế phù hợp.

**Bước 6:** Tài xế nhận chuyến.

**Bước 7:** Khách hàng theo dõi trạng thái và vị trí tài xế.

**Bước 8:** Tài xế thực hiện chuyến và cập nhật trạng thái.

**Bước 9:** Tài xế hoàn thành chuyến.

**Bước 10:** Khách hàng thanh toán.

**Bước 11:** Hệ thống lưu lịch sử chuyến.

**Bước 12:** Khách hàng đánh giá tài xế.

---
*Đăng nhập → Đặt xe → Chọn loại xe → Xác nhận chuyến → Tài xế nhận chuyến → Theo dõi chuyến → Hoàn thành chuyến → Thanh toán → Xem lịch sử → Đánh giá tài xế.*
---
## Lộ trình 7 tuần 

| Tuần | Nội dung thực hiện | Kết quả cần đạt |
|:---:|---|---|
| **Tuần 1** | Phân tích yêu cầu, xác định phạm vi, thiết kế cơ sở dữ liệu và kiến trúc hệ thống. | Hoàn thiện yêu cầu, sơ đồ nghiệp vụ, cơ sở dữ liệu và thiết kế tổng thể. |
| **Tuần 2** | Xây dựng **Module Xác thực** và **Module Quản lý người dùng**. | Người dùng có thể đăng ký, đăng nhập, đăng xuất và được phân quyền. |
| **Tuần 3** | Xây dựng **Module Quản lý tài xế** và **Module Quản lý phương tiện**. | Tài xế có hồ sơ, phương tiện và trạng thái sẵn sàng nhận chuyến. |
| **Tuần 4** | Xây dựng **Module Quản lý đặt xe** và **Module Quản lý chuyến đi**. | Khách hàng có thể đặt xe và tài xế có thể nhận, cập nhật chuyến. |
| **Tuần 5** | Xây dựng **Module Quản lý bản đồ và định vị**. | Hiển thị vị trí, điểm đón, điểm đến và theo dõi vị trí tài xế. |
| **Tuần 6** | Xây dựng **Module Quản lý thanh toán**, **Module Lịch sử & Đánh giá** và **Module Quản trị hệ thống**. | Hoàn thành các chức năng thanh toán, lịch sử, đánh giá và quản trị cơ bản. |
| **Tuần 7** | Tích hợp toàn bộ module, kiểm thử, sửa lỗi và hoàn thiện hệ thống. | Hệ thống hoạt động hoàn chỉnh theo quy trình đặt xe trực tuyến cơ bản. |

### Bước 5: Yêu cầu nghiệp vụ 

## Bảng Ma trận Quy trình Nghiệp vụ (MMBP Matrix)

| STT | Giai đoạn                  | Quy trình nghiệp vụ      | Bước thực hiện                                                              | Tác nhân           | Modul hệ thống   | Thực thể dữ liệu                    |
| :-: | -------------------------- | ------------------------ | --------------------------------------------------------------------------- | ------------------ | ---------------- | ----------------------------------- |
|  1  | **Khởi tạo & Xác thực**    | Đăng ký & Đăng nhập      | Tạo tài khoản, xác thực OTP/Mật khẩu và cấp Token phiên làm việc            | Khách hàng, Tài xế | Auth Module      | `User`, `Account`, `Token`          |
|  2  |                            | Phân quyền (RBAC)        | Cấp quyền truy cập giao diện và chức năng tương ứng theo vai trò            | All Users          | Auth Module      | `Role`, `Permission`                |
|  3  | **Quản lý Khách & Tài xế** | Quản lý Hồ sơ Khách hàng | Lưu địa chỉ yêu thích, xem lịch sử chuyến đi & cài đặt thanh toán           | Khách hàng         | Customer Module  | `CustomerProfile`, `SavedAddress`   |
|  4  |                            | Duyệt & Quản lý Tài xế   | Cập nhật bằng lái/đăng ký xe, kiểm duyệt hồ sơ tài xế vận hành              | Tài xế, Ops        | Driver Module    | `DriverProfile`, `Vehicle`          |
|  5  | **Đặt xe & Điều phối**     | Khởi tạo Đặt xe          | Chọn điểm đi/đến, hệ thống đo khoảng cách, ước tính thời gian & báo giá     | Khách hàng         | Booking Module   | `Trip`, `FareEstimation`            |
|  6  |                            | Ghép chuyến Tự động      | Định vị GPS, tìm tài xế gần nhất và phát thông báo mời chuyến               | Hệ thống, Tài xế   | Booking Module   | `Trip`, `DriverLocation`            |
|  7  |                            | Xử lý Từ chối / Timeout  | Tài xế nhận/từ chối. Quá thời gian chờ tự động chuyển sang tài xế tiếp theo | Hệ thống, Tài xế   | Booking Module   | `TripStatusLog`, `DispatchRule`     |
|  8  | **Vận hành & Theo dõi**    | Quản lý Tiến trình       | Cập nhật: Đã nhận → Đón khách → Đang di chuyển → Hoàn thành                 | Tài xế             | Booking Module   | `Trip`, `TripStatusHistory`         |
|  9  |                            | Theo dõi Real-time       | Cập nhật vị trí GPS tài xế liên tục trên bản đồ thời gian thực              | Khách hàng, Tài xế | Tracking Module  | `GPSLog`, `LiveTracking`            |
|  10 |                            | Giám sát & Hỗ trợ        | Giám sát danh sách chuyến đi real-time, can thiệp điều xe/hủy xe khi sự cố  | NV Vận hành        | Dashboard Module | `Trip`, `IncidentLog`               |
|  11 | **Thanh toán & Tài chính** | Thanh toán Tiền mặt      | Khách trả tiền mặt khi đến nơi; tài xế xác nhận đã thu đủ trên ứng dụng     | Khách hàng, Tài xế | Payment Module   | `PaymentTransaction`, `CashReceipt` |
|  12 |                            | Thanh toán Trực tuyến    | Tự động trừ tiền qua Ví/Thẻ (Tokenization) khi kết thúc chuyến              | Hệ thống, Cổng TT  | Payment Module   | `PaymentTransaction`, `Invoice`     |
|  13 |                            | Đối soát Tài chính       | Tra cứu giao dịch, tính chiết khấu hoa hồng & quản lý ví tài xế             | NV Tài chính       | Dashboard Module | `DriverWallet`, `RevenueShare`      |
|  14 | **Đánh giá & Báo cáo**     | Đánh giá Dịch vụ         | Chấm điểm 1-5 sao và gửi phản hồi chất lượng phục vụ sau chuyến             | Khách hàng         | Customer Module  | `Feedback`, `Rating`                |
|  15 |                            | Báo cáo Quản trị         | Trích xuất báo cáo doanh thu, tỷ lệ hoàn thành/hủy chuyến & chỉ số KPI      | Ban Giám đốc       | Dashboard Module | `ExecutiveReport`, `Analytics`      |

## Bảng Yêu cầu Nghiệp vụ (Business Requirements)

|   Mã YC   | Nhóm nghiệp vụ         | Mô tả Yêu cầu Nghiệp vụ (Business Requirement)                                                  |
| :-------: | ---------------------- | ----------------------------------------------------------------------------------------------- |
| **BR-01** | **Xác thực & RBAC**    | Đăng ký/Đăng nhập an toàn và phân quyền truy cập theo vai trò (Khách hàng, Tài xế, Ops, Admin). |
| **BR-02** | **Quản lý Khách hàng** | Lưu trữ thông tin hồ sơ, lịch sử chuyến đi, ưu đãi và phản hồi của Khách hàng.                  |
| **BR-03** | **Khởi tạo Chuyến đi** | Nhập Điểm đi, Điểm đến, xem trước cước phí ước tính và chọn loại hình dịch vụ.                  |
| **BR-04** | **Điều phối Tài xế**   | Tự động tìm kiếm và phân công tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng.            |
| **BR-05** | **Quản lý Chuyến đi**  | Cho phép tài xế nhận chuyến và cập nhật trạng thái từ nhận chuyến đến hoàn thành.               |
| **BR-06** | **Theo dõi Real-time** | Cập nhật và hiển thị vị trí tài xế trên bản đồ theo thời gian thực.                             |
| **BR-07** | **Thanh toán**         | Hỗ trợ thanh toán tiền mặt và thanh toán trực tuyến sau khi hoàn thành chuyến.                  |
| **BR-08** | **Quản lý Giao dịch**  | Lưu trữ và tra cứu thông tin giao dịch, hóa đơn và biên nhận thanh toán.                        |
| **BR-09** | **Đánh giá Dịch vụ**   | Cho phép khách hàng đánh giá tài xế từ 1-5 sao và gửi phản hồi sau chuyến.                      |
| **BR-10** | **Báo cáo Quản trị**   | Cung cấp báo cáo doanh thu, số chuyến, tỷ lệ hoàn thành/hủy và các chỉ số KPI.                  |

### Bước 6: Phân rã các yêu cầu chức năng


### Bước 7: Vẽ use case diagram

### Bước 8: Đặc tả use case



### Bước 9: Phân tích quy trình nghiệp vụ seq



### Bước 10: Phân tích quy tắc nghiệp vụ business rule
ví dụ ưu tiên cho rating cao
s
