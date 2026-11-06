# In 3D – In mọi thứ bạn thích!

## I. Tóm tắt các Công cụ và Nền tảng

### 1. Tinkercad
- Phần mềm thiết kế CAD 3D trên nền tảng đám mây, sử dụng trực tiếp trên trình duyệt web.
- Cho phép dựng mô hình từ các khối cơ bản bằng phép cộng/trừ khối:
  - **Solid:** Khối đặc.
  - **Hole:** Khối rỗng dùng để khoét vật liệu.

### 2. Thingiverse và MakerWorld
- Các kho thư viện mở chứa hàng triệu mô hình in 3D miễn phí từ cộng đồng Maker toàn cầu.
- Hỗ trợ các định dạng file phổ biến như `.STL`, `.3MF`.

### 3. Bambu Lab và Bambu Studio
- **Bambu Lab:** Dòng máy in 3D FDM tốc độ cao.
- **Bambu Studio:** Phần mềm cắt lớp (Slicer), dùng để:
  - Tiền xử lý file `.STL`.
  - Thiết lập thông số in (chiều cao lớp, loại nhựa, Support...).
  - Xuất lệnh `.GCODE` hoặc lưu dự án `.3MF` cho máy in.

### 4. Lithophanemaker.com
- Công cụ trực tuyến chuyển đổi ảnh 2D thành mô hình Lithophane 3D.
- Lithophane là dạng tranh nổi, hiển thị hình ảnh khi có ánh sáng chiếu xuyên qua.

## II. Định hướng In 3D như thế nào là tốt nhất?

### Key 1: Chọn đúng máy in

**Máy FDM (Fused Deposition Modeling):**
- Phù hợp với mẫu thử kỹ thuật, móc khóa, đồ dùng học tập và vỏ hộp IoT.
- Sử dụng sợi nhựa được nung chảy và đùn qua đầu phun.
- Ưu điểm: Giá thành thấp, độ bền cơ học tốt.
- Nhược điểm: Bề mặt có các đường vân lớp in.

**Máy SLA/Resin:**
- Sử dụng nhựa lỏng nhạy sáng UV.
- Ưu điểm: Bề mặt rất mịn, độ chi tiết cao.
- Ứng dụng: Chi tiết nhỏ, nha khoa và kim hoàn.

### Key 2: Chọn hướng đặt chi tiết (Part Orientation)

Tối ưu hướng đặt mô hình trên bàn in bằng các quy tắc:

- **Tối đa diện tích tiếp xúc:** Chọn mặt phẳng có diện tích lớn áp sát bàn in để sản phẩm bám chắc, hạn chế đổ ngã. Có thể sử dụng lệnh `Lay on Face` (phím F).
- **Giảm Support:** Xoay mô hình sao cho các khoang rỗng hoặc mặt chữ hướng lên trên hoặc nằm ngang để giảm vật liệu chống đỡ.
- **Đảm bảo độ bền:** Chi tiết in FDM thường chịu lực tốt hơn dọc theo mặt phẳng X-Y (theo các lớp nhựa) so với phương Z. Vì vậy, cần cân nhắc hướng đặt để hạn chế lực gây tách lớp.

### Key 3: Chọn đúng loại nhựa (PLA vs PETG)

**Nhựa PLA:**
- Dễ in, ít co ngót và cong vênh.
- Màu sắc đa dạng.
- Phù hợp làm móc khóa, mô hình và vỏ hộp nhẹ.
- Hạn chế: Chịu nhiệt kém, có thể mềm ở khoảng 55°C.

**Nhựa PETG:**
- Độ bền cơ học và khả năng chịu va đập tốt.
- Kháng nước và một số hóa chất tốt.
- Chịu nhiệt tốt hơn PLA, khoảng 75°C tùy loại nhựa.
- Phù hợp in chi tiết máy và vật dụng ngoài trời.
- Hạn chế: Dễ xuất hiện hiện tượng kéo tơ nhện (stringing), đặc biệt khi nhựa bị ẩm.

