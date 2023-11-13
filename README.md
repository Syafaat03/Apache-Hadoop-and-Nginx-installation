# Apacahe2 And Nginx Installation
**Berikut adalah langkah-langkah menginstall apache2 dan nginx**!
# Daftar Isi

1. [Proses Installasi Apache2](#proses-installasi-apache2)
    - [Instal Apache2](#1-instal-apache2)
    - [Konfigurasi Firewall](#2-konfigurasi-firewall)
    - [Mengakses Server Web Apache2 Melalui Browser](#3-mengakses-server-web-apache2-melalui-browser)
    - [Akses Jarak Jauh ke Ubuntu Server](#4-akses-jarak-jauh-ke-ubuntu-server)

2. [Proses Instalasi Nginx di Ubuntu Server](#proses-instalasi-nginx-di-ubuntu-server)
    - [Spesifikasi Perangkat](#spesifikasi-perangkat)
    - [Update Repository](#1-update-repository)
    - [Install Nginx](#2-install-nginx)
    - [Config UFW (Ubuntu Firewall)](#3-config-ufw-ubuntu-firewall)
    - [Open Port 80](#4-open-port-80)
    - [Cek Status UFW](#5-cek-status-ufw)
    - [Cek Status Nginx](#6-cek-status-nginx)
    - [Pengujian Website](#7-pengujian-website)

#   Proses installasi Apache2
## 1. Instal Apache2
-  Perbarui Repositori Paket:
    ```bash
      sudo apt update
    ```
    ![Upfate.png](https://www.dropbox.com/scl/fi/vbj3lx6en71r833x4oss6/Upfate.png?rlkey=i8f0ofio9qwgbi8w4pt61i1mo&dl=0&raw=1)

- Tingkatkan Paket:
    ```bash
      sudo apt upgrade -y
    ```
    ![upgrade.png](https://www.dropbox.com/scl/fi/v564miaabjce4dpcm1omi/upgrade.png?rlkey=ysxg6jiuzjztprsh32haext6q&dl=0&raw=1)
- Instal Apache:
    ```bash
      sudo apt install apache2 -y
    ```
    ![install apache2.png](https://www.dropbox.com/scl/fi/hotsy3wdnoxe751zm1dit/install-apache2.png?rlkey=i96flxwc18u6xdbw2g9jwh2ft&dl=0&raw=1)

## 2. Konfigurasi Firewall
- Daftar Aplikasi UFW:
    ```bash
      sudo ufw app list
    ```
    ![ufw check.png](https://www.dropbox.com/scl/fi/ofi110i987gnjzbmx3wut/ufw-check.png?rlkey=q619iqoue9f26ndgbtiujq68p&dl=0&raw=1)
- Izinkan Apache Melalui Firewall:
    ```bash
      sudo ufw allow 'Apache'
    ```
    ![allow apache2.png](https://www.dropbox.com/scl/fi/as1kvgjmklqkjd2bx81n4/allow-apache2.png?rlkey=xhtl0leeboaglxenbhokjuiwc&dl=0&raw=1)
- Aktifkan UFW:
    ```bash
      sudo ufw enable
    ```
    ![sudo ufw enable.png](https://www.dropbox.com/scl/fi/utey8gpge20xy88a5s464/sudo-ufw-enable.png?rlkey=np9wv0dykoabx4fv9ngy6m4if&dl=0&raw=1)
- kemudian Periksa Status UFW:
    ```bash
      sudo ufw status
    ```
    ![ufw status.png](https://www.dropbox.com/scl/fi/ydf4yu6fhf5zjrggpxmze/ufw-status.png?rlkey=0yowrqz2hilxc00etcbhailzb&dl=0&raw=1)
- Periksa Status Apache:
    ```bash
      sudo systemctl status apache2
    ```
    ![apache 2status.png](https://www.dropbox.com/scl/fi/pwgwdueyytflnnubspla7/apache-2status.png?rlkey=jj2seknc78nlowvmz5j6e9txv&dl=0&raw=1)

## 3. Mengakses Server Web Apache2 Melalui Browser
- **Periksa Alamat IP**:
    ```bash
      hostname -I
    ```
    ![mengecek ip.png](https://www.dropbox.com/scl/fi/zp68nufxoryo3eiytzwen/mengecek-ip.png?rlkey=jor3pxjvhkuk7oz99bt3ybyt1&dl=0&raw=1)
- Buka Browser: Buka browser di mesin host Anda.
- Masukkan Alamat IP: Masukkan alamat IP mesin virtual Anda di browser mesin host Anda. Halaman default Apache2 harus muncul.
![web default.png](https://www.dropbox.com/scl/fi/iq9sophi93auowwczmr4m/web-default.png?rlkey=ofao28ce7a9ct68323ihu6m91&dl=0&raw=1)

## 4. Akses Jarak Jauh ke Ubuntu Server]
   - **Command Prompt**
      - Buka Command Prompt: Buka Command Prompt di mesin host.
      - SSH ke Server:
        ```bash
        ssh username@ip.address
        ```
   - **PuTTY**
      - Buka PuTTY: Buka PuTTY di mesin host.
      - Masukkan Alamat IP: Masukkan alamat IP Anda, lalu klik Open.
      - Terima Koneksi: Klik Accept.
      - Masuk: Masuk dengan memasukkan nama pengguna dan kata sandi server Ubuntu Anda.
   - **Ubuntu Desktop**
      - Buka Ubuntu Desktop di VirtualBox: Buka Ubuntu Desktop di VirtualBox.
      - Buka Terminal: Buka Terminal di Ubuntu Desktop.
      - SSH ke Server:
        ```bash
        ssh username@ip.address
        ```
# Proses instalasi Nginx di ubuntu server

## Spesifikasi Perangkat
- OS: Ubuntu 20.04
- 1 Core
- 2 GB RAM
- 40 GB Disk Usage

##  1. Update Repository
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
