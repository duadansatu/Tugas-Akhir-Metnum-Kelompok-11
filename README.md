# Tugas-Akhir-Metnum-Kelompok-11
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Metode Numerik Oseanografi 2021. Repositori ini memuat executable (.exe) file yang dapat memproses beberapa persamaan metode numerik untuk penyelesaian perhitungan numerik. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Google Colaboratory dan Jupyter Notebook. Sedangkan untuk library yang digunakan kali ini adalah Numpy, Matplotlib, IPython, Scipy, Pprint, dan Math. Seluruh script yang dibuat adalah hasil kelompok 11 Oseanografi 2019. Semoga dapat bermanfaat!

### AUTHOR (KELOMPOK 11)
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

### Cara Penggunaan

### Metode Pengerjaan
1. Modul 2: Akar-akar Persamaan
2. Modul 3: Sistem Persamaan Linear dan Matrix
3. Modul 4: Integrasi Numerik
4. Modul 5: Persamaan Differensial Biasa

#### Modul 5 : Persamaan Diferensial Biasa
##### Metode Heun
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


### Saran Pengembangan
1. Lebih dikreasiin lagi untuk tipe-tipe pembuatan grafik
2. Kedepannya untuk script supaya customizable
