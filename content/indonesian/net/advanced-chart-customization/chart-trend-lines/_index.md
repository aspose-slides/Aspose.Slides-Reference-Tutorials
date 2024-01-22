---
title: Menjelajahi Garis Tren Bagan di Aspose.Slides untuk .NET
linktitle: Garis Tren Bagan
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menambahkan berbagai garis tren ke bagan menggunakan Aspose.Slides untuk .NET dalam panduan langkah demi langkah ini. Tingkatkan keterampilan visualisasi data Anda dengan mudah!
type: docs
weight: 12
url: /id/net/advanced-chart-customization/chart-trend-lines/
---

Dalam dunia visualisasi dan presentasi data, menggabungkan bagan dapat menjadi cara ampuh untuk menyampaikan informasi secara efektif. Aspose.Slides for .NET menyediakan seperangkat alat yang kaya fitur untuk bekerja dengan grafik, termasuk kemampuan untuk menambahkan garis tren ke grafik Anda. Dalam tutorial ini, kita akan mempelajari proses menambahkan garis tren ke grafik secara langkah demi langkah menggunakan Aspose.Slides untuk .NET. 

## Prasyarat

Sebelum kita mulai bekerja dengan Aspose.Slides untuk .NET, Anda harus memastikan bahwa Anda memiliki prasyarat berikut:

1.  Aspose.Slides for .NET: Untuk mengakses perpustakaan dan menggunakannya, Anda harus menginstal Aspose.Slides for .NET. Anda bisa mendapatkan perpustakaan dari[Unduh Halaman](https://releases.aspose.com/slides/net/).

2. Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan, sebaiknya menggunakan lingkungan pengembangan terintegrasi .NET seperti Visual Studio.

3. Pengetahuan Dasar tentang C#: Pemahaman mendasar tentang pemrograman C# bermanfaat, karena kita akan menggunakan C# untuk bekerja dengan Aspose.Slides untuk .NET.

Sekarang kita telah membahas prasyaratnya, mari kita uraikan proses penambahan garis tren ke grafik langkah demi langkah.

## Mengimpor Namespace

Pertama, pastikan Anda mengimpor namespace yang diperlukan ke proyek C# Anda. Namespace ini penting untuk bekerja dengan Aspose.Slides untuk .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Langkah 1: Buat Presentasi

Pada langkah ini, kita membuat presentasi kosong untuk dikerjakan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";

// Buat direktori jika belum ada.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Membuat presentasi kosong
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide

Selanjutnya, kita menambahkan bagan kolom berkerumun ke slide.

```csharp
// Membuat bagan kolom berkerumun
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Langkah 3: Tambahkan Garis Tren ke Grafik

Sekarang, kami menambahkan berbagai jenis garis tren ke rangkaian grafik.

### Menambahkan Garis Tren Eksponensial

```csharp
// Menambahkan garis tren eksponensial untuk seri grafik 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Menambahkan Garis Tren Linier

```csharp
// Menambahkan garis tren linier untuk seri grafik 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Menambahkan Garis Tren Logaritma

```csharp
// Menambahkan garis tren logaritmik untuk seri grafik 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Menambahkan Garis Tren Rata-Rata Bergerak

```csharp
// Menambahkan garis tren rata-rata bergerak untuk seri grafik 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Menambahkan Garis Tren Polinomial

```csharp
// Menambahkan garis tren polinomial untuk seri grafik 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Menambahkan Garis Tren Kekuatan

```csharp
// Menambahkan garis tren kekuatan untuk seri grafik 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Langkah 4: Simpan Presentasi

Setelah menambahkan garis tren ke grafik, simpan presentasinya.

```csharp
// Menyimpan presentasi
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah berhasil menambahkan berbagai garis tren ke bagan Anda menggunakan Aspose.Slides untuk .NET.

## Kesimpulan

Aspose.Slides for .NET adalah perpustakaan serbaguna yang memungkinkan Anda membuat dan memanipulasi grafik dengan mudah. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat menambahkan berbagai jenis garis tren ke grafik Anda, sehingga meningkatkan representasi visual data Anda.

### FAQ

### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk .NET?
 Anda dapat mengakses dokumentasinya[Di Sini](https://reference.aspose.com/slides/net/).

### Bagaimana cara mengunduh Aspose.Slides untuk .NET?
 Anda dapat mengunduh Aspose.Slides untuk .NET dari halaman unduh[Di Sini](https://releases.aspose.com/slides/net/).

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?
 Ya, Anda dapat mencoba Aspose.Slides untuk .NET secara gratis dengan mengunjungi[Link ini](https://releases.aspose.com/).

### Di mana saya dapat membeli Aspose.Slides untuk .NET?
 Untuk membeli Aspose.Slides untuk .NET, kunjungi halaman pembelian[Di Sini](https://purchase.aspose.com/buy).

### Apakah saya memerlukan lisensi sementara untuk Aspose.Slides untuk .NET?
 Anda dapat memperoleh lisensi sementara untuk Aspose.Slides untuk .NET dari[Link ini](https://purchase.aspose.com/temporary-license/).