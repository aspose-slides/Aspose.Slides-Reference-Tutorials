---
"date": "2025-04-15"
"description": "Pelajari cara menambahkan diagram lingkaran secara terprogram ke presentasi Anda dengan Aspose.Slides untuk .NET, meningkatkan visualisasi data dengan mudah."
"title": "Membuat Diagram Lingkaran di PowerPoint menggunakan Aspose.Slides untuk .NET"
"url": "/id/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat dan Menambahkan Diagram Lingkaran ke Presentasi Menggunakan Aspose.Slides untuk .NET
## Perkenalan
Membuat presentasi yang menarik sering kali melibatkan lebih dari sekadar teks; elemen visual seperti diagram dapat secara signifikan meningkatkan dampak penceritaan data Anda. Jika Anda ingin menambahkan diagram pai dinamis ke presentasi PowerPoint Anda secara terprogram, **Aspose.Slides untuk .NET** adalah alat hebat yang membuat tugas ini lancar dan efisien. Tutorial ini akan memandu Anda menambahkan diagram pai ke slide presentasi dan mengonfigurasinya dengan sumber data eksternal.

### Apa yang Akan Anda Pelajari
- Cara membuat presentasi baru menggunakan Aspose.Slides untuk .NET
- Menambahkan diagram lingkaran ke slide pertama Anda
- Menetapkan URL buku kerja eksternal sebagai sumber data untuk bagan Anda
- Menyimpan presentasi Anda dalam format PPTX
Mari kita bahas bagaimana Anda dapat mencapainya dengan mudah, dimulai dengan prasyarat.
## Prasyarat
Sebelum kita mulai, pastikan Anda telah menyiapkan hal-hal berikut:
- **Aspose.Slides untuk .NET** pustaka yang terpasang. Anda memerlukan versi yang kompatibel dengan .NET Framework atau .NET Core/.NET 5+.
- Pengetahuan dasar tentang pemrograman C# dan keakraban dengan Visual Studio IDE.
- Lingkungan pengembangan yang disiapkan di komputer Anda (Windows, macOS, atau Linux).
## Menyiapkan Aspose.Slides untuk .NET
### Petunjuk Instalasi
Aspose.Slides untuk .NET dapat ditambahkan ke proyek Anda menggunakan berbagai metode:
**.KLIK NET**
```shell
dotnet add package Aspose.Slides
```
**Konsol Pengelola Paket**
```powershell
Install-Package Aspose.Slides
```
**Antarmuka Pengguna Pengelola Paket NuGet**
1. Buka NuGet Package Manager di Visual Studio.
2. Cari "Aspose.Slides".
3. Instal versi terbaru.
### Akuisisi Lisensi
Untuk menggunakan Aspose.Slides, Anda dapat memulai dengan lisensi uji coba gratis untuk menjelajahi fitur-fiturnya tanpa batasan. Untuk lingkungan produksi, pertimbangkan untuk membeli lisensi komersial atau memperoleh lisensi sementara untuk pengujian yang lebih lama. Kunjungi [Halaman pembelian Aspose](https://purchase.aspose.com/buy) untuk lebih jelasnya.
### Inisialisasi Dasar
Untuk menggunakan Aspose.Slides di proyek Anda, Anda perlu menginisialisasinya dengan lisensi Anda jika tersedia:
```csharp
// Inisialisasi perpustakaan
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Panduan Implementasi
Sekarang Anda sudah menyiapkannya, mari kita bahas setiap fitur langkah demi langkah.
### Membuat dan Menambahkan Bagan ke Presentasi
#### Ringkasan
Kita akan mulai dengan membuat presentasi dan menambahkan diagram lingkaran ke slide pertama.
#### Tangga:
1. **Inisialisasi Presentasi**
   Mulailah dengan membuat contoh `Presentation` kelas, yang mewakili berkas PowerPoint Anda.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // Di sinilah kita akan menambahkan bagan kita.
   }
   ```
2. **Tambahkan Diagram Lingkaran**
   Gunakan `Shapes.AddChart` metode untuk menyisipkan diagram lingkaran pada koordinat tertentu pada slide Anda.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Mengatur Buku Kerja Eksternal untuk Data Bagan
#### Ringkasan
Sekarang mari konfigurasikan diagram lingkaran untuk menggunakan data dari buku kerja eksternal.
#### Tangga:
1. **Akses Data Bagan**
   Ambil antarmuka data bagan tempat Anda akan menentukan URL sumber data eksternal Anda.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **Tetapkan URL Buku Kerja Eksternal**
   Tetapkan URL untuk sumber data Anda menggunakan `SetExternalWorkbook`Contoh ini menggunakan URL pengganti, yang harus diganti dengan jalur sumber data Anda yang sebenarnya.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://jalur/tidak/ada", salah);
   ```
### Simpan Presentasi ke File
#### Ringkasan
Terakhir, simpan presentasi dalam format PPTX ke lokasi yang Anda inginkan.
#### Tangga:
1. **Simpan Presentasi**
   Gunakan `Save` metode dari `Presentation` kelas untuk menulis berkas ke disk.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Aplikasi Praktis
- **Laporan Bisnis**: Secara otomatis membuat bagan untuk tinjauan kinerja triwulan.
- **Dasbor Data**: Integrasikan dengan sumber data untuk memperbarui laporan visual secara real-time.
- **Konten Edukasi**Buat presentasi dinamis yang menarik data terkini dari studi eksternal atau makalah penelitian.
Dengan mengintegrasikan Aspose.Slides, Anda dapat mengotomatiskan dan meningkatkan proses pembuatan presentasi Anda di berbagai domain.
## Pertimbangan Kinerja
Saat bekerja dengan kumpulan data besar atau banyak grafik:
- Optimalkan penggunaan sumber daya dengan mengelola memori secara efektif dalam .NET.
- Buang `Presentation` objek dengan benar untuk membebaskan sumber daya.
- Gunakan operasi asinkron jika memungkinkan untuk meningkatkan respons aplikasi.
## Kesimpulan
Dengan mengikuti tutorial ini, Anda telah mempelajari cara membuat presentasi dengan diagram lingkaran secara terprogram menggunakan Aspose.Slides for .NET. Kini Anda memiliki alat untuk mengotomatiskan pembuatan diagram dan mengelola sumber data eksternal secara efisien.
### Langkah Berikutnya
Jelajahi lebih jauh dengan menyesuaikan gaya bagan, menambahkan lebih banyak jenis bagan, atau mengintegrasikan komponen Aspose lainnya seperti Aspose.Cells untuk kemampuan manipulasi data yang lebih baik.
## Bagian FAQ
1. **Apa itu Aspose.Slides?**  
   Pustaka yang tangguh untuk memanipulasi presentasi PowerPoint secara terprogram dalam .NET.
2. **Bisakah saya menggunakan Aspose.Slides tanpa lisensi?**  
   Ya, tetapi ada batasannya. Pertimbangkan untuk mendapatkan uji coba gratis atau membeli lisensi untuk fitur lengkap.
3. **Bagaimana cara memperbarui data grafik secara dinamis?**  
   Memanfaatkan buku kerja eksternal dan mengatur URL mereka di `SetExternalWorkbook` metode.
4. **Bisakah Aspose.Slides digunakan di banyak platform?**  
   Ya, ini mendukung .NET Framework dan .NET Core/.NET 5+ di Windows, macOS, dan Linux.
5. **Jenis grafik apa lagi yang didukung?**  
   Selain diagram lingkaran, Anda dapat membuat diagram batang, diagram garis, dan lainnya dengan Aspose.Slides.
## Sumber daya
- [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Unduh Versi Terbaru](https://releases.aspose.com/slides/net/)
- [Beli Lisensi](https://purchase.aspose.com/buy)
- [Uji Coba Gratis](https://releases.aspose.com/slides/net/)
- [Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- [Forum Dukungan](https://forum.aspose.com/c/slides/11)
Mulailah mengintegrasikan Aspose.Slides ke dalam proyek Anda hari ini untuk menyempurnakan dan mengotomatiskan presentasi PowerPoint Anda!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}