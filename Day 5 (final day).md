# BÁO CÁO CUỐI KỲ

**Slides Canva:** (https://canva.link/hxhp7t1ttltc2pl)

## 1. Đặt vấn đề & Giải pháp

- **Đặt vấn đề:**
  - Việc chăm sóc cây thường dựa vào kinh nghiệm cá nhân, dễ dẫn đến quên tưới nước khiến đất bị khô hoặc tưới quá nhiều gây úng rễ.
  - Khó theo dõi và chăm sóc cây khi người dùng vắng nhà.

- **Giải pháp:**
  - Xây dựng chậu cây thông minh ứng dụng công nghệ IoT.
  - Đo đạc và hiển thị các thông số môi trường: nhiệt độ, độ ẩm không khí và độ ẩm đất.
  - Truyền dữ liệu qua Internet để người dùng có thể theo dõi tình trạng cây từ xa.

## 2. Thành phần linh kiện & Kiến trúc hệ thống

| Thành phần | Linh kiện | Chức năng |
|---|---|---|
| Bộ điều khiển trung tâm | ESP32-S3 | Xử lý dữ liệu và kết nối Wi-Fi |
| Cảm biến không khí | DHT11 | Đo nhiệt độ và độ ẩm không khí |
| Cảm biến đất | Cảm biến độ ẩm đất | Đo độ ẩm của đất |
| Hiển thị tại chỗ | Màn hình OLED | Hiển thị thông số môi trường |
| Giám sát từ xa | Website | Theo dõi dữ liệu qua Wi-Fi / Internet |

## 3. Đánh giá sản phẩm

### Ưu điểm

- Giám sát đồng thời nhiều thông số môi trường.
- Cho phép theo dõi tình trạng cây từ xa qua Internet.
- Có khả năng cảnh báo khi cây cần được tưới nước.
- Thiết kế nhỏ gọn, dễ sử dụng và có khả năng nâng cấp.

### Hạn chế

- Chưa tích hợp hệ thống tưới nước tự động.
- Phụ thuộc vào kết nối Wi-Fi để giám sát từ xa.
- Cảm biến có thể phát sinh sai số.
- Cảm biến độ ẩm đất cần được hiệu chuẩn để đảm bảo độ chính xác.

## 4. Hướng phát triển trong tương lai

1. **Trực quan hóa dữ liệu:** Bổ sung biểu đồ lịch sử nhiệt độ và độ ẩm để theo dõi sự thay đổi của môi trường theo thời gian.
2. **Cảnh báo thông minh:** Gửi thông báo đến điện thoại khi độ ẩm đất xuống thấp.
3. **Tự động hóa tưới nước:** Tích hợp máy bơm và hệ thống điều khiển tự động dựa trên dữ liệu cảm biến.
4. **Mở rộng hệ thống:** Bổ sung cảm biến ánh sáng và phát triển khả năng quản lý nhiều chậu cây cùng lúc.
