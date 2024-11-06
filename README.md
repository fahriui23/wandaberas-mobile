# Tugas 7 - Trias Fahri Naufal
1. Dalam Flutter, terdapat dua jenis widget utama: StatelessWidget dan StatefulWidget. Berikut adalah perbedaan utama antara keduanya:

## StatelessWidget
Tidak memiliki state: StatelessWidget tidak dapat berubah setelah dibuat. Semua properti yang dimiliki bersifat final.
Sederhana: Digunakan untuk widget yang tidak memerlukan perubahan data atau tampilan selama siklus hidupnya.
Contoh: Widget seperti Text, Icon, dan RaisedButton biasanya adalah StatelessWidget.

```dart
class MyStatelessWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text('I am a StatelessWidget');
  }
}
```
## StatefulWidget
Memiliki state: StatefulWidget dapat berubah selama siklus hidupnya. Perubahan ini dikelola oleh objek State yang terkait.
Kompleks: Digunakan untuk widget yang memerlukan perubahan data atau tampilan, seperti input pengguna, animasi, atau data yang diperbarui secara dinamis.
Contoh: Widget seperti Checkbox, TextField, dan Slider biasanya adalah StatefulWidget.

```dart
class MyStatefulWidget extends StatefulWidget {
  @override
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
}

class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Counter: $_counter'),
        ElevatedButton(
          onPressed: _incrementCounter,
          child: Text('Increment'),
        ),
      ],
    );
  }
}
```

2. 

### Scaffold
Fungsi: Menyediakan struktur dasar untuk halaman aplikasi, termasuk AppBar, Body, dan FloatingActionButton.

### AppBar
Fungsi: Menampilkan bar di bagian atas halaman yang biasanya berisi judul dan tindakan (actions).

### Padding
Fungsi: Menambahkan ruang di sekitar widget anak (child) untuk memberikan jarak.

### Column
Fungsi: Menyusun widget anak secara vertikal.

### Row
Fungsi: Menyusun widget anak secara horizontal.

### Text
Fungsi: Menampilkan teks pada layar.

### ElevatedButton
Fungsi: Menampilkan tombol yang dapat ditekan dengan efek elevasi.

### Card
Fungsi: Menampilkan kotak dengan bayangan di bawahnya untuk memberikan efek elevasi.

### GridView
Fungsi: Menyusun widget anak dalam bentuk grid.

### Material
Fungsi: Menyediakan efek material seperti bayangan dan bentuk melengkung.

### InkWell
Fungsi: Menambahkan efek sentuhan (tap) pada widget anak.

### Container
Fungsi: Menyediakan kotak untuk menyusun widget anak dengan properti seperti padding, margin, dan ukuran.

### Icon
Fungsi: Menampilkan ikon dari pustaka ikon yang tersedia di Flutter.

### SizedBox
Fungsi: Menyediakan kotak dengan ukuran tetap untuk memberikan jarak atau ukuran tertentu.

### Center
Fungsi: Menyusun widget anak di tengah widget induk.

### SnackBar
Fungsi: Menampilkan pesan sementara di bagian bawah layar.

### MediaQuery
Fungsi: Menyediakan informasi tentang ukuran dan orientasi layar.

### Theme
Fungsi: Menyediakan akses ke tema aplikasi, seperti warna dan gaya teks.

3. Fungsi setState()

Fungsi setState() dalam Flutter digunakan untuk memberitahu framework bahwa ada perubahan pada state yang memerlukan pembaruan tampilan (UI). Ketika setState() dipanggil, Flutter akan menjalankan ulang metode build() dari widget yang bersangkutan, sehingga tampilan dapat diperbarui sesuai dengan perubahan state.

4.  Perbedaan Utama

Waktu nilai ditentukan: nilai final ditentukan saat runtime, sedangkan const ditentukan saat compile-time.
Penggunaan: final digunakan untuk nilai yang ditentukan saat runtime dan tidak berubah setelah inisialisasi, sedangkan const digunakan untuk nilai yang diketahui dan tetap pada waktu kompilasi.
Instance Variables: final dapat digunakan untuk variabel instance, sedangkan const tidak dapat digunakan untuk variabel instance kecuali jika variabel tersebut adalah static const.

Contoh Penggunaan

```dart
void main() {
  final DateTime now = DateTime.now();
  const double pi = 3.14159;

  final DateTime now = DateTime.now();
  final String name = 'John Doe';
}
```

5. Step implementasi checklist

    1. Buat proyek flutter baru dengan kode berikut
    ```dart
    flutter create WandaBeras
    cd WandaBeras
    ```
    2. Membuat Tiga Tombol Sederhana dengan Ikon dan Teks
    Pindahkan MyHomePage ke menu.dart. Pada class ItemCard, tambahkan button "Lihat Daftar Produk", "Tambah Produk", dan "Logout".
    3. Jadikan color menjadi salah satu parameter di ItemCard untuk memberikan warna yang berbeda untuk setiap tombol.
    4. Tambahkan action onTap pada InkWell di dalam ItemCard untuk memunculkan SnackBar dengan pesan yang sesuai ketika tombol ditekan.