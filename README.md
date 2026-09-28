# esp32-smart-greenhouse
Hệ thống tưới tiêu và giám sát khu vườn thông minh dựa trên ESP32, MicroPython và Web Dashboard (Dự án STEM).

# 🌿 KHU VƯỜN VUI VẺ (Smart Greenhouse System)

> **Dự án STEM:** Hệ thống tự động hóa tưới tiêu và giám sát môi trường thực vật ứng dụng vi điều khiển ESP32 và MicroPython.

---

## 📌 Giới thiệu dự án
Dự án **Khu Vườn Vui Vẻ** được phát triển nhằm tối ưu hóa việc chăm sóc cây trồng tự động. Hệ thống kết hợp giữa **Core Logic độc lập** (xử lý trực tiếp trên phần cứng) và **Web Dashboard** (giám sát/điều khiển từ xa qua mạng IP cục bộ).

### Các tính năng chính:
- **Tự động hóa thông minh:** Tự động kích hoạt bơm/Relay, phun sương, quạt làm mát dựa trên thông số môi trường thực tế.
- **Giám sát đa thông số:** Đo độ ẩm đất, nhiệt độ & độ ẩm không khí (DHT22), phát hiện mưa.
- **Bảo vệ độc lập (Fail-safe):** Core logic chạy trực tiếp trên ESP32, đảm bảo hệ thống duy trì tưới đúng chu kỳ ngay cả khi mất kết nối mạng.
- **Giao diện Web tích hợp:** Hiển thị trực quan dữ liệu cảm biến và hỗ trợ chuyển đổi chế độ điều khiển thủ công.

---

## 🛠️ Phần cứng & Linh kiện (Hardware)

- **Vi điều khiển:** ESP32-WROOM-32
- **Cảm biến:**
  - Cảm biến nhiệt độ & độ ẩm không khí: **DHT22** (GPIO 19)
  - Cảm biến độ ẩm đất: **Capacitive Soil Moisture Sensor** (GPIO 34 & GPIO 34)
- **Thiết bị khác:**
  - Mạch Rơ-le (Relay) kích tưới/phun sương (GPIO 4)
  - Quạt tản nhiệt/làm mát PWM (GPIO 32)

---

## 💻 Công nghệ & Ngôn ngữ (Software)

- **Ngôn ngữ lập trình:** MicroPython
- **Web Frontend:** HTML, CSS, JavaScript (Embedded Web Server)
- **Giao thức kết nối:** HTTP REST API / Local Socket Server

---

## 📁 Cấu trúc thư mục (Repository Structure)

```text
├── main.py              # Chương trình chính & Khởi chạy Web Server
├── config.py            # Cấu hình chân GPIO và ngưỡng cảm biến (Thresholds)
├── sensors.py           # Module đọc & xử lý dữ liệu cảm biến
├── logic_control.py     # Thuật toán điều khiển tự động (Core Logic)
├── web_server.py        # Xử lý các request HTTP từ giao diện
└── templates/
    └── index.html       # Giao diện Web Dashboard

🚀 Hướng dẫn cài đặt & Vận hành
Chuẩn bị môi trường:

Cài đặt firmware MicroPython mới nhất cho ESP32.

Sử dụng công cụ Thonny IDE hoặc VS Code (Pymakr) để nạp code.

Cấu hình mạng Wi-Fi:

Mở file config.py và cập nhật thông tin Wi-Fi của bạn:

Python
WIFI_SSID = "Tên_WiFi_Của_Bạn"
WIFI_PASS = "Mat_Khau_WiFi"
Nạp nguồn & Truy cập:

Kết nối ESP32 với nguồn điện.

Mở Terminal để xem địa chỉ IP cục bộ được cấp (Ví dụ: 192.168.1.15).

Nhập địa chỉ IP vào trình duyệt bất kỳ cùng mạng để mở Web Dashboard.

📜 Giấy phép (License)
Dự án được phân phối dưới giấy phép MIT License.
