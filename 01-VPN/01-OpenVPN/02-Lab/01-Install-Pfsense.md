# Cài đặt Pfsense cơ bản

## I. Chuẩn bị

### 1. Tài file iso của pfsense [tại đây](https://www.pfsense.org/download/)

<img src="../../../Images/Pfsense/Lab/1.png">

### 2. Chuẩn bị VM

- Cấu hình VM cho Pfsense:
  - CPU: 2
  - Ram: 2 GB
  - Disk: 20 GB
  - Chuẩn bị 2 Card mạng: 1 LAN có IP: 172.16.4.29 và 1 WAN có IP: 10.10.13.29

## II. Install Pfsense

<img src="../../../Images/Pfsense/Lab/2.png">

<img src="../../../Images/Pfsense/Lab/3.png">

<img src="../../../Images/Pfsense/Lab/4.png">

<img src="../../../Images/Pfsense/Lab/5.png">

<img src="../../../Images/Pfsense/Lab/6.png">

<img src="../../../Images/Pfsense/Lab/7.png">
Sau khi hoàn thành các bước trên, đợi 1-2 phút để VM khởi động lại.

## Phần III. Configuare Pfsense terminal
### Bước 1: Bỏ qua thiết lập DHCP cho VLAN

<img src="../../../Images/Pfsense/Lab/8.png">

### Bước 2: Cấu hình VLAN thủ công

Bước này ta chọn cấu hình cho `vtnet0`
<img src="../../../Images/Pfsense/Lab/9.png">

Bỏ qua bước cấu hình cho vtnet1 

<img src="../../../Images/Pfsense/Lab/10.png">

<img src="../../../Images/Pfsense/Lab/11.png">
- Chờ Pfsense chạy thiết lập cấu hình cơ bản

### Bước 3: Đặt cấu hình IP tĩnh
- Sử dụng phím tùy chọn `2` để tiến hành cấu hình IP tĩnh

<img src="../../../Images/Pfsense/Lab/12.png">

<img src="../../../Images/Pfsense/Lab/13.png">

```
- Đặt IP:

> 172.16.4.29/20

- Đặt Gateway:

>172.16.10.1

```
### Bước 4: Bỏ qua Cấu hình IPv6

<img src="../../../Images/Pfsense/Lab/14.png">

<img src="../../../Images/Pfsense/Lab/15.png">

### Bước 5: Thiết lập revert to HTTP

<img src="../../../Images/Pfsense/Lab/16.png">

* Thông báo thiết lập cấu hình thành công
<img src="../../../Images/Pfsense/Lab/17.png">

- Truy cập Pfsense : `http://172.16.4.29/` có thông tin quản trị:
  - Account: `admin`
  - Password: `pfsense`

<img src="../../../Images/Pfsense/Lab/18.png">

## IV. Configuare Pfsense qua Giao diện
<img src="../../../Images/Pfsense/Lab/19.png">

### 1. Thiết lập cơ bản ban đầu
<img src="../../../Images/Pfsense/Lab/20.png">

- Thiết lập DNS Google:

<img src="../../../Images/Pfsense/Lab/21.png">

- Thiêt lập Timezone:

<img src="../../../Images/Pfsense/Lab/22.png">

- Kéo màn hình xuống cuối rồi bấm `Next` ở phần Configure WAN Interface do đã cấu hình đặt IP ở [Bước 3 Phần II](https://github.com/thang290298/Network/blob/main/01-VPN/01-OpenVPN/02-Lab/01-Install-Pfsense.md#b%C6%B0%E1%BB%9Bc-3-%C4%91%E1%BA%B7t-c%E1%BA%A5u-h%C3%ACnh-ip-t%C4%A9nh)

- Thay đổi mật khẩu cho tài khoản `admin`

<img src="../../../Images/Pfsense/Lab/23.png">

- Reload để cập nhật lại `Pfsense`

<img src="../../../Images/Pfsense/Lab/24.png">

- Hoàn thành thiết lập ban đầu:

<img src="../../../Images/Pfsense/Lab/25.png">

- Giao diện màn hình Dashboard của Pfsense:

<img src="../../../Images/Pfsense/Lab/26.png">

### 2. Tắt Hardware Checksum Offloading

- Truy cập `System` > `Advanced`
<img src="../../../Images/Pfsense/Lab/27.png">

- Chọn `Networking` và kéo màn hình xuống phần `Network Interfaces` và `tick` chọn `Hardware Checksum Offloading` rồi bấm `save`:

<img src="../../../Images/Pfsense/Lab/28.png">

<img src="../../../Images/Pfsense/Lab/29.png">

### 3. Bổ sung Rule Firewall cho phép kết nối giao diện Pfsense qua IP Public

- Cho phép kết nối qua HTTP và HTTPS: `Firewall` > `Rules` > `WAN` chọn `Add`:

<img src="../../../Images/Pfsense/Lab/30.png">

  - kéo xuống mục `Destination` và câu hình chọn `HTTP (80)` và lưu lại:

<img src="../../../Images/Pfsense/Lab/31.png">

  - Cấu hình tương tự đối với `HTTPS (443)`

<img src="../../../Images/Pfsense/Lab/32.png">
  
  - Chọn `Apply Changes` để lưu các thiết lập:

<img src="../../../Images/Pfsense/Lab/33.png">

<img src="../../../Images/Pfsense/Lab/34.png">

  - Chuyển kết nối dashboard mặc định Pfsense tới HTTPS:

<img src="../../../Images/Pfsense/Lab/35.png">

<img src="../../../Images/Pfsense/Lab/36.png">

### 4. Enable card mạng LAN

<img src="../../../Images/Pfsense/Lab/37.png">

- Add card mạng `vtnet1`

<img src="../../../Images/Pfsense/Lab/38.png">

<img src="../../../Images/Pfsense/Lab/39.png">

<img src="../../../Images/Pfsense/Lab/40.png">

  - Chọn `save` rồi chọn `Apply Change` để lưu cấu hình:

<img src="../../../Images/Pfsense/Lab/41.png">

  - Kiểm tra nhận 2 IP ở màn hình `Dashboard`

<img src="../../../Images/Pfsense/Lab/42.png">

### <p align="center">*--- Hoàn thành Setup PfSense ---*</p>
