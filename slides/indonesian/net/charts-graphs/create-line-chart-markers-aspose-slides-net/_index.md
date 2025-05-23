---
"date": "2025-04-15"
"description": "Pelajari cara membuat diagram garis dengan penanda menggunakan Aspose.Slides for .NET. Panduan langkah demi langkah ini mencakup pengaturan, pembuatan diagram, dan penyesuaian."
"title": "Cara Membuat Grafik Garis dengan Penanda di C# Menggunakan Aspose.Slides untuk .NET"
"url": "/id/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Grafik Garis dengan Penanda di C# Menggunakan Aspose.Slides untuk .NET

## Perkenalan
Membuat diagram garis yang menarik secara visual dan informatif sangat penting untuk penyajian data yang efektif dalam C#. **Aspose.Slides untuk .NET** menyederhanakan proses penambahan bagan yang tampak profesional, termasuk bagan yang memiliki penanda. Tutorial ini akan memandu Anda membuat bagan garis dengan penanda default menggunakan Aspose.Slides for .NET.

Dalam tutorial ini, Anda akan mempelajari:
- Menyiapkan lingkungan Anda untuk menggunakan Aspose.Slides untuk .NET.
- Membuat dan menyesuaikan presentasi dengan diagram garis yang menyertakan penanda.
- Mengonfigurasi properti bagan seperti kategori, seri, dan titik data.
- Menyimpan berkas presentasi akhir.

Mari kita mulai dengan meninjau prasyarat yang diperlukan sebelum menerapkan solusi kita.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
- **Pustaka yang dibutuhkan:** Aspose.Slides untuk .NET diinstal di lingkungan pengembangan Anda melalui NuGet.
- **Persyaratan Pengaturan Lingkungan:** Lingkungan pengembangan C# yang berfungsi seperti Visual Studio dan kerangka kerja .NET yang terinstal di komputer Anda.
- **Prasyarat Pengetahuan:** Pemahaman dasar tentang pemrograman C# dan keakraban dalam membuat presentasi secara terprogram.

## Menyiapkan Aspose.Slides untuk .NET
### Informasi Instalasi
Untuk mulai menggunakan Aspose.Slides untuk .NET, tambahkan ke proyek Anda melalui salah satu metode berikut:

**Menggunakan .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Melalui Konsol Manajer Paket di Visual Studio:**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet:**
- Buka solusi Anda di Visual Studio.
- Buka "Kelola Paket NuGet untuk Solusi..."
- Cari "Aspose.Slides" dan instal versi terbaru.

### Akuisisi Lisensi
Sebelum menggunakan Aspose.Slides, dapatkan uji coba atau beli lisensi:
1. **Uji Coba Gratis:** Mengunjungi [Halaman Uji Coba Gratis Aspose](https://releases.aspose.com/slides/net/) untuk memulai dengan cepat.
2. **Lisensi Sementara:** Untuk akses lebih lanjut, kunjungi [Halaman Lisensi Sementara](https://purchase.aspose.com/temporary-license/).
3. **Pembelian:** Untuk menggunakan Aspose.Slides dalam produksi, beli lisensi di [Aspose Pembelian](https://purchase.aspose.com/buy).

### Inisialisasi Dasar
Setelah menyiapkan proyek Anda dan memperoleh lisensi yang diperlukan, inisialisasi Aspose.Slides sebagai berikut:
```csharp
using Aspose.Slides;
// Buat instance kelas Presentasi
Presentation pres = new Presentation();
```
Sekarang setelah kita menyiapkan lingkungan kita, mari lanjutkan untuk membuat diagram garis dengan penanda.

## Panduan Implementasi
### Membuat Diagram Garis dengan Penanda
Di bagian ini, Anda akan mempelajari setiap langkah yang diperlukan untuk membuat dan mengonfigurasi diagram garis dengan penanda default dalam presentasi Anda menggunakan Aspose.Slides for .NET.

#### Langkah 1: Buat Objek Presentasi
Mulailah dengan membuat contoh `Presentation` kelas:
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
Di sini, kita mengakses slide pertama dalam presentasi yang baru dibuat.

#### Langkah 2: Tambahkan Bagan Garis dengan Penanda
Berikutnya, tambahkan diagram garis dengan penanda ke slide Anda:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
Kode ini menambahkan grafik baru bertipe `LineWithMarkers` pada koordinat `(10, 10)` dengan dimensi `400x400`.

#### Langkah 3: Hapus Seri dan Kategori yang Ada
Sebelum menambahkan data, hapus semua seri atau kategori yang ada:
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
Hal ini memastikan bagan kita dimulai dengan awal yang bersih.

#### Langkah 4: Konfigurasikan Buku Kerja Data Bagan
Akses `ChartDataWorkbook` untuk mengelola data grafik Anda:
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
Objek ini penting untuk mengelola sel yang berisi data seri dan kategori.

#### Langkah 5: Tambahkan Seri dan Kategori
Tambahkan seri baru ke bagan dan isi dengan titik data:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// Tentukan kategori dan titik data yang sesuai
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// Tambahkan titik data nol untuk menunjukkan penanganan nilai yang hilang
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
Di sini, kami mengisi bagan dengan kategori dan data seri yang sesuai. Perhatikan bagaimana `null` nilai ditangani sebagai demonstrasi.

#### Langkah 6: Tambahkan Seri Lain
Ulangi proses untuk menambahkan seri lainnya:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### Langkah 7: Mengaktifkan dan Mengonfigurasi Legenda
Aktifkan legenda bagan untuk meningkatkan keterbacaan:
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
Ini memastikan bahwa legenda terlihat dan tidak terhampar pada bagan.

#### Langkah 8: Simpan Presentasi
Terakhir, simpan presentasi Anda dengan bagan yang baru ditambahkan:
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### Tips Pemecahan Masalah
- **Kesalahan Pengikatan Data:** Pastikan titik data sesuai dengan kategori dengan benar.
- **Bagan Tidak Ditampilkan:** Verifikasi bahwa `chart.HasLegend` dan properti lainnya diatur dengan tepat.

## Aplikasi Praktis
1. **Laporan Bisnis:** Gunakan diagram garis dengan penanda untuk melacak kinerja penjualan dari waktu ke waktu, yang menunjukkan tren pendapatan bulanan.
2. **Analisis Keuangan:** Visualisasikan pergerakan harga saham dengan penanda default untuk menyorot puncak dan palung.
3. **Riset ilmiah:** Menyajikan hasil eksperimen di mana titik data memerlukan batasan yang jelas untuk analisis.

## Pertimbangan Kinerja
- Optimalkan dengan membatasi jumlah seri data dan kategori saat menangani kumpulan data besar.
- Gunakan teknik manajemen memori seperti membuang objek segera di .NET untuk mengurangi penggunaan sumber daya.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara membuat diagram garis dengan penanda menggunakan Aspose.Slides for .NET. Dengan mengikuti langkah-langkah ini, Anda dapat menyempurnakan presentasi Anda dengan diagram yang terperinci dan tampak profesional. Pertimbangkan untuk menjelajahi fitur-fitur Aspose.Slides lainnya untuk lebih memperkaya tayangan slide Anda.

### Langkah Berikutnya
- Bereksperimenlah dengan berbagai jenis bagan yang tersedia di Aspose.Slides.
- Sesuaikan tampilan grafik untuk dampak visual yang lebih baik.
- Jelajahi dokumentasi tambahan pada Aspose.Slides untuk fungsionalitas yang lebih canggih.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}