# Các khái niệm cơ bản về Robot thông minh

**Giảng viên:** TS. Nguyễn Công Hồng Phong

## 1. Khái niệm và Lịch sử phát triển Robotics

### 1.1. Khái niệm Robot

- **Nguồn gốc thuật ngữ:** Từ "Robot" xuất phát từ tiếng Séc (*Robota* nghĩa là công việc tạp dịch), xuất hiện lần đầu năm 1920 trong vở kịch *Rossum's Universal Robots* của Karel Capek.
- **Định nghĩa:** Robot là một máy móc/tác nhân cơ khí – điện tử hoạt động tự động dưới sự điều khiển của máy tính. Theo tiêu chuẩn ISO 8373, robot công nghiệp có thể lập trình, vận động trên 3 trục trở lên.
- **Tính liên ngành:** Ngành Robotics kết hợp giữa Cơ học, Cơ khí, Kỹ thuật điện - điện tử, Kỹ thuật điều khiển - lập trình và CNTT.

### 1.2. Cột mốc lịch sử và xu hướng

- **1495:** Leonardo Da Vinci thiết kế robot hình người đầu tiên.
- **Thập niên 1960:** Robot thương mại Unimate ra đời.
- **Xu hướng hiện đại:** Tích hợp AI/Machine Learning, robot di động tự động (AMR), robot cộng tác (Cobot), Digital Twin và Robot hình người (Humanoid).

## 2. Cấu trúc cơ bản của Robot công nghiệp

Một hệ thống robot gồm các thành phần chính kết nối khép kín:

- **Tay máy robot:** Kết cấu cơ khí di chuyển và thao tác.
- **Hệ thống cảm biến:**
  - Encoder: Đo vị trí và góc.
  - Cảm biến lực/mô-men: Đo lực và mô-men tác động.
- **Hệ thống điều khiển:**
  - CPU: Bộ xử lý trung tâm.
  - I/O: Khối đầu vào/đầu ra.
  - Drive: Các bộ lái điều khiển động cơ.
  - Safety: Hệ thống an toàn.
- **Môi trường làm việc:** Không gian hoạt động của robot.

## 3. Phân loại Robot

### 3.1. Theo dạng chuyển động

- **Cartesian (Gantry):** Tốc độ và độ chính xác cao, chi phí thấp nhưng cần không gian rộng.
- **Cylindrical / SCARA (Tọa độ trụ):** Tốc độ cao, tối ưu cho lắp ráp nhanh và gắp - đặt.
- **Articulated (Khớp quay):** Vùng làm việc rộng, linh hoạt trong hàn và sơn.
- **Parallel (Robot song song):** Tốc độ rất cao, phù hợp gắp - đặt vật nhẹ (ví dụ: đóng gói bánh kẹo).

### 3.2. Theo ứng dụng

- **Robot công nghiệp:** Sử dụng trong sản xuất và nhà máy.
- **Robot cộng tác (Cobot):** Làm việc cùng con người.
- **Robot di động (AMR):** Tự động di chuyển và vận chuyển.
- **Robot đi chân:** Ví dụ Spot của Boston Dynamics.
- **Robot dịch vụ/y tế:** Hỗ trợ con người trong sinh hoạt và y tế.

## 4. Quy trình thiết kế Robot

Quy trình gồm 9 bước tiêu chuẩn:

1. **Ý tưởng (Idea)**
2. **Thiết kế cơ cấu (Mechanism Design)**
3. **Phân tích động học (Kinematic Analysis)**
4. **Phân tích động lực học (Dynamic Analysis)**
5. **Lựa chọn bộ truyền động (Actuator Selection)**
6. **Thiết kế chi tiết (Detailed Design)**
7. **Thiết kế hệ thống điều khiển (Control Design)**
8. **Chế tạo mẫu thử (Prototyping)**
9. **Tối ưu hóa (Optimization)**

## 5. Đạo đức và Ba định luật an toàn Robot

### 5.1. Ba định luật của Isaac Asimov

1. **Định luật 1:** Robot không được hại con người hoặc để con người bị hại do không hành động.
2. **Định luật 2:** Robot phải tuân lệnh con người, trừ khi lệnh đó vi phạm Định luật 1.
3. **Định luật 3:** Robot phải bảo vệ sự tồn tại của mình, miễn là không vi phạm Định luật 1 và Định luật 2.

### 5.2. Thảo luận đạo đức

Đánh giá các trường hợp thực tế như:

- **Chatbot:** Có thể cung cấp thông tin sai lệch hoặc gây hại cho con người.
- **Drone tự động tấn công:** Đặt ra vấn đề về trách nhiệm và nguy cơ gây tổn hại cho con người.
- **AI tự bảo vệ hệ thống:** Cần đảm bảo việc tự bảo vệ không gây nguy hiểm cho con người.

Các tình huống trên có thể được đối chiếu với ba định luật của Isaac Asimov để thảo luận về trách nhiệm và đạo đức trong phát triển robot thông minh.
