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

> Matplotlib = _pip install matplotlib_

> Numpy = _pip install numpy_

> sys = _pip install os-sys_

> Siphon = _pip install siphon_

# **Modul 1 Adveksi Difusi 1 Dimensi**
### **Materi**

### **Hasil**

# **Modul 2 Adveksi Difusi 2 Dimensi**
### **Materi**


### **Penjelasan Coding**

```
import matplotlib.pyplot as plt
import numpy as np
import sys

def percentage(part, whole):
    percentage = 100 * float(part)/float(whole)
    return str(round(percentage,2)) + "x"

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

#Lama Simulasi
Tend = 1
#Tend = 0,5
dt = 0.5

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

#pembuatan grid 
x_grid = np.linspace(0-dx, x+dx, Nx+2) #ghostnode boundary
y_grid = np.linspace(0-dx, y+dy, Ny+2) #ghostnode boundary
t = np.linspace(0, Tend, Nt+1)
x_mesh, y_mesh = np.meshgrid(x_grid,y_grid)
F = np.zeros((Nt+1, Ny+2, Nx+2))

#kondisi awal
F[0,py1,px1]=Ic
#%%

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
    plt.title('NAMA_NIM \n t='+str(round(dt*(n+1),3))+ ', Initial condition='+str(Ic),fontsize=10)
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
