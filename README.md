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

Adveksi pada pemodelan Oseanografi dapat dikatakan secara ringkas sebagai proses transportasi/ perpindahan massa suatu materi dari titik ke titik lainnya berupa aliran rata rata arus. Sedangkan Difusi merupakan proses transportasi materi dari suatu sistem ke bagian sistem yang lain sebagai hasil dari gerakan molekul acak. Difusi ini dapat dipengaruhi karena adanya kecepatan dan perbedaan konsentrasi.

Pada model adveksi difusi 2 Dimensi, terdapat 2 persamaan pembangun dalam penerapannya. Yang pertama adalah persamaan pembangun adveksi dan difusi. Berikut merupakan persamaan pembangun dan diskritisasinya.

Adveksi Model 2D
> Persamaan dasarnya yaitu
> ![image](https://user-images.githubusercontent.com/105927463/169943453-98c3d7f7-a9f8-402e-84db-8e9010463ef9.png).
  
Difusi Model 2D
> Persamaan dasarnya yaitu
> ![image](https://user-images.githubusercontent.com/105927463/169943703-8292b982-5006-4a8e-8c4c-48627880ac13.png)
		
Kedua persamaan diatas merupakan persamaan umum yang menggambarkan proses adveksi-difusi yang membentuk persamaan model 2D di alam, dimana perlu adanya diskritisasi untuk kedua persamaan tersebut.
		
Diskritisasi merupakan suatu metode untuk mencari solusi persamaan secara numerik dari persamaan matematis sehingga dapat dibentuk menjadi dimensi ruang dan waktu.
Untuk Diskritisasinya dapat menggunakan metode upstream (Eksplisit) dimana persamaan beda hingga menggunakan pendekatan beda maju untuk turunan waktu dan untuk turunan ruang menggunakan dengan menggunakan arah kecepatan u.ika u > 0 maka turunan terhadap ruang menggunakan pendekatan beda mundur, sebaliknya jika u < 0 digunakan pendekatan beda maju.
>Persamaan dari metode diskritisasi untuk suku adveksi 2D adalah sebagai berikut :
>![image](https://user-images.githubusercontent.com/105927463/169944973-9f25a4a3-09b4-467d-9141-bf3c1dc08cc5.png)
		
Dan untuk mekanisme transpor difusi 2D dapat menggunakan pendekatan beda maju untuk turunan waktu dan beda pusat untuk turunan ruang. Indeks n untuk waktu, indeks i untuk ruang, dan koefisiesn difusi AD dianggap konstan terhadap ruangdan waktu.
>Persamaan dari metode diskritisasi untuk suku difusi 2D adalah sebagai berikut :
>![image](https://user-images.githubusercontent.com/105927463/169945106-060f17cf-d4ba-4603-a366-9749f1fb956e.png)
		
Dan dari kedua diskritisasi berikut digabungkan untuk mendapatkan proses adveksi difusi 2D dengan hasil sebagai berikut
>![image](https://user-images.githubusercontent.com/105927463/169945255-ffa3121e-9104-4ca1-8430-892ba357e5bb.png)
		
 Untuk Pernerapan di Bidang Oseanografi itu sendiri Modul Adveksi Difusi 2D ini dapat digunakan untuk
>1.Mengetahui Persebaran Polutan di Laut dan memodelkannya
		
>2.Mengetahui Persebaran Nutrient di laut dan memodelkannya
		
>3.Mengetahui Persebaran kebocoran atau tumpahan minyak di lautan
		
>4.Memodelkan penyebaran polutan yang tersebar dari hasil limbah industry dari sungai ke laut


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

![2022-05-24_094215](https://user-images.githubusercontent.com/106040998/169937924-ab936413-a85b-4fbd-9da2-3e6979bbfbec.png)

![kec arus dalam waktu](https://user-images.githubusercontent.com/106040998/169938817-717bda93-9b08-48f0-9211-6a5c66ac1f1d.png)



### **Hasil**

![1](https://user-images.githubusercontent.com/106040998/169938957-dc305df3-7c7a-4028-994e-5ac71299455c.png)

![2](https://user-images.githubusercontent.com/106040998/169939003-d0969581-935e-4373-a4e7-eadb93c70092.png)

![3](https://user-images.githubusercontent.com/106040998/169939043-b17c9ae3-6dba-4bb1-bcbe-e9e0516f291c.png)

![4](https://user-images.githubusercontent.com/106040998/169939090-e012ec27-2fb1-441a-9947-a8e3a469e394.png)


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
