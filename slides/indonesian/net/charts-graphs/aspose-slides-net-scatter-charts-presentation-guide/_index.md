---
"date": "2025-04-15"
"description": "Pelajari cara menyempurnakan presentasi Anda dengan diagram sebar menggunakan Aspose.Slides for .NET. Ikuti panduan lengkap ini untuk membuat dan menyesuaikan diagram secara efektif."
"title": "Menambahkan Bagan Sebar ke Presentasi Menggunakan Aspose.Slides .NET&#58; Panduan Langkah demi Langkah"
"url": "/id/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Menambahkan Bagan Sebar ke Presentasi Menggunakan Aspose.Slides .NET: Panduan Langkah demi Langkah

## Perkenalan
Apakah Anda ingin menyempurnakan presentasi Anda dengan mengintegrasikan diagram sebar dengan mudah? Dengan kekuatan Aspose.Slides untuk .NET, membuat dan menyesuaikan diagram menjadi mudah. Tutorial ini akan memandu Anda menambahkan diagram sebar ke slide Anda menggunakan Aspose.Slides untuk .NET. Dengan menguasai teknik ini, Anda akan menyajikan data dengan lebih efektif dan membuat presentasi yang menarik secara visual.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk .NET di proyek Anda
- Membuat presentasi baru dan mengakses slide pertamanya
- Menambahkan diagram sebaran dengan garis halus ke slide
- Menghapus seri yang ada dan menambahkan seri baru ke grafik
- Memodifikasi titik data dan gaya penanda untuk visualisasi yang lebih baik
- Menyimpan presentasi ke direktori tertentu

Mari kita mulai dengan meninjau prasyaratnya.

## Prasyarat
Sebelum mengimplementasikan Aspose.Slides untuk .NET, pastikan Anda memiliki yang berikut ini:
- **Aspose.Slides untuk Pustaka .NET**: Versi 23.7 atau yang lebih baru.
- **Lingkungan Pengembangan**: Visual Studio 2019 atau yang lebih baru dengan .NET Framework 4.6.1+ atau .NET Core/5+.
- **Pengetahuan Dasar C#**: Keakraban dengan pemrograman berorientasi objek dalam C#.

## Menyiapkan Aspose.Slides untuk .NET
Untuk mulai menggunakan Aspose.Slides, Anda perlu memasang pustaka tersebut di proyek Anda. Berikut caranya:

**Menggunakan .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Menggunakan Konsol Manajer Paket:**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet:**
- Cari "Aspose.Slides" dan instal versi terbaru.

### Akuisisi Lisensi
Anda dapat memulai dengan uji coba gratis atau mengajukan lisensi sementara untuk menjelajahi semua fitur. Untuk membeli, ikuti langkah-langkah berikut:
1. Mengunjungi [Beli Aspose.Slides](https://purchase.aspose.com/buy) untuk membeli lisensi penuh.
2. Untuk lisensi sementara, kunjungi [Halaman Lisensi Sementara](https://purchase.aspose.com/temporary-license/).

Setelah Anda memperoleh berkas lisensi, tambahkan ke proyek Anda menggunakan:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Panduan Implementasi
Kami akan membagi implementasi ke dalam beberapa bagian logis berdasarkan fitur.

### Buat Presentasi dan Tambahkan Slide
Bagian ini menunjukkan cara membuat presentasi dan mengakses slide pertamanya.

#### Ringkasan
Mulailah dengan membuat contoh `Presentation` kelas, yang mewakili berkas PowerPoint Anda. Mengakses slide mudah dilakukan menggunakan model objek ini.

#### Langkah-langkah Implementasi
**Langkah 1: Inisialisasi Presentasi**
```csharp
using Aspose.Slides;

// Buat presentasi baru
t Presentation pres = new Presentation();
```
Kode ini menginisialisasi dokumen presentasi baru.

**Langkah 2: Akses Slide Pertama**
```csharp
// Akses slide pertama dalam presentasi
ISlide slide = pres.Slides[0];
```
Di Sini, `pres.Slides[0]` mengakses slide pertama. 

### Tambahkan Bagan Sebar ke Slide
Sekarang mari tambahkan diagram sebar ke presentasi Anda.

#### Ringkasan
Menambahkan diagram dapat membantu Anda menyajikan data secara visual dalam presentasi. Aspose.Slides memudahkan penggabungan berbagai jenis diagram, termasuk diagram sebar.

#### Langkah-langkah Implementasi
**Langkah 1: Buat dan Tambahkan Bagan Sebar**
```csharp
using Aspose.Slides.Charts;

// Buat dan tambahkan diagram sebaran default dengan garis halus
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Cuplikan ini menambahkan bagan sebar pada posisi dan ukuran yang ditentukan.

### Hapus dan Tambahkan Seri ke Data Bagan
#### Ringkasan
Anda mungkin perlu menyesuaikan diagram dengan menghapus rangkaian yang ada dan menambahkan rangkaian yang baru. Bagian ini membahas fungsionalitas tersebut.

#### Langkah-langkah Implementasi
**Langkah 1: Akses Buku Kerja Data Bagan**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Hapus semua seri yang sudah ada sebelumnya
chart.ChartData.Series.Clear();
```
Kode ini menghapus data yang ada untuk memulai lagi dengan seri baru.

**Langkah 2: Tambahkan Seri Baru**
```csharp
// Tambahkan seri baru bernama "Seri 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Tambahkan seri lain bernama "Seri 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Langkah-langkah ini menambahkan dua seri baru ke bagan.

### Ubah Titik Data Seri Pertama dan Gaya Penanda
#### Ringkasan
Sesuaikan titik data dan gaya penanda untuk visualisasi diagram sebar yang lebih baik.

#### Langkah-langkah Implementasi
**Langkah 1: Akses dan Tambahkan Titik Data**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Tambahkan titik data (1, 3) dan (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Langkah 2: Ubah Gaya Penanda**
```csharp
// Ubah jenis seri dan modifikasi gaya penanda
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Ubah Titik Data Seri Kedua dan Gaya Penanda
#### Ringkasan
Demikian pula, sesuaikan seri kedua untuk menyesuaikan kebutuhan presentasi Anda.

#### Langkah-langkah Implementasi
**Langkah 1: Akses dan Tambahkan Beberapa Titik Data**
```csharp
// Akses seri grafik kedua
series = chart.ChartData.Series[1];

// Tambahkan beberapa titik data
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Langkah 2: Ubah Gaya Penanda**
```csharp
// Ubah ukuran penanda dan simbol untuk seri kedua
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Simpan Presentasi
Terakhir, simpan presentasi Anda ke direktori yang ditentukan.

#### Langkah-langkah Implementasi
**Langkah 1: Tentukan Direktori**
Pastikan direktori output ada. Jika tidak, buatlah:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Simpan presentasi
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Kode ini menyimpan berkas presentasi Anda ke lokasi yang ditentukan.

## Kesimpulan
Anda kini telah berhasil menambahkan diagram sebar ke presentasi Anda menggunakan Aspose.Slides for .NET. Terus jelajahi fitur dan kustomisasi tambahan yang tersedia dalam pustaka untuk meningkatkan keterampilan visualisasi data Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}