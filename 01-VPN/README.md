# Overview VPN ( Virtual Private Network )

## I. Mạng riêng ảo VPN là gì?
- `VPN` (Virtual Private Network) hay còn gọi là mạng ảo nội bộ. VPN là công nghệ mạng giúp tạo ra các kết nối mạng an toàn khi tham gia sử dụng dịch vụ của các nhà cung cấp dịch vụ mạng công cộng như internet, intranet
- Đối với mỗi hệ thống có thể mạng ảo có thể kêt nối đến nhiều site khác nhau dựa trên diện tich địa lý, khu vực. Ta thường thấy các cơ quan, tổ chức chính phủ cho phép người dùng kết nối an toàn đến mạng nội bộ của chính phủ hay các cơ quan tổ chức, đó là nhờ có `VPN` (Virtual Private Network)

- Hình thức hoạt động của VPN:

  - Để kết nối đên VPN, người dùng cần có 1 tài khoản với thông tin `account` và `password`, đồng thời được cấp quyền truy cập từ xa thông qua xác nhận tài khoản với mã pin. Mã pin thường sẽ áp dụng trong khoảng thời gian nhất định từ 30s – 1 phút
  - Có thể sử dụng VPN trên máy tinh, điện thoại giống như đang sử dung trên mạng nội bộ. Tất cả traffic đều được gửi qua và kết nối an toàn đến VPN. Do đó hoàn toàn có thể yên tâm về độ bảo mật tài nguyên mạng nội bộ.



## II. Tổng quan về VPN
### 1. Chức năng của VPN

- Tải tệp tin
- Thay đổi IP giúp truy cập dễ dàng tới website bị chặn, giới hạn địa lý
- Loại bỏ cac vướng mắc về firewalld, giúp bạn truy cập nhanh chóng và dễ dàng cho dù bất kể vị trí nào
- Truy cập mạng nội bộ cho dù đang ở bên ngoài

### 2. Ưu & nhược điểm của VPN
#### 2.1 Ưu điểm
- Tiết kiệm chi phí đầu tư và thuê bằng thông đường truyền, đuy trì hoạt động hệ thống.
- Tính linh hoạt trong qua trình vận hành, hỗ trợ kết nối đa điểm tới nhiều vị trí văn phòng làm việc khác nhau cùng 1 thời điểm.
- Khả năng mở rộng dựa trên hạ tầng mạng công cộng internet nên ở bất cứ nơi nào có mạng đều triển khai được VPN.
- Giảm thiểu hỗ trợ về mặt kỹ thuật
- Đáp ứng nhu cầu thương mại

#### 2.1 Nhược điểm
- VPN không có khả năng quản lý QoS (Quality of Server) qua môi trường internet dẫn đến các goi tin dữ liệu trong quá trình vận chuyện vẫn có thể thác lạc.

## III. Các loại VPN
- Mạng VPN cục bộ (intranet VPN)
- Mạng VPN mở rộng (extranet VPN)
- Mạng VPN truy cập từ xa (Remote Access VPN)

## IV. Các giao thức thường dùng trong VPN
- Tunnelling: Tunnelling: Là kỹ thuật truyền dữ liệu qua nhiều mạng có giao thức khác nhau. VPN có chức năng cơ bản là phân phối các gói từ điểm này tới điểm khác một cách bảo mật. Để làm được điều đó thì tất cả các gói dữ liệu cần được định dạng sao cho chỉ máy khách và máy chủ hiểu được. Bên gửi dữ liệu sẽ định dạng chúng theo Tunnelling để bên nhận có thể trích xuất được thông tin.
- Mã hóa: Vì Tunnelling không có tính năng bảo vệ nên bất cứ ai cũng có thể trích xuất dữ liệu. Khi đó cần phải mã hóa trên đường truyền sao cho chỉ bên nhận mới có thể giải mã.
- Quản lý phiên: Là cách duy trì phiên để khách hàng tiếp tục giao tiếp trong một khoảng thời gian nhất định.
- Xác thực: Là cách xác nhận danh tính để bảo mật an toàn hơn.