### Key 4: Cấu trúc chống đỡ (Support)

- **Quy tắc 45°:** Những phần nhô ra có góc nghiêng lớn hơn khoảng 45° so với phương thẳng đứng thường cần được xem xét sử dụng Support. Mức độ cần Support còn phụ thuộc vào hình dạng và cấu hình máy in.
- **Tree Support (Support dạng cây):**
  - Có cấu trúc phân nhánh giống cây.
  - Giúp giảm diện tích tiếp xúc với mô hình.
  - Có thể tiết kiệm vật liệu và dễ tháo gỡ hơn trong nhiều trường hợp.
  - Hạn chế nguy cơ làm hỏng bề mặt sản phẩm khi tháo Support.

## III. Tóm tắt Nội dung Buổi học

### Buổi 1: Công nghệ In 3D và Thiết kế Tinkercad

**1. Kiến thức cơ bản**
- Khái niệm Sản xuất bồi đắp (Additive Manufacturing): Tạo sản phẩm bằng cách đắp vật liệu từng lớp.
- Phân biệt In 3D với công nghệ cắt gọt truyền thống (CNC).

**2. Nguyên lý máy in FDM**
- Tìm hiểu 7 bộ phận chính của máy in FDM.
- Các bộ phận tiêu biểu:
  - Cuộn nhựa (Filament).
  - Bộ đùn (Extruder).
  - Đầu phun (Nozzle) 0.4 mm.
  - Bàn nhiệt và bề mặt PEI.

**3. Làm chủ Tinkercad**
- Tư duy hình học CSG: Kết hợp khối Solid và Hole.
- Công cụ Align (L): Căn chỉnh các khối.
- Công cụ hạ đáy về mặt bàn (D).
- Tính toán dung sai lắp ghép, ví dụ: +0.3 mm.

**4. Thực hành**
- Xuất file `.STL` cho bài tập cá nhân:
  - Móc khóa.
  - Bảng tên.
- Bài tập nhóm: Thiết kế vỏ hộp IoT ESP32.

### Buổi 2: Xử lý STL trên Bambu Studio và Vận hành Bambu Lab

**1. Tìm hiểu định dạng file**

| Định dạng | Đặc điểm |
|---|---|
| `.STL` | Lưu mô hình dưới dạng lưới tam giác. |
| `.3MF` | Lưu dự án 3D, có thể chứa mô hình và thông số in. |
| `.GCODE` | Chứa các lệnh điều khiển máy in theo tọa độ và thông số chuyển động. |

**2. Cấu hình Bambu Studio – Kiềng 3 chân**

- **Printer:** Chọn máy in.
- **Filament:** Chọn loại nhựa.
- **Process:** Thiết lập quy trình và thông số in.

**3. Bộ 4 thông số in quan trọng**

| Thông số | Giá trị tham khảo | Ý nghĩa |
|---|---|---|
| Layer Height | 0.2 mm | Chiều cao mỗi lớp in. |
| Wall Loops | 2–3 | Số vòng thành bao quanh sản phẩm. |
| Infill | 15–20% | Mật độ vật liệu bên trong, có thể chọn kiểu Gyroid. |
| Support | Tree Support | Cấu trúc chống đỡ dạng cây. |

**4. Quy trình SOP 6 bước vận hành máy Bambu Lab**

1. Lau sạch bàn in PEI.
2. Nạp nhựa (Filament).
3. Gửi lệnh in.
4. Quan sát lớp in đầu tiên (First Layer) trong khoảng 5 phút đầu.
5. Theo dõi quá trình in.
6. Thu hoạch sản phẩm và xử lý Support.

## IV. Sản phẩm thực hành

- **Tên sản phẩm:** Phone Stand Minion.
- **Phần mềm thiết kế:** Tinkercad.
- **Đường dẫn sản phẩm:** https://www.tinkercad.com/things/cX3UZPYbt8I-minion-phone-stand/edit?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fall&sharecode=mvW6qXPR4r6-5YCFwayWUGJ7bM7o_fKNeRASgWQk8lU
