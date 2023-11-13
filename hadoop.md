# Harmonisasi Big Data: Membelai Melodi ribuan Data dalam Dataset Lagu melalui Analisis HDFS
Penulis Korespondensi:	
Syafaat Muhammad Bahril Huda (09011282227075@student.unsri.ac.id)
## Table of Contents
1. [ABSTRACT](#abstract)
2. [PENDAHULUAN](#pendahuluan)
3. [TINJAUAN PUSTAKA](#tinjauan-pustaka)
    - [HDFS (Hadoop Distributed File System)](#21-hdfs-hadoop-distributed-file-system)
    - [MapReduce](#22-mapreduce)
    - [Big Data](#23-big-data)
    - [Multi-node Hadoop](#24-multi-node-hadoop)
4. [METODELOGI PENELITIAN](#metodologi-penelitian)
    - [Tahap Awal Perencanaan](#tahap-awal-perencanaan)
    - [Langkah-langkah Percobaan](#langkah-langkah-percobaan)
5. [HASIL PENELITIAN](#hasil-penelitian)
    - [Implementasi Sistem](#41-implementasi-sistem)
        - [Implementasi Sistem Perangkat Keras](#411-implementasi-sistem-perangkat-keras)
        - [Implementasi Sistem Perangkat Lunak](#412-implementasi-sistem-perangkat-lunak)
    - [Hasil Data](#42-hasil-data)
        - [Hasil Data Mapreduce](#421-hasil-data-mapreduce)
        - [Hasil Data Menggunakan Apache Hadoop](#422-hasil-data-menggunakan-apache-hadoop)
6. [KESIMPULAN](#kesimpulan)
7. [DAFTAR PUSTAKA](#daftar-pustaka)


## ABSTRACT
Industri musik saat ini menghadapi tantangan Big Data dengan melimpahnya informasi dalam dataset lagu, seperti judul, artis, lirik, dan lebih banyak lagi. Perkembangan platform streaming musik telah menciptakan volume data besar dalam metadata lagu dan preferensi pengguna. Untuk mengatasi pengolahan data yang besar ini, Hadoop dan algoritma MapReduce hadir sebagai solusi efisien. Dengan judul "Harmonisasi Big Data: Membelai Melodi ribuan Data dalam Dataset Lagu melalui Analisis HDFS," penelitian ini bertujuan menganalisis implementasi MapReduce dengan menggunakan Hadoop dengan Cluster Multinode, dengan fokus pada pengurutan data secara abjad pada Dataset serta menghitung data (WordCount) berdasarkan genre.

**Keywords:** Big Data, Data Lagu, Hadoop, Multinode, Mapreduce, HDFS

## 1. PENDAHULUAN
Industri musik adalah salah satu sektor yang telah mengalami perubahan signifikan seiring dengan perkembangan teknologi digital. Dengan platform streaming musik seperti Spotify, Apple Music, dan lainnya, para pengguna sekarang dapat mengakses jutaan lagu dengan mudah. Namun, dibalik layar, industri musik juga menciptakan volume data yang luar biasa besar dalam hal metadata lagu, preferensi pengguna, dan lainnya. Dalam dunia digital ini, data bukan hanya sebuah aset, tetapi juga menjadi elemen kunci yang dapat menggerakkan bisnis dan inovasi. Industri musik bukan pengecualian; data digunakan untuk memahami perilaku pendengar, menyesuaikan rekomendasi musik, dan bahkan untuk menemukan bakat musik baru. Namun, dengan jumlah data yang terus meningkat, tantangan utama adalah bagaimana mengelola, menyimpan, dan menganalisisnya secara efisien.
Disini, Big Data dan teknologi seperti HDFS berperan amat penting. Big Data merupakan metode yang digunakan untuk memvisualisasikan kumpulan data yang besar, kompleks, dan banyak yang sulit direpresentasikan dengan menggunakan metode konvensional. Selain itu, HDFS merupakan suatu sistem penyimpanan data yang dirancang khusus untuk menangani kumpulan data yang besar dan terdistribusi.
Judul "Harmonisasi Big Data: Membelai Melodi ribuan Data dalam Dataset Lagu melalui Analisis HDFS" mencerminkan upaya untuk menggabungkan potensi Big Data dan teknologi HDFS dalam industri musik. "Harmonisasi" di sini mengacu pada upaya untuk menyatukan berbagai sumber data musik dalam satu entitas yang terstruktur. Dataset lagu adalah contoh konkret dari Big Data dalam industri musik. Ini mencakup informasi tentang lagu, seperti judul, artis, durasi, lirik, dan banyak elemen lainnya. Saat jumlah lagu dan detailnya terus bertambah, penting untuk memiliki cara efisien untuk mengelola dan menganalisis dataset ini.
Analisis HDFS adalah komponen penting dalam proses ini. HDFS memungkinkan penyimpanan dan pengolahan data yang terdistribusi secara efisien di sejumlah node komputer, sehingga mengatasi kendala kapasitas penyimpanan tradisional. Dengan menggunakan HDFS, data lagu dapat diakses, dikelola, dan dianalisis dengan cepat dan efisien. Hasil dari analisis HDFS pada dataset lagu dapat menghasilkan wawasan berharga. Ini bisa mencakup pemahaman tentang tren musik saat ini, preferensi pendengar berdasarkan daerah geografis, atau bahkan prediksi potensi kesuksesan lagu baru. Dengan kata lain, kombinasi Big Data dan HDFS memungkinkan industri musik untuk mengambil keputusan yang lebih terinformasi.
Dengan judul ini, penelitian dan implementasi teknologi ini diharapkan akan membantu menciptakan "harmoni" antara Big Data dan dunia musik, memungkinkan industri musik untuk terus berinovasi dan memberikan pengalaman yang lebih baik kepada pendengarnya, sambil memanfaatkan potensi data yang luar biasa besar yang telah dihasilkan oleh perkembangan teknologi digital.”.

## 2. TINJAUAN PUSTAKA

### 2.1 HDFS (Hadoop Distributed File System)
HDFS, atau Hadoop Distributed File System, merupakan sistem distribusi file yang dirancang dari awal untuk dijalankan pada perangkat keras. Sistem distribusi file yang ada dan HDFS memiliki banyak kesamaan, secara halus. Namun, perbedaan antara HDFS dan sistem distribusi file lainnya cukup signifikan. HDFS sangat menyadari kesalahan yang terjadi ketika distribusi file sedang berlangsung dan HDFS dibuat sedemikian rupa sehingga dapat berjalan pada perangkat keras yang murah.

Dua komponen utama HDFS adalah NameNode dan DataNode. DataNode merupakan sepasang komputer yang berfungsi sebagai slave dalam sebuah cluster, sedangkan NameNode adalah satu komputer yang berfungsi sebagai master cluster. Efisiensi proses distribusi file HDFS saat ini disebabkan oleh kerja dua komponen utama yang tercantum di atas.
![topologi hdfs.png](https://www.dropbox.com/scl/fi/hqy56m5whcx12igeo5k67/topologi-hdfs.png?rlkey=lsnyyy3qmv3eorc4g4446ekxl&dl=0&raw=1)

### 2.2 MapReduce
MapReduce adalah paradigma pemrograman yang memungkinkan skalabilitas besar-besaran pada cluster Hadoop. Pekerjaan MapReduce melibatkan tugas Mapping dan Reducing untuk memproses dan mengelompokkan data.
Sesuai dengan nama tekniknya, MapReduce, pekerjaan pengurangan selalu dilakukan setelah pekerjaan hewan peliharaan. MapReduce menawarkan beberapa manfaat untuk membantu Anda mengekstrak informasi berharga dari data besar Anda. MapReduce beroperasi pada kecepatan yang lebih tinggi di beberapa area yang terhubung secara paralel pada setiap node dalam sebuah cluster. Prosedur Peta dan Prosedur Pengurangan adalah dua langkah utama dalam implementasi MapReduce saat menjalankan proses.
1.	Mapping Procedure
Mapping Procedure didefinisikan sebagai satu lintasan melewati sekumpulan gerbang kunci/nilai, dan fungsi intinya adalah kumpulan dari lintasan hingga melewati gerbang kunci/nilai (kunci perantara). Algoritma MapReduce akan menggabungkan setiap kunci/nilai yang dikaitkan dengan kunci perantara yang sama dan menerapkannya pada fungsi Reduce. 
2.	Reduce Procedure
Reduce Procedure didefinisikan sebagai pembuatan kunci perantara dengan nilai ambang batas untuk kunci yang dihasilkan oleh fungsi Mapping. Nilai saat ini diterapkan secara menyeluruh untuk menciptakan nilai asosiasi yang lebih kecil. Secara umum, hanya 0 atau 1 nilai himpunan yang tersedia untuk fungsi Pengurangan apa pun. Klausa perantara yang ditawarkan berpindah ke fungsi pengurangan menggunakan iterator. Iterator yang disebutkan di atas digunakan untuk memungkinkan sejumlah besar disimpan dalam format seperti daftar di memori.
![topologi mapreduce.png](https://www.dropbox.com/scl/fi/ps6jtkv5lzval6ocpr2o8/topologi-mapreduce.png?rlkey=34d8f6luq3x80qnv02ql9im1q&dl=0&raw=1)
### 2.3 Big Data
Big Data adalah kumpulan data yang sangat besar, sangat bervariasi, sangat cepat diproses, dan mungkin tidak terstruktur. Jika komputer yang digunakan untuk memproses data tidak memenuhi standar yang disyaratkan oleh data besar tertentu, proses komputasi yang dihasilkan dari data besar mungkin berjalan lambat. Oleh karena itu diperlukan suatu algoritma khusus agar informasi dapat diperoleh dengan mudah dan dapat membantu dalam pengembangan kesimpulan yang lebih baik.
![topologi big data.png](https://www.dropbox.com/scl/fi/fwrcor90vgbvsyspgni73/topologi-big-data.png?rlkey=kn9xdyinfdslvq6bbedl9lk6t&dl=0&raw=1)
### 2.4 Multi-node Hadoop
Multi-node Hadoop menggunakan koneksi antara dua server node tunggal, satu untuk komputer slave dan satu lagi untuk master komputer. Dalam versi Hadoop dengan multi node ini, komputer slave menggunakan lebih dari satu komputer. Oleh karena itu, pada multinode Hadoop ini, sejumlah pengguna dapat mengirimkan pekerjaan secara kooperatif. Lapisan komputer master HDFS sekarang menjalankan namenode, jps, SecondaryNameNode, dan ResourceManager. Di sisi lain, datanode, jps, dan manajer node diluncurkan di komputer budak. Dua komputer di jaringan ini, master dan slave, dikonfigurasi menggunakan sejumlah file, termasuk hdfs-site.xml, core-site.xml, mapred-site.xml, dan Yarnsite.xml. 
![topologi multinode hadoop.png](https://www.dropbox.com/scl/fi/xag5xauzopbyzg0g5nfc2/topologi-multinode-hadoop.png?rlkey=crpyoq3loglms52k4vjxy4ify&dl=0&raw=1)
## 3. METODELOGI PENELITIAN
### Tahap Awal Perencanaan
Dalam langkah perencanaan sebelum implementasi HDFS dengan mapreduce sebagai analisis big data 
agar berjalan dengan benar dilakukan. Ada langkah-langkah yang harus diikuti seperti, menginstal hadoop  sebagai lingkungan big data penelitian pada masternode dan slavenode, melakukan konfigurasi untuk tiap node (bashrc, namenode, datanode, dll) agar dapat saling berinteraksi dan dengan bantuan python. Setelah kedua 
langkah tersebut dilakukan dengan benar, maka HDFS dapat dijalankan dengan menggunakan MapReduce dan bisa dijalankan.[3]
![tahap awal perencanaan.png](https://www.dropbox.com/scl/fi/cuwguntqavrh251m77bop/tahap-awal-perencanaan.png?rlkey=0hh3epqmr2jk1196285k0uvuh&dl=0&raw=1)
### Langkah-langkah Percobaan
-	Mengaktifkan Linux (Ubuntu 15)
![aktifkan linux ubuntu.png](https://www.dropbox.com/scl/fi/jgwcozkc7v5q8cx2z5drp/aktifkan-linux-ubuntu.png?rlkey=zz4weym93g82nb3bnho9r30ko&dl=0&raw=1)
-	Menyiapkan Dataset yang diperlukan serta Coding Mapper dan Reducer di Hadoop Master.
![menyiapkan dataset yang diperlukan.png](https://www.dropbox.com/scl/fi/392gfc4moi6ne4nufnozq/menyiapkan-dataset-yang-diperlukan.png?rlkey=046tzpfsz7c1ajuyzeqns3tyv&dl=0&raw=1)
-	Mengaktifkan HDFS dan YARN
![mengaktifkan hdfs dan yarn.png](https://www.dropbox.com/scl/fi/afue5kbtrdkwr8brxp11y/mengaktifkan-hdfs-dan-yarn.png?rlkey=m1iqz1ltf0imw4q8z2y6b039m&dl=0&raw=1)
-	Mengecek Keaktifan Localhost:9870 dan Localhost:8042 
![mengecek keaktifan locallhost1.png](https://www.dropbox.com/scl/fi/r2v10i4p7bpdb5wzrhjlp/mengecek-keaktifan-locallhost1.png?rlkey=j9f9yskra0u9iocgaghqiumjb&dl=0&raw=1)
![mengecek keaktifan locallhost2.png](https://www.dropbox.com/scl/fi/lbx9nvqt1gempc5khmde5/mengecek-keaktifan-locallhost2.png?rlkey=t6832wgr6vozs6auzd1vxyueq&dl=0&raw=1)
![mengecek keaktifan locallhost3.png](https://www.dropbox.com/scl/fi/d7ox23r99t0mtkhuy6uve/mengecek-keaktifan-locallhost3.png?rlkey=3x94iiogxnk8qtuagtynvga2h&dl=0&raw=1)
-	Mengcopy Dataset ke HDFS dan Melakukan Pengecekan
![copy dataset.png](https://www.dropbox.com/scl/fi/nomj6rrcmxyghfm3v4rla/copy-dataset.png?rlkey=7xlr79t2rb1n42nqt1o549dcf&dl=0&raw=1)
-	Menggunakan Fungsi MapReduce, dilakukan dengan Hadoop Jar agar dapat mengubah bahasa pemrograman tersebut dari Java ke Python agar bisa dibaca sistem.
![gunakan fungsi mareduce.png](https://www.dropbox.com/scl/fi/azqw8pfzj15yww91wfq2e/gunakan-fungsi-mareduce.png?rlkey=xzuknuzaif6v24qg9egj26ims&dl=0&raw=1)
-	Proses Pelaksanaan MapReduce
![proses pelaksanaan mapreduce.png](https://www.dropbox.com/scl/fi/xq787bofcuz29197fat5h/proses-pelaksanaan-mapreduce.png?rlkey=27txv11x5cn95vp6v5mpyx8pg&dl=0&raw=1)
-	Hasil Akhir dari Proses MapReduce
![hasil akhir mapreduce.png](https://www.dropbox.com/scl/fi/lo9fmrinoalh1im6eg2fc/hasil-akhir-mapreduce.png?rlkey=mjwn4ae4n6ob04zhx9t81fg18&dl=0&raw=1)
## 4. HASIL PENELITIAN
### 4.1 Implementasi Sistem

#### 4.1.1 Implementasi Sistem Perangkat Keras
Penelitian ini menggunakan platform virtualisasi VirtualBox dengan konfigurasi multi-node.
# Komponen Perangkat Keras
Penelitian ini menerapkan sistem dengan basis VirtualBox sebagai platform virtualisasi, dengan konfigurasi multi-node. Rincian spesifikasi perangkat keras yang digunakan dapat ditemukan dalam tabel yang disediakan.


| Komponen Perangkat Keras | Hardware User | Hardware VirtualBox (Master-node) | Hardware VirtualBox (Node-1) | Hardware VirtualBox (Node-2) |
|--------------------------|---------------|-----------------------------------|-------------------------------|-------------------------------|
| Processor                |               | cores                             |                               |                               |
| RAM                      |               | GB                                |                               |                               |
| Graphicard               |               |                                   |                               |                               |


#### 4.1.2 Implementasi Sistem Perangkat Lunak
Dalam penelitian ini, perangkat lunak yang diterapkan adalah linux  (Ubuntu 15) Untuk sistem Hadoop, digunakan versi Hadoop 3.2.2 . kami memakai satu komputer menggunakan koneksi antara dua server node tunggal, satu untuk komputer slave dan satu lagi untuk master komputer..
![implementasi spl.png](https://www.dropbox.com/scl/fi/4p5hiza3v73sf2z0rrkob/implementasi-spl.png?rlkey=veq8llniqpr3zk8hpvjp3qjrt&dl=0&raw=1)
### 4.2 Hasil Data

#### 4.2.1 Hasil Data Mapreduce
Setelah berhasil menjalankan proses MapReduce pada dataset yang diberikan, hasilnya adalah pengelompokan lagu berdasarkan genre musik. Dari hasil pengolahan data, kami dengan bangga menyampaikan bahwa terdapat 516 lagu dengan genre Mellow, 1134 lagu dengan genre Pop, dan 339 lagu dengan genre Rock. Pengelompokan genre ini diperoleh melalui pengurutan tempo yang diimplementasikan pada mapper dan reducer.
Implementasi kode yang digunakan untuk pengolahan data ini adalah sebagai berikut:
![hasilmapreduce.png](https://www.dropbox.com/scl/fi/a2uiquh23t1vgphtykd16/hasilmapreduce.png?rlkey=2a1urbdn3ud9ipnvfyy0zjwwm&dl=0&raw=1)

#### 4.2.2 Hasil Data Menggunakan Apache Hadoop
Pengecekan melalui command "cat" pada Hadoop, dan hasilnya adalah sebagai berikut:
![hasilapache2.png](https://www.dropbox.com/scl/fi/9cbf7d9bynntryp0hrp6z/hasilapache2.png?rlkey=llqeztai84rucd9kl3ayoxasy&dl=0&raw=1)
![mapperpy.png](https://www.dropbox.com/scl/fi/6wtsc312waghq6wy33e1a/mapperpy.png?rlkey=akn94rrv73mqk969ep9scie4z&dl=0&raw=1)mapper.py
![reducerpy.png](https://www.dropbox.com/scl/fi/1yhspxy0z4qzmiebsm5gv/reducerpy.png?rlkey=m7y517q1ougg8o6s8687ullsg&dl=0&raw=1)reducer.py
 Selain itu juga dilakukan pengecekan melalui command cat untuk memastikan bahwa hasil output mapper dan reducer dari terminal linux sama seperti hasil output pada HDFS, dan hasilnya mereka memiliki output yang sama persis
 
 ## 5. KESIMPULAN
Dari implementasi diatas, dapat disimpulkan bahwa MapReduce merupakan suatu paradigma pemrograman yang memungkinkan skalabilitas besar-besaran di ratusan atau ribuan server dalam cluster Hadoop. Sebagai komponen pemrosesan, MapReduce juga disebut jantung dari Apache Hadoop. Istilah "MapReduce" mengacu pada dua tugas terpisah dan berbeda yang dilakukan program Hadoop. Yang pertama adalah tugas peta, yang mengambil sekumpulan data dan mengubahnya menjadi kumpulan data lain, di mana masing-masing elemen dipecah menjadi tupel. Pekerjaan pengurangan mengambil keluaran dari peta sebagai masukan dan menggabungkan tupel data tersebut menjadi kumpulan tupel yang lebih kecil. 

Dengan melakukan MapReduce, kita dapat mengambil beberapa hal yang kita perlukan dari suatu dataset terutama file yang memiliki jumlah data yang besar. Dengan begitu, akan menjadi mudah untuk menarik kesimpulan dari suatu kumpulan data-data yang ada dan terstruktur.


# DAFTAR PUSTAKA

1. V. S. Martha, Weizhong Zhao, and Xiaowei Xu, "h-MapReduce: A Framework for Workload Balancing in MapReduce," in 2013 IEEE 27th International Conference on Advanced Information Networking and Applications (AINA), IEEE, Mar. 2013, pp. 637-644. doi: 10.1109/AINA.2013.48.

2. C. Verma and R. Pandey, "Big Data representation for grade analysis through Hadoop framework," in 2016 6th International Conference - Cloud System and Big Data Engineering (Confluence), IEEE, Jan. 2016, pp. 312-315. doi: 10.1109/CONFLUENCE.2016.7508134.

3. Kumar, Ganesh & Basri, Shuib & Abubakar Imam, Abdullahi & Balogun, Abdullateef. (2020). Data Harmonization for Heterogeneous Datasets in Big Data -A Conceptual Model. 10.1007/978-3-030-63322-6_61.

4. Smith, J., Petrovic, P., Rose, M., De Souz, C., Muller, L., Nowak, B., & Martinez, J. (2021). PlaceholderText: A Study. The Journal of Citation Styles, 3. https://doi.org/10.10/X.

5. Shengying Yang, Wuyin Jin, Yunxiang Yu, Kamarul Faizal Hashim, "Optimized Hadoop MapReduce system for strong analytics of cloud big product data on Amazon Web Service," Information Processing & Management, Volume 60, Issue 3, 2023, https://doi.org/10.1016/j.ipm.2023.103271.

6. Antônio José Alves Neto, José Aprígio Carneiro Neto, Edward David Moreno, "The development of a low-cost big data cluster using Apache Hadoop and Raspberry Pi. A complete guide," Computers and Electrical Engineering, Volume 104, Part A, 2022, https://doi.org/10.1016/j.compeleceng.2022.108403.

7. NETPLG.COM, Jurnal Ilmu Komputer, Vol. 1 No. 1, Januari 2021. [Online] Available: https://jik.netplg.com. "Harmonisasi Big Data: Membelai Melodi ribuan Data dalam Dataset Lagu melalui Analisis HDFS."

       
