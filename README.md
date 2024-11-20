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
# Tugas 8 - Trias Fahri Naufal


1. Kegunaan const di Flutter

const di Flutter digunakan untuk mendeklarasikan konstanta yang nilainya tetap dan diketahui pada waktu compile.

Keuntungan Menggunakan const

  1. Optimisasi Performa: Widget yang dideklarasikan sebagai const hanya dibuat sekali dan dapat digunakan kembali tanpa perlu dibuat ulang, sehingga mengurangi beban pada garbage collector.
  2. Immutability: Nilai yang dideklarasikan sebagai const tidak dapat diubah, sehingga membantu mencegah perubahan yang tidak disengaja.
  3. Peningkatan Kecepatan Kompilasi: Karena nilai const diketahui pada waktu kompilasi, Dart dapat melakukan optimisasi yang lebih baik, sehingga meningkatkan kecepatan kompilasi.

Kapan Sebaiknya Menggunakan const

  1. Gunakan const ketika nilai tidak akan berubah selama runtime dan dapat diketahui pada waktu kompilasi.
  2. Gunakan const untuk widget yang tidak memerlukan perubahan state atau properti dinamis.

  Kapan Sebaiknya Tidak Menggunakan const

  Jangan gunakan const untuk nilai yang akan berubah selama runtime atau yang bergantung pada input pengguna atau data dinamis.

2. Perbandingan Penggunaan Column dan Row pada Flutter
Column dan Row adalah widget placement dasar di Flutter yang digunakan untuk menyusun widget anak secara vertikal dan horizontal.

a. Column

Fungsi: Menyusun widget anak secara vertikal.
Properti Utama: mainAxisAlignment, crossAxisAlignment, children.
contoh:
```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
  children: [
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
)
```

b. Row

Fungsi: Menyusun widget anak secara horizontal.
Properti Utama: mainAxisAlignment, crossAxisAlignment, children.
contoh:
```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  crossAxisAlignment: CrossAxisAlignment.center,
  children: [
    Icon(Icons.star),
    Icon(Icons.star),
    Icon(Icons.star),
  ],
)
```

3. Elemen Input yang Digunakan pada Halaman Form

Elemen input yang digunakan adalah TextFormField-> Untuk input teks seperti nama produk, deskripsi, dan harga.

Elemen Input Flutter Lain yang Tidak Digunakan:

Checkbox: Untuk input boolean.
Radio: Untuk memilih satu dari beberapa opsi.
Switch: Untuk input boolean dengan tampilan switch.
Slider: Untuk input nilai numerik dalam rentang tertentu.
DropdownButton: Untuk memilih satu dari beberapa opsi dalam bentuk dropdown.

4. Mengatur Tema dalam Aplikasi Flutter
Untuk mengatur tema dalam aplikasi Flutter agar konsisten, gunakan ThemeData dan tentukan properti seperti warna, text style, dan elemen desain lainnya.
contoh penggunaan pada aplikasi ini
```dart
      theme: ThemeData(
        colorScheme: ColorScheme.fromSwatch(
          primarySwatch: Colors.deepPurple,
        ).copyWith(secondary: Colors.deepPurple[400]),
        useMaterial3: true,
      ),
      home: MyHomePage(),
```

