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

## 1. Chức năng Đăng ký và xác thực tài khoản

### FR-01: Đăng ký tài khoản
- Hệ thống cho phép khách hàng đăng ký tài khoản bằng thông tin cá nhân.
- Hệ thống kiểm tra thông tin đăng ký hợp lệ.
- Hệ thống không cho phép đăng ký trùng thông tin tài khoản.

### FR-02: Đăng nhập
- Hệ thống cho phép người dùng đăng nhập bằng tài khoản và mật khẩu.
- Hệ thống kiểm tra thông tin xác thực.
- Hệ thống xác định vai trò của người dùng sau khi đăng nhập.

### FR-03: Phân quyền người dùng
- Hệ thống phân quyền theo vai trò:
  - Khách hàng.
  - Tài xế.
  - Nhân viên vận hành.
  - Quản trị viên.
  - Nhân viên tài chính.

---

## 2. Chức năng Đặt xe

### FR-04: Nhập thông tin chuyến đi
- Hệ thống cho phép khách hàng nhập điểm đón.
- Hệ thống cho phép khách hàng nhập điểm đến.
- Hệ thống xác định khoảng cách giữa điểm đón và điểm đến.

### FR-05: Chọn loại xe
- Hệ thống hiển thị các loại xe đang được cung cấp.
- Khách hàng có thể lựa chọn loại xe phù hợp.
- Hệ thống chỉ tìm tài xế có phương tiện phù hợp với loại xe khách hàng đã chọn.

### FR-06: Tính giá cước
- Hệ thống xác định giá cước dựa trên loại xe và quãng đường.
- Hệ thống hiển thị giá cước dự kiến cho khách hàng.
- Khách hàng xác nhận giá trước khi đặt xe.

### FR-07: Xác nhận đặt xe
- Hệ thống tạo yêu cầu đặt xe sau khi khách hàng xác nhận.
- Hệ thống lưu thông tin điểm đón, điểm đến, loại xe và giá cước dự kiến.
- Hệ thống chuyển yêu cầu sang chức năng tìm tài xế.

---

## 3. Chức năng Tìm và phân bổ tài xế

### FR-08: Xác định vị trí tài xế
- Hệ thống lấy vị trí hiện tại của các tài xế.
- Hệ thống chỉ xem xét các tài xế đang **sẵn sàng nhận chuyến**.

### FR-09: Lọc tài xế theo loại xe
- Hệ thống kiểm tra loại phương tiện của tài xế.
- Hệ thống loại bỏ các tài xế không phù hợp với loại xe khách hàng đã chọn.

### FR-10: Lọc tài xế theo trạng thái
- Hệ thống chỉ lựa chọn tài xế có trạng thái **Đang sẵn sàng**.
- Không lựa chọn tài xế đang thực hiện chuyến.
- Không lựa chọn tài xế đang ngoại tuyến.

### FR-11: Tính khoảng cách
- Hệ thống tính khoảng cách từ tài xế đến điểm đón.
- Hệ thống sắp xếp danh sách tài xế theo khoảng cách.

### FR-12: Ưu tiên tài xế
- Hệ thống ưu tiên tài xế phù hợp dựa trên:
  1. Đúng loại xe.
  2. Đang sẵn sàng.
  3. Khoảng cách gần điểm đón.
  4. Điểm đánh giá cao hơn khi các điều kiện khác tương đương.

### FR-13: Gửi yêu cầu nhận chuyến
- Hệ thống gửi thông tin chuyến đến tài xế được ưu tiên.
- Tài xế nhận được thông tin điểm đón, điểm đến và loại xe.

### FR-14: Chờ tài xế xác nhận
- Hệ thống chờ phản hồi của tài xế trong một khoảng thời gian quy định.
- Nếu tài xế **chấp nhận**, hệ thống xác nhận tài xế cho chuyến.
- Nếu tài xế **từ chối**, hệ thống chuyển sang tài xế tiếp theo.
- Nếu tài xế **không phản hồi**, hệ thống xem như yêu cầu đã hết thời gian và tiếp tục tìm tài xế khác.

### FR-15: Tiếp tục tìm tài xế
- Hệ thống tiếp tục tìm tài xế phù hợp khi tài xế trước từ chối hoặc không phản hồi.
- Hệ thống không gửi lại yêu cầu cho tài xế đã từ chối chuyến.
- Nếu không còn tài xế phù hợp, hệ thống thông báo cho khách hàng.

---

## 4. Chức năng Quản lý chuyến đi

### FR-16: Xác nhận tài xế
- Hệ thống xác nhận tài xế sau khi tài xế chấp nhận chuyến.
- Hệ thống cập nhật trạng thái chuyến thành **Đã nhận tài xế**.
- Hệ thống thông báo thông tin tài xế cho khách hàng.

### FR-17: Cập nhật trạng thái chuyến
Hệ thống cho phép tài xế cập nhật:

**Đã nhận chuyến → Đã đến điểm đón → Đã đón khách → Đang di chuyển → Hoàn thành chuyến**

