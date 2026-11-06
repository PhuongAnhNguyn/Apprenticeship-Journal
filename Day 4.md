# Nhật ký học tập & Nghiên cứu Kỹ thuật

## 1. Học tập & Nghiên cứu Kỹ thuật Ô tô (Automotive Engineering)

### Nội dung nghiên cứu

- Tìm hiểu về hệ thống điện – điện tử và mạng giao tiếp trên ô tô hiện đại:
  - Giao thức CAN Bus và LIN Bus.
  - Các cụm cảm biến và hộp điều khiển trung tâm ECU.
- Nghiên cứu cơ chế thu thập dữ liệu từ các cảm biến nhiệt độ, áp suất và độ ẩm trong khoang động cơ / cabin.
- Phân tích nguyên lý tối ưu nguồn điện 12V / 5V / 3.3V và khả năng chống nhiễu tín hiệu trong môi trường hoạt động khắc nghiệt.

### Bài học & Kỹ năng đạt được

- Hiểu rõ cách các cảm biến truyền tín hiệu điện áp / analog về vi điều khiển và cách xử lý nhiễu trên đường truyền.
- Nắm vững tư duy thiết kế hệ thống phần cứng bền bỉ.
- Hiểu tầm quan trọng của việc tối ưu hóa chu kỳ đọc dữ liệu để hệ thống vận hành ổn định và liên tục.

---

## 2. Buổi chiều: Lên ý tưởng & Đặt nền móng dự án "Chậu cây thông minh" (Smart Plant Pot)

**Thời gian:** 13:30 – 17:30

### 2.1. Xác định mục tiêu dự án

Phát triển hệ thống chậu cây thông minh có khả năng tự động giám sát môi trường đất và không khí thông qua kết nối không dây.

### 2.2. Nghiên cứu & Lựa chọn linh kiện phần cứng

| Thành phần | Linh kiện / Công nghệ | Chức năng |
|---|---|---|
| Vi điều khiển trung tâm | ESP32 | Xử lý dữ liệu, tích hợp Wi-Fi / Bluetooth |
| Cảm biến môi trường | DHT11 | Đo nhiệt độ và độ ẩm không khí |
| Cảm biến độ ẩm đất | Analog Soil Moisture Sensor | Đo độ ẩm đất thông qua tín hiệu ADC |
| Thiết bị hiển thị | OLED I2C 0.96 inch | Hiển thị thông số trực tiếp |
| Giao tiếp | Web Dashboard | Theo dõi dữ liệu qua trình duyệt |

### 2.3. Thiết kế kiến trúc mạng (Architecture Design)

- Lựa chọn giải pháp **Wi-Fi Access Point (AP Mode)**.
- ESP32 tự phát sóng Wi-Fi nội bộ, cho phép điện thoại hoặc máy tính kết nối trực tiếp.
- Người dùng truy cập Web Dashboard thông qua địa chỉ IP mặc định:

  `192.168.4.1`

- Ưu điểm:
  - Không phụ thuộc vào hạ tầng Internet bên ngoài.
  - Có thể truy cập và theo dõi dữ liệu trực tiếp từ ESP32.
  - Phù hợp với mô hình IoT độc lập.

### 2.4. Lên sơ đồ thuật toán & Chu kỳ lấy mẫu

- **Chu kỳ lấy mẫu:** 2 giây/lần (2000ms).
  - Đảm bảo khoảng thời gian đọc dữ liệu phù hợp với giới hạn của cảm biến DHT11.
  - Hạn chế việc đọc dữ liệu quá thường xuyên.
- **Giao thức trao đổi dữ liệu:**
  - Xây dựng JSON API tại endpoint `/data`.
  - ESP32 trả về dữ liệu cảm biến dưới dạng JSON.
- **Cập nhật giao diện:**
  - Sử dụng AJAX / Fetch API.
  - Tự động cập nhật Web Dashboard theo thời gian thực mà không cần tải lại toàn bộ trang.

---

## 3. Đánh giá cuối ngày & Hướng phát triển tiếp theo (Next Steps)

### 3.1. Đánh giá cá nhân

- Hoàn thành đúng tiến độ nội dung lý thuyết về kỹ thuật ô tô.
- Hoàn thiện khung kiến trúc phần cứng và phần mềm cho dự án IoT.
- Xác định được các linh kiện chính, phương thức kết nối và cơ chế trao đổi dữ liệu của hệ thống chậu cây thông minh.

### 3.2. Kế hoạch tiếp theo

1. **Lắp ráp phần cứng:** Kết nối ESP32, cảm biến độ ẩm đất, DHT11 và màn hình OLED.
2. **Hiệu chuẩn cảm biến (Calibration):** Khảo sát giá trị ADC trong các điều kiện đất khác nhau để xây dựng ngưỡng độ ẩm phù hợp.
3. **Kiểm thử Web Server:** Đánh giá khả năng kết nối, tốc độ phản hồi và độ ổn định khi cập nhật dữ liệu liên tục.
4. **Nghiên cứu điều khiển tự động:** Tích hợp Rơ-le (Relay) để điều khiển máy bơm nước dựa trên dữ liệu độ ẩm đất.
