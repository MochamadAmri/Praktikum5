# PRAKTIKUM 5

# Program Menghitung Nilai Mahasiswa Menggunakan Dictionary

Pada praktek kali ini, saya mencoba membuat program menentukan nilai mahasiswa dengan menggunakan Dictionary.

    Source Code dan Penjelasan

dataMhs = {}                                                                                     ## Membuat Dictionary kosong
print("==================================================================")
print("|      PROGRAM INPUT NILAI MAHASISWA MENGGUNAKAN DICTIONARY      |")
print("==================================================================")

while True:                                                                                      ## LOOPING AKTIF
    c = input("\nA)dd, E)dit, S)earch, D)elete L)ist, Q)uit: ")                                  ## Membuat Menu

    ## MENU ADD
    if (c.lower() == 'a'):                                                                       ## MENU ADD
        print("\n=========================")
        print("| TAMBAH DATA MAHASISWA |")
        print("=========================")
        nama          = input("Masukkan Nama        : ")                                         ## Menginput Nama
        nim           = input("Masukkan NIM         : ")                                         ## Menginput NIM
        nilaiTugas    = int(input("Masukkan Nilai Tugas : "))                                    ## Menginput Nilai Tugas
        nilaiUts      = int(input("Masukkan Nilai UTS   : "))                                    ## Menginput Nilai UTS
        nilaiUas      = int(input("Masukkan Nilai UAS   : "))                                    ## Menginput Nilai UAS
        nilaiAkhir    = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)              ## Menghitung Nilai Akhir
        dataMhs[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir                          ## Menambahkan data yang sudah diinput ke Dictionary
        print("\nData Berhasil Ditambahkan!")

    ## MENU EDIT
    elif (c.lower() == 'e'):                                                                     ## Menu EDIT
        print("\n=======================")
        print("| EDIT DATA MAHASISWA |")
        print("=======================")
        nama = input("Masukkan Nama: ")                                                          ## Cari nama yang akan diedit
        if nama in dataMhs.keys():                                                               ## Mengambil key dari Dictionary
            nim           = input("Masukkan NIM Baru         : ")                                ## Menginput NIM baru
            nilaiTugas    = int(input("Masukkan Nilai Tugas Baru : "))                           ## Menginput Nilai Tugas Baru
            nilaiUts      = int(input("Masukkan Nilai UTS Baru   : "))                           ## Menginput Nilai UTS Baru
            nilaiUas      = int(input("Masukkan Nilai UAS Baru   : "))                           ## Menginput Nilai UAS Baru
            nilaiAkhir    = (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)          ## Menghitung Nilai Akhir Baru
            dataMhs[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir                      ## Mengupdate data ke Dictionary
            print("\nData Berhasil Di Update!")
        else:                                                                                    
            print("Data tidak ditemukan!")                                                       ## Jika nama tidak ditemukan maka muncul perintah tsb.

    ## MENU SEARCH
    elif (c.lower() == 's'):                                                                     ## Menu SEARCH
        print("\n=======================")
        print("| CARI DATA MAHASISWA |")
        print("=======================")
        nama = input("Masukan Nama:  ")                                                          ## Masukkan nama yang akan dicari
        if nama in dataMhs.keys():                                                               ## Mengambil keys dari Dictionary
            print("\n                   DAFTAR NILAI MAHASISWA                   ")
            print("==============================================================")
            print("|     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==============================================================")
            print("| {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(nama, nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir)) ## Format tabel
            print("==============================================================")
        else:
            print("Datanya {0} Tidak Ada ".format(nama))                                        ## Jika data tidak ditemukan, akan muncul perintah tsb.

    ## MENU DELETE
    elif (c.lower() == 'd'):                                                                    ## Menu DELETE
        nama = input("Masukkan Nama:  ")                                                        ## Masukkan nama yang akan didelete
        if nama in dataMhs.keys():                                                              ## Mengambil keys dari Dictionary
            del dataMhs[nama]                                                                   ## Menghapus data yang dipilih
            print("Data Telah dihapus!")
        else:
            print("Data Mahasiswa Tidak Ada".format(nama))                                      ## Jika data tidak ditemukan, akan muncul perintah tsb.

    ## MENU LIST
    elif (c.lower() == 'l'):                                                                    ## Menu LIST
        if dataMhs.items():                                                                     ## Mengambil items dari Dictionary
            print("\n                      DAFTAR NILAI MAHASISWA                    ")
            print("==================================================================")
            print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==================================================================")
            i = 0
            for x in dataMhs.items():
                i += 1
                print("| {6:2} | {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(x[0], x[1][0], x[1][1], x[1][2], x[1][3], x[1][4], i))  ## Format tabel
            print("==================================================================")
        else:
            print("\n                      DAFTAR NILAI MAHASISWA                    ")
            print("==================================================================")
            print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==================================================================")
            print("|                          TIDAK ADA DATA!                       |")
            print("==================================================================")        ## Jika data masih kosong, akan muncul pesan tsb.

    ## MENU KELUAR PROGRAM
    elif (c.lower() == 'q'):                                                                   ## Menu QUIT
        print("\n mochamad amri adrian wiratama \n 311910226 \n TI.19.A.2")
        break                                                                                  ## Mengakhiri LOOPING

    else:
        print("Pilih menu yang tersedia: ")                                                    ## Jika menu yang dipilih tidak valid, akan muncul pesan tsb
# Flowchart
![Flowchart Praktikum5](https://user-images.githubusercontent.com/56380838/71565865-5a5ad100-2ae5-11ea-8107-c4cbe94a8191.jpeg)
# Screenshot Input
Input (1)
![Input(1) Praktikum5](https://user-images.githubusercontent.com/56380838/71576654-e5f35280-2b23-11ea-851c-298dda2f2ffc.png)
Input (2)
![Input (2) Praktikum5](https://user-images.githubusercontent.com/56380838/71576713-1cc96880-2b24-11ea-86df-81b44f23f9ae.png) 
Input (3)
![Input(3) Praktikum5](https://user-images.githubusercontent.com/56380838/71576742-37034680-2b24-11ea-8a51-f56361ff0008.png)
Input (4)
![Input(4) Praktikum5](https://user-images.githubusercontent.com/56380838/71576779-4f736100-2b24-11ea-87b3-7f3e0269119e.png)
# Screenshot Ouput
ADD

LIST
![List Praktikum5](https://user-images.githubusercontent.com/56380838/71577109-6d8d9100-2b25-11ea-8b9c-591b2f782708.png)
SEARCH
![Search Praktikum5](https://user-images.githubusercontent.com/56380838/71577129-826a2480-2b25-11ea-8539-3c468b895bdc.png)
EDIT
![Edit Praktikum5](https://user-images.githubusercontent.com/56380838/71577033-37e8a800-2b25-11ea-8a64-a59f7acd538d.png)
DELETE
![Delete Parktikum5](https://user-images.githubusercontent.com/56380838/71577012-23a4ab00-2b25-11ea-9c65-9881f6b9524a.png)
QUIT
![Quit Praktikum5](https://user-images.githubusercontent.com/56380838/71577070-59e22a80-2b25-11ea-9c1d-fd11fcca037e.png)
