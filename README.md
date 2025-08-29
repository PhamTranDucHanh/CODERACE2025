# weCAN-SupportSystem

Dự án hỗ trợ người lái xe bằng hệ thống đọc dữ liệu CAN.

## Cấu trúc thư mục

```
Parking Assistance/ 
│
├── docs/                     # Tài liệu
│   ├── architecture/         # Sơ đồ hệ thống, kiến trúc phần cứng/phần mềm
│   ├── images/               # Hình ảnh demo, sản phẩm, PCB
│   ├── videos/               # Link/video demo (gif/mp4)
│   └── reports/              # Báo cáo, slide thuyết trình
│
├── src/                 # Code nhúng chính
│   ├── Arduino/              # Code Arduino Mega + MCP2515
│   ├── stm32/                # Code STM32 (CubeIDE hoặc Keil project)
│   └── esp32/                # Code ESP32 (PlatformIO / Arduino framework)
│
├── simulation/                # proteus
│   ├── arduino-test/         # Test gửi/nhận CAN signal bằng Arduino
│   ├── stm32-test/           # Test riêng cho STM32
│   └── esp32-test/           # Test kết nối WiFi/MQTT, debug CAN <-> WebApp
│
├── webapp/                   # Web application hiển thị & xử lý
│   ├── backend/              # Node.js/Python (xử lý dữ liệu từ ESP32/MQTT)
│   └── frontend/             # React/Next.js (dashboard HMI)
│
├── hardware/                 # Tài liệu phần cứng
│   ├── schematics/           # Sơ đồ mạch
│   └── pcb/                  # PCB design (KiCad/Altium)
│
├── tests/                    # Unit test / Integration test cho code nhúng
│
├── LICENSE                   # License MIT/GPL rõ ràng
├── README.md                 # Giới thiệu chính, nổi bật
├── CONTRIBUTING.md           # Hướng dẫn đóng góp (nếu public)
└── .gitignore
```


## Cách chạy thử
(Hướng dẫn chạy code hoặc build)


