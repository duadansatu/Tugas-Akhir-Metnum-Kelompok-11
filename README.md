# Tugas-Akhir-Metnum-Kelompok-11
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Metode Numerik Oseanografi 2021. Repositori ini memuat executable (.exe) file yang dapat memproses beberapa persamaan metode numerik untuk penyelesaian perhitungan numerik. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Google Colaboratory dan Jupyter Notebook. Sedangkan untuk library yang digunakan kali ini adalah Numpy, Matplotlib, IPython, Scipy, Pprint, dan Math. Seluruh script yang dibuat adalah hasil kelompok 11 Oseanografi 2019. Semoga dapat bermanfaat!

# AUTHOR (KELOMPOK 11)
1. Rachel Maelisa Damanik 26050119120017 A
2. Siti Wulandari 26050119120016 B
3. Jane E.V. Siahaan 26050119120015 B
4. Riyanti Maharani Ilyas 26050119120014 B
5. Sephia Anggi Claudia 26050119120013 A
6. Sekar Adiningsih 26050119120012 A
7. Naela Marizka 26050119120011 A
8. Eka Salma Afifah Putri 26050119120010 B
9. Sativa Haliza Tiatama 26050119120008 B
10. Dara Sartika 26050119120007 B
11. Adella Eka Wardani 26050119120005 B

# Cara Penggunaan

# Metode Pengerjaan
1. Modul 2: Akar-akar Persamaan
2. Modul 3: Sistem Persamaan Linear dan Matrix
3. Modul 4: Integrasi Numerik
4. Modul 5: Persamaan Differensial Biasa

## Modul 4 : Sistem Persamaan Linear dan Matrix
* ##### Metode Gauss
Metode eliminasi Gauss adalah suatu cara mengoperasikan nilai-nilai di dalam matriks menjadi matriks yang lebih sederhana dan banyak digunakan dalam penyelesaian sistem persamaan linier. Prosedur penyelesaian dari metode ini adalah dengan melakukan operasi baris menjadi matriks eselon-baris. Metode ini mengubah persamaan linear tersebut ke dalam matriks augmentasi dan mengoperasikannya. Metode eliminasi gauss termasuk dalam metode penyelesaian persamaan linear dengan cara langsung. Inti dari metode ini adalah membawa persamaan kedalam bentuk matriks dan menyederhanakan matriks menjadi bentuk segitiga atas. Setelah mendapat bentuk matriks tersebut dilakukan subtitusi balik untuk mendapat nilai dari akar persamaan tadi. 

* ##### Metode Gauss - Jordan
Metode eliminasi Gauss-Jordan adalah pengembangan dari eliminasi Gauss yang hasilnya lebih sederhana lagi. Caranya adalah dengan meneruskan operasi baris dari eliminasi Gauss sehingga menghasilkan matriks yang Eselon-baris. Ini juga dapat digunakan sebagai salah satu metode penyelesaian persamaan linear dengan menggunakan matriks. Metode ini digunakan untuk mencari invers dari sebuah matriks. Prosedur umum untuk metode eliminasi Gauss-Jordan ini adalah:
1. Ubah sistem persamaan linier yang ingin dihitung menjadi matriks augmentasi.
2. Lakukan operasi baris elementer pada matriks augmentasi (A|b) untuk mengubah matriks A menjadi dalam bentuk baris eselon yang tereduksi

* ##### Metode Gauss - Seidel
Metode iterasi Gauss-Seidel adalah metode yang menggunakan proses iterasi hingga diperoleh nilai-nilai yang berubah-ubah dan akhirnya relatif konstan. Metode iterasi Gauss Seidel dikembangkan dari gagasan metode iterasi pada solusi persamaan tak linier. Metode eliminasi gauss-seidel digunakan untuk menyelesaikan SPL yang berukuran kecil karena metode ini lebih efisien. Dengan metode iterasi Gauss-Seidel toleransi pembulatan dapat diperkecil karena iterasi dapat diteruskan sampai seteliti mungkin sesuai dengan batas toleransi yang diinginkan. Kelemahan dari metode ini adalah masalah pivot (titik tengah) yang harus benar–benar diperhatikan, karena penyusunan yang salah akan menyebabkan iterasi menjadi divergen dan tidak diperoleh hasil yang benar.

