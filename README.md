# Lapres Praktikum Jarkom Modul 4

![Soal Shift Modul 4](Soal_Shift_Modul_4.png)

- CLOUD diberikan IP TUNTAP.
- Server diberikan IP DMZ.
- Berikan memori sebesar 64MB pada setiap UML.
- Pembagian IP dan routing harus SE-EFISIEN MUNGKIN.
- Pastikan semua UML dapat melakukan ping ke its.ac.id
- Hasil perhitungan untuk VLSM / CIDR, berbeda dengan di CPT / UML

## VLSM / CPT

### Hasil Perhitungan

##### Langkah 1 - Tentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan.
| Subnet| Jumlah IP | Submask |
| ------------- |:-------------:| -----:|
| A2 | 2 | /30 |
| A4 | 2 | /30 |
| A9 | 2 | /30 |
| A11 | 2 | /30 |
| A7 | 13 | /28 |
| A6 | 101 | /25 |
| A13 | 251 | /24 |
| A8 | 502 | /23 |
| A1 | 1001 | /22 |
| A3 | 701 | /22 |
| A10 | 521 | /22 |
| A12 | 721 | /22 |
| A5 | 2021 | /21 |
| Total | 5840 | /19 |

### Pohon Pembagian IP

### Routing

## CIDR / UML

### Hasil Perhitungan

##### Langkah 1 - Tentukan subnet yang ada dalam topologi dan lakukan labelling netmask terhadap masing-masing subnet.

![Gambar CIDR_1](CIDR_1.png)

##### Langkah 2 - Gabungkan subnet paling bawah di dalam topologi, diulang sampai menjadi sebuah subnet besar mencakup 1 topologi

![Gambar CIDR_2](CIDR_2.png)

![Gambar CIDR_3](CIDR_3.png)

![Gambar CIDR_4](CIDR_4.png)

![Gambar CIDR_5](CIDR_5.png)

![Gambar CIDR_6](CIDR_6.png)

![Gambar CIDR_7](CIDR_7.png)

### Pohon Pembagian IP

![Gambar Tree Hasil Hitung CIDR](CIDR_Tree.png)

### Routing

```
# ROUTING SURABAYA
route add -net 192.168.0.0 netmask 255.255.224.0 gw 192.168.32.2
route add -net 192.168.128.0 netmask 255.255.128.0 gw 192.168.192.2
route add -net 10.151.77.76 netmask 255.255.255.252 gw 192.168.32.2

# ROUTING  BATU
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.8.2
route add -net 192.168.18.0 netmask 255.255.255.240 gw 192.168.16.2
route add -net 10.151.77.76 netmask 255.255.255.252 gw 192.168.8.2

# ROUTING KEDIRI
route add -net 192.168.0.0 netmask 255.255.252.0 gw 192.168.4.2

# ROUTING PASURUAN
route add -net 192.168.128.0 netmask 255.255.240.0 gw 192.168.144.2
```
