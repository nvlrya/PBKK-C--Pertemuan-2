# Sistem Data Mahasiswa

Nama: Naufal Nararya Aydinullah <br>
NRP: 5025241251 <br>
Kelas: C <br>

## 1. Tampilan Menu Utama

Saat program pertama kali dijalankan, pengguna akan melihat menu utama yang berisi beberapa pilihan. Pengguna dapat memilih fitur yang ingin digunakan dengan memasukkan nomor sesuai menu.

Menu yang tersedia:
- 1. Tambah Mahasiswa
- 2. Tampilkan Mahasiswa
- 3. Cari Mahasiswa
- 4. Hapus Mahasiswa
- 5. Keluar

 ## 2. Tambah Mahasiswa

Fitur ini digunakan untuk menambahkan data mahasiswa baru ke dalam sistem. Pengguna perlu memasukkan NIM, nama, program studi, dan IPK. Setelah semua data dimasukkan dengan benar, data mahasiswa akan disimpan ke dalam sistem.

```csharp
  static void TambahMahasiswa()
        {
            Console.Clear();

            Console.WriteLine("========================================");
            Console.WriteLine(" TAMBAH MAHASISWA");
            Console.WriteLine("========================================");

            Console.Write("NIM : ");
            string nim = Console.ReadLine();

            Console.Write("Nama : ");
            string nama = Console.ReadLine();

            Console.Write("Program Studi : ");
            string prodi = Console.ReadLine();

            double ipk;

            while (true)
            {
                Console.Write("IPK : ");

                if (double.TryParse(
                    Console.ReadLine(),
                    out ipk))
                {
                    if (ipk >= 0 && ipk <= 4)
                    {
                        break;
                    }
                }

                Console.WriteLine(
                    "IPK harus berupa angka 0 - 4."
                );
            }

            Mahasiswa mahasiswa =
                new Mahasiswa(
                    nim,
                    nama,
                    prodi,
                    ipk
                );

            daftarMahasiswa.Add(mahasiswa);

            Console.WriteLine();
            Console.WriteLine(
                "Data mahasiswa berhasil ditambahkan."
            );
        }
