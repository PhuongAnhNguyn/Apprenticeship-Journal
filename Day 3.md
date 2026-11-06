# Chế tạo trạm quan trắc thời tiết thông minh
**Ứng dụng: ESP32 IoT, AI và In 3D**

## 1. Tổng quan dự án và phương pháp tiếp cận

### 1.1. Mục tiêu dự án

Tạo ra một trạm thời tiết thông minh tích hợp 4 lĩnh vực STEM: **Điện tử, Lập trình, AI và Cơ khí**.

Hệ thống có các chức năng:
- Đo các thông số môi trường.
- Hiển thị dữ liệu trực tiếp tại trạm.
- Truyền dữ liệu lên Website theo thời gian thực.
- Đánh giá nguy cơ mưa bằng mô hình AI nhúng.

### 1.2. Phương pháp sư phạm 3 bước

1. Trực quan hóa bằng ví dụ đời thực.
2. Giải thích bản chất kỹ thuật.
3. Thực hành trực tiếp.

## 2. Bối cảnh và ví dụ ẩn dụ "Cơ thể con người"

Hệ thống được ví như một cơ thể sinh học:

| Bộ phận cơ thể | Thành phần trong hệ thống | Chức năng |
|---|---|---|
| Làn da | Cảm biến DHT11 và cảm biến mưa | Thu thập dữ liệu môi trường. |
| Dây thần kinh | Dây Jumper và các chân GPIO | Truyền tín hiệu giữa các linh kiện. |
| Bộ não | Vi điều khiển ESP32 | Xử lý dữ liệu và thuật toán. |
| Khuôn mặt | Màn hình OLED 0.96 inch | Hiển thị thông tin tại chỗ. |
| Điện thoại / Mạng | Wi-Fi và Web Server | Theo dõi dữ liệu từ xa. |
| Khả năng phán đoán | Thuật toán AI | Đánh giá và dự báo nguy cơ mưa. |

## 3. Chi tiết kiến thức kỹ thuật chính

### 3.1. Bo mạch ESP32 và tín hiệu

- **Nguồn nuôi:**
  - 3V3: Nguồn điện áp 3.3V.
  - GND: Chân nối đất, dùng làm mốc điện áp chung.
- **GPIO:** Các chân đầu vào/đầu ra dùng để kết nối và giao tiếp với linh kiện.
- **Digital và Analog:**
  - Digital: Tín hiệu có hai trạng thái 0/1 (Bật/Tắt).
  - Analog: Tín hiệu có giá trị thay đổi liên tục.
  - ESP32 sử dụng bộ ADC 12-bit để chuyển đổi tín hiệu Analog thành giá trị số từ 0 đến 4095.

### 3.2. Nhóm cảm biến (DHT11 và cảm biến mưa)

**Cảm biến DHT11:**
- Gồm bộ phận cảm biến độ ẩm và điện trở nhiệt NTC để đo nhiệt độ.
- Truyền dữ liệu qua một dây DATA (GPIO 4).
- Vỏ cảm biến có các khe hở để tiếp xúc với không khí xung quanh.

**Cảm biến mưa:**
- Hoạt động dựa trên nguyên lý dẫn điện giữa hai hàng mạch kim loại khi có nước mưa.
- Khi bề mặt càng ướt, điện trở càng giảm.
- Giá trị Analog đọc được tại GPIO 34 thường giảm khi độ ướt tăng.

### 3.3. Màn hình OLED 0.96 inch và giao thức I2C

**Cấu tạo:**
- Màn hình có ma trận 128 × 64 điểm ảnh, tương đương 8.192 pixels.
- Các điểm ảnh OLED có khả năng tự phát sáng.

**Giao thức I2C:**
- SCL (Clock): Tạo xung nhịp đồng bộ cho quá trình truyền dữ liệu.
- SDA (Data): Truyền dữ liệu giữa các thiết bị.
- Địa chỉ I2C mặc định thường dùng: `0x3C`.

### 3.4. Kết nối Wi-Fi và Web Server thời gian thực

- ESP32 hoạt động như một Web Server thu nhỏ.
- Khi điện thoại hoặc máy tính truy cập địa chỉ IP của ESP32, trạm sẽ gửi lại trang Web.

**Cấu trúc Website gồm 3 lớp:**

1. **HTML:** Xây dựng cấu trúc và nội dung trang Web.
2. **CSS:** Thiết kế giao diện, màu sắc và bố cục.
3. **JavaScript:** Tự động cập nhật dữ liệu JSON mỗi 2 giây thông qua AJAX/Fetch.