* ##### Metode Jacobi
Metode iterasi Jacobi ini digunakan untuk menyelesaikan persamaan linier yang proporsi koefisien nol nya besar. Metode ini ditemukan oleh matematikawan yang berasal dari Jerman, Carl Gustav Jakob Jacobi. Penemuan ini diperkirakan pada tahun 1800-an. Iterasi dapat diartikan sebagai suatu proses atau metode yang digunakan secara berulang-ulang (pengulangan) dalam menyelesaikan suatu permasalahan matematika. 

## Modul 4 : Integrasi Numerik
### Metode Trapesium Satu Pias

```
def trapesium_1pias():
        #Pemberi Keterangan
        print(" =========================================================\n",
              "Modul 4 Integrasi Numerik: Trapesium 1 Pias \n",
              "KELOMPOK 11 \n",
              "OSEANOGRAFI 2019 \n",
              "PRAKTIKUM METODE NUMERIK 2021 \n",
              "=========================================================\n")
        #Pendefinisian funsgi
        x = np.linspace(-10,10,100)
        y = 3*(x**3)+3*(x**2)
        plt.plot(x,y)
        
        #Pemberian nilai
        x1 = 0
        x2 = 1
        
        #Pendefenisian Fungsi
        fx1 = 3*x1**3
        fx2 = 3*x2**2
        
        #Untuk pembuatan grafik
        plt.fill_between([x1,x2], [fx1,fx2])
        plt.xlim([-1.5,1.5]); plt.ylim([0,4]);
        plt.title('Trapesium 1 pias')
        plt.savefig('C:/TA Metnum/Images/Trapesium 1 Pias.png')
        L = 0.5*(fx2 + fx1)*(x2 - x1)
        
        #Perintah output hasil grafik
        print("Luas dengan metode trapesium 1 pias:", L)
```
### Metode Trapesium Banyak Pias
```
# PERSAMAAN 2X^3+4X^2+10

#Pendegenisian Fungsi
def trapesium_banyakpias(f,a,b,N):
        x = np.linspace(a,b,N+1)
        y = f(x)
        y_kanan = y[1:] 
        y_kiri = y[:-1] #diberikan + - agar garis pada grafik jalan, tidak stuck di satu titik
        dx = (b - a)/N
        T = (dx/2) * np.sum(y_kanan + y_kiri)
        return T
    
    #Definisi x
    f = lambda x : 2*x**3 + 4*x**2 + 10
    
    #Pemberian nilai pada a, b, N
    a = 0
    b = 10
    N = 10
    
    #Pengatur Nilai dan Trapesium secara Vertikal dan Horizontal
    x = np.linspace(a,b,N+1)
    y = f(x)
    X = np.linspace(a,b+1,N)
    Y = f(X)
```
### Metode Simspson 1/3
```
#Pendefinisian fungsi
def simpson1per3(x0,xn,n):
        f = lambda x: 2*x**3 + 4*x**2 + 10
        h = (xn - x0) / n
        integral = f(x0) + f(xn)
        for i in range(1,n): #Pemberian interval
            k = x0 + i*h
            if i%2 == 0:
                integral = integral + 2 * f(k)
            else:
                integral = integral + 4 * f(k)
        integral = integral * h / 3
        return integral
```
## Modul 5 : Persamaan Diferensial Biasa
### Metode Heun
Metode Heun merupakan salah satu peningkatan dari Metode Euler. Modifikasi dilakukan dengan memperkirakan kemiringan. Metode Heun merupakan perbaikan dari Metode Euler untuk meningkatkan efisiensi sehingga dapat menyelesaikan persamaan diferensial biasa dengan kondisi awal dengan mengasumsikan kemiringan tangen sebagai rata-rata dari rata-rata aritmatika dan rata-rata kontra-harmonik. Metode Heun mempunyai ketelitian yang rendah karena memiliki nilai error yang besar (sebanding dengan h). Nilai error dapat dikurangi dengan menggunakan Metode Heun yang merupakan perbaikan dari Metode Euler. Metode ini melibatkan 2 buah persamaan. Persamaan pertama disebut sebagai persamaan prediktor yang digunakan untuk memprediksi nilai integrasi awal. Persamaan kedua disebut sebagai persamaan korektor yang mengoreksi hasil integrasi awal. Pada Metode Heun, solusi Metode Euler dijadikan solusi perkiraan awal (predictor). Selanjutnya, solusi perkiraan awal ini diperbaiki dengan Metode Heun (corrector).

Kita dapat membangun sebuah fungsi yang dapat melakukan proses integrasi menggunakan Metode Heun. Berikut adalah algoritma yang digunakan:
```
def heun():
        Nama = (input("Masukkan Nama: "))
        Nim = (input("Masukkan NIM: "))
        Kelas = (input("Masukkan Kelas: "))
        plt.style.use('seaborn-poster')
        ipy = get_ipython()
        if ipy is not None:
            ipy.run_line_magic('matplotlib', 'inline')
            
  #Proses pendefinisian parameter dan fungsi
        h = float(input("Masukkan nilai h: ")) #Banyak langkah yang akan digunakan 
        x0 = float(input("Masukkan nilai x awal: ")) #Masukkan kondisi awal 0
        xn = float(input("Masukkan nilai x akhir: ")) #Untuk x akhir ketentuan 2 nim akhir dibalik 
        x = np.arange(x0, xn + h, h) #Grid
        y0 = float(input("Masukkan nilai y awal: ")) #Masukkan kondisi awal 0
        G = (2*(x**3)+9*(x**2)+2*(x)+20) #Fungsi
        f = lambda x, y: 2*(x**3)+9*(x**2)+2*(x)+20 #Persamaan Diferensial Biasa
        y = np.zeros(len(x))
        y[0] = y0

  #Persamaan Metode Heun
        for i in range(0, len(x) - 1):
            k1 = f(x[i], y[i]) #Persamaan Prediktor
            k2 = f((x[i] + h), (y[i] + (h*k1))) #Persamaan Korektor
            y[i+1] = y[i] + (0.5 * h * (k1 + k2)) #Persamaan Metode Heun
        print(y)
        
    #Menghitung Error
        error = G-y
        print(error)
        judul = ("\n Grafik Pendekatan Persamaan Differensial Biasa Dengan Metode Heun \n\n %s_%s_%s \n" % (Nama,Nim,Kelas))
        plt.figure(figsize = (12, 10))
        plt.plot(x, y, 'b--', color='r', label='Hasil Pendekatan')
        plt.plot(x, G, '-g', color='y', label='Hasil Analitik')
        plt.title(judul) #Judul Plot
        plt.xlabel('x') #Label u/ sumbu x
        plt.ylabel('F(x)') #Label u/ sumbu y
        plt.grid() #u/ menampilkan grid
        plt.legend(loc='lower right')
    #Hasil Grafik yang didapat:
        plt.savefig('image\heun.png')
```
![image](https://user-images.githubusercontent.com/85225313/120581960-e0efac80-c455-11eb-9c46-7b475e47cfb3.png)

Berdasarkan hasil visualisasi dapat dilihat bahwa Metode Heun dapat dengan baik memberikan pendekatan nilai integrasi persamaan. Pembaca dapat mencoba untuk melakukan simulasi kembali dengan nilai h yang lebih kecil. Selain itu juga terdapat beberapa proses yang diubah. Seperti pada library dan pada proses penampilan grafik. Hal tersebut dikarenakan supaya gambar grafik untuk Metode Heun dan Metode Euler bisa langsung tersimpan di directory file perangkat yg kita gunakan.


# Saran Pengembangan
1. Lebih dikreasiin lagi untuk tipe-tipe pembuatan grafik
