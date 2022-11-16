# Laporan Praktikum Konsep Jaringan

### Nama : Muhammad Faishal Nabhan

### NRP : 3121600021

### Kelas : 2 D4 Teknik Informatika A

# Praktikum 5 - VLAN

## Praktikum

Gambar di bawah merupakan topologi VLAN yang akan digunakan dalam praktikum kali ini.

![topologi](assets/Tugas6/topologi.png)

Sedangkan untuk konfigurasi IP-nya adalah sebagai berikut :

| Device   | Interface    | IP Address      | Gateway      |
| -------- | ------------ | --------------- | ------------ |
| Router0  | gig0/0       | 192.17.1.1/24   |              |
| pc0      | vlan10       | 192.168.10.2/24 | 192.168.10.1 |
| pc1      | vlan20       | 192.168.20.3/24 | 192.168.20.1 |
| pc2      | vlan30       | 192.168.30.4/24 | 192.168.30.1 |
| pc3      | vlan10       | 192.168.10.2/24 | 192.168.10.1 |
| pc4      | vlan20       | 192.168.20.3/24 | 192.168.20.1 |
| pc5      | vlan30       | 192.168.30.4/24 | 192.168.30.1 |
| pc6      | vlan10       | 192.168.10.2/24 | 192.168.10.1 |
| pc7      | vlan20       | 192.168.20.3/24 | 192.168.20.1 |
| pc8      | vlan30       | 192.168.30.4/24 | 192.168.30.1 |
| Switch 0 | fa0/1 vlan10 |                 |              |
|          | fa0/2 vlan20 |                 |              |
|          | fa0/3 vlan30 |                 |              |
|          | fa0/10 trunk |                 |              |
| Switch 1 | fa0/1 vlan10 |                 |              |
|          | fa0/2 vlan20 |                 |              |
|          | fa0/3 vlan30 |                 |              |
|          | fa0/10 trunk |                 |              |
|          | fa0/11 trunk |                 |              |
|          | fa0/12 trunk |                 |              |
| Switch 2 | fa0/1 vlan10 |                 |              |
|          | fa0/2 vlan20 |                 |              |
|          | fa0/3 vlan30 |                 |              |
|          | fa0/10 trunk |                 |              |

Konfigurasi pada Switch 1 agar dapat terhubung dengan Switch 0 & Switch 2 yang terhbung juga dengan router. VLAN 10 ditujukan untuk admin, VLAN 20 untuk developer, dan VLAN 30 untuk Management.

![switch vlan config](assets/Tugas6/vlan%20config.png)

Konfigurasi pada Switch 0

![config switch0 fa0/10](assets/Tugas6/sw0%20fa10.png)

Konfigurasi Switch 1

![config switch1 fa0/10](assets/Tugas6/sw1%20fa10.png)

![config switch1 fa0/11](assets/Tugas6/sw1%20fa11.png)

![config switch1 fa0/12](assets/Tugas6/sw1%20fa12.png)

Konfigurasi Switch 2

![config switch2 fa0/10](assets/Tugas6/sw2%20fa10.png)

Konfigurasi pada Router

![config router gig0/0](assets/Tugas6/gig%200.png)

Pengetesan ping dari PC-10.4 ke PC-10.2 dan dari PC-10.4 ke PC30.3

![ping](assets/Tugas6/test%20ping.png)

Pada testing ping diatas saat PC-10.4 ke PC-10.2 sukses dilakukan karena PC-10.4 memiliki vlan yang sama dengan PC-10.2 yaitu vlan 10, sedangkan saat melakukan ping dari PC-10.4 ke PC30.3 tidak sukses karena vlan yang digunakan berbeda PC-10.4 menggunakan vlan 10 dan PC30.3 menggunakan vlan 30 sehingga ping yang dikirim tidak akan pernah sampai.
