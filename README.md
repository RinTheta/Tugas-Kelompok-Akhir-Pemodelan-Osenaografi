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

## **Daftar Library yang Digunakan**

> Matplotlib = ```pip install matplotlib```

> Numpy = ```pip install numpy```

> sys = ```pip install os-sys```

> Siphon = ```pip install siphon```

# **Modul 1 Adveksi Difusi 1 Dimensi**
## **Materi**

Persamaan Adveksi merupakan salah satu persamaan diferensial parsial yang memodelkan pergerakan konsentrat dalam cairan yang mengalir, dengan asumsi konsentrat tersebut tidak mengalami proses difusi di dalam cairan. Adveksi berkaitan erat dengan aktivitas atau pergerakan suatu benda dari suatu tempat ke tempat lainnya untuk waktu tertentu. Persamaan adveksi merupakan bentuk khusus dari persamaan diferensial untuk hukum kekekalan.

### **Persamaan umum Adveksi 1D:**

![image](https://user-images.githubusercontent.com/106157138/170030902-792d5b52-3b81-4150-8d0c-e9f9dc7b392e.png)

dimana:

F : Konsentrasi zat pelarut (mg/L)

u : Kecepatan

x : ruang sumbu horisontal (meter)

t : waktu (detik)

Dalam pemodelan numerik secara umum dibagi menjadi 2 pendekatan yaitu eksplisit dan implisit. metode eksplisit dibagi menjadi 3 yaitu:

### **FTCS (Forward in Time Central in Space)**

Metode FTCS merupakan gabungan dari selisih maju terhadap waktu dan selisih pusat terhadap ruang. Solusi FTCS juga termasuk ke dalam solusi stabil bersyarat.

Syarat kestabilan:

![image](https://user-images.githubusercontent.com/106157138/170031298-746aac0f-3545-4e54-86be-197e7243b6d7.png)

### **Leapfrog (CTCS)**

Metode beda hingga ini merupakan perluasan dari metode beda tengah (central difference) terhadap ruang dan waktu. Skema Leapfrog didapatkan dari turunan deret taylor, ini adalah skema konsisten. Leapfrog ini akan konsisten apabila nilai C ???1.

![image](https://user-images.githubusercontent.com/106157138/170031458-cb0c0ea8-8cf0-4eb7-949c-3e148aa6d0db.png)

### **Upstream**

Metode ini menggunakan pendekatan beda maju untuk turunan waktu, sedangkan untuk turunan terhadap ruang dilakukan dengan melihat arah kecepatan u. jika > 0 maka turunan terhadap menggunakan pendejatan beda mundur. Sebaliknya jika u < 0 maka digunakan pendekatan beda maju. Stabilitas metode upstream adalah sebagai berikut:

Jika u > 0, turunan terhadap ruang menggunakan pendekatan beda mundur.

![image](https://user-images.githubusercontent.com/106157138/170031798-bfe073a0-9a8a-4622-aa41-03ed5f05f9f8.png)

dengan skema langkah sebagai berikut 

![image](https://user-images.githubusercontent.com/106157138/170031955-3f438c62-f079-45aa-b55b-575ba04cd345.png)

Jika u < 0, turunan terhadap ruang menggunakan pendekatan beda maju.

![image](https://user-images.githubusercontent.com/106157138/170032056-826a6338-8771-4879-9647-54804fbf3697.png)

dengan skema langkah sebagai berikut 

![image](https://user-images.githubusercontent.com/106157138/170032169-74136452-c837-479a-999c-4810aedcb70d.png)

### **Difusi 1D**

Persamaan difusi merupakan persamaan diferensial parsial linier yang merupakan representasi berpindahnya zat dalam pelarut berkonsentrasi tinggi ke bagian yang berkonsentrasi rendah. Zat meyebar karena adanya gradien konsentrasi. Proses ini akan terjadi sampai seluruh partikel tersebar luas secara merata atau mencapai keadaan setimbang yaitu dimana perpindahan molekul tetap terjadi namun tidak ada perubahan konsentrasi. Faktor-faktor yang mempengaruhi kecepatan difusi diantaranya ukuran partikel, luas area, jarak dan suhu, dan ketebalan membran. Pengaplikasian di oseanografi salah satunya dalam tumpahan minyak (oil spill).

Dalam metode ini, deskritisasi dilakukan secara eksplisit (FTCS) dimana syarat batas terpenuhi=overflow

![image](https://user-images.githubusercontent.com/106157138/170033374-825d8423-f6ef-4023-9e1b-1b48ce4b6fa2.png)


# **Modul 2 Adveksi Difusi 2 Dimensi**
## **Materi**

Adveksi pada pemodelan Oseanografi dapat dikatakan secara ringkas sebagai proses transportasi/ perpindahan massa suatu materi dari titik ke titik lainnya berupa aliran rata rata arus. Sedangkan Difusi merupakan proses transportasi materi dari suatu sistem ke bagian sistem yang lain sebagai hasil dari gerakan molekul acak. Difusi ini dapat dipengaruhi karena adanya kecepatan dan perbedaan konsentrasi.

Pada model adveksi difusi 2 Dimensi, terdapat 2 persamaan pembangun dalam penerapannya. Yang pertama adalah persamaan pembangun adveksi dan difusi. Berikut merupakan persamaan pembangun dan diskritisasinya.

### **Adveksi Model 2D**
> Persamaan dasarnya yaitu


> ![image](https://user-images.githubusercontent.com/105927463/169943453-98c3d7f7-a9f8-402e-84db-8e9010463ef9.png).

### **Difusi Model 2D**
> Persamaan dasarnya yaitu

> ![image](https://user-images.githubusercontent.com/105927463/169943703-8292b982-5006-4a8e-8c4c-48627880ac13.png)

Kedua persamaan diatas merupakan persamaan umum yang menggambarkan proses adveksi-difusi yang membentuk persamaan model 2D di alam, dimana perlu adanya diskritisasi untuk kedua persamaan tersebut.

> ![image](https://user-images.githubusercontent.com/105927463/169943453-98c3d7f7-a9f8-402e-84db-8e9010463ef9.png).
  
### **Difusi Model 2D**
> Persamaan dasarnya yaitu

> ![image](https://user-images.githubusercontent.com/105927463/169943703-8292b982-5006-4a8e-8c4c-48627880ac13.png)
		
Kedua persamaan diatas merupakan persamaan umum yang menggambarkan proses adveksi-difusi yang membentuk persamaan model 2D di alam, dimana perlu adanya diskritisasi untuk kedua persamaan tersebut.
		

Diskritisasi merupakan suatu metode untuk mencari solusi persamaan secara numerik dari persamaan matematis sehingga dapat dibentuk menjadi dimensi ruang dan waktu.
Untuk Diskritisasinya dapat menggunakan metode upstream (Eksplisit) dimana persamaan beda hingga menggunakan pendekatan beda maju untuk turunan waktu dan untuk turunan ruang menggunakan dengan menggunakan arah kecepatan u.ika u > 0 maka turunan terhadap ruang menggunakan pendekatan beda mundur, sebaliknya jika u < 0 digunakan pendekatan beda maju.
>Persamaan dari metode diskritisasi untuk suku adveksi 2D adalah sebagai berikut :

>![image](https://user-images.githubusercontent.com/105927463/169944973-9f25a4a3-09b4-467d-9141-bf3c1dc08cc5.png)


Dan untuk mekanisme transpor difusi  2D dapat menggunakan pendekatan beda maju untuk turunan waktu dan beda pusat untuk turunan ruang. Indeks n untuk waktu, indeks i untuk ruang, dan koefisiesn difusi AD dianggap konstan terhadap ruangdan waktu.
>Persamaan dari metode diskritisasi untuk suku difusi 2D adalah sebagai berikut :

>![image](https://user-images.githubusercontent.com/105927463/169945106-060f17cf-d4ba-4603-a366-9749f1fb956e.png)

Dan dari kedua diskritisasi berikut digabungkan untuk mendapatkan proses adveksi difusi 2D dengan hasil sebagai berikut
>![image](https://user-images.githubusercontent.com/105927463/169945255-ffa3121e-9104-4ca1-8430-892ba357e5bb.png)

Untuk Pernerapan di Bidang Oseanografi itu sendiri Modul Adveksi Difusi 2D ini dapat digunakan untuk
>1.Mengetahui Persebaran Polutan di Laut dan memodelkannya

>2.Mengetahui Persebaran Nutrient di laut dan memodelkannya

>3.Mengetahui Persebaran kebocoran atau tumpahan minyak di lautan

>4.Memodelkan penyebaran polutan yang tersebar dari hasil limbah industry dari sungai ke laut

		
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



## **Penjelasan Coding**

### **Input Library**

```
import matplotlib.pyplot as plt
import numpy as np
import sys
```

Pada modul ini library yang digunakan adalah library Matplotlib, Numpy, dan sys
> Library Matplotlib merupakan library yang digunakan untuk menjalankan visualisasi data dan pustaka plot grafis untuk Python dan ekstensi numeriknya NumPy

> Library Numpy digunakan sebagai ekstensi  untuk melakukan berbagai macam operasi matematika pada suatu array

> Library sys berguna untuk menyediakan berbagai fungsi dan variabel yang digunakan untuk memanipulasi bagian yang berbeda dari lingkungan runtime Python

### **Pendefinisian Bilangan yang digunakan**

```
def percentage(part, whole):
    percentage = 100 * float(part)/float(whole)
    return str(round(percentage,2)) + "x"
```

fungsi def digunakan untuk mendefinisikan penggunaan angka dalam satuan persen desimal

### **Input Parameter**

```
#Masukan Parameter Awal
C = 0.05
ad = 1.05

#Arah Arus
#theta = 5
#theta = 65
#theta = 140
theta = 320

#Parameter Lanjutan
q = 0.95 
x = 300 
y = 300 
dt = 0.5 
dx = 3 
dy = 3 
```

Masukan parameter yang digunakan adalah C, ad, arah arus, dan q, x, y, dt, dx, dan dy
> C merupakan kecepatan aliran

> ad merupakan parameter yang menunjukkan koefisen difusi

> Arah arus yang digunakan didefinisikan dalam bentuk arah derajat

> q merupakan parameter yang menunjukan 

> x dan y merupakan parameter yang menunjukkan arah perubahan sudut

> dt merupakan parameter yang menunjukan perubahan arah sepanjang waktu

> dx merupakan parameter yang menunjukan arah perubuhan sepanjang x

> dy merupakan parameter yang menunjukan arah perubahan sepanjang y

### **Penentuan Lama Waktu Simulasi**

```
#Lama Simulasi
Tend = 1
#Tend = 0,5
dt = 0.5

```

Pada bagian Lama simulasi, Tend menunjukkan simulasi ke n waktu dari keseluruhan waktu yang dimodelkan

### **Perhitungan Sebaran Polutan**

```
#Polutan
px = 150
py = 130
Ic = 550

#Perhitungan U dan V
u = C * np.sin(theta*np.pi/180)
v = C * np.cos(theta*np.pi/180)
dt_count = 1/((abs(u)/(q*dx))+(abs(v)/(q*dy))+(2*ad/(q*dx**2))+(2*ad/(q*dy*2)))

Nx = int(x/dx)  #number of mesh in x direction
Ny = int(y/dy)  #number of mesh in y direction
Nt = int(Tend/dt)

#perhitungan titik polutan di buang
px1 = int(px/dx)
py1 = int(py/dy)

#fungsi disederhanakan
lx = u*dt/dx
ly = v*dt/dy
ax = ad*dt/dx**2
ay = ad*dt/dy**2
cfl = (2*ax + 2*ay + abs(lx) + abs(ly))  #syarat kestabilan CFL

#perhitungan cfl
if cfl >= q:
    print('CFL Violated, please use dt :'+str(round(dt_count,4)))
    sys.exit ()
#%%
```
### **Pembuatan Grid Penyebaran Polutan**

```

#pembuatan grid 
x_grid = np.linspace(0-dx, x+dx, Nx+2) #ghostnode boundary
y_grid = np.linspace(0-dx, y+dy, Ny+2) #ghostnode boundary
t = np.linspace(0, Tend, Nt+1)
x_mesh, y_mesh = np.meshgrid(x_grid,y_grid)
F = np.zeros((Nt+1, Ny+2, Nx+2))
```

### **Iterasi, Perhitungan Syarat Batas. dan Pembuatan Output Gambar**

```
#Iterasi
for n in range (0, Nt):
    for i in range (1,Ny+1):
        for j in range (1, Nx+1):
         F[n+1,i,j]=((F[n,i,j]*(1-abs(lx)-abs(ly))) + \
                (0.5*(F[n,i-1,j]*(ly+abs(ly)))) + \
                (0.5*(F[n,i+1,j]*(abs(ly)-ly))) + \
                (0.5*(F[n,i,j-1]*(lx+abs(lx)))) + \
                (0.5*(F[n,i,j+1]*(abs(lx)-lx))) + \
                (ay*(F[n,i+1,j]-2*(F[n,i,j])+F[n,i-1,j])) +\
                (ax*(F[n,i,j+1]-2*(F[n,i,j])+F[n,i,j-1])))
    #syarat batas
    F[n+1,0,:] = 0 #bc bawah
    F[n+1,:,0] = 0 #bc kiri
    F[n+1,Ny+1,:] = 0 #bc atas
    F[n+1,:,Nx+1] = 0 #bc kanan
#%%

    #Output Gambar
    plt.clf()
    plt.pcolor(x_mesh, y_mesh, F[n+1, :, :], cmap = 'jet',shading='auto',edgecolor='k')
    cbar=plt.colorbar(orientation='vertical',shrink=0.95,extend='both')
    plt.clf()
    plt.pcolor(x_mesh,y_mesh,F[n+1,:,:],cmap='jet',shading='auto',edgecolor='k')
    cbar = plt.colorbar(orientation='vertical',shrink=0.95,extend='both')
    cbar.set_label(label='Concentration',size = 8)
    #plt.clim(0,100)
    plt.title('Identitas \n t='+str(round(dt*(n+1),3))+ ', Initial condition='+str(Ic),fontsize=10)
    plt.xlabel('x_grid',fontsize=9)
    plt.ylabel('y_grid',fontsize=9)
    plt.axis([0, x, 0, y])
    #plt.pause(0.01)
    plt.savefig(str(n+1)+'.jpg', dpi=300)
    plt.pause(0.01)
    plt.close()
    print('running timestep ke:' +str(n+1) + ' dari:' +str(Nt) + '('+ percentage(n+1,Nt)+')')
    print('Nilai CFL:' +str(cfl) + 'dengan arah: ' +str(theta))
    print( 'Nilai u: ' +str(u))
    print( 'Nilai v: ' +str(v))
    print( 'Nilai ax: ' +str(ax))
    print( 'Nilai ay: ' +str(ay))
    print( 'Nilai lx: ' +str(lx))
    print( 'Nilai ly: ' +str(ly))
```

## **Hasil**
> ![ezgif com-gif-maker](https://user-images.githubusercontent.com/102911269/169705494-142fc028-55fd-4464-9595-cfb69ba51802.gif)

Berdasarkan Hasil yang didapat dapat disimpulkan bahwa persebaran dari polutan pada perairan berjalan sesuai dengan nilai dari C (kecepatan aliran) dan Ad (koefisien difusi) yang ada. Semakin besar koefisien difusi, proses difusi akan terjadi lebih cepat. Sementara itu, semakin kecil  kecepatan alirannya maka proses pergerakan dari polutan akan semakin kecil. Sementara itu arah dari penyebaran polutan sangat bergantung pada nilai theta (arah gerak arus) yang berlaku pada pemodelan tersebut.  

# **Modul 3 Hidrodinamika 1 Dimensi**
## **Materi**
Hidrodinamika adalah cabang dari mekanika fluida, khususnya zat cair incompressible yang di pengaruhi oleh gaya internal dan eksternal. Dalam
hidrodinamika laut gaya-gaya yang terpenting adalah gaya gravitasi, gaya gesekan, dan gaya coriolis . Dalam oseanografi, mekanika fluida digunakan berdasarkan mekanika
Newton yang dimodifikasi dengan memperhitungkan turbelensi.

### Persamaan - Persamaan 
Hidrodinamika 1 Dimensi merupakan model yang dibangun dari adanya proses - proses yang mempengaruhi pergerakan massa air.hidrodinamika 1 Dimensi ini menggunakan beberapa persamaan pembangun yaitu persamaan konservasi massa/ kontinuitas ,persamaan momentum, dan persamaan penggerak fluida .selain itu terdapat persamaan pendukung yaitu menggunakan persamaan transport. untuk persamaannya dijelaskan sebagai berikut : 

### Persamaan Momentum 
![image](https://user-images.githubusercontent.com/106175982/170150807-89f82897-7388-4b9e-8746-0253bb155ffc.png)

Persamaan momentum diturunkan dari Hukum Newton II. Hukum Newton II digunakan untuk menentukan percepatan yang dihasilkan dari gaya-gaya luar yang berpengaruh terhadap suatu massa; dalam hal kasus ini adalah massa air dalam volume kontrol.
persamaan momentum pada hidrodinamika 1 D digunakan Dengan asumsi bahwa gesekan angin dan gesekan dasar diabaikan serta friksi horizontal dianggap kecil atau diabaikan sehingga suku-suku ini dapat dihilangkan

### persamaan konservasi massa/ kontinuitas 
![image](https://user-images.githubusercontent.com/106175982/170151069-f37f2107-bfb3-44f7-86b0-e7d1dbee62e5.png)

Persamaan kontinuitas merupakan persamaan untuk menggambarkan perubahan massa dari fluida yang melewati suatu ruang yang tetap haruslah sama antara debit masukkan dan
keluarannya

### Persamaan pembangun (Penggerak fluida) 
![image](https://user-images.githubusercontent.com/106175982/170152517-6ce4de99-2b67-4caf-b99e-7eabe585dc87.png)
![image](https://user-images.githubusercontent.com/106175982/170152537-1c4faa77-4056-4a00-847c-9d571e27edd5.png)

### Persamaan transport 
![image](https://user-images.githubusercontent.com/106175982/170152597-76d8911f-b7d3-43b9-95b4-636fb0e620e0.png)
![image](https://user-images.githubusercontent.com/106175982/170152609-2b7f876a-da08-4697-8906-9adb571db3b3.png)
![image](https://user-images.githubusercontent.com/106175982/170152631-a00f8d58-9337-430d-8168-9a533409075e.png)

### Diskretisasi Model 
persamaan model hidrodinamika sederhana 1- D dapat di diskretisasikan secara eksplisit melalui metode beda hingga menjadi :

![image](https://user-images.githubusercontent.com/106175982/170154660-e7e197d1-2f06-42e7-ad11-12092e599737.png)

Deskritisasi numerik persamaan hidrodinamika 1 dimensi secara eksplisit tersebut diatas harus memenuhi kriteria stabilitas Courant-Freiderichs-Lewy (CFL) sebagai berikut 

![image](https://user-images.githubusercontent.com/106175982/170154722-08e441b8-30b9-447c-bae1-71ab1724419d.png)

### Solusi Numerik 
Penyelesaian secara numerik adalah cara pendekatan. sehingga kita hanya mendapatkan jawaban pendekatan persamaan differensial. Metode yang paling sering digunakan dalam model numerik untuk menyelesaikan masalah aliran dan angkutan sungai, muara, dan pantai adalah metode beda hingga karena perumusannya relatif mudah dan efisien, dan memberikan hasil yang memuaskan. Metode ini mengganti turunan-turunan dalam persamaan pembangun dengan pendekatan hingga.Solusi model akan didapat dengan memasukkan syarat batas dan syarat awal.

Penyelesaian Numerik yang di gunakan adalah seperti berikut : 

![image](https://user-images.githubusercontent.com/106175982/170155487-b56ce5ca-8258-4a9e-9c39-2e2b257e55b5.png)

sehingga diperoleh solusi analitik kecepatan adalah :

![image](https://user-images.githubusercontent.com/106175982/170155540-4e4331cf-b6e1-4bd7-9c9f-47e6465366f4.png)

Kedua solusi analitik tersebut diatas  akan digunakan sebagai nilai awal dan syarat batas numerik.

### Kelemahan Model Hidrodinamika 

1.memerlukan Banyak Data
2. Data rawan bocor 
3. memiliki waktu simulasi yang lama 

### Pengaplikasian Model Hidrodinamika 1 -D di bidang Hidro-oseanografi

1.	Dapat menentukan Perubahan Kecepatan Arus dalam ruang Tertentu di Sepanjang Waktu
2.	Perubahan Kecepatan Arus dalam Waktu Tertentu di Sepanjang ruang.
3.	Perubahan Elevasi Permukaan Air dalam ruang Tertentu di Sepanjang Waktu.
4.	Perubahan Elevasi Permukaan Air dalam Waktu Tertentu di Sepanjang Grid.


## **Penjelasan Coding**

### **Input Library**

![2022-05-24_093539](https://user-images.githubusercontent.com/106040998/169937453-4cb0cc42-4fde-4aac-8710-3eb123f72168.png)

Pada modul ini library yang digunakan yaitu matplotlib dan numpy
> Library Matplotlib merupakan library yang digunakan untuk menjalankan visualisasi data dan pustaka plot grafis untuk Python dan ekstensi numeriknya Numpy

> Library Numpy digunakan sebagai ekstensi untuk melakukan berbagai macam operasi matematika pada suatu array

### **Input Parameter**

![2022-05-24_094215](https://user-images.githubusercontent.com/106040998/169937924-ab936413-a85b-4fbd-9da2-3e6979bbfbec.png)

### **Pemodelan Hidrodinamika 1D**

![hidrodinamika](https://user-images.githubusercontent.com/106040998/170171959-ab4798ff-95fc-4f30-b7b1-07ac16ec8d95.png)

### **Pembuatan Grafik Perubahan Kecepatan Arus Dalam Grid Tertentu di Sepanjang Waktu**

![SATU](https://user-images.githubusercontent.com/106040998/170172147-5c94f8c1-c8bf-401f-a7e0-4c350d0a8f64.png)

### **Pembuatan Grafik Perubahan Elevasi Permukaan Air Dalam Grid Tertentu di Sepanjang Waktu**

![DUA](https://user-images.githubusercontent.com/106040998/170172258-7e57ec3f-0947-4915-af4c-cce71e27c553.png)

### **Pembuatan Grafik Perubahan Kecepatan Arus Dalam Waktu Tertentu di Sepanjang Grid**

![TIGA](https://user-images.githubusercontent.com/106040998/170172354-6065b240-8bab-4b40-af94-ce1d9baeac14.png)

### **Pembuatan Grafik Perubahan Elevasi Permukaan Air Dalam Waktu Tertentu di Sepanjang Grid**

![EMPAT](https://user-images.githubusercontent.com/106040998/170172438-2bd7a3be-b2ff-4192-b7f1-9d709fd21796.png)


## **Hasil**

![1 1](https://user-images.githubusercontent.com/106040998/169955243-4ab3e2f5-54a3-4c00-832f-9254afa806db.png)

![2 2](https://user-images.githubusercontent.com/106040998/169955270-dbb5f9e7-92e2-46ff-94de-207ee9b6bda0.png)

![3 3](https://user-images.githubusercontent.com/106040998/169955315-08f10ae4-406d-41c0-87d5-6e76a49ca600.png)

![4 4](https://user-images.githubusercontent.com/106040998/169955350-35d5eba3-6262-46a4-a309-ddb71f261989.png)


# **Modul 4 Hidrodinamika 2 Dimensi**
## **Materi**
Menurut Milasari _et al_. (2021), model hidrodinamika merupakan sistem model numerik umum untuk pemodelan permukaan air dan arus. Model hidrodinamika yang dikembangkan untuk mensimulasikan aliran 2D dalam satu layer fluida yang dianggap homogen secara vertikal. Terdapat dua persamaan pembangun yang mendukung model, antara lain :
> 1. Persamaan Kontinuitas

> ![image](https://user-images.githubusercontent.com/106028435/170100924-2d3a62a0-92b8-4703-bbe8-bffe51cd8b18.png)

> 2. Persamaan Momentum

> ![image](https://user-images.githubusercontent.com/106028435/170100762-6e1d2268-f062-4198-a862-f5851ad8a1c5.png)


Pengaplikasian hidrodinamika 2D pada bidang oseanografi diantaranya adalah :
* Pemodelan sampah plastik di laut.
* Pemodelan gelombang oleh angin.
* Pemodelan _coastal dynamics_ dan sedimentasi pantai. 
## **Penjelasan Coding**

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

## **Hasil**
> ![image](https://user-images.githubusercontent.com/105922284/169754981-ffc8c40c-abd2-4348-a2de-82d2e68add8e.png)

Berdasarkan Hasil yang didapat dapat disimpulkan bahwa terjadi korelasi antara parameter tekanan air, angin, dan suhu perairan. Angin dihasilkan oleh perbedaan tekanan dan suhu di atmosfer akibat distribusi energi radiasi matahari, tutupan awan serta dinamika disekitarnya. Angin menghantarkan kandungan panas terutama dengan proses adveksi massa air hangat ke daerah dingin dan sebaliknya (Aldrian, 2008). Ketika lautan mendingin, maka laut akan merespon dengan menghasilkan gerak konveksi vertikal yang akan mensuplai panas ke permukaan. Hal ini terjadi karena persamaan kontinuitas massa membutuhkan air dingin mengendap ke kedalaman dari permukaan tergantikan oleh massa air di bawahnya yang notabene lebih hangat. Air hangat tersebut akan menyembul ke permukaan. Proses perubahan suhu di lautan terjadi jauh lebih lambat daripada di atmosfer. Sebagai akibat maka lautan terus panas meskipun ekuinok atau titik nadir matahari telah menjauhi garis khatulistiwa.

# DAFTAR PUSTAKA
Milasari, A., D.H. Ismunarti, E. Indrayanti, F. Muldiyatno, A. Ismanto dan A. Rifai. 2021. Model Arus Permukaan Teluk 	Lampung pada Musim Peralihan II dengan Pendekatan Hidrodinamika. _Buletin Oseanografi Marina_. 10(3):259-268.

# PENUTUP

Demikian repositori ini kami buat untuk memenuhi Tugas Akhir Kelompok Praktikum Pemodelan Oseanografi 2022 Departemen Oseanografi Fakultas Perikanan dan Ilmu Kelautan. Kami selaku authors berharap dengan repositori ini dapat membantu pembaca dalam menyelesaikan permasalahan pada modul-modul yang telah kami jelaskan, mulai dari model adveksi-difusi hingga model hidrodinamika. Kami selaku authors memohon maaf yang sebesar-besarnya apabila terdapat kekurangan dan kesalahan pada repository ini. Authors juga mengucapkan terima kasih kepada :

1. Dr. Aris Ismanto, S.Si, M.Si. selaku dosen pengampu mata kuliah Metode Numerik
2. Rikha Widiaratih, S.Si, M.Si. selaku dosen pengampu mata kuliah Metode Numerik
3. Prof. Dr. Denny Nugroho Sugianto, S.T., M.Si. selaku dosen pengampu matakuliah Pemodelan Oseanografi.
4. Dr. Elis Indrayanti, S.T., M.Si. selaku dosen pengampu matakuliah Pemodelan Oseanografi.
5. Tim asisten Praktikum Pemodelan Oseanografi 2022 yang membimbing authors dalam pengerjaan tugas akhir ini
6. Seluruh mahasiswa Oseanografi 2020 yang turut mendukung tersusunnya repositori ini

Hormat Kami,
																			

Authors
