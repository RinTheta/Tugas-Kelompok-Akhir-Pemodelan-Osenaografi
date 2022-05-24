# **Tugas Kelompok Akhir Pemodelan Oseanografi**
Repositori ini merupakan tugas akhir mata kuliah Praktikum Pemodelan Oseanografi tahun 2022. Bahasa pemograman yang digunakan dalam repositori ini adalah bahasa pemograman Python yang dapat dikerjakan pada text editor Google Colaboratory, Visual Studio Code  dan Jupyter Notebook. Modul yang digunakan pada repositori ini adalah matplotlib, numpy, dan sys.

# **Kelompok 22**
1. Agustia Cahyaningtyas - 26050120130094
2. Dzaki Al Furqon - 26050120140160
3. Raid Arjun Permana - 26050120140139
4. Rafa Fahrezi Tagore - 26050120130117
5. Raja Morga Daniel - 26050120130039
6. Rizki Taqwa Putranto - 26050120130050
7. Zahra Ardhanaswari - 26050120140153

# **Prosedur Instalasi Miniconda**
1. Unduh file instalasi miniconda melalui website pilihlah sesuai jenis perangkat yang digunakan
> ![image](https://user-images.githubusercontent.com/102911269/169704071-63026bad-f7d7-457a-87e2-a51f8a1df97c.png)
 
2. Jalankan program yang sebelumnya di unduh dan setujui setiap step yang ada, atau kustomisasi sesuai kengininan, jika proses pengintalan selesai maka klik finish 
> ![image](https://user-images.githubusercontent.com/102911269/169704193-bc2c7632-bec9-458c-8dfe-49f542f0f06d.png)

# **Prosedur Instalasi Library**
1. Untuk instalasi library pertama buka aplikasi Anaconda Prompt (miniconda 3)
> ![minicon](https://user-images.githubusercontent.com/102911269/169704841-9b3cbbb4-6104-41e4-b620-8c31e1dd213c.png)


2. Ketikan (pip install + nama librray yang digunakan (selengkapnya dapat di cek di bawah))
> ![image](https://user-images.githubusercontent.com/102911269/169704739-8550e56f-e503-41f4-897f-eaa4a86b5c9a.png)

3. Enter untuk run tunggu hingga selesai dan ulangi langkah yang sama untuk library lainnya
> ![image](https://user-images.githubusercontent.com/102911269/169704754-446896b6-30f6-4f09-990b-cec8387c8547.png)

**Daftar Library yang Digunakan**

> Matplotlib = ```pip install matplotlib```

> Numpy = ```pip install numpy```

> sys = ```pip install os-sys```

> Siphon = ```pip install siphon```

# **Modul 1 Adveksi Difusi 1 Dimensi**
### **Materi**

### **Hasil**

# **Modul 2 Adveksi Difusi 2 Dimensi**
### **Materi**


### **Penjelasan Coding**

![image](https://user-images.githubusercontent.com/102911269/169702805-d1f21fcd-6bcc-48a0-a9ad-8f810ef5fe25.png)

Pada modul ini library yang digunakan adalah library Matplotlib, Numpy, dan sys
> Library Matplotlib merupakan library yang digunakan untuk menjalankan visualisasi data dan pustaka plot grafis untuk Python dan ekstensi numeriknya NumPy

> Library Numpy digunakan sebagai ekstensi  untuk melakukan berbagai macam operasi matematika pada suatu array

> Library sys berguna untuk menyediakan berbagai fungsi dan variabel yang digunakan untuk memanipulasi bagian yang berbeda dari lingkungan runtime Python

![image](https://user-images.githubusercontent.com/102911269/169703324-3524c1cd-980b-459d-94d2-0d4be1c8a9ab.png)

fungsi def digunakan untuk mendefinisikan penggunaan angka dalam satuan persen desimal

![image](https://user-images.githubusercontent.com/102911269/169703150-ace83883-daae-4011-aca6-509d71e9a1b8.png)

Masukan parameter yang digunakan adalah C, ad, arah arus, dan q, x, y, dt, dx, dan dy
> C merupakan kecepatan aliran

> ad merupakan parameter yang menunjukkan koefisen difusi

> Arah arus yang digunakan didefinisikan dalam bentuk arah derajat

> q merupakan parameter yang menunjukan 

> x dan y merupakan parameter yang menunjukkan 

> dt merupakan parameter yang menunjukan koefisien Delta T

> dx merupakan parameter yang menunjukan

> dy merupakan parameter yang menunjukan

![image](https://user-images.githubusercontent.com/102911269/169703304-f34c6edf-fde4-4075-9993-7d23a080d1ff.png)


### **Hasil**
> ![ezgif com-gif-maker](https://user-images.githubusercontent.com/102911269/169705494-142fc028-55fd-4464-9595-cfb69ba51802.gif)

Berdasarkan Hasil yang didapat dapat disimpulkan bahwa 

# **Modul 3 Hidrodinamika 1 Dimensi**
### **Materi**

### **Penjelasan Coding**

![2022-05-24_093539](https://user-images.githubusercontent.com/106040998/169937453-4cb0cc42-4fde-4aac-8710-3eb123f72168.png)


### **Hasil**


# **Modul 4 Hidrodinamika 2 Dimensi**
### **Materi**

### **Penjelasan Coding**

![image](https://user-images.githubusercontent.com/105922284/169753571-b9ddc764-0370-453c-be02-6ab0d177787e.png)

Pada modul ini library yang digunakan adalah library Matplotlib dan Siphon
> Library Matplotlib merupakan library yang digunakan untuk menjalankan visualisasi data dan pustaka plot grafis untuk Python. Matplotlib memberikan visualisasi berupa grafik fungsi yang didapat dengan memasukkan beberapa fungsi matematika.

> Library Siphon merupakan kumpulan penggunaan Python untuk mengunduh data dari layanan data jarak jauh dan mudah diintegrasikan ke dalam alur kerja yang dibangun menggunakan ekosistem Python ilmiah, termasuk proyek Numpy, Scipy, dan Matplotlib, serta dengan perpustakaan MetPy Unidata, yang merupakan kumpulan alat dalam Python untuk membaca, memvisualisasikan, dan melakukan perhitungan dengan data cuaca.

Masukkan persamaan dengan menggunakan library yang sebelumnya telah ditambahkan dalam modul ini. Masukkan pula stasiun yang akan dituju, misalnya NWPR1 (Newport, Rhode Island, USA).

![image](https://user-images.githubusercontent.com/105922284/169758512-74b4529c-94a0-4a85-96d8-1c7fb3d3ee1f.png)

Masukkan persamaan yang memuat parameter tekanan air. Jangan lupa diberikan identitas untuk membedakan pengguna satu dengan pengguna lainnya.

![image](https://user-images.githubusercontent.com/105922284/169758682-f5e465fa-9a42-4be7-b9b0-f74a27ee9167.png)

Masukkan persamaan yang memuat parameter kecepatan angin dan arah angin.

![image](https://user-images.githubusercontent.com/105922284/169758891-d49679f1-1726-4808-8d04-6252de15b0ad.png)

Masukkan persamaan yang memuat parameter suhu perairan.

![image](https://user-images.githubusercontent.com/105922284/169758961-8351a61e-7908-4acf-99ef-8258f90830bb.png)

Maka, script dapat dijalankan untuk mendapatkan hasil berupa grafik visualisasi yang memuat grafik tekanan, kecepatan dan arah angin, dan suhu perairan.

![image](https://user-images.githubusercontent.com/105922284/169759306-d75c97c2-5877-4042-ab0f-37d8ccf53beb.png)

### **Hasil**
> ![image](https://user-images.githubusercontent.com/105922284/169754981-ffc8c40c-abd2-4348-a2de-82d2e68add8e.png)

Berdasarkan Hasil yang didapat dapat disimpulkan bahwa terjadi korelasi antara parameter tekanan air, angin, dan suhu perairan. Angin dihasilkan oleh perbedaan tekanan dan suhu di atmosfer akibat distribusi energi radiasi matahari, tutupan awan serta dinamika disekitarnya. Angin menghantarkan kandungan panas terutama dengan proses adveksi massa air hangat ke daerah dingin dan sebaliknya (Aldrian, 2008). Ketika lautan mendingin, maka laut akan merespon dengan menghasilkan gerak konveksi vertikal yang akan mensuplai panas ke permukaan. Hal ini terjadi karena persamaan kontinuitas massa membutuhkan air dingin mengendap ke kedalaman dari permukaan tergantikan oleh massa air di bawahnya yang notabene lebih hangat. Air hangat tersebut akan menyembul ke permukaan. Proses perubahan suhu di lautan terjadi jauh lebih lambat daripada di atmosfer. Sebagai akibat maka lautan terus panas meskipun ekuinok atau titik nadir matahari telah menjauhi garis khatulistiwa.
