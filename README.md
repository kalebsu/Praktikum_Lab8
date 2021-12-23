# Praktikum_Lab8
# Latihan OOP dalam bahasa python
Dalam latihan dasar OOP pythonini, saya menggunakan Visual Studio Codesebagai teks editornya.

Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah classuntuk menampilkan daftar nilai mahasiswa, dengan ketentuan:

◾ Metode tambah()untuk menambah data
◾ Metode tampilkan()untuk menampilkan data
◾ Metode hapus(nama)untuk menghapus data berdasarkan nama
◾ Metode ubah(nama)untuk mengubah data berdasarkan nama

FLOWCHART
![mig]gambarlab8/gbr1.png

Pertama kita mendeklarasikan sebuah classMahasiswa yang didalamnya terdapat atributNIM, Nama, nilai tugas, nilai UTS dan nilai UAS.

class mahasiswa:
    def __init__(self, nim, nama, tugas, uts, uas):
        self.nim = nim
        self.nama = nama
        self.tugas = tugas
        self.uts = uts
        self.uas = uas

Jangan lupa, untuk mendeklarasikan sebuah class didalam OOP kita harus menggunakan def__init__dan jugaself

Seperti biasa, deklarasikan satu kamus kosong sebagai tempat menyimpan data-data yang sudah kita masukan. Ada 5 daftar kosong yang nanti isinya yaitu NIM, Nama, nilai tugas, nilai UTS dan nilai UAS.

data = mahasiswa([],[],[],[],[])

Kita akan membuat beberapa methoduntuk menambahkan, menampilkan, menghapus, mengubah data mahasiswa.
Metode pertama membuat tambah(), metode ini berfungsi untuk menambahkan data. Dalam metode ini kita menggunakan append()agar data yang terakhir ditambahkan, ada di urutan daftar paling akhir.

def tambah(self,nim,nama,tugas,uts,uas):
    data.nim.append(nim)
    data.nama.append(nama)
    data.tugas.append(tugas)
    data.uts.append(uts)
    data.uas.append(uas)

Ini tampilan jika kita memanggil method tambah():
![img]gambarlab8/gbr2.png

Metode membuat lihat(), berguna untuk menampilkan seluruh data yang sudah kita tambahkan tadi. Jika tidak ada data sama sekali, maka akan muncul tulisan TIDAK ADA DATA . Kita menggunakan for loopuntuk menampilkan banyak data. Nantinya data akan ditampilkan sebanyak n kali.

def lihat(self):
     for i in range(len(data.nama)):
         print("|", i+1, "  |", end="")
         print('{0:<25}'.format(self.nama[i]), end="")
         print("|", self.nim[i], end="")
         print(" |", self.tugas[i], end="")
         print("    |", self.uts[i], end="")
         print("  |", self.uas[i], " | ", end="")
         print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

Ini tampilan jika kita memanggil method lihat():
![img]gambarlab8/gbr3.png

Membuat metode ubah()yang berfungsi untuk mengubah data. jika metode ini dipanggil, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no)akan diubah sesuai dengan inputan dari pengguna. Index ke - (no)akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh pengguna.

def ubah(self,nim,nama,tugas,uts,uas):
     self.nim[no] = nim
     self.nama[no] = nama
     self.tugas[no] = tugas
     self.uts[no] = uts
     self.uas[no] = uas

Ini tampilan jika kita memanggil method ubah():
![img]gambarlab8/gbr4.png

Terakhir kita buat metode hapus(). Gunanya adalah melacak data berdasarkan nama. Kita bisa menggunakan deluntuk menghapus datanya. Seperti tadi, daftar nomor indeks yang akan dihapus disesuaikan dengan inputan dari pengguna. Yaitu indeks nomor ke - (no).

def hapus(self):
     del self.nim[no]
     del self.nama[no]
     del self.tugas[no]
     del self.uts[no]
     del self.uas[no]

Ini tampilan jika kita memanggil method hapus():
![img]gambarlab8/gbr5.png

Kita sudah mendeklarasikan class, instance class dan juga method. Sekarang semua itu bisa dilihat dengan diagram seperti ini :

![img]gambarlab8/gbr8.png

Dan untuk menjalankan program dan dapat memanggil metode masing-masing, seperti biasa kita menggunakan while loopyang didalamnya ada conditionalseperti ini.

while True:
    menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
    if menu == "t" or menu == "T":
       print("\nTambah Data")
       data.tambah(
           input("Masukkan NIM : "), 
           input("Masukkan Nama : "), 
           int(input("Nilai Tugas : ")), 
           int(input("Nilai UTS : ")), 
           int(input("Nilai UAS : "))
           )
       print("\nData berhasil ditambahkan")

    elif menu == "l" or menu == "L":
        print("\nDaftar Nilai")
        print("==========================================================================")
        print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
        print("==========================================================================")
        if len(data.nama) != 0:
            data.lihat()
        else:
            print("                         TIDAK ADA DATA                               ")
        print("==========================================================================")

    elif menu == "u" or menu == "U":
        print("\nUbah Data")
        ubah = input("Masukkan Nama : ")
        if ubah in data.nama:
           no = data.nama.index(ubah)
           print("Masukkan Data Yang Baru : ")
           data.ubah(
               input("NIM : "),
               input("Nama : "),
               int(input("Nilai Tugas : ")),
               int(input("Nilai UTS : ")),
               int(input("Nilai UAS : "))
               )
        else:
            print(ubah, "tidak ada di dalam data")

    elif menu == "h" or menu == "H":
        print("\nHapus Data")
        hapus = input("Masukkan Nama : ")
        if hapus in data.nama:
            no = data.nama.index(hapus)
            data.hapus()
            print("Data", hapus, "Berhasil dihapus")
        else:
            print(hapus, "tidak ada di dalam data")

    elif menu == "k" or menu == "K":
        print("\nTerimakasih\n")
        break

    else:
        print("\nPerintah yang dimasukkan salah!\n")


sekian dan terimakasih