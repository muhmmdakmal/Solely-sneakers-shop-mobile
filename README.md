# Solely Sneakers Shop Mobile

<h2>
Nama : Muhammad Akmal Abdul Halim

NPM : 2306245125

Kelas : PBP-D
</h2>

<details>
    <summary> Tugas 7: Elemen Dasar Flutter </summary>

**1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.** 

1. Stateless Widget

Stateless Widget adalah widget yang tidak memiliki status internal atau perubahan kondisi. Artinya, setelah widget ini dirender di layar, isinya tidak akan berubah selama aplikasi berjalan. Biasanya, Stateless Widget cocok untuk konten statis atau UI yang tidak memerlukan pembaruan.

Contoh penggunaan:

- Label teks yang hanya menampilkan satu kalimat.
- Ikon atau tombol yang hanya melakukan satu fungsi tanpa mengubah tampilannya.
- Struktur layout sederhana yang tidak membutuhkan interaksi kompleks.

2. Stateful Widget

Stateful Widget adalah widget yang memiliki status atau state yang dapat berubah. Dengan Stateful Widget, kita bisa mengubah tampilan atau properti widget secara dinamis sesuai dengan interaksi atau input dari pengguna. Ini sangat berguna untuk komponen UI yang harus merespons perubahan, seperti input form, slider, atau data yang di-refresh.

Contoh penggunaan:

- Tombol yang mengubah tampilan atau ikon setelah ditekan.
- Kolom input yang memperbarui teks yang dimasukkan pengguna.
- Widget yang menampilkan data dinamis dari API atau perubahan waktu (misalnya, countdown timer).

**2. Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.**

1. MyApp (StatelessWidget):

    - Ini adalah widget utama aplikasi yang memulai aplikasi dengan MaterialApp.
    - Berfungsi sebagai root aplikasi, mengatur MaterialApp sebagai kerangka kerja dasar.

2. MaterialApp:

    - Menyediakan berbagai konfigurasi global seperti title, theme, dan halaman awal (home) aplikasi.
    - Menggunakan ThemeData untuk menerapkan tema warna merah.

3. ThemeData:

    - Mengatur tema aplikasi secara keseluruhan, termasuk ColorScheme.
    - Dalam contoh ini, warna utama (primary) adalah merah, dengan warna sekunder (secondary) merah tua.

4. MyHomePage (StatelessWidget):

    - Halaman utama aplikasi yang menampilkan beberapa informasi seperti NPM, nama, dan kelas.
    - Memiliki daftar ItemHomepage yang digunakan untuk membuat menu.

5. Scaffold:

    - Kerangka dasar halaman yang menyediakan AppBar dan body.
    - Mempermudah pengaturan struktur dasar UI halaman.

6. AppBar:

    - Menampilkan judul aplikasi pada bagian atas halaman dengan - gaya teks khusus dan warna latar sesuai tema.

7. Padding:

    - Mengatur jarak di sekitar widget untuk tampilan yang lebih rapi.

8. Column dan Row:

    - Digunakan untuk menyusun widget secara vertikal (Column) dan horizontal (Row).
    - Dalam proyek ini, Row menampung tiga InfoCard untuk menampilkan data seperti NPM, nama, dan kelas.

9. InfoCard (StatelessWidget):

    - Kartu informasi yang menampilkan judul (misalnya, NPM) dan isinya (misalnya, nilai NPM).
    - Menggunakan Card untuk memberikan tampilan seperti kartu dengan bayangan ringan.

10. SizedBox:

    - Menyediakan jarak antar widget atau mengatur ukuran widget.

11. GridView.count:

    - Menampilkan menu dalam bentuk grid dengan tiga kolom.
    - Setiap item dalam GridView adalah ItemCard yang berasal dari daftar ItemHomepage.

12. ItemHomepage (Model Data):

    - Model data sederhana yang menyimpan name dan icon untuk setiap item dalam menu.

