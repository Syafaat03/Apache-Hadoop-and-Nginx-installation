# Proses instalasi Nginx di ubuntu server
berikut adalah proses penginstallan Nginx di ubuntu server 20.04
## Spesifikasi Perangkat
- OS: Ubuntu 20.04
- 1 Core
- 2 GB RAM
- 40 GB Disk Usage

## Daftar Isi
1. [Update Repository](#1-update-repository)
2. [Install Nginx](#2-install-nginx)
3. [Config UFW (Ubuntu Firewall)](#3-config-ufw-ubuntu-firewall)
4. [Open Port 80](#4-open-port-80)
5. [Cek Status UFW](#5-cek-status-ufw)
6. [Cek Status Nginx](#6-cek-status-nginx)
7. [Pengujian Website](#7-pengujian-website)

## 1. Update Repository
Lakukan update package Ubuntu Server dengan perintah berikut:
```bash
sudo apt update && sudo apt upgrade -y
```
![lakukan update dan upgrade.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/68466708f0307f1a0871f2be9173ac2c2e2170e6/lakukan%20update%20dan%20upgrade.png)

## 2. Install Nginx
Langkah selanjutnya, kita akan menginstal web server Nginx dengan perintah berikut:
```bash
sudo apt install nginx -y
```
![install nginx.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/68466708f0307f1a0871f2be9173ac2c2e2170e6/install%20nginx.png)

## 3. Config UFW (Ubuntu Firewall)
Sekarang masuk tahap penyesuaian Ubuntu Firewall atau UFW, silahkan cek daftar aplikasi yang diizinkan oleh UFW dengan perintah:
```bash
sudo ufw app list
```
![config ufw.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/68466708f0307f1a0871f2be9173ac2c2e2170e6/config%20ufw.png)

## 4. Open Port 80
Langkah selanjutnya yaitu membuka port 80 agar Nginx dapat berjalan, berikut perintahnya:
```bash
sudo ufw allow 80
```
![open port 80.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/68466708f0307f1a0871f2be9173ac2c2e2170e6/open%20port%2080.png)

## 5. Cek Status UFW
Untuk memastikan bahwa Nginx telah diizinkan di Ubuntu, kita bisa melihat statusnya melalui perintah berikut:
```bash
sudo ufw status
```
![cek ufw.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/68466708f0307f1a0871f2be9173ac2c2e2170e6/cek%20ufw.png)

apabila ufw dalam keadaan disable maka kita harus mengaktifkannya dengan perintah :
```bash
sudo ufw enable
```
![aktifkan ufw.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/1762c3d40c2cb9d7585301ac79b6fa84dd656027/aktifkan%20ufw.png)

## 6. Cek Status Nginx
Untuk memastikan bahwa service Nginx telah berjalan, kita bisa melakukan pengecekan status dengan perintah berikut:
```bash
sudo systemctl status nginx
```
![cek status nginx.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/68466708f0307f1a0871f2be9173ac2c2e2170e6/cek%20status%20nginx.png)


## 7. Pengujian Website
Langkah terakhir adalah melakukan test akses melalui browser. Akses dapat dilakukan dengan cara memasukkan IP VPS Anda pada address bar.
Apabila instalasi Nginx di Ubuntu Server berhasil, maka akan tampil default page Nginx seperti berikut.
![tes website.png](https://github.com/Syafaat03/Apache-Hadoop-and-Nginx-installation/blob/1762c3d40c2cb9d7585301ac79b6fa84dd656027/tes%20website.png)