### FR-18: Theo dõi chuyến đi
- Hệ thống cập nhật vị trí tài xế.
- Hệ thống hiển thị vị trí tài xế trên bản đồ.
- Khách hàng có thể theo dõi trạng thái chuyến.

### FR-19: Hủy chuyến
- Hệ thống cho phép khách hàng hủy chuyến theo điều kiện quy định.
- Hệ thống cập nhật trạng thái chuyến thành **Đã hủy**.
- Hệ thống thông báo kết quả hủy chuyến.

---

## 5. Chức năng Thanh toán

### FR-20: Chọn phương thức thanh toán
Khách hàng có thể chọn:
- Tiền mặt.
- Thanh toán trực tuyến.

### FR-21: Thanh toán
- Hệ thống ghi nhận số tiền cần thanh toán.
- Nếu thanh toán tiền mặt, hệ thống ghi nhận trạng thái thanh toán sau khi chuyến hoàn thành.
- Nếu thanh toán trực tuyến, hệ thống gửi yêu cầu đến cổng thanh toán.

### FR-22: Cập nhật trạng thái thanh toán
Hệ thống nhận kết quả thanh toán và cập nhật:
- Thanh toán thành công.
- Thanh toán thất bại.
- Chưa thanh toán.

---

## 6. Chức năng Đánh giá tài xế

### FR-23: Đánh giá chuyến đi
- Sau khi chuyến hoàn thành, hệ thống cho phép khách hàng đánh giá tài xế.
- Khách hàng có thể chọn số sao.
- Khách hàng có thể nhập nhận xét.

### FR-24: Lưu đánh giá
- Hệ thống lưu đánh giá gắn với chuyến đi.
- Hệ thống cập nhật điểm đánh giá của tài xế.

---

## 7. Chức năng Lịch sử chuyến đi

### FR-25: Lưu lịch sử
- Hệ thống lưu thông tin các chuyến đã thực hiện.

### FR-26: Xem lịch sử
- Khách hàng có thể xem lịch sử chuyến đi của mình.
- Tài xế có thể xem lịch sử các chuyến đã nhận.

Thông tin lịch sử gồm:
- Mã chuyến.
- Điểm đón.
- Điểm đến.
- Loại xe.
- Tài xế.
- Giá cước.
- Phương thức thanh toán.
- Trạng thái chuyến.
- Thời gian thực hiện.

---

## 8. Chức năng Quản lý tài xế

### FR-27: Quản lý trạng thái tài xế

Hệ thống quản lý các trạng thái:

**Ngoại tuyến → Sẵn sàng → Đang nhận chuyến → Đang thực hiện chuyến → Hoàn thành**

### FR-28: Quản lý thông tin tài xế
- Lưu thông tin cá nhân tài xế.
- Lưu thông tin giấy phép lái xe.
- Lưu thông tin phương tiện.
- Lưu loại xe.
- Lưu điểm đánh giá.

---

## 9. Chức năng Quản trị hệ thống

### FR-29: Quản lý người dùng
- Xem danh sách người dùng.
- Thêm, sửa, khóa tài khoản.
- Quản lý vai trò người dùng.

### FR-30: Quản lý tài xế
- Xem danh sách tài xế.
- Kiểm tra thông tin tài xế.
- Quản lý trạng thái tài xế.
- Quản lý thông tin phương tiện.

### FR-31: Quản lý chuyến đi
- Xem danh sách chuyến.
- Tra cứu chuyến.
- Xem trạng thái chuyến.
- Xem thông tin thanh toán.

---

## 10. Chức năng Đối soát tài chính

### FR-32: Quản lý giao dịch
- Hệ thống lưu thông tin các giao dịch thanh toán.
- Nhân viên tài chính có thể tra cứu giao dịch.

### FR-33: Đối soát doanh thu
- Hệ thống tổng hợp doanh thu từ các chuyến hoàn thành.
- Phân loại doanh thu theo phương thức thanh toán.
- Cho phép nhân viên tài chính kiểm tra trạng thái thanh toán.

---

# QUY TRÌNH CHỨC NĂNG CỐT LÕI

```text
Khách hàng đặt xe
        ↓
Xác định điểm đón + loại xe
        ↓
Lấy danh sách tài xế đang sẵn sàng
        ↓
Lọc theo loại xe
        ↓
Tính khoảng cách đến điểm đón
        ↓
Sắp xếp tài xế phù hợp
        ↓
Ưu tiên tài xế gần + đánh giá tốt
        ↓
Gửi yêu cầu cho tài xế
        ↓
   Tài xế phản hồi?
      ↙       ↘
   Nhận       Từ chối/
    ↓        không phản hồi
Xác nhận        ↓
tài xế      Tìm tài xế tiếp theo
    ↓
Bắt đầu chuyến
    ↓
Hoàn thành
    ↓
Thanh toán
    ↓
Đánh giá

### Bước 7: Vẽ use case diagram

### Bước 8: Đặc tả use case



### Bước 9: Phân tích quy trình nghiệp vụ seq



### Bước 10: Phân tích quy tắc nghiệp vụ business rule
ví dụ ưu tiên cho rating cao
s