13. ItemCard (StatelessWidget):

    - Kartu yang menampilkan ikon dan nama item.
    - Menggunakan Material dengan InkWell untuk memberikan efek klik pada kartu.

14. SnackBar:

    - Digunakan untuk menampilkan pesan sementara di bagian bawah layar ketika pengguna menekan ItemCard.

**3. Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.**


setState() adalah fungsi yang sangat penting dalam widget berbasis StatefulWidget di Flutter. Fungsinya adalah untuk memberi tahu Flutter bahwa ada perubahan pada state dari widget yang perlu ditampilkan ulang di layar.

Ketika setState() dipanggil, Flutter akan menjalankan ulang metode build() dari widget tersebut, dan hasilnya adalah tampilan yang diperbarui dengan kondisi terbaru.

Variabel yang Terpengaruh oleh setState()

Hanya variabel-variabel dalam State yang dideklarasikan dalam widget Stateful yang bisa diubah dengan setState(). Beberapa contohnya:

1. Boolean untuk Menyembunyikan/Menampilkan Widget: 

    Misalnya, jika kita ingin menyembunyikan atau menampilkan bagian dari UI, kita bisa menggunakan boolean yang diubah dengan setState().

2. List atau Daftar: 

    Jika Anda memiliki daftar item yang ditampilkan dalam UI, menambah atau menghapus item dari daftar dengan setState() akan memperbarui daftar yang ditampilkan.

3. String dan Teks Lainnya: 

    Jika teks yang ditampilkan di layar berubah berdasarkan kondisi tertentu, kita bisa menggunakan setState() untuk memperbarui teks tersebut.

4. Warna atau Style Lainnya: 

    Variabel yang menentukan warna, ukuran font, atau elemen gaya lainnya pada UI juga bisa diubah melalui setState().\

**4. Jelaskan perbedaan antara const dengan final.**

1. const (Constant)
- Nilai Konstanta yang Imenable (Immutable): Variabel yang dideklarasikan dengan const memiliki nilai yang bersifat compile-time constant, artinya nilainya harus ditentukan pada saat kompilasi dan tidak bisa diubah setelah itu.
- Bersifat Immutable: Semua objek yang dibuat dengan const benar-benar immutable, yang berarti setiap aspek dari objek tersebut tidak dapat diubah setelah inisialisasi.
- Diakses Secara Global: Karena const adalah konstanta waktu kompilasi, objek yang dibuat dengan const akan diakses sebagai objek tunggal di memori, sehingga tidak akan terjadi pembuatan objek baru jika const tersebut digunakan di beberapa tempat.

2. final (Final)
- Nilai Ditentukan Saat Run-Time: Variabel yang dideklarasikan dengan final hanya dapat diinisialisasi satu kali, tetapi nilainya dapat ditentukan saat run-time. Artinya, kita tidak perlu mengetahui nilai dari variabel ini pada saat kompilasi, tetapi setelah diberi nilai sekali, tidak bisa diubah.
- Immutable pada Level Referensi: Objek yang dideklarasikan dengan final tidak bisa diubah setelah inisialisasi, tetapi isinya (untuk tipe data koleksi seperti List atau Map) masih bisa dimodifikasi.
- Konteks yang Fleksibel: final cocok digunakan ketika kita hanya ingin memastikan bahwa variabel tidak akan berubah, tetapi nilai yang dipegangnya baru diketahui di runtime.

**5. Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.**

1. Buatlah file baru bernama menu.dart pada directory lib, tambahkan import ini :

    ```dart
    import 'package:flutter/material.dart';
    ```
2. Pindahkan class MyHomePage dan _MyHomePageState dari main.dart ke menu.dart
3. Tambahkan import ini :
    ```dart
    import 'package:mental_health_tracker/menu.dart';
    ```
    pada main.dart.

4. Ubah colorScheme nya menjadi yang anda mau.
5. Sebelum membuat button untuk card, anda membuat class baru bernama ItemHomepage yang berisi atribut-atribut dari card yang akan anda buat. Tambahkan ini pada menu.dart anda :

    ```dart
    class ItemHomepage {
        final String name;
        final IconData icon;

        ItemHomepage(this.name, this.icon);
    }
    ```