**Chế độ Wi-Fi dự phòng (Access Point - AP):**
- Khi mất kết nối Wi-Fi của phòng Lab, ESP32 có thể tự phát một mạng Wi-Fi riêng.
- Người dùng kết nối trực tiếp vào mạng này để truy cập trạm.
- Địa chỉ truy cập mặc định: `192.168.4.1`.

### 3.5. Trí tuệ nhân tạo nhúng (TinyML / AI dự báo)

**Nguyên lý:**
- Khác với lập trình truyền thống chỉ kiểm tra một điều kiện cố định, AI có thể kết hợp nhiều thông tin:
  - Nhiệt độ.
  - Độ ẩm không khí.
  - Độ ướt bề mặt cảm biến mưa.

**Mô hình AI nhúng:**
- Sử dụng nơ-ron nhân tạo với các trọng số:
  - W1 = 0.45
  - W2 = 0.40
  - W3 = 0.15
- Kết hợp với cây quyết định (Decision Tree) để tính điểm nguy cơ mưa từ 0–100%.

**Phân loại 4 trạng thái thời tiết:**

1. Nắng đẹp.
2. Râm mát.
3. Sắp mưa!
4. Đang mưa!

Mỗi trạng thái đi kèm lời khuyên hành động thực tế cho người sử dụng.

### 3.6. Thiết kế vỏ cơ khí và In 3D

**Phân biệt công nghệ:**

- **Gia công cắt gọt (Subtractive Manufacturing):** Loại bỏ vật liệu bằng các phương pháp như phay, tiện để tạo hình sản phẩm.
- **In 3D FDM (Additive Manufacturing):** Tạo sản phẩm bằng cách đắp từng lớp nhựa PLA mỏng, ví dụ với chiều cao lớp 0.2 mm.

**Quy trình thiết kế và in 3D gồm 4 bước:**

1. Dựng mô hình 3D bằng SolidWorks (`.SLDPRT`).
2. Xuất file lưới tam giác (`.STL`).
3. Cắt lớp bằng phần mềm Slicer và xuất mã lệnh (`.GCODE`).
4. In 3D và lắp ráp.

**Đặc điểm thiết kế vỏ:**
- Có cửa sổ hiển thị OLED.
- Có khe thoáng cho cảm biến DHT11.
- Có mái nghiêng 35° cho cảm biến mưa để hỗ trợ thoát nước.
- Có lỗ cắm cáp USB.

## 4. Sơ đồ đấu nối phần cứng chính

| Linh kiện | Chân linh kiện | Chân nối ESP32 | Ghi chú kỹ thuật |
|---|---|---|---|
| Nguồn chung | VCC / GND | 3V3 / GND | Dùng chung mốc GND và nguồn 3.3V. |
| OLED 0.96" | SCL / SDA | GPIO 22 / GPIO 21 | Giao tiếp I2C. |
| DHT11 | DATA (S) | GPIO 4 | Truyền dữ liệu một dây. |
| Cảm biến mưa | AO (Analog Out) | GPIO 34 | Sử dụng ADC1 vì ADC2 có thể bị hạn chế khi Wi-Fi hoạt động. |
| Còi báo động | S | GPIO 12 | Cảnh báo khi AI dự báo "Sắp mưa" hoặc "Đang mưa". |

## 5. Cẩm nang xử lý sự cố nhanh (Troubleshooting)

### 5.1. Lỗi nạp code (Timed out)

- Kiểm tra cổng COM/Port đã chọn.
- Khi màn hình hiển thị `Connecting...`, thử giữ nút BOOT trên bo ESP32 khoảng 2 giây.

### 5.2. Màn hình OLED không sáng

- Kiểm tra nguồn 3V3 và GND.
- Kiểm tra dây SDA (GPIO 21) và SCL (GPIO 22) đã nối đúng chưa.
- Có thể kiểm tra lại thứ tự dây tín hiệu.

### 5.3. DHT11 báo `nan` hoặc 0

- Kiểm tra dây DATA đã nối đúng GPIO 4 chưa.
- Kiểm tra khai báo đúng loại cảm biến trong code.
- Kiểm tra nguồn cấp và kết nối dây.

### 5.4. Không mở được Website trên điện thoại

- Đảm bảo điện thoại và ESP32 đang kết nối cùng mạng Wi-Fi.
- Nếu sử dụng Wi-Fi dự phòng (AP), kết nối vào mạng do ESP32 phát ra.
- Truy cập địa chỉ `192.168.4.1`.
