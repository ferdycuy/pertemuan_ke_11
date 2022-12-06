## Latihan 1

### code 

```# mengubah code menjadi fungsi menggunakan lambda
import math
def a(x):
    return x**2
    a = lambda x : x ** 2
print(a(2))
def b(x, y):
    return math.sqrt(x**2 + y**2)
    b = lambda x, y : x ** 2  + y ** 2
print(b(2, 2))
def c(*args):
    return sum(args)/len(args)
    c = lambda *args : sum(args)/len(args)
print(c(5, -1, 8, 19))
def d(s):
    return "".join(set(s))
    d = lambda s: "".join(set(s))
print(d("eka"))
```

![Screenshot (59)](https://user-images.githubusercontent.com/115714443/205929156-7cad39df-3e12-4eb1-957a-d360608bd1dc.png)


## Tugas Pratikum

- Buat program sederhana dengan mengaplikasikan penggunaan fungsi
  yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan:
- Fungsi tambah() untuk menambah data
- Fungsi tapilkan() untuk menampilkan data
- Fungsi hapus(nama) untuk menghapus data berdasarkan nama
- Fungsi ubah(nama) untuk mengubah data berdasarkan nama
  
  - Flowchart
  
  ![flowchart](https://user-images.githubusercontent.com/115714443/205926673-720b7582-92c5-4edf-a612-343f7a68abc0.png)
  
  ### code
  
```dataMahasiswa = {}
print("=" * 65)
print("|\tPROGRAM INPUT NILAI MAHASISWA MENGGUNAKAN FUNGSI\t|")
print("=" * 65)


def tambah():
    nama = str(input("Masukan Nama : "))
    nim = int(input("Masukan Nim   : "))
    tugas = int(input("Masukan Nilai Tugas : "))
    uts = int(input("Masukan Nilai UTS     : "))
    uas = int(input("Masukan Nilai UAS     : "))
    akhir = (tugas / 3) + (uts / 3.5) + (uas / 3.5)
    dataMahasiswa[nama] = nim, tugas, uts, uas, akhir,
    print("\nDATA BERHASIL DITAMBAHKAN!")


def tampilkan():
    print("=" * 69)
    print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
          "    |")
    print("=" * 69)
    print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
    print("=" * 69)
    for tampil in dataMahasiswa.items():
        no = 0
        no += 1
        print("| {6:2} |\t {0:15}   | {1:9} \t| {2:5} | {3:3} | {4:3} | {5:5} |".format(tampil[0], tampil[1][0],
                                                                                        tampil[1][1], tampil[1][2],
                                                                                        tampil[1][3],
                                                                                        "%.2f" % float(tampil[1][4]),
                                                                                        no))
        print("=" * 69)


def hapus(nama):
    del dataMahasiswa[nama]
    print("DATA BERHASIL DIHAPUS!")


def ubah(nama):
    if nama in dataMahasiswa.keys():
        nim = int(input("Masukan Nim  : "))
        tugas = int(input("Masukan Nilai Tugas : "))
        uts = int(input("Masukan Nilai UTS     : "))
        uas = int(input("Masukan Nilai UAS     : "))
        akhir = (tugas / 3) + (uts / 3.5) + (uas / 3.5)
        dataMahasiswa[nama] = nim, tugas, uts, uas, akhir
        print("\nDATA BERHASIL DI UBAH!")
    else:
        print("\DATA TIDAK DITEMUKAN!")

while True:
    data = input(
        "\n 1 - Tambahkan Data,\t 2 - Tampilkan Data,\t 3 - Hapus Data,\t 4 - Ubah Data, 5 - Keluar \n : "
    )
    if (data.lower() == '1'):
        tambah()

    elif (data.lower() == '4'):
        nama = str(input("Masukan Nama : "))
        ubah(nama)
    elif (data.lower() == '3'):
        nama = str(input("Masukan Nama : "))
        if nama in dataMahasiswa:
            hapus(nama)
        else:
            print("DATA TIDAK DITEMUKAN ".format(nama))
    elif (data.lower() == '2'):
        if dataMahasiswa.items():
            tampilkan()
        else:
            print("=" * 69)
            print("|" + "\t" * 3 + "DAFTAR NILAI MAHASISWA" + "\t" * 3 +
                  "    |")
            print("=" * 69)
            print("| NO |   \tNAMA\t   |\tNIM \t| TUGAS | UTS | UAS | AKHIR |")
            print("=" * 69)
            print("|    " + "\t" * 3 + "TIDAK ADA DATA!" + "\t" * 4 + "    |")
            print("=" * 69)
    elif (data.lower() == '5'):
        print("\nTERIMA KASIH! \n")
        exit()
    else:
        print("YANG ANDA CARI TIDAK ADA!")
        ```
        
### Penjelasan
        
- 1. Fungsi tambah() untuk menambah data
- 2. Fungsi tapilkan() untuk menampilkan data
- 3. Fungsi hapus(nama) untuk menghapus data berdasarkan nama
- 4. Fungsi ubah(nama) untuk mengubah data berdasarkan nama

- ![Screenshot (60)](https://user-images.githubusercontent.com/115714443/205928874-e9617b7a-b918-47f5-ba53-4bc1b547820d.png)

