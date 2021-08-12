# Cấu hình Pfsense Site to Site (Không HA)
## Phần I. Mô hình hoạt động

<img src="../../../Images/Pfsense/Lab/137.png">

### Chuẩn bị
#### 1. Cấu hình Site 1

- 1 máy chủ `Pfsense01`:
  - `vtnet0`: 172.16.4.29 - WAN IP Public
  - `vtnet1`: 10.10.13.29 - VLAN13 IP Private

- 1 Client Windown: IP 10.10.13.245

<img src="../../../Images/Pfsense/Lab/138.png">

#### 2. Cấu hình Site 2

- 1 máy chủ `Pfsense03`:
  - `vtnet0`: 172.16.2.29 - WAN IP Public
  - `vtnet1`: 10.10.12.29 - VLAN12 IP Private
- 1 Client Windown: IP 10.10.12.245

<img src="../../../Images/Pfsense/Lab/139.png">
<img src="../../../Images/Pfsense/Lab/140.png">
<img src="../../../Images/Pfsense/Lab/141.png">
<img src="../../../Images/Pfsense/Lab/142.png">
<img src="../../../Images/Pfsense/Lab/143.png">
<img src="../../../Images/Pfsense/Lab/144.png">
<img src="../../../Images/Pfsense/Lab/145.png">
<img src="../../../Images/Pfsense/Lab/146.png">
<img src="../../../Images/Pfsense/Lab/147.png">
<img src="../../../Images/Pfsense/Lab/148.png">
<img src="../../../Images/Pfsense/Lab/149.png">
<img src="../../../Images/Pfsense/Lab/150.png">
<img src="../../../Images/Pfsense/Lab/151.png">
<img src="../../../Images/Pfsense/Lab/152.png">
<img src="../../../Images/Pfsense/Lab/153.png">
<img src="../../../Images/Pfsense/Lab/154.png">
<img src="../../../Images/Pfsense/Lab/155.png">
<img src="../../../Images/Pfsense/Lab/156.png">
<img src="../../../Images/Pfsense/Lab/157.png">
<img src="../../../Images/Pfsense/Lab/158.png">
<img src="../../../Images/Pfsense/Lab/159.png">
<img src="../../../Images/Pfsense/Lab/160.png">
<img src="../../../Images/Pfsense/Lab/161.png">
<img src="../../../Images/Pfsense/Lab/162.png">
<img src="../../../Images/Pfsense/Lab/163.png">
<img src="../../../Images/Pfsense/Lab/164.png">