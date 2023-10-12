NAMA : RIZKY ANGKATA P. S.

NIM  : 2141720223

KELAS : TI-3A

PEMROGRAMAN MOBILE P7

*Praktikum 1*

Langkah 1: Buat Project Baru

Buatlah sebuah project flutter baru dengan nama layout_flutter. Atau sesuaikan style laporan praktikum yang Anda buat.

Langkah 2: Buka file lib/main.dart

Buka file main.dart lalu ganti dengan kode berikut. Isi nama dan NIM Anda di text title.

```
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter layout: Rizky Angkata dan 2141720223',
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Flutter layout demo'),
        ),
        body: const Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```
Output :

![image](https://github.com/RIZKYANGKATA/mobile_p7/assets/88949529/7ece65e7-f1d0-4596-8b12-9e5640a6e866)

Langkah 4: Implementasi title row

Pertama, Anda akan membuat kolom bagian kiri pada judul. Tambahkan kode berikut di bagian atas metode build() di dalam kelas MyApp:

```
Widget buildTitleSection() {
    return Container(
      padding: const EdgeInsets.all(16.0),
      child: Row(
        children: [
          Expanded(
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Container(
                  padding: const EdgeInsets.only(bottom: 8.0),
                  child: const Text(
                    'Telaga Sarangan',
                    style: TextStyle(
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                ),
                Text(
                  'Magetan, Jawa Timur, Indonesia',
                  style: TextStyle(
                    color: Colors.grey[500],
                  ),
                ),
              ],
            ),
          ),
          Icon(
            Icons.star,
            color: Colors.purple[500],
          ),
          const Text('41'),
        ],
      ),
    );
  }

  //PRAKTIKUM 2 LANGKAH 2
  Widget buildButtonSection(Color color) {
    return Row(
      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
      children: [
        _buildButtonColumn(color, Icons.call, 'CALL'),
        _buildButtonColumn(color, Icons.near_me, 'ROUTE'),
        _buildButtonColumn(color, Icons.share, 'SHARE'),
      ],
    );
  }
```
Output : 

![image](https://github.com/RIZKYANGKATA/mobile_p7/assets/88949529/926e7b44-d44b-456e-b9cd-76af0bfb8811)

*Praktium 2*

Langkah 1: Buat method Column _buildButtonColumn

Bagian tombol berisi 3 kolom yang menggunakan tata letak yang sama—sebuah ikon di atas baris teks. Kolom pada baris ini diberi jarak yang sama, dan teks serta ikon diberi warna primer.

Karena kode untuk membangun setiap kolom hampir sama, buatlah metode pembantu pribadi bernama buildButtonColumn(), yang mempunyai parameter warna, Icon dan Text, sehingga dapat mengembalikan kolom dengan widgetnya sesuai dengan warna tertentu.

lib/main.dart (_buildButtonColumn)
```
Column _buildButtonColumn(Color color, IconData icon, String label) {
    return Column(
      mainAxisSize: MainAxisSize.min,
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Icon(icon, color: color),
        Container(
          margin: const EdgeInsets.only(top: 8),
          child: Text(
            label,
            style: TextStyle(
              fontSize: 12,
              fontWeight: FontWeight.w400,
              color: color,
            ),
          ),
        ),
      ],
    );
  }
```
Langkah 2: Buat widget buttonSection

Buat Fungsi untuk menambahkan ikon langsung ke kolom. Teks berada di dalam Container dengan margin hanya di bagian atas, yang memisahkan teks dari ikon.

Bangun baris yang berisi kolom-kolom ini dengan memanggil fungsi dan set warna, Icon, dan teks khusus melalui parameter ke kolom tersebut. Sejajarkan kolom di sepanjang sumbu utama menggunakan MainAxisAlignment.spaceEvenly untuk mengatur ruang kosong secara merata sebelum, di antara, dan setelah setiap kolom. Tambahkan kode berikut tepat di bawah deklarasi titleSection di dalam metode build():

lib/main.dart (buttonSection)
```
Widget buildButtonSection(Color color) {
    return Row(
      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
      children: [
        _buildButtonColumn(color, Icons.call, 'CALL'),
        _buildButtonColumn(color, Icons.near_me, 'ROUTE'),
        _buildButtonColumn(color, Icons.share, 'SHARE'),
      ],
    );
  }
```
Output : 

![image](https://github.com/RIZKYANGKATA/mobile_p7/assets/88949529/3cf9751f-9291-409e-ad50-302e4e44f2d8)

*Praktikum 3*

Langkah 1: Buat widget textSection

Tentukan bagian teks sebagai variabel. Masukkan teks ke dalam Container dan tambahkan padding di sepanjang setiap tepinya. Tambahkan kode berikut tepat di bawah deklarasi buttonSection:
```
Widget buildTextSection() {
    return Container(
      padding: const EdgeInsets.all(32),
      child: const Text(
        'Telaga Sarangan adalah sebuah tempat wisata alam yang menakjubkan di kawasan Magetan, Kabupaten'
        ' Magetan, Indonesia. Destinasi ini terkenal karena danau kawahnya yang memiliki air berwarna hijau'
        ' yang dihasilkan oleh kandungan belerang dan mineral lainnya yang larut dalam air.' 
        ' Pemandangan kawah yang memukau, dengan latar belakang hutan tropis, membuatnya menjadi tempat yang' 
        ' sangat populer bagi para pengunjung yang mencari kedamaian dan keindahan alam. Selain menikmati' 
        ' kecantikan alamnya, wisatawan juga dapat menjelajahi area sekitarnya, berjalan-jalan di tepi danau,' 
        ' atau hanya duduk bersantai sambil menikmati udara segar dan pemandangan yang menenangkan di Kawah'
        ' Telaga Sarangan.',
        softWrap: true,
      ),
    );
  }
```
Output :

![image](https://github.com/RIZKYANGKATA/mobile_p7/assets/88949529/25a902e7-0e6c-4d3d-b8dc-67dc8ff174b3)

*Praktikum 4*

Langkah 1: Siapkan aset gambar

Anda dapat mencari gambar di internet yang ingin ditampilkan. Buatlah folder images di root project layout_flutter. Masukkan file gambar tersebut ke folder images, lalu set nama file tersebut ke file pubspec.yaml 
```
flutter:
  assets:
    - assets/images/ts.jpeg
```

Langkah 2: Tambahkan gambar ke body

Tambahkan aset gambar ke dalam body

Langkah 3: Terakhir, ubah menjadi ListView

Pada langkah terakhir ini, atur semua elemen dalam ListView, bukan Column, karena ListView mendukung scroll yang dinamis saat aplikasi dijalankan pada perangkat yang resolusinya lebih kecil.
```
 body: ListView(
          children: [
            Image.asset(
              'images/ts.jpeg',
              width: 600,
              height: 240,
              fit: BoxFit.cover,
            ),
```
Output :

![image](https://github.com/RIZKYANGKATA/mobile_p7/assets/88949529/c197a25e-6b7b-443e-87e7-835bd356f90d)









