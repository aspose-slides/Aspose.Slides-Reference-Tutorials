---
"date": "2025-04-15"
"description": "Pelajari cara membuat dan menyesuaikan diagram donat dengan mudah dalam presentasi PowerPoint menggunakan Aspose.Slides for .NET. Sempurnakan presentasi data visual Anda dengan panduan lengkap ini."
"title": "Cara Membuat Bagan Donat di PowerPoint Menggunakan Aspose.Slides untuk .NET&#58; Panduan Langkah demi Langkah"
"url": "/id/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Bagan Donat di PowerPoint Menggunakan Aspose.Slides untuk .NET: Panduan Langkah demi Langkah

## Perkenalan

Meningkatkan presentasi PowerPoint Anda dengan bagan donat yang menarik secara visual dapat meningkatkan cara Anda menyajikan data secara signifikan. Aspose.Slides for .NET menyediakan cara yang efisien untuk membuat dan menyesuaikan bagan ini. Tutorial ini akan memandu Anda melalui langkah-langkah penggunaan Aspose.Slides for .NET untuk menambahkan bagan donat yang dapat disesuaikan, termasuk menyesuaikan ukuran lubang, ke slide PowerPoint Anda.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk .NET
- Langkah-langkah untuk menambahkan diagram donat ke slide Anda
- Teknik untuk mengonfigurasi ukuran lubang pada diagram donat Anda
- Aplikasi praktis dan pertimbangan kinerja

Mari kita mulai dengan apa yang Anda butuhkan sebelum menyelaminya!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki persyaratan berikut:

### Pustaka dan Versi yang Diperlukan
- Aspose.Slides untuk .NET (versi terbaru)
- Visual Studio atau IDE kompatibel apa pun yang mendukung pengembangan .NET

### Persyaratan Pengaturan Lingkungan
- Lingkungan Windows dengan .NET Framework terinstal
- Pengetahuan dasar pemrograman C#

## Menyiapkan Aspose.Slides untuk .NET

Untuk memulai, Anda perlu memasang pustaka Aspose.Slides. Berikut ini cara melakukannya dengan menggunakan berbagai metode:

**Menggunakan .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Menggunakan Konsol Manajer Paket:**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet:**
Cari "Aspose.Slides" dan instal versi terbaru langsung melalui antarmuka NuGet IDE Anda.

### Langkah-langkah Memperoleh Lisensi
1. **Uji Coba Gratis:** Mulailah dengan mengunduh uji coba gratis untuk mengevaluasi fitur.
2. **Lisensi Sementara:** Jika Anda memerlukan lebih banyak waktu, mintalah lisensi sementara dari Aspose.
3. **Pembelian:** Untuk penggunaan jangka panjang, pertimbangkan untuk membeli versi lengkap.

Setelah terinstal, inisialisasi proyek Anda dengan pengaturan dasar ini:
```csharp
using Aspose.Slides;

// Inisialisasi objek Presentasi baru
Presentation presentation = new Presentation();
```

## Panduan Implementasi

Mari kita uraikan proses pembuatan bagan donat menggunakan Aspose.Slides untuk .NET menjadi langkah-langkah yang dapat dikelola.

### Membuat Bagan Donat

#### Ringkasan
Kita akan mulai dengan menambahkan bagan donat ke slide PowerPoint Anda, mengatur posisi dan ukurannya.

**Menambahkan Bagan:**
```csharp
using Aspose.Slides.Charts;

// Akses slide pertama dalam presentasi (secara default, satu slide dibuat)
ISlide slide = presentation.Slides[0];

// Tambahkan diagram donat ke slide pada posisi (50, 50) dengan lebar dan tinggi 400 unit
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **Parameternya:** `ChartType.Doughnut`, posisi x: 50, posisi y: 50, lebar: 400, tinggi: 400.

### Mengatur Ukuran Lubang

#### Ringkasan
Berikutnya, kita akan mengonfigurasi ukuran lubang pada bagan donat agar menarik secara visual.

**Mengonfigurasi Ukuran Lubang:**
```csharp
// Atur ukuran lubang untuk diagram donat menjadi 90%
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **Konfigurasi Kunci:** `DoughnutHoleSize` menentukan seberapa banyak bagian tengah yang "dipotong." Nilai antara 0 dan 100 menunjukkan persentase.

### Simpan Presentasi Anda

Terakhir, simpan perubahan Anda ke file PowerPoint baru:
```csharp
// Tentukan jalur tempat presentasi akan disimpan
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// Simpan presentasi yang dimodifikasi dalam format PPTX
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **Catatan:** Mengganti `YOUR_OUTPUT_DIRECTORY` dengan lokasi berkas yang Anda inginkan.

### Tips Pemecahan Masalah

- Pastikan Aspose.Slides terinstal dan diimpor dengan benar.
- Verifikasi bahwa jalur direktori keluaran Anda ada sebelum menyimpan presentasi.

## Aplikasi Praktis

Bagan donat yang dibuat dengan Aspose.Slides untuk .NET dapat digunakan dalam berbagai skenario:

1. **Laporan Bisnis:** Mengilustrasikan data keuangan seperti alokasi anggaran atau distribusi penjualan.
2. **Analisis Pemasaran:** Menampilkan persentase pangsa pasar di antara berbagai merek.
3. **Materi Pendidikan:** Digunakan untuk menjelaskan konsep statistik dengan cara yang menarik secara visual.

Integrasikan Aspose.Slides dengan sistem lain untuk pembuatan dan pendistribusian laporan otomatis dalam lingkungan perusahaan.

## Pertimbangan Kinerja

Saat bekerja dengan presentasi besar atau banyak bagan, pertimbangkan kiat berikut:

- Optimalkan pemrosesan data sebelum menambahkannya ke slide.
- Gunakan kembali objek presentasi jika memungkinkan untuk menghemat memori.
- Perbarui pustaka Aspose.Slides Anda secara berkala untuk mendapatkan manfaat peningkatan kinerja.

## Kesimpulan

Anda telah mempelajari cara membuat dan menyesuaikan diagram donat menggunakan Aspose.Slides for .NET. Alat serbaguna ini meningkatkan daya tarik visual presentasi Anda, membuat data lebih mudah dipahami sekilas.

**Langkah Berikutnya:**
Jelajahi jenis bagan lain yang tersedia di Aspose.Slides atau pelajari fitur-fitur lanjutan seperti animasi.

Siap untuk mencobanya? Kunjungi bagian sumber daya di bawah ini dan mulailah bereksperimen!

## Bagian FAQ

1. **Untuk apa Aspose.Slides for .NET digunakan?**  
   Ini adalah pustaka untuk membuat, memodifikasi, dan mengonversi presentasi PowerPoint secara terprogram.

2. **Bagaimana cara mengubah warna segmen donat?**  
   Menggunakan `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` untuk menyesuaikan properti pengisian.

3. **Bisakah saya membuat beberapa bagan dalam satu presentasi?**  
   Ya, tambahkan bagan sebanyak yang diperlukan dengan mengulangi langkah-langkah pembuatan bagan pada slide atau posisi yang berbeda.

4. **Bagaimana cara melisensikan Aspose.Slides for .NET untuk penggunaan komersial?**  
   Beli lisensi melalui situs web resmi Aspose untuk menggunakannya secara komersial.

5. **Apa yang harus saya lakukan jika presentasi saya tidak tersimpan dengan benar?**  
   Periksa izin jalur file dan pastikan referensi proyek Anda mutakhir.

## Sumber daya

- [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Unduh Aspose.Slides untuk .NET](https://releases.aspose.com/slides/net/)
- [Beli Lisensi](https://purchase.aspose.com/buy)
- [Versi Uji Coba Gratis](https://releases.aspose.com/slides/net/)
- [Permintaan Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- [Forum Dukungan](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}