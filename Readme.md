# <p align=center> Praktikum 5

Berikut adalah dictionary yang di definisikan terlebih dahulu :

    daftar = {}

Selanjutnya adalah perulangan yang digunakan :

    while True:
	    statement
Perulangan di atas adalah perulangan yang akan berjalan terus menerus, dan akan berhenti jika kode berikut di eksekusi :

    if perintah.lower() == 'k':
	    break
Kode di atas berfungsi untuk menghentikan perulangan yang berlangsung terus menerus tanpa ada kondisi untuk dipenuhi, 
di tulis di dalam kondisi `if`

### 1. Input Data
Kondisi berikut digunakan untuk melakukan input data seperti Nama, NIM, Nilai Tugas, UTS dan UAS :

    elif perintah.lower() == 't':
		print("Masukan data mahasiswa")
        print("...")
        nama = input("Masukan nama: ")
        nim = input("Masukan NIM: ")
        n_tugas = int(input("Masukan nilai tugas: "))
        n_UTS = int(input("Masukan nilai UTS: "))
        n_UAS = int(input("Masukan nilai UAS: "))
        a = n_tugas * 30 / 100
        b = n_UTS * 35 / 100
        c = n_UAS * 35 / 100
        n_akhir = a + b + c
        daftar[nama] = [nama, nim, n_tugas, n_UTS, n_UAS, n_akhir]

Untuk **nilai akhir** (`n_akhir`) , di buat berdasarkan operasi dari variabel `n_tugas`, `n_UTS` dan `n_UAS` 

yang mewakili **Nilai Tugas**, **UTS** dan **UAS**.


### 2. Menampilkan Input Data
Selanjutnya adalah kode yang digunakan untuk melihat input yang sudah dimasukan :

    elif perintah.lower() == 'l':
	    no = 1
        for tabel in daftar.values():
            print("| {0:2} | {1:14} | {2:9} | {3:5} 
		           | {4:5} | {5:5} | {6:5} |".format
	               (no, tabel[0],
                   tabel[1], tabel[2],
                   tabel[3], tabel[4], tabel[5]))
            no += 1
Data dalam perulangan `for` di ambil dari variabel dictionary `daftar` pada bagian value yang berbentuk list. 

variabel `no` diguanakan untuk membuat nomor. Data yang akan ditampilkan adalah **Nama**, **NIM**, **Nilai** **Tugas**, **UTS**, **UAS**, dan **Nilai Akhir**.



### 3. Mengubah Data
Perintah dijalankan jika input yang di masukan adalah `u`, di dalam kondisi ini terdapat input dan kondisi,

dimana jika input `nama` ada di dalam variabel `daftar.keys` maka akan muncul beberapa pilihan 

untuk mengubah semua data atau data tertentu saja.

    elif perintah.lower() == 'u':
        nama = input("Masukan nama untuk mengubah data: ")
        if nama in daftar.keys():
            data = input("(Semua), (Nama), (NIM), "
                         "(Tugas), (UTS), (UAS) : ")

Berikut kondisi yang digunakan untuk memasukan pilihan :

    if data.lower() == "semua":
	    daftar[nama][1] = input("Edit NIM:")
        daftar[nama][2] = int(input("Edit Nilai Tugas: "))
        daftar[nama][3] = int(input("Edit Nilai UTS: "))
        daftar[nama][4] = int(input("Edit Nilai UAS: "))
    elif data.lower() == "nim":
        daftar[nama][1] = input("NIM:")
    elif data.lower() == "tugas":
	...



### 4. Mencari Data
Berikut bagaimana mencari data yang sudah di inputkan sebelumnya :

    elif perintah.lower() == 'c':
	    nama = input("Masukan nama untuk mencari daftar nilai : ")
	    if nama in daftar.keys():
		    print()

Perbandingan untuk mencari data yang akan diubah sama seperti cara mengubah data, 

hanya saja perintah ini digunakan untuk menampilkan data yang di input berdasarkan nama.




### 5. Menghapus data
Sama seperti mengubah dan mencari data, untuk menghapus data yang dipilih :

    elif perintah.lower() == 'h':
	    nama = input("Masukan nama untuk menghapus data : ")
        if nama in daftar.keys():
	        del daftar[nama]

Data yang di hapus adalah data yang di input dalam variabel `nama` dimana berisi nama (string) 

yang mewakili data NIM, Nilai Tugas, UTS dan UAS.



Jika `k` di input dan  `lower()` digunakan untuk mengkonversi input yang dimasukan ke bentuk ***lower case***

dan Input `k` digunakan berdasarkan perintah yang sudah di masukan dalam keterangan pada fungsi input di bawah ini :

    perintah = input("(L) Lihat, (T) Tambah, 
					  (U) Ubah, (H) Hapus, 
					  (C) Cari, (K) Keluar: ")

