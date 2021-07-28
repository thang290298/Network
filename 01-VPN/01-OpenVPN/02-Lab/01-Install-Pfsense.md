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

<img src="../../../Images/Pfsense/Lab/20.png">

- Thiết lập DNS Google:

<img src="../../../Images/Pfsense/Lab/21.png">

- Thiêt lập Timezone:

<img src="../../../Images/Pfsense/Lab/22.png">

- Bấm `Next` ở phần Configure WAN Interface do đã cấu hình đặt IP ở [Bước 3 Phần II]()
<img src="../../../Images/Pfsense/Lab/23.png">
<img src="../../../Images/Pfsense/Lab/24.png">
<img src="../../../Images/Pfsense/Lab/25.png">
<img src="../../../Images/Pfsense/Lab/26.png">
<img src="../../../Images/Pfsense/Lab/27.png">
<img src="../../../Images/Pfsense/Lab/28.png">
<img src="../../../Images/Pfsense/Lab/29.png">