6. Setelah itu, anda dapat membuat list of ItemHomepage yang berisi tombol-tombol yang ingin anda tambahkan pada class MyHomePage.

    ```dart
    class MyHomePage extends StatelessWidget {  
        ...
        final List<ItemHomepage> items = [
            ItemHomepage("Lihat Daftar Produk", Icons.mood),
            ItemHomepage("Tambah Produk", Icons.add),
            ItemHomepage("Logout", Icons.logout),
        ];
        ...
    }
    ```

7. Untuk menampilkan snackbar, tambahkan kode berikut pada menu.dart :

    ```dart
    class ItemCard extends StatelessWidget {
    // Menampilkan kartu dengan ikon dan nama.

    final ItemHomepage item; 
    
    const ItemCard(this.item, {super.key}); 

    @override
    Widget build(BuildContext context) {
        return Material(
        // Menentukan warna latar belakang dari tema aplikasi.
        color: Theme.of(context).colorScheme.secondary,
        // Membuat sudut kartu melengkung.
        borderRadius: BorderRadius.circular(12),
        
        child: InkWell(
            // Aksi ketika kartu ditekan.
            onTap: () {
            // Menampilkan pesan SnackBar saat kartu ditekan.
            ScaffoldMessenger.of(context)
                ..hideCurrentSnackBar()
                ..showSnackBar(
                SnackBar(content: Text("Kamu telah menekan tombol ${item.name}!"))
                );
            },
            // Container untuk menyimpan Icon dan Text
            child: Container(
            padding: const EdgeInsets.all(8),
            child: Center(
                child: Column(
                // Menyusun ikon dan teks di tengah kartu.
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                    Icon(
                    item.icon,
                    color: Colors.white,
                    size: 30.0,
                    ),
                    const Padding(padding: EdgeInsets.all(3)),
                    Text(
                    item.name,
                    textAlign: TextAlign.center,
                    style: const TextStyle(color: Colors.white),
                    ),
                ],
                ),
            ),
            ),
        ),
        );
    }
    
    }
    ```

</details>

##
<details>
    <summary>Tugas 8: Flutter Navigation, Layouts, Forms, and Input Elements</summary>

**1.Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?**

- Apa kegunaan const di Flutter?

    const digunakan untuk mendefinisikan objek atau widget yang bersifat konstan, artinya nilainya tidak akan berubah selama aplikasi berjalan.

- Keuntungan menggunakan const:
    
    - Efisiensi Memori: Objek const tidak akan dibuat ulang setiap kali diperlukan, sehingga menghemat memori. Misalnya, kalau ada widget yang sering muncul, cukup buat satu kali, dan sisanya Flutter akan memanfaatkan instance yang sudah ada.
    - Performa Render: Karena objek const hanya dibuat sekali, widget yang memakai const tidak akan di-rebuild (dibuat ulang) setiap kali aplikasi berubah atau ada state baru, kecuali benar-benar diperlukan. Hal ini bikin UI lebih responsif dan performa lebih stabil.
    - Code Readability: Dengan menggunakan const, kita bisa memberikan petunjuk ke developer lain kalau objek tersebut tidak akan berubah. Jadi, kode jadi lebih jelas dan terstruktur.

- Kapan sebaiknya kita menggunakan const:
    
    - Widget Statik: Kalau kita punya widget yang tidak akan berubah selama aplikasi berjalan, seperti Text, Container dengan warna latar yang tetap, atau ikon, gunakan const.
    - Immutable Object: Ketika kita tahu objek tersebut tidak akan mengalami perubahan atau tidak punya dependensi dinamis, gunakan const untuk membuatnya efisien.