5. Menangani Navigasi dalam Aplikasi dengan Banyak Halaman
Untuk menangani navigasi dalam aplikasi dengan banyak halaman, gunakan Navigator dan Route di Flutter.
contoh
```dart
// Navigasi ke halaman baru
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => SecondPage()),
);

// Kembali ke halaman sebelumnya
Navigator.pop(context);
```
# Tugas 9 - Trias Fahri Naufal
  1. Mengapa Kita Perlu Membuat Model untuk Pengambilan atau Pengiriman Data JSON?
  Membuat model untuk pengambilan atau pengiriman data JSON sangat penting karena:

  Struktur Data yang Konsisten: Model memastikan bahwa data yang diterima atau dikirim memiliki struktur yang konsisten. Ini membantu dalam menghindari kesalahan yang mungkin terjadi karena data yang tidak terstruktur dengan baik.

  Validasi Data: Model dapat digunakan untuk memvalidasi data yang diterima atau dikirim. Ini memastikan bahwa data yang diproses adalah valid dan sesuai dengan yang diharapkan.

  Kemudahan Penggunaan: Dengan model, kita dapat dengan mudah mengakses dan memanipulasi data. Model menyediakan metode dan properti yang memudahkan pengolahan data.

  Pemeliharaan Kode: Model membuat kode lebih mudah dipelihara dan dibaca. Dengan model, kita dapat dengan mudah memahami struktur data dan bagaimana data tersebut digunakan dalam aplikasi.

  Jika kita tidak membuat model terlebih dahulu, kita mungkin tidak akan mendapatkan error langsung, tetapi akan lebih sulit untuk mengelola dan memproses data. Tanpa model, kita harus mengakses data secara langsung dari JSON, yang bisa menyebabkan kesalahan jika struktur data berubah atau jika data tidak valid.

  2. Fungsi dari Library http
  Library http dalam Flutter digunakan untuk melakukan permintaan HTTP ke server. Berikut adalah beberapa fungsi utama dari library http yang telah diimplementasikan dalam tugas ini:

  Mengirim Permintaan HTTP:

  GET Request: Digunakan untuk mengambil data dari server. Misalnya, mengambil daftar produk dari server.
  POST Request: Digunakan untuk mengirim data ke server. Misalnya, mengirim data registrasi pengguna atau login.
  Mengelola Respons HTTP:

  Membaca Data dari Respons: Data yang diterima dari server dapat dibaca dan diolah lebih lanjut.
  Mendukung Pemrograman Asinkronus:

  Library http mendukung pemrograman asinkron dengan menggunakan Future dan async/await. Ini memungkinkan aplikasi untuk mengirim permintaan HTTP tanpa memblokir thread utama, sehingga UI tetap responsif.
  Mengatur Header dan Body:

  Library http memungkinkan pengaturan header dan body pada permintaan HTTP. Ini penting untuk autentikasi, pengiriman data dalam format tertentu (seperti JSON), dan pengaturan lainnya.

  3. Fungsi dari CookieRequest
  CookieRequest adalah kelas yang digunakan untuk mengelola permintaan HTTP yang memerlukan autentikasi berbasis cookie. Fungsi utama dari CookieRequest adalah:

  Mengelola Cookie:

  CookieRequest menyimpan dan mengelola cookie yang diterima dari server. Cookie ini digunakan untuk autentikasi pada permintaan selanjutnya.
  Cookie disimpan dalam memori dan ditambahkan secara otomatis ke setiap permintaan HTTP yang memerlukannya.
  Mengirim Permintaan HTTP:

  CookieRequest dapat digunakan untuk mengirim permintaan HTTP seperti GET, POST, dll., dengan menyertakan cookie untuk autentikasi.
  Ini memastikan bahwa setiap permintaan yang memerlukan autentikasi dapat dilakukan tanpa perlu menambahkan cookie secara manual.
  Menyimpan Status Login:

  CookieRequest menyimpan status login pengguna, yang dapat digunakan untuk menentukan apakah pengguna sudah login atau belum.
  Ini memungkinkan aplikasi untuk menampilkan atau menyembunyikan konten berdasarkan status login pengguna.
  Mengapa Instance CookieRequest Perlu Dibagikan ke Semua Komponen di Aplikasi Flutter
  Konsistensi Autentikasi:

  Dengan membagikan instance CookieRequest, semua komponen dapat menggunakan cookie yang sama untuk autentikasi, memastikan konsistensi dalam status login pengguna.
  Ini penting untuk menjaga sesi pengguna tetap aktif dan memastikan bahwa semua permintaan yang memerlukan autentikasi dapat dilakukan dengan benar.
  Kemudahan Akses:

  Membagikan instance CookieRequest memudahkan komponen untuk mengakses dan mengirim permintaan HTTP yang memerlukan autentikasi.
  Komponen tidak perlu membuat instance CookieRequest baru setiap kali mereka perlu mengirim permintaan HTTP, yang mengurangi duplikasi kode dan potensi kesalahan.
  Pengelolaan Sesi yang Efisien:

  Dengan satu instance CookieRequest, pengelolaan sesi menjadi lebih efisien karena cookie dan status login disimpan di satu tempat.
  Ini juga memudahkan untuk mengelola logout pengguna, karena cukup menghapus cookie dari satu instance CookieRequest.
  4. 
  Input Data: Pengguna memasukkan data melalui elemen input di Flutter.
  Mengirim Data ke Server: Data dikirim ke server menggunakan permintaan HTTP.
  Memproses Data di Server: Server memproses data dan menyimpannya ke database.
  Menerima Respons di Flutter: Aplikasi Flutter menerima respons dari server.
  Mengambil Data dari Server: Data yang telah disimpan di server diambil kembali untuk ditampilkan.
  Menampilkan Data di Flutter: Data ditampilkan di UI Flutter menggunakan widget yang sesuai.
  5. 
  Register:

  Pengguna memasukkan data akun di Flutter.
  Data dikirim ke server Django.
  Django memproses data dan membuat akun baru.
  Flutter menerima respons dan menampilkan pesan sukses atau gagal.

  Login:

  Pengguna memasukkan username dan password di Flutter.
  Data dikirim ke server Django.
  Django memverifikasi kredensial dan membuat sesi.
  Flutter menyimpan cookie sesi dan menampilkan menu utama.

  Logout:

  Flutter mengirim permintaan logout ke server Django.
  Django menghapus sesi.
  Flutter menghapus cookie sesi dan mengarahkan pengguna ke halaman login.

  ## Implementasi Checklist
  1. Mengimplementasikan Fitur Registrasi Akun pada Proyek Tugas Flutter
    1. Membuat Halaman Registrasi di Flutter:

    Buat halaman baru RegisterPage di Flutter.
    Tambahkan elemen input untuk username, password, dan konfirmasi password menggunakan TextFormField.
    Tambahkan tombol ElevatedButton untuk mengirim data registrasi.

  2. Membuat Endpoint Registrasi di Django:
  Buat view untuk menangani registrasi pengguna di Django.
    1. Membuat Halaman Login pada Proyek Tugas Flutter
      Membuat Halaman Login di Flutter:

    Buat halaman baru LoginPage di Flutter.
    Tambahkan elemen input untuk username dan password menggunakan TextFormField.
    Tambahkan tombol ElevatedButton untuk mengirim data login.
    2. Membuat Endpoint Login di Django:
    Buat view untuk menangani login pengguna di Django.
  3. Mengintegrasikan Sistem Autentikasi Django dengan Proyek Tugas Flutter
    1. Menggunakan CookieRequest di Flutter:
    Pastikan CookieRequest digunakan untuk mengelola permintaan HTTP yang memerlukan autentikasi.
    2. Mengelola Status Login di Flutter:
    Gunakan CookieRequest untuk menyimpan status login pengguna dan mengelola sesi.
  4. Membuat Model Kustom Sesuai dengan Proyek Aplikasi Django
    1. Membuat Model di Django:
    Buat model kustom sesuai dengan kebutuhan aplikasi di Django.
    2. Membuat Serializer untuk Model di Django:
    Buat serializer untuk mengonversi model ke format JSON.
    3. Membuat View untuk Mengelola Data di Django:
    Buat view untuk mengelola data model, seperti mengambil, menambah, mengubah, dan menghapus data.
    4. Mengambil dan Menampilkan Data di Flutter:
    Gunakan http atau CookieRequest untuk mengambil data dari server dan menampilkannya di Flutter.