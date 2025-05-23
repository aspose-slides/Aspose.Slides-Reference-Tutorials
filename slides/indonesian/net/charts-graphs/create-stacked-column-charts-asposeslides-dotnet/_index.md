---
"date": "2025-04-15"
"description": "Pelajari cara membuat bagan kolom bertumpuk berbasis persentase yang menarik secara visual menggunakan Aspose.Slides for .NET. Ikuti panduan langkah demi langkah ini untuk visualisasi data yang jelas."
"title": "Cara Membuat Grafik Kolom Bertumpuk Berbasis Persentase di .NET menggunakan Aspose.Slides"
"url": "/id/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Bagan Kolom Bertumpuk Berbasis Persentase menggunakan Aspose.Slides untuk .NET

## Perkenalan

Dalam bidang visualisasi data, penyajian informasi yang jelas dan efektif sangat penting untuk pengambilan keputusan yang berdampak. Untuk menampilkan kumpulan data yang kompleks secara intuitif, bagan kolom bertumpuk berbasis persentase sangatlah ideal. Panduan ini akan memandu Anda dalam membuat bagan ini menggunakan Aspose.Slides for .NET, pustaka tangguh yang dirancang untuk memanipulasi berkas presentasi.

Dengan mengikuti tutorial ini, Anda akan belajar:
- Menyiapkan data bagan dan mengonfigurasi format angka.
- Menambahkan seri dan menyesuaikan tampilannya.
- Memformat label untuk meningkatkan keterbacaan.

Siap untuk memulai? Mari kita mulai dengan prasyarat yang Anda butuhkan!

## Prasyarat

Sebelum membuat diagram kolom bertumpuk berbasis persentase, pastikan lingkungan Anda telah diatur dengan benar. Anda akan memerlukan:

### Pustaka, Versi, dan Ketergantungan yang Diperlukan
- **Aspose.Slides untuk .NET**Pastikan pustaka ini terinstal.

### Persyaratan Pengaturan Lingkungan
- Lingkungan pengembangan dengan .NET SDK terpasang.
- Visual Studio atau IDE apa pun yang kompatibel untuk menjalankan kode C#.

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman C#.
- Kemampuan dalam pengaturan proyek .NET dan manajemen paket.

## Menyiapkan Aspose.Slides untuk .NET

Untuk mulai membuat bagan dengan Aspose.Slides, pertama-tama instal pustaka menggunakan salah satu metode berikut:

**.KLIK NET**
```bash
dotnet add package Aspose.Slides
```

**Manajer Paket**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet**
- Cari "Aspose.Slides" dan instal versi terbaru.

### Langkah-langkah Memperoleh Lisensi

Mulailah dengan uji coba gratis dengan mengunduh lisensi sementara dari [Situs web Aspose](https://purchase.aspose.com/temporary-license/)Untuk penggunaan berkelanjutan, pertimbangkan untuk membeli lisensi penuh. 

Setelah disiapkan, jalankan Aspose.Slides di proyek Anda:
```csharp
using Aspose.Slides;
```

## Panduan Implementasi

Setelah lingkungan siap, mari kita uraikan pembuatan bagan kolom bertumpuk berbasis persentase ke dalam beberapa langkah.

### Membuat dan Mengonfigurasi Bagan

#### Ringkasan
Buat contoh dari `Presentation` kelas, yang penting untuk bekerja dengan slide. Kemudian, tambahkan dan konfigurasikan diagram kolom bertumpuk pada slide Anda.

#### Menambahkan Bagan Kolom Bertumpuk
```csharp
// Buat instance kelas Presentasi
document = new Presentation();

// Dapatkan referensi ke slide pertama
slide = document.Slides[0];

// Tambahkan bagan PercentsStackedColumn pada posisi (20, 20) dengan ukuran (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Mengonfigurasi Format Angka
Pastikan data Anda ditampilkan sebagai persentase:
```csharp
// Konfigurasikan format angka untuk sumbu vertikal
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Atur format angka ke persentase
```

#### Menambahkan Seri Data dan Titik
Hapus data seri yang ada dan tambahkan yang baru:
```csharp
// Hapus semua data seri yang ada
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Akses buku kerja data grafik
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Tambahkan seri data baru "Merah"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Atur warna isian untuk seri menjadi Merah
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Konfigurasikan properti format label untuk seri "Reds"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Atur format persentase
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Tambahkan seri lain "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Atur warna isian untuk seri menjadi Biru
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Atur format persentase
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Menyimpan Presentasi
Simpan presentasi Anda ke sebuah file:
```csharp
// Simpan presentasi dalam format PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Tips Pemecahan Masalah
- Pastikan semua namespace diimpor dengan benar.
- Periksa kesalahan ketik pada nama properti dan pemanggilan metode.
- Verifikasi apakah jalur untuk menyimpan file ada dan memiliki izin yang benar.

## Aplikasi Praktis

Berikut adalah beberapa skenario di mana diagram kolom bertumpuk berbasis persentase dapat berguna:
1. **Analisis Penjualan**: Visualisasikan kinerja produk di berbagai wilayah sebagai proporsi total penjualan.
2. **Alokasi Anggaran**: Tunjukkan bagaimana departemen mengalokasikan anggaran mereka dalam kaitannya dengan pengeluaran perusahaan secara keseluruhan.
3. **Riset Pasar**: Bandingkan preferensi konsumen untuk berbagai kategori produk dari waktu ke waktu.
4. **Data Pendidikan**: Menampilkan distribusi nilai siswa dalam berbagai mata pelajaran.
5. **Statistik Kesehatan**: Mewakili demografi pasien di berbagai kondisi kesehatan.

## Pertimbangan Kinerja

Untuk kinerja optimal, pertimbangkan:
- Membatasi jumlah titik data sesuai kebutuhan.
- Pra-pemuatan data untuk meminimalkan pemrosesan waktu proses.
- Menggunakan praktik manajemen memori yang efisien dengan Aspose.Slides untuk .NET.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara membuat bagan kolom bertumpuk berbasis persentase menggunakan Aspose.Slides for .NET. Alat ini menyempurnakan presentasi dengan membuat data yang kompleks lebih mudah dipahami dan menarik secara visual.

Langkah selanjutnya? Jelajahi jenis bagan lain yang tersedia di Aspose.Slides atau integrasikan fungsionalitas ini ke dalam aplikasi yang lebih besar. Selamat membuat kode!

## Bagian FAQ

**Q1: Dapatkah saya menggunakan Aspose.Slides secara gratis?**
A1: Ya, Anda dapat memulai dengan uji coba gratis untuk menguji fitur Aspose.Slides.

**Q2: Jenis bagan apa yang didukung oleh Aspose.Slides untuk .NET?**
A2: Mendukung berbagai grafik seperti pai, batang, kolom, garis, dan banyak lagi.

**Q3: Bagaimana cara memulai dengan Aspose.Slides untuk .NET?**
A3: Instal pustaka menggunakan NuGet atau .NET CLI seperti dijelaskan di atas. Ikuti dokumentasi kami untuk membuat bagan pertama Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}