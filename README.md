# PERTEMUAN9
TUGAS DIBUAT UNTUK MEMENUHI TUGAS PADA PERTEMUAN 9
 

### Nama : Denas Aria Pamungkas
### Kelas : TI.20.A1
### NIM : 312010089
### Matkul : Bahasa Pemrograman
________________________________________________________________________________________________________________
## Program Data Mahasiswa
pada praktikum 5 ini, saya akan membuat program sederhana untuk menginput data kedalam list.



### Membuat Pintasan "Keluar"
Kali ini kita akan membuat pintasan "keluar" dengan baris perintah sebagai berikut

```python
    if menu.lower() == 'k':
        break
```


![hasil](https://user-images.githubusercontent.com/72905634/100190062-5c1e4780-2ea2-11eb-8fd0-9ba8e20fed57.png)
<br>


### Membuat Pintasan "lihat"
dan ini adalah baris perintah untuk membuat perintah "lihat"

```python
    elif menu.lower() == 'l':
        print("Daftar Nilai:")
        print("_______________________")
        print("| No |      Nama      |    NIM    | Tugas |  UTS  |  UAS  | Akhir |")
        print("===================================================================")
        no = 1
        for tabel in data.values():
            print("| {0:2} | {1:14} | {2:9} | {3:5} | {4:5} | {5:5} | {6:5} |".format
                  (no, tabel[0],
                   tabel[1], tabel[2],
                   tabel[3], tabel[4], tabel[5]))
            no += 1
```


![hasil1](https://user-images.githubusercontent.com/72905634/100190613-83294900-2ea3-11eb-9ef2-d28f4399e4cc.png)
<br>



### Membuat Pintasan "Tambah"
kali ini kita akan membuat baris perintah "tambah" untuk menambahkan data baru kedalam syntax database tersebut, berikut adalah baris perintahnya:

```python
    elif menu.lower() == 't':
        print("Masukan data mahasiswa")
        print("...")
        nama = input("Masukan nama: ")
        nim = input("Masukan NIM: ")
        nilai_tugas = int(input("Masukan nilai tugas: "))
        nilai_uts = int(input("Masukan nilai UTS: "))
        nilai_uas = int(input("Masukan nilai UAS: "))
        nilai_akhir = (nilai_tugas)*30/100 + (nilai_uts)*35/100 + (nilai_uas)*35/100 
        data[nama] = [nama, nim, nilai_tugas, nilai_uts, nilai_uas, nilai_akhir]
        print('\nData berhasil di tambah!')
        print("_______________________")
        print("| No |      Nama      |    NIM    | Tugas |  UTS  |  UAS  | Akhir |")
        print("===================================================================")
        no = 1
        for tabel in data.values():
            print("| {0:2} | {1:14} | {2:9} | {3:5} | {4:5} | {5:5} | {6:5} |".format
                  (no, tabel[0],
                   tabel[1], tabel[2],
                   tabel[3], tabel[4], tabel[5]))
            no += 1
```


Berikut adalah tampilan outputnya;
![hasil2](https://user-images.githubusercontent.com/72905634/100191814-a3f29e00-2ea5-11eb-8fde-ca11701bfeec.png)
<br>



### Membuat Pintasan "Ubah"
baris perintah dibawah ini digunakan untuk membuat pintasan "ubah" pada database, yang dimana pintasan ini berguna untuk mengubah data yang telah ada di dalam database tersebut. Disini, kita bisa mengubah nama, Nim, nilai tugas, nilai UTS serta nilai UAS. Sesuaikan data yang ingin kamu ganti. Seperti contoh dibawah, saya akan mengubah nama yang ada di dalam database.


```python
    elif menu.lower() == 'u':
        nama = input("Masukan nama untuk mengubah data: ")
        if nama in data.keys():
            print("Mau mengubah apa?")
            sub_data = input("(Semua), (Nama), (NIM), "
                         "(Tugas), (UTS), (UAS) : ")
            if sub_data.lower() == "semua":
                print("==========================")
                print("Ubah data {}.".format(nama))
                print("==========================")
                data[nama][1] = input("Ubah NIM:")
                data[nama][2] = int(input("Ubah Nilai Tugas: "))
                data[nama][3] = int(input("Ubah Nilai UTS: "))
                data[nama][4] = int(input("Ubah Nilai UAS: "))
                data[nama][5] = data[nama][2] *30/100 + data[nama][3]*35/100 + data[nama][4] *35/100 
                print("\nBerhasil ubah data!")
                print("_______________________")
                print("| No |      Nama      |    NIM    | Tugas |  UTS  |  UAS  | Akhir |")
                print("===================================================================")
                no = 1
                for tabel in data.values():
                    print("| {0:2} | {1:14} | {2:9} | {3:5} | {4:5} | {5:5} | {6:5} |".format
                        (no, tabel[0],
                        tabel[1], tabel[2],
                        tabel[3], tabel[4], tabel[5]))
                    no += 1
            elif sub_data.lower() == "nim":
                data[nama][1] = input("NIM:")
                print('Data berhasil di ubah!')
            elif sub_data.lower() == "tugas":
                data[nama][2] = int(input("Nilai Tugas: "))
                print('Data berhasil di ubah!')
            elif sub_data.lower() == "uts":
                data[nama][3] = int(input("Nilai UTS: "))
                print('Data berhasil di ubah!')
            elif sub_data.lower() == "uas":
                data[nama][4] = int(input("Nilai UAS: "))
                print('Data berhasil di ubah!')
            else:
                print("menu tidak ditemukan.")

        else:
            print("'{}' tidak ditemukan.".format(nama))
```


Berikut adalah tampilan outputnya;
![hasil3](https://user-images.githubusercontent.com/72905634/100193832-6a239680-2ea9-11eb-9c24-d54c2ed804b0.png)
<br>


### Membuat Pintasan "Cari"
Pintasan "cari" dibuat untuk memudahkan kita mencari data yang kita inginkan di dalam database, baris perintahnya adalah

```python
 elif menu.lower() == 'c':
        print("Mencari data: ")
        print("=================================================")
        nama = input("Masukan nama untuk mencari data: ")
        if nama in data.keys():
            print('\nResult')
            print("Nama: {0}\nNIM : {1}\nNilai Tugas: {2}\nUTS: {3}\nUAS: {4}\nNilai akhir: {5}"
                  .format(nama, data[nama][1],
                                data[nama][2], data[nama][3],
                                data[nama][4], data[nama][5]))
        else:
            print("'{}' tidak ditemukan.".format(nama))
```


Berikut adalah tampilan outputnya;
![hasil4](https://user-images.githubusercontent.com/72905634/100194137-0188e980-2eaa-11eb-8827-d996facafcb7.png)
<br>


### Membuat Pintasan "Hapus"
Pintasan "hapus" ini berfungsi untuk menghapus data yang ada di dalam database, berikut adalah baris perintahnya

```python
    elif menu.lower() == 'h':
        nama = input("Masukan nama untuk menghapus sub_data : ")
        if nama in data.keys():
            del data[nama]
            print("sub_data '{}' berhasil dihapus.".format(nama))
        else:
            print("'{}' tidak ditemukan.".format(nama))

    else:
        print("Upss ada yang salah, silahkan cek kembali.")
```


Berikut adalah tampilan outputnya;
![hasil5](https://user-images.githubusercontent.com/72905634/100203456-7b739f80-2eb7-11eb-8a2f-780bfd660de7.png)
<br>


### Hasil Akhir

Pada pertemuan kali ini hasil akhir atau tampilan output yang diminta oleh bapak/ibu dosen pada praktikum 5 adalah sebagai berikut

Berikut adalah tampilan outputnya;
![hasil6](https://user-images.githubusercontent.com/72905634/100203752-dad1af80-2eb7-11eb-949c-381c8227304e.png)
<br>
