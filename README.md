 # Network Infrastructure Configuration Project

Dự án này tập trung vào việc thiết kế và cấu hình hạ tầng mạng doanh nghiệp sử dụng các thiết bị Cisco, bao gồm định tuyến, chuyển mạch và các dịch vụ mạng cơ bản.

## 1. Tổng quan hệ thống
- **Thiết bị:** Bao gồm Router (R12, ISP), Switch Access (SW1, SW2, SW3) và Switch Server (SW-Server).
- **Phân chia mạng:** Hệ thống được chia thành 7 VLAN (VLAN 10 đến VLAN 70) để quản lý lưu lượng và tăng tính bảo mật.

## 2. Các kỹ thuật đã triển khai
- **VLAN & Trunking:** Cấu hình chuẩn IEEE 802.1Q trên các đường truyền Trunk để kết nối giữa Switch và Router (Router-on-a-Stick).
- **Dịch vụ DHCP:** Thiết lập DHCP Pool trên Router R12 để cấp phát IP tự động cho các máy trạm thuộc 7 VLAN khác nhau, có cấu hình loại trừ (excluded-address) cho các thiết bị cố định.
- **Định tuyến OSPF:** Triển khai giao thức định tuyến động OSPF (Area 0) trên toàn bộ mạng nội bộ để đảm bảo khả năng hội tụ nhanh và tối ưu đường truyền.
- **Dịch vụ mạng:** Cấu hình DNS Server, NTP Server để đồng bộ thời gian hệ thống và hỗ trợ phân giải tên miền.
- **Quản lý & Bảo mật:** Cấu hình SSH, tắt các dịch vụ không cần thiết (HTTP/HTTPS) và thiết lập tuyến đường tĩnh (Static Route) để đi ra mạng ngoài thông qua ISP.

## 3. Sơ đồ kết nối
- **SW1:** VLAN 10, 20.
- **SW2:** VLAN 30, 40.
- **SW3:** VLAN 50, 60, 70.
- **R12:** Đóng vai trò làm Gateway và DHCP Server cho toàn mạng.