- Kapan sebaiknya tidak menggunakan const:

    - Dependensi Dinamis: Kalau widget atau objek bergantung pada nilai yang akan berubah, seperti hasil input pengguna atau data dari API, jangan pakai const. Karena const mengunci nilai, widget dengan nilai dinamis tidak cocok menggunakan const.
    - Incompatibility with Late Changes: Kalau ada kemungkinan besar bahwa widget akan diubah atau dibangun ulang secara dinamis, const nggak diperlukan.


**2. Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!**

- Column :
    Column adalah widget yang menata anak-anaknya (child widgets) dari atas ke bawah. Ini cocok digunakan saat kita ingin menyusun elemen secara bertumpuk, seperti daftar item atau teks dengan ikon di bawahnya.

    - Implementasi:
    ```dart
    Column(
        mainAxisAlignment: MainAxisAlignment.center,
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
            Text('Hello, world!'),
            Icon(Icons.star, color: Colors.amber),
            Text('Welcome to Flutter!'),
        ],
        )
    ```

- Row :
    Row digunakan untuk menyusun widget secara horizontal, dari kiri ke kanan. Ini ideal saat kita ingin menampilkan elemen-elemen yang sejajar, seperti ikon dengan teks di sebelah kanannya.

    - Implementasi:
    ```dart
    Row(
        mainAxisAlignment: MainAxisAlignment.spaceBetween,
        crossAxisAlignment: CrossAxisAlignment.center,
        children: [
            Icon(Icons.favorite, color: Colors.pink),
            Text('Flutter is awesome!'),
            Icon(Icons.thumb_up, color: Colors.blue),
        ],
        )
    ```

| Perbandingan         | Column                                      | Row                                      |
|----------------------|---------------------------------------------|------------------------------------------|
| **Arah Layout**      | Vertikal (atas ke bawah)                    | Horizontal (kiri ke kanan)               |
| **Properti Utama**   | `mainAxisAlignment`, `crossAxisAlignment`   | `mainAxisAlignment`, `crossAxisAlignment`|
| **Contoh Penggunaan**| Tampilan daftar, teks bertumpuk             | Ikon dengan teks di sampingnya           |
| **Cocok Untuk**      | Layout yang mengalir dari atas ke bawah     | Layout yang mengalir dari kiri ke kanan  |


**3. Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!**

Elemen Input yang Digunakan :
1. TextFormField:

    - Fungsi: Digunakan untuk memasukkan teks umum seperti nama produk, deskripsi, dan harga.
    - Contoh Penggunaan di Form:
        - Ada TextFormField untuk mengisi nama produk, dengan hintText dan labelText diset ke "Product Name".
        - Variabel _name akan di-update ketika ada perubahan input, dan terdapat validator untuk memeriksa apakah nama produk tidak boleh kosong.

Elemen Input Lain di Flutter yang Tidak Digunakan :
1. Checkbox
2. Radio
3. Switch
4. Slider
5. DropdownButtonFormField
6. DatePicker

**4. Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?**

- Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? 

    Cara saya mengatur tema (theme) dalam aplikasi saya agar konsisten adalah menggunakan `ThemeData` didalam file `main.dart` untuk mengatur seluruh tema aplikasi yang saya buat. Contohnya ada pada di AppBar saya difile `productentry_form.dart` dan Drawer saya difile `left_drawer.dart`

- Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?
    
    Ya, saya mengimplementasikan tema berwarna merah pada aplikasi saya. Bisa dilihat pada `main.dart` saya sebagai berikut :
    ```dart
    theme: ThemeData(
         colorScheme: ColorScheme.fromSwatch(
                primarySwatch: Colors.red,
          ).copyWith(secondary: Colors.redAccent[600]),
          useMaterial3: true,
    )
    ```

**5. Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?**

Dengan membuat file baru didalam proyek saya yaitu `left_drawer.dart`. Pada file left_drawer.dart, terdapat penggunaan widget Drawer untuk menyediakan navigasi, yang digunakan sebagai panel navigasi samping. Dengan pendekatan ini, pengguna bisa mengakses beberapa halaman dari menu samping dan mengakses halaman lain seperti halaman utama dan halaman untuk menambahkan produk.

</details>