# Tugas Akhir Praktikum Metode Numerik Kelompok 11🌊
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Metode Numerik Oseanografi 2021. Repositori ini memuat *executable* (.exe) file yang dapat memproses beberapa persamaan metode numerik untuk penyelesaian perhitungan numerik. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti *Google Colaboratory* dan *Jupyter Notebook*. Sedangkan untuk library yang digunakan kali ini adalah *Numpy, Matplotlib, IPython, Scipy,* dan *Pprint*. Seluruh script yang dibuat adalah hasil kelompok 11 Oseanografi 2019. Semoga dapat bermanfaat!

## 1. AUTHORS (KELOMPOK 11):two_women_holding_hands:
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

## 2. Cara Penggunaan *Executable File* (.exe):computer:
Perlu diperhatikan bahwa file (.exe) ini berkaitan dengan *directory file* dalam penggunaannya, maka terdapat beberapa bagian script yang harus disesuaikan. Berikut adalah langkah dalam menggunakan file (.exe):
1. Pengguna dapat mengunduh folder **Kelompok 11** pada repositori ini.
2. Buka file **codemetnum11.py** pada folder **code**.
![2 0](https://user-images.githubusercontent.com/85191303/120666395-c0a40a00-c4b6-11eb-849a-eda965a748bc.png)
4. Pada bagian **Modul 4: Metode Trapesium 1 Pias**, ubah *directory file* sesuai dengan lokasi *directory file* folder image anda.
![2](https://user-images.githubusercontent.com/85191303/120666849-20021a00-c4b7-11eb-8e29-50107166713e.png)
Hal yang sama juga dilakukan pada **Modul 4: Metode Trapesium Banyak Pias** dan **Modul 5: Metode Euler dan Heun**. 
5. Sesuaikan akhiran *directory file* dengan metode yang digunakan. 
```
plt.savefig(r'C:\Users\asus\Documents\KULIAH\Sem 4\METNUM\Kelompok 11\image\**NamaMetode**.png')
```
6. Kemudian *save* file **codemetnum11.py**.
6. Buka file **setup.exe**.
![1](https://user-images.githubusercontent.com/85191303/120664873-7f5f2a80-c4b5-11eb-9798-a1b6432cc535.png)
7. Lalu ikuti perintah yang terdapat pada program. 

## 3. Metode Pengerjaan
1. Modul 2: Akar-akar Persamaan
2. Modul 3: Sistem Persamaan Linear dan Matrix
3. Modul 4: Integrasi Numerik
4. Modul 5: Persamaan Differensial Biasa

### 🏷️3.1. Modul 2 : Akar-akar Persamaan
* #### Metode Setengah Interval
Metode Setengah Interval merupakan suatu metode bagi dua dimana akar penyelesaian metode ini adalah jumlah interval batas bawah dengan interval batas atas bagi 2. Metode ini merupakan bentuk paling sederhana diantara beberapa metode lainnya. Kelebihan dari metode ini adalah selalu berhasil dalam menentukan akar-akar (solusi) yang dicari atau dengan kata lain selalu konvergen. Untuk melakukan perhitungan dengan metode ini maka hitung fungsu pada interval yang sama dai x sampai pada tanda fungsi f(Xi) dan (fXi+1), yaitu apabila f(Xi)× (fXi+1)<0. Perkirakan pertama dari akar Xt dan dihitung rerata nilai Xi dan Xi+1 , ytiu Xt = (Xi + Xi+1)/2. Lalu buat evaluasi dimana apabila f(Xi)× (fXi+1)<0, akar persamaan berada pada sub interval pertama dimana Xt=Xi+1 , apabila f(Xi)× (fXi+1)>0, maka akar persamaan pada sub bab interval kedua dimana Xt=Xi, dan apabila f(Xi)× (fXi+1)=0 maka akar persamaan adalah Xt dan perhitungan selesai. Apabila ternyata nilai yang diperoleh f(Xi)× (fXi+1)<0 dan f(Xi)× (fXi+1)>0, maka hitung perkiraan baru Xt = (Xi + Xi+1)/2. Jika perkiraan baru ternyata sudah kecil atau sesuai batasan yang ditentukan,maka hitungan selesai dan Xt adalah akar persamaan yang dicari. Proses iterasi berhenti jika toleransi kesalahan yang diberikan dalam soal sudah terpenuhi dan setelah menjalankan jumlah tertentu dari iterasi dan jumlahnya sudah ditentukan dalam soal yang diberikan.

```
def metnum_modul2():
    def setengah_interval (X1,X2):
        print(" =========================================================\n",
             "Modul 2 Akar-Akar Persamaan: Metode Setengah Interval\n",
             "KELOMPOK 11 \n",
             "OSEANOGRAFI 2019 \n",
             "PRAKTIKUM METODE NUMERIK 2021 \n",
             "=========================================================\n")
        X1 = X1
        X2 = X2
        error = 1
        iterasi = 0
        while(error > 0.0001):
            iterasi +=1
            FXi = (float(-0.0371*(X1**3)))+(float(1.5072*(X1**2)))-(9.9433*X1)+(-14.997)
            FXii = (float(-0.0371*(X2**3)))+(float(1.5072*(X2**2)))-(9.9433*X2)+(-14.997)
            Xt = (X1 + X2)/2
            FXt = (float(-0.0371*(Xt**3)))+(float(1.5072*(Xt**2)))-(9.9433*Xt)+(-14.997)
            if FXi * FXt > 0:
                X1 = Xt
            elif FXi * FXt < 0:
                X2 = Xt
            else:
                print("Akar Penyelesaian: ", Xt) 
            if FXt < 0:
                error = FXt * (-1)
            else:
                error = FXt
            if iterasi > 100:
                print("Angka tak hingga")
                break
            print(iterasi, "|", FXi, "|", FXii, "|", Xt, "|", FXt, "|", error)
        print("Jumlah Iterasi: ", iterasi)
        print("Akar persamaan adalah: ", Xt)
        print("Toleransi Error: ", error)
 ```
 
* #### Metode Interpolasi Linier
Metode Interpolasi Linier atau dikenal *false position* merupakan metode dimana didasarkan pada interpolasi antara dua nilai dari fungsi yang mempunyai tanda berlawanan. Metode Interpolasi Linier merupakan penyempurna dari metode setnegah interval sehingga hampir mirip dimana diperlukan dua harga taksiran awal pada awal pengurungan akar persamaan. Perbedaan kedua metode tersebut terletak pada proses pencarian pendekatan akar persamaan selanjutnya setelah pendekatan akar saat ini ditemukan Prinsip pencarian akar persamaan dari metode ini didasarkan pada penggunaan interpolasi linier. Interpolasi linier dilakukan melalui dua titik pertama dengan garis interpolasi memotong sumbu x dan dititik perpotongan tersebut didapatkan pendekatan akar yang pertama.
Kemudian pendekatan tersebut dievaluasi pada fungsi nonlinier sehingga diperoleh titik pada fungsi nonlinier tersebut. Kemudian dilakukan lagi interpolasi melalui ujung sebelumnya diperoleh pendekatan akar berikutnya. Demikian seterusnya, hingga diperoleh hargapendekatan akar yang sudah sangat dekat dengan akar persamaan eksaknya.

```

def interpolasi_linier(X1):
            print(" =========================================================\n",
                  "Modul 2 Akar-Akar Persamaan: Metode Interpolasi Linier \n",
                  "KELOMPOK 11 \n",
                  "OSEANOGRAFI 2019 \n",
                  "PRAKTIKUM METODE NUMERIK 2021 \n",
                  "=========================================================\n")
            X1 = X1
            X2 = X1 + 1
            error = 1
            iterasi = 0
            while(error > 0.0001):
                iterasi +=1
                FX1 = (float(-0.0371*(X1**3)))+(float(1.5072*(X1**2)))-(9.9433*X1)+(-14.997)
                FX2 = (float(-0.0371*(X2**3)))+(float(1.5072*(X2**2)))-(9.9433*X2)+(-14.997)
                Xt = X2 - ((FX2/(FX2-FX1)))*(X2-X1)
                FXt = (float(-0.0371*(Xt**3)))+(float(1.5072*(Xt**2)))-(9.9433*Xt)+(-14.997)
                if FXt*FX1 > 0:
                    X2 = Xt
                    FX2 = FXt
                else:
                    X1 = Xt
                    FX1 = FXt 
                if FXt < 0:
                    error = FXt * (-1)
                else:
                    error = FXt
                if iterasi > 500:
                    print("Angka tak hingga")
                    break
                print(iterasi, "|", FX1, "|", FX2, "|", Xt, "|", FXt, "|", error)
            print("Jumlah Iterasi: ", iterasi)
            print("Akar persamaan adalah: ", Xt)
            print("Toleransi Error: ", error)
            
 ```
 
* #### Metode Newton Rapson
Metode Newton Rapson adalah metode pencarian akar yang sederhana dan handal dalam mendapatkan akar persamaan _non-linier_. Prosedur penyelesaian persamaan ini adalah dengan mengurangi persamaan terhadap pembagian turunan persamaan. Metode ini cukup dengan memberikan satu terkaan awal saja. Terdapat syarat yang harus dipenuhi yaitu nilai taksiran awal yang diberikan harus sedekat mungkin dengan harga eksaknya.

```
def newton_rapson(X1): #pendefinisian metode Newton Rapson
    X1 = X1
    iterasi = 0
    akar = 1
    
    while (akar > 0.0001): #looping metode Newton Rapson
        iterasi += 1
        Fxn = (float(-0.0371*(X1**3)))+(float(1.5072*(X1**2)))-(9.9433*X1)+(-14.997)
        Fxxn = (float(-0.0371*3*(X1**2)))+(float(1.5072*2*X1))-(9.9433)
        xnp1 = X1 - (Fxn/Fxxn)
        fxnp1 = (xnp1**3)+(xnp1**2)-(3*xnp1)-3
        Ea = ((xnp1-X1)/xnp1)*100
        if Ea < 0.0001: #kondisi metode newton rapson
            X1 = xnp1
            akar = Ea*(-1)
        else:
            akar = xnp1
            print("Nilai akar adalah: ", akar)
            print("Nilai error adalah: ", Ea)
        if iterasi > 1000:
            break
        print(iterasi, "|", X1, "|", xnp1, "|", akar, "|", Ea) 
    print("Jumlah Iterasi: ", iterasi) #perintah untuk print 
    print("Akar persamaan adalah: ", xnp1)
    print("Toleransi Error: ", akar)
```

* #### Metode Secant
Metode Secant ini pada dasarnya sama dengan metode Newton Raphson, namun berbeda pada pendekatan untuk turunan dari f saja. Metode secant bertujuan untuk menyelesaikan masalah yang terdapat pada metode Newton-Raphson yang terkadang sulit digunakan untuk mendapatkan turunan pertama. Metode Secant merupakan perbaikan dari metode regula-falsi dan Newton-Raphson dimana kemiringan dua titik dinyatakan secara diskrit, dengan mengambil bentuk garis lurus yang melalui satu titik. Metode secant memerlukan 2 tebakan awal yang tidak harus mengurung/mengapit akar. Iterasi berlangsung sampai batas maksimum atau sampai batas toleransi terpenuhi.

```
def Metode_Secant(X1): #Pendefinisian
    X1 = X1
    X2 = X1 - 1
    error = 1
    iterasi = 0
    while(error > 0.0001): #Looping
        iterasi +=1:
        FX1 = -9772.8*(X1**3)+7055.2*(X1**2)-1102.2*(X1)+10.639
        FXmin = -9772.8*(X2**3)+ 7055.2*(X2**2)- 1102.2*(X2)+10.639
        X3 = X1 - ((FX1)*(X1-(X2)))/((FX1)-(FXmin))
        FXplus = -9772.8*(X3**3)+ 7055.2*(X3**2)- 1102.2*(X3)+10.639
        if FXplus < 0:
            error = FXplus * (-1)
        else:
            error = FXplus
        if error > 0.0001:
            X2 = X1
            X1 = X3
        else:
            print("Selesai")
        if iterasi > 100:
            print("Angka tak hingga")
        break
        print(iterasi, "|", FX1, "|", FXmin, "|", X3, "|", FXplus, "|", error)
    print("Jumlah Iterasi: ", iterasi)
    print("Akar persamaan adalah: ", X3)
    print("Toleransi Error: ", error)
```

* #### Metode Iterasi
Metode Iterasi merupakan metode yang berbasiskan langkah-langkah/algoritma sederhana yang diulang-ulang pada sistem persamaan tersebut hingga sistem persamaan mencapai keadaan konvergen yang merepresentasikan solusi dari sistem persamaan tersebut. Kelebihan dari metode ini ialah memori komputer yang digunakan sedikit. Namun, kelemahannya banyaknya langkah-langkah perhitungan yang dilakukan tidak dapat diprediksi sistem persamaan tidak berada pada kondisi yang kondusif, maka konvergensi dari suatu sistem persamaan tidak dapat terjamin.

```
def iterasi(X1): #pendefinisian
    X1 = X1
    error = 1
    iterasi = 0
    while (error > 0.0001): #kondisi dan looping
        iterasi +=1
        Fxn = -0.0371*(X1**3)+(1.5072*(X1**2))-9.9433*(X1)-14.997
        X2 = (((1.5072*(X1**2))-(-9.9433*(X1))-14.997)/-0.0371)**(1/3)
        Ea = (((X2-X1)/(X2))*100)
        if Ea < error:
            X1 = X2
            if Ea > 0:
                error = Ea
            else:
                error = Ea*(-1)
        else:
            error = Ea
            
        if iterasi > 100: #memeriksa konvergensi
            print("Angka tak hingga")
            break
        print(iterasi, "|", X1, "|", X2, "|", Ea, "|", error) 
    print("Jumlah Iterasi: ", iterasi) #peintah untuk print
    print("Akar persamaan adalah: ", X2)
    print("Toleransi Error: ", error)
```

### 🏷️3.2. Modul 3 : Sistem Persamaan Linear dan Matriks
* #### Metode Gauss
Metode eliminasi Gauss adalah suatu cara mengoperasikan nilai-nilai di dalam matriks menjadi matriks yang lebih sederhana dan banyak digunakan dalam penyelesaian sistem persamaan linier. Prosedur penyelesaian dari metode ini adalah dengan melakukan operasi baris menjadi matriks eselon-baris. Metode ini mengubah persamaan linear tersebut ke dalam matriks augmentasi dan mengoperasikannya. Metode eliminasi gauss termasuk dalam metode penyelesaian persamaan linear dengan cara langsung. Inti dari metode ini adalah membawa persamaan kedalam bentuk matriks dan menyederhanakan matriks menjadi bentuk segitiga atas. Setelah mendapat bentuk matriks tersebut dilakukan subtitusi balik untuk mendapat nilai dari akar persamaan tadi. 

Contoh persamaan untuk metode Gauss:
* 11x1 + 5x2 + 2x3 + 7x4 = -2.328
* 2x1 + 11x2 + 5x3 + 3x4 = 1.672
* 4x1 + 6x2 + 11x3 + 2x4 = 9.005
* 2x1 + 8x2 + 4x3 + 11x4 = 7.338

Pendefenisian metode Gauss
```
def Gauss(A, f):
    A = np.array((A), dtype=float)
    f = np.array((f), dtype=float)
    n = len(f)
```
Looping dan kondisi pada matrix
```
for i in range(0, n - 1):  
    if np.abs(A[i, i]) == 0:
         for k in range(i + 1, n):
            if np.abs(A[k, i]) > np.abs(A[i, i]):
```
Tukar antara baris i dan k
```
 A[[i, k]] = A[[k, i]]
 f[[i, k]] = f[[k, i]]
 ```
Pengulangan baris yang ada di bawah diagonal untuk setiap kolom
```
for j in range(i + 1, n):
    m = A[j, i] / A[i, i]
    A[j, :] = A[j, :] - m * A[i, :]
    f[j] = f[j] - m * f[i]
```
Perintah untuk print hasil metode Gauss
```
return A, f
```

* #### Metode Gauss - Jordan
Metode eliminasi Gauss-Jordan adalah pengembangan dari eliminasi Gauss yang hasilnya lebih sederhana lagi. Caranya adalah dengan meneruskan operasi baris dari eliminasi Gauss sehingga menghasilkan matriks yang Eselon-baris. Ini juga dapat digunakan sebagai salah satu metode penyelesaian persamaan linear dengan menggunakan matriks. Metode ini digunakan untuk mencari invers dari sebuah matriks. Prosedur umum untuk metode eliminasi Gauss-Jordan ini adalah:
1. Ubah sistem persamaan linier yang ingin dihitung menjadi matriks augmentasi.
2. Lakukan operasi baris elementer pada matriks augmentasi (A|b) untuk mengubah matriks A menjadi dalam bentuk baris eselon yang tereduksi

Contoh persamaan untuk metode Gauss - Jordan: 
* 2x1 + 5x2 + 3x3 + 4x4 = 4.067
* 2x1 + 7x2 + 5x3 + 3x4 = 3.067
* 4x1 + 8x2 + 2x3 + 8x4 = 4.067
* 5x1 + 9x2 + 6x3 + 4x4 = 6.067

Pendefenisian Gauss-Jordan
```
def GaussJordan(a,n):
```
Looping untuk pengolahan metode Gauss Jordan
```
print('=============Mulai Iterasi===============')
for i in range(n):
    if a[i][i]==0:
        sys.exit('Dibagi dengan angka nol (proses tidak dapat dilanjutkan)')
    for j in range(n):
        if i !=j:
            ratio=a[j][i]/a[i][i]
            for k in range(n+1):
                a[j,k]=a[j][k]-ratio*a[i][k]
            print(a)
            print(f'============================================')
```
Membuat semua variabel
```
ax=np.zeros((n,n+1))
for i in range(n):
    for j in range(n+1):
        ax[i,j]=a[i][j]/a[i][i]
print('===================Akhir Iterasi===================')
```
Perintah untuk print hasil metode Gauss-Jordan
```
return ax
```

* #### Metode Gauss - Seidel
Metode iterasi Gauss-Seidel adalah metode yang menggunakan proses iterasi hingga diperoleh nilai-nilai yang berubah-ubah dan akhirnya relatif konstan. Metode iterasi Gauss Seidel dikembangkan dari gagasan metode iterasi pada solusi persamaan tak linier. Metode eliminasi gauss-seidel digunakan untuk menyelesaikan SPL yang berukuran kecil karena metode ini lebih efisien. Dengan metode iterasi Gauss-Seidel toleransi pembulatan dapat diperkecil karena iterasi dapat diteruskan sampai seteliti mungkin sesuai dengan batas toleransi yang diinginkan. Kelemahan dari metode ini adalah masalah pivot (titik tengah) yang harus benar–benar diperhatikan, karena penyusunan yang salah akan menyebabkan iterasi menjadi divergen dan tidak diperoleh hasil yang benar.

Contoh persamaan untuk metode Gauss - Seidel:
* 4x1 + 6x2 + 2x3 + 8x4 = 8.063
* 2x1 + 4x2 + 3x3 + 6x4 = 9.063
* 5x1 + 9x2 + 6x3 + 4x4 = 6.063
* 2x1 + 5x2 + 4x3 + 3x4 = 4.063

Pendefenisian metode Gauss Seidel
```
def GaussSeidel(A,B,x,n):
    L= np.tril(A)
    U=A-L
```
Looping pada perhitungan
```
for i in range(n):
            x = np.dot(np.linalg.inv(L), B-np.dot(U, x))
            print(x)
```
Perintah untuk print hasil metode Gauss-Seidel
```
return x
```
* #### Metode Jacobi
Metode iterasi Jacobi ini digunakan untuk menyelesaikan persamaan linier yang proporsi koefisien nol nya besar. Metode ini ditemukan oleh matematikawan yang berasal dari Jerman, Carl Gustav Jakob Jacobi. Penemuan ini diperkirakan pada tahun 1800-an. Iterasi dapat diartikan sebagai suatu proses atau metode yang digunakan secara berulang-ulang (pengulangan) dalam menyelesaikan suatu permasalahan matematika. 
Contoh persamaan untuk metode Jacobi:
* 2x1 + 6x2 + 5x3 + 3x4 = 5.135
* 2x1 + 5x2 + 3x3 + 6x4 = 6.135
* 1x1 + 5x2 + 4x3 + 2x4 = 2.135
* 3x1 + 9x2 + 2x3 + 5x4 = 1.802

Pendefenisian metode Jacobi
```
 def Jacobi(A,b, N=10, x=None, info=True):
     print("Hasil perhitungan : ")
```
Kondisi pada perhitungan metode Jacobi
```
if x is None:
   x = zeros(len(A[0]))
D = diag(A)
R = A - diagflat(D)
```
Looping Metode Jacobi
```
for i in range(N):
    x = (b - dot(R,x))/D
    if info:
         pprint(x)
```
Perintah untuk print hasil metode Gauss-Seidel
```
return x
```

### :label: 3.3. Modul 4 : Integrasi Numerik
Metode Integrasi Numerik merupakan integrasi tertentu yang didasarkan pada hitungan perkiraan dengan mendekatinya melalui fungsi polinomial dengan data yang tersedia.


* #### Metode Trapesium Satu Pias
Metode Integrasi Trapesium merupakan salah satu metode integrasi numerik untuk menghitung luasan kurva f(x) dengan batasan tertentu yang didekati dengan sebagai luasan trapesium. Metode Trapesium Satu Pias digunakan apabila terdapat dua data f (a) dan f (b).

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
* #### Metode Trapesium Banyak Pias
Metode Trapesium Banyak Pias merupakan modifikasi dari metode trapesium satu pias. Modifikasi dilakukan dengan memperbanyak pias yang digunakan, yang artinya memperbanyak jumlah trapesium yang digunakan, hal ini bertujuan untuk mengestimasi luas daerah yang ingin dicari. Metode Trapesium Banyak Pias ini digunakan jika tersedia lebih dari dua data yang dapat dilakukan dengan lebih dari satu trapesium.

```
# PERSAMAAN 2X^3+4X^2+10

#Pendefenisian Fungsi
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

Metode Trapesium dengan Banyak Pias menghasilkan estimasi atau keakurasian perhitungan yang lebih baik, dibandingkan dengan Metode Trapesium Satu Pias. Karena memiliki nilai errror yang lebih kecil.

* #### Metode Simspson 1/3
Metode simpson 1/3 adalah metode yang mencocokkan polinomial derajat2 pada tiga titik data diskrit yang mempunyai jarak yang sama. Hampiran nilaiintegrasi yang lebih baik dapat ditingkatkan dengan menggunakan polinominterpolasi berderajat yang lebih tinggi.

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
* #### Metode Simspson 3/8
Metode Simspson 3/8 merupakan metode yang sama halnya dengan metode Simpson 1/3, hampiran nilai integrasi yanglebih teliti dapat ditingkatkan terus dengan mengunakan polinom interpolasi berderajat lebih tinggi pula. Misalkan sekarang fungsi f(x) hampiri dengan polinom interpolasi derajat 3. 

Keakurasin Metode Simspson 3/8 lebih teliti dari Metode Simspson 1/3, hal ini dikarenakan Metode Simspson 3/8 memiliki polinomial interpolasi berderajat yang lebih tinggi pula.

Untuk Keakurasian Metode Trapesium dan Metode Simspson, Metode Simspson jauh lebih teliti dan lebih baik, hal ini dikarenakan galatnya lebih tinggi.
```
#Pendefenisian fungsi
def simpson3per8(x0,xn,n):
        #Memberi keterangan
        print(" =========================================================\n",
              "Modul 4 Integrasi Numerik: Simpson 3/8 \n",
              "KELOMPOK 11 \n",
              "OSEANOGRAFI 2019 \n",
              "PRAKTIKUM METODE NUMERIK 2021 \n",
              "=========================================================\n")
        f = lambda x: 3*(x**3)+3*(x**2)
        h = (xn - x0) / n
        integral = f(x0) + f(xn)
        
        #untuk pengulangan
        for i in range(1,n):
            k = x0 + i*h
            if i%2 == 0:
                integral = integral + 3 * f(k)
            else:
                integral = integral + 3 * f(k)
        integral = integral * 3 * h / 8
        return integral
    
    #Perintah Output (Penyelesaian integral numerik)
    print("Kode untuk penyelesaian integrasi numerik: \n",
         "1. Metode Trapesium 1 Pias \n",
         "2. Metode Trapesium Banyak Pias \n",
         "3. Metode Simpson 1/3 \n",
         "4. Metode Simpson 3/8 \n")
    setting = int(input("Masukkan kode penyelesaian integrasi numerik: "))
    
    #Bagian untuk menginput angka 1 (Pemanggilan Fungsi Trapesium Satu Pias)
    if (setting == 1):
        Cel = trapesium_1pias()
    
    #Jika Input angka 2 maka Output Trapesium banyak pias (Pemanggilan Fungsi Trapesium Banyak Pias)
    elif (setting == 2):
        #Pemberi keterangan
        print(" =========================================================\n",
              "Modul 4 Integrasi Numerik: Trapesium Banyak Pias \n",
              "KELOMPOK 11 \n",
              "OSEANOGRAFI 2019 \n",
              "PRAKTIKUM METODE NUMERIK 2021 \n",
              "=========================================================\n")
        plt.plot(X,Y)
        
        #Pengulangan N dan Settingan untuk grafik serta perintah Output grafik
        for i in range(N):
            xs = [x[i],x[i],x[i+1],x[i+1]]
            ys = [0,f(x[i]),f(x[i+1]),0]
            plt.fill(xs,ys, 'b', edgecolor='b',alpha=0.2)
        plt.title('Trapesium banyak pias, N = {}'.format(N))
        plt.savefig('C:/TA Metnum/Images/Trapesium Banyak Pias.png')
        L = trapesium_banyakpias(f,a,b,N)
        print(L)
    
    #Pemanggilan fungsi untuk simpson 1/3
    elif (setting == 3):
        #Pemberi keterangan
        print(" =========================================================\n",
              "Modul 4 Integrasi Numerik: Simpson 1/3 \n",
              "KELOMPOK 11 \n",
              "OSEANOGRAFI 2019 \n",
              "PRAKTIKUM METODE NUMERIK 2021 \n",
              "=========================================================\n")
        
        #Untuk pengisian variabel x1 dan x2 serta perintah output hasil simpson 1/3
        x1 = float(input("Batas bawah (a): "))
        x2 = float(input("Batas atas (b): "))
        hasil = simpson1per3(x1, x2, 10)
        print("Nilai integral metode Simpson 1/3:", hasil)
   
   #Pemanggilan fungsi simpson 3.8
   elif (setting == 4):
        #Untuk pengisian variabel x1 dan x2 serta perintah output hasil simpson 3/8
        x1 = float(input("Batas bawah (x1): "))
        x2 = float(input("Batas atas (x2): "))  
        hasil = simpson3per8(x1, x2, 3)
        print("Nilai integral metode Simpson 3/8:", hasil)
    else:
        print("Periksa kembali kode yang ingin digunakan:)")
```
### :label:3.4. Modul 5 : Persamaan Diferensial Biasa
* #### Metode Euler
Metode Euler merupakan metode paling sederhana yang diturunkan dari deret Taylor. dalah prosedur numerik orde pertama untuk menyelesaikan persamaan diferensial biasa (ODE) dengan nilai awal yang diberikan . Ini adalah metode eksplisit paling dasar untuk integrasi numerik dari persamaan diferensial biasa dan merupakan metode Runge-Kutta 
yang paling sederhana. Metode Euler merupakan metode yang lebih sederhana, dibandingkan metode Heun. Metode Heun memiliki nilai yang lebih akurat dikarenakan metode heun adalah metode peningkatan dari metode euler.

Penggunaan Metode Euler dalam suatu fungsi untuk suatu proses integrasi. Berikut ini adalah alogritma yang digunakan:
```
 def euler():
        Nama = (input("Masukkan Nama: "))
        Nim = (input("Masukkan NIM: "))
        Kelas = (input("Masukkan Kelas: "))
        plt.style.use('seaborn-poster')
        ipy = get_ipython()
        if ipy is not None:
            ipy.run_line_magic('matplotlib', 'inline')
   
  #Mendapatkan nilai Persamaan Diferensial Biasa 
        h = float(input("Masukkan nilai h: ")) #Banyak langkah yang akan digunakan 
        x0 = float(input("Masukkan nilai x awal: ")) #Masukkan kondisi awal 0
        xn = float(input("Masukkan nilai x akhir: "))  
        x = np.arange(x0, xn + h, h) #Grid
        y0 = float(input("Masukkan nilai y awal: ")) #Masukkan kondisi awal 0
        G = (2*(x**3)+9*(x**2)+2*(x)+20) #Fungsi
        f = lambda x, y: 2*(x**3)+9*(x**2)+2*(x)+20 #Persamaan Diferensial Biasa
        y = np.zeros(len(x))
        y[0] = y0
        for i in range(0, len(x) - 1):
            y[i + 1] = y[i] + h*f(x[i], y[i])
        print(y)
        
  #Untuk menentukan nilai error      
        error = G-y
        
  #Pembuatan Grafik      
        print(error)
        judul = ("\n Grafik Pendekatan Persamaan Differensial Biasa Dengan Metode Euler \n\n %s_%s_%s \n" % (Nama,Nim,Kelas))
        plt.figure(figsize = (12, 10))
        plt.plot(x, y, 'b--', color='r', label='Hasil Pendekatan')
        plt.plot(x, G, '-g', color='y', label='Hasil Analitik')
        plt.title(judul) #Judul Plot
        plt.xlabel('x') #sumbu x
        plt.ylabel('F(x)') #sumbu y
        plt.grid() #untuk menampilkan grid
        plt.legend(loc='lower right')
        plt.savefig('image\euler.png')
  ```
* #### Metode Heun
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

Diantara kedua Metode yang digunakan, keduanya menunjukkan hasil nilai yang sama. Oleh karena itu kedua Metode bisa dijadikan pilihan dalam proses perhitungan persamaan diferensial. Namun kedua metode memiliki kelebihan masing - masing. Metode Heun yang mana merupakan Metode pengembangan dari Metode Euler sudah terdapat persamaan prediksi dan koreksi. Namun pada Metode Euler memiliki kelebihan bahwa, perhitungan yang dilakukan menggunakan cara yang lebih mudah dibandingkan Metode Heun yang menggunakan 2 persamaan. Perbedaan penyelesaian kedua Metode dalam persamaan diferensial biasa yaitu pada Metode Euler menggunakan garis yang bersinggungan dengan fungsi di awal interval sebagai perkiraan kemiringan fungsi selama interval. Akan teteapi, Metode Heun mempertimbangkan garis singgung kurva solusi di kedua ujung interval. Hal ini yang menyebabkan perhitungan iterasi yang lebih banyak pada Metode Heun dibandingkan dengan Metode Euler. Semakin banyak iterasi menandakan bahwa perhitungan itu akan semakin baik hasilnya.


## 4. Saran Pengembangan
1. Tipe pembuatan grafik dapat dikreasikan dengan mengacu pada [Style sheets referece](https://matplotlib.org/stable/gallery/style_sheets/style_sheets_reference.html)
2. Tipe garis dan warna pada grafik dapat dikreasikan dengan mengacu pada [Line and Color style](https://matplotlib.org/2.1.1/api/_as_gen/matplotlib.pyplot.plot.html)
3. Persamaan untuk setiap metode dapat *customizable*

## 5. Ucapan Terima Kasih:pray:
Demikianlah tugas akhir praktikum metode numerik ini kami buat. Seluruh authors memohon maaf apabila terdapat kesalahan dalam tugas akhir ini. Kelompok 11 selaku author dari repositori kali ini juga mengucapkan terimakasih kepada:
1. Dr. Aris Ismanto, S.Si, M.Si. selaku dosen pengampu mata kuliah Metode Numerik
2. Rikha Widiaratih, S.Si, M.Si. selaku dosen pengampu mata kuliah Metode Numerik
3. Aziz Rifai, S.T, M.Si. selaku dosen pengampu mata kuliah Metode Numerik
4. Dr. Ir. Dwi Haryo Ismunarti, M.Si. selaku dosen pengampu mata kuliah Metode Numerik
5. Tim asisten Praktikum Metode Numerik 2021 yang selalu mendampingi dalam pengerjaan tugas akhir ini
6. Seluruh rekan-rekan Oseanografi 2019 yang turut mendukung tersusunnya repositori ini

#### :mailbox:Jika terdapat pertanyaan mengenai repositori ini, dapat menghubungi *contact person* berikut: [Kelompok 11](http://bit.ly/Metnum11Queries)

