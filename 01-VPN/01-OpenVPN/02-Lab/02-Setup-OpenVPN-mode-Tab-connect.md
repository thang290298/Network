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

## Phần III. Cài gói Openvpn export client

### Bước 1: chọn `System > Package Manager`

<img src="../../../Images/Pfsense/Lab/57.png">

### Bước 2: Chọn `Available Packages`

<img src="../../../Images/Pfsense/Lab/58.png">

<img src="../../../Images/Pfsense/Lab/59.png">

<img src="../../../Images/Pfsense/Lab/60.png">

## Phần IV. Thiết lập OPENVPN

### Bước 1: Chọn `VPN > OpenVPNb > Add`

<img src="../../../Images/Pfsense/Lab/61.png">

### Bước 2: Tạo mới server OpenVPN

#### Chọn Server:
- Tại mục `General Information`:
  - `Server mode > Remote Access ( SSL/TLS + User Auth )`
  - `Protocol > UDP on IPV4 only`
  - `Device mode > tap - Layer 2 Tap Mode`
  - `Local port: 1194`
  - `Interface: WAN` -> Sử dụng để kết nối đến mạng bên ngoài thông qua internet

<img src="../../../Images/Pfsense/Lab/62.png">

- Tại mục `Cryptographic Settings`: 
  - Chọn `TLS Configuration > Use a TLS Key`
  - Chọn `TLS Configuration > Automatically generate a TLS Key`
  - Chọn `Peer Certificate Authority` > thangnvlab01 LƯU Ý: ĐÂY LÀ CERT TẠO TỪ PHẦN 1
  - Chọn `Server certificate > thangnv-server` LƯU Ý: ĐÂY LÀ CERT TẠO TỪ PHẦN 1
  - Chọn `Data Encryption Algorithms > AES-256-CBC` (256 bit key, 128 bit block)
  - Chọn `Enable NCP > Enable Negotiable Cryptographic Parameters`
  - Tại `Fallback Data Encryption Algorithm - Chọn AES-256-CBC (256bit key, 128 bit block)`

<img src="../../../Images/Pfsense/Lab/63.png">

<img src="../../../Images/Pfsense/Lab/64.png">

- Tunner Settings
  - Chọn `Bridge DHCP`: Tick chọn  `Allow client on the bridge to obtain DHCP`
  - `Bridge Interface: LAN`
  - Server Bridge DHCP Start: 10.10.13.20
  - Server Bridge DHCP End: 10.10.13.254
  
<img src="../../../Images/Pfsense/Lab/65.png">

- `Custom Options` thêm cấu hình: `push "route 10.10.40.0 255.255.255.0"`

<img src="../../../Images/Pfsense/Lab/66.png">

<img src="../../../Images/Pfsense/Lab/67.png">

<img src="../../../Images/Pfsense/Lab/68.png">


## Phần V. Cấu hình Interface
### 1. Cấu hình Interface VPN
#### Bước 1: Chọn `Interfaces > Assignments`

<img src="../../../Images/Pfsense/Lab/69.png">



#### Bước 2: Mục `Available network ports` chọn `ovpns1 ()` tiếp theo chọn `add`

<img src="../../../Images/Pfsense/Lab/70.png">

### Bước 3: Chỉnh sửa `OPT1`

<img src="../../../Images/Pfsense/Lab/71.png">

- General Configuration:
  - Chọn Enable > `Enable interface`
  - Sửa  `Description: vpn`
  - Bấm `Save`

<img src="../../../Images/Pfsense/Lab/72.png">

<img src="../../../Images/Pfsense/Lab/73.png">

<img src="../../../Images/Pfsense/Lab/74.png">
<img src="../../../Images/Pfsense/Lab/75.png">
<img src="../../../Images/Pfsense/Lab/76.png">
<img src="../../../Images/Pfsense/Lab/77.png">
<img src="../../../Images/Pfsense/Lab/78.png">
<img src="../../../Images/Pfsense/Lab/79.png">
<img src="../../../Images/Pfsense/Lab/80.png">
<img src="../../../Images/Pfsense/Lab/81.png">
<img src="../../../Images/Pfsense/Lab/82.png">
<img src="../../../Images/Pfsense/Lab/83.png">
<img src="../../../Images/Pfsense/Lab/84.png">
<img src="../../../Images/Pfsense/Lab/85.png">
<img src="../../../Images/Pfsense/Lab/86.png">
<img src="../../../Images/Pfsense/Lab/87.png">
<img src="../../../Images/Pfsense/Lab/88.png">
<img src="../../../Images/Pfsense/Lab/89.png">
<img src="../../../Images/Pfsense/Lab/90.png">