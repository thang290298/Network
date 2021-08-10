# Hướng dẫn cấu hình kết nối OpenVPN mode TAP

## Yêu cầu cấu hình Network cơ bản

```
2 Card mạng, 1 LAN, 1 WAN (Có IP Public).

Đường WAN sẽ sử dụng để Client được kết nối tới. IP WAN: 172.16.4.29

Đường LAN là đường quản trị, các Server sẽ được SSH qua dảy mạng LAN. Dải IP LAN 10.10.13.x
```

## Phần I:  Thiết lập Certificate

### 1.1 Khởi tạo CA cho OpenVPN
- CA có nhiệm vụ xác thực tất cả các Certificate trên Server VPN và user VPN khi kết nối đến Pfsense OpenVPN.

#### Bước 1: chọn `System` > `Cert. Manager` bấm `add`:

<img src="../../../Images/Pfsense/Lab/43.png">

#### Bước 2: Điền thông tin Certificate

- Ở mục `Create / Edit CA` điền thông tin như sau:
   - `Descriptive name`: ca-user
   - `Method`: Create an internal Certificate Authority

<img src="../../../Images/Pfsense/Lab/44.png">

- Điền đầy đủ thông tin ở mục `Internal Certificate Authority` và bấm `save`

<img src="../../../Images/Pfsense/Lab/45.png">

- Kết quả:

<img src="../../../Images/Pfsense/Lab/46.png">

#### Bươc 3: tạo Certificate : ` Certificate ` > ` add `
<img src="../../../Images/Pfsense/Lab/47.png">

- Tại mục: `Add/Sign a New Certificate`
  - `Method`: Create an internal Certificate
  - `Descriptive name`: ca-serer
- Tại mục: `Certificate Attributes`
  - `Certificate Type`: Server Certificate
- Sau đó bấm `save`:

<img src="../../../Images/Pfsense/Lab/50.png">

<img src="../../../Images/Pfsense/Lab/49.png">

<img src="../../../Images/Pfsense/Lab/51.png">


## Phần II. Tạo User Client

#### Add new user cho OpenVPN
### Bước 1: Add new user
- Truy cập theo đường dẫn: `System` > `User Manager`

<img src="../../../Images/Pfsense/Lab/52.png">

- chọn `add` để thêm user:

<img src="../../../Images/Pfsense/Lab/53.png">

### Bước 2: điền thông tin user:

<img src="../../../Images/Pfsense/Lab/54.png">

<img src="../../../Images/Pfsense/Lab/55.png">

<img src="../../../Images/Pfsense/Lab/56.png">
