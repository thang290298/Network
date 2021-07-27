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

## III. Configuare Pfsense
### Bước 1: Bỏ qua thiết lập DHCP cho VLAN

<img src="../../../Images/Pfsense/Lab/8.png">

### Bước 2: Cấu hình VLAN thủ công

Bước này ta chọn cấu hình cho `vtnet0`
<img src="../../../Images/Pfsense/Lab/9.png">

Bỏ qua bước cấu hình cho vtnet1 
<img src="../../../Images/Pfsense/Lab/10.png">
<img src="../../../Images/Pfsense/Lab/11.png">
<img src="../../../Images/Pfsense/Lab/12.png">
<img src="../../../Images/Pfsense/Lab/13.png">

<img src="../../../Images/Pfsense/Lab/14.png">
<img src="../../../Images/Pfsense/Lab/15.png">
<img src="../../../Images/Pfsense/Lab/16.png">
<img src="../../../Images/Pfsense/Lab/17.png">


