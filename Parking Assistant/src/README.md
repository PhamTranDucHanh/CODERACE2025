Thư mục `src` chứa toàn bộ mã nguồn chính của dự án **weCAN – Support System for Monitoring Startup and Parking Procedures for New Drivers Based on CAN Signals**.

## Nội dung

- **Xử lý tín hiệu CAN**: đọc dữ liệu từ bus CAN thông qua MCP2515 và vi điều khiển.
- **Giao diện hiển thị**: màn hình OLED / LCD hoặc dashboard trên web để trực quan hóa thông tin cho người lái.
- **Thuật toán hỗ trợ người lái**: cảnh báo, hướng dẫn thao tác khởi động và dừng đỗ xe an toàn.

## Cấu trúc mã nguồn

Dự án được phát triển và mở rộng trên **3 dòng vi điều khiển chính**:

1. **Arduino (Arduino Mega/Uno)**  
   - Code chính: đọc tín hiệu CAN từ MCP2515, xử lý logic, hiển thị cảnh báo trên màn hình OLED.(Reader)  
   - Code giả lập: sử dụng **Arduino Nano + MCP2515** để gửi thử nghiệm các tín hiệu CAN mô phỏng (ví dụ: số P/R/N/D/S, trạng thái phanh, trạng thái động cơ). (Writer)

2. **STM32 (Bluepill – STM32F103C8T6)**  
   - Code chính: lập trình trên STM32 (CubeIDE), xử lý CAN trực tiếp bằng CAN peripheral hoặc qua MCP2515. (Reader) 
   - Code giả lập: luôn dùng **Arduino Nano + MCP2515** để phát tín hiệu CAN giả lập phục vụ test.(Writer)

3. **ESP32**  
   - Code chính: đọc/ghi tín hiệu CAN, xử lý logic và truyền dữ liệu qua WiFi/MQTT để hiển thị trên Web App. (Reader) 
   - Code giả lập: vẫn dùng **Arduino Nano + MCP2515** để mô phỏng các tín hiệu CAN cần thiết. (Writer)

## Lưu ý
- Mỗi cụm vi điều khiển sẽ có **2 phần code**:  
  - **Main**: xử lý & hiển thị.  
  - **Simulator**: Arduino Nano + MCP2515 dùng để giả lập tín hiệu CAN test.  
- Việc tách rõ code chính và code giả lập giúp dễ dàng kiểm thử, demo và mở rộng hệ thống.

---
