---
"description": "Pelajari cara menambahkan berbagai garis tren ke grafik menggunakan Aspose.Slides for .NET dalam panduan langkah demi langkah ini. Tingkatkan keterampilan visualisasi data Anda dengan mudah!"
"linktitle": "Garis Tren Grafik"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Menjelajahi Garis Tren Grafik di Aspose.Slides untuk .NET"
"url": "/id/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menjelajahi Garis Tren Grafik di Aspose.Slides untuk .NET


Dalam dunia visualisasi dan presentasi data, menggabungkan diagram dapat menjadi cara yang ampuh untuk menyampaikan informasi secara efektif. Aspose.Slides for .NET menyediakan serangkaian alat yang kaya fitur untuk bekerja dengan diagram, termasuk kemampuan untuk menambahkan garis tren ke diagram Anda. Dalam tutorial ini, kita akan mempelajari proses menambahkan garis tren ke diagram secara bertahap menggunakan Aspose.Slides for .NET. 

## Prasyarat

Sebelum kita mulai bekerja dengan Aspose.Slides untuk .NET, Anda harus memastikan bahwa Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk .NET: Untuk mengakses pustaka dan menggunakannya, Anda harus menginstal Aspose.Slides untuk .NET. Anda bisa mendapatkan pustaka dari [halaman unduhan](https://releases.aspose.com/slides/net/).

2. Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan, sebaiknya menggunakan lingkungan pengembangan terintegrasi .NET seperti Visual Studio.

3. Pengetahuan Dasar C#: Pemahaman dasar tentang pemrograman C# akan bermanfaat, karena kita akan menggunakan C# untuk bekerja dengan Aspose.Slides untuk .NET.

Sekarang setelah kita membahas prasyaratnya, mari kita uraikan proses penambahan garis tren ke grafik langkah demi langkah.

## Mengimpor Ruang Nama

Pertama, pastikan Anda mengimpor namespace yang diperlukan ke dalam proyek C# Anda. Namespace ini penting untuk bekerja dengan Aspose.Slides for .NET.

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

Berikutnya, kita tambahkan bagan kolom berkelompok ke slide.

```csharp
// Membuat bagan kolom berkelompok
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Langkah 3: Tambahkan Garis Tren ke Grafik

Sekarang, kami menambahkan berbagai jenis garis tren ke rangkaian grafik.

### Menambahkan Garis Tren Eksponensial

```csharp
// Menambahkan garis tren eksponensial untuk rangkaian grafik 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Menambahkan Garis Tren Linier

```csharp
// Menambahkan garis tren linier untuk rangkaian grafik 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Menambahkan Garis Tren Logaritmik

```csharp
// Menambahkan garis tren logaritmik untuk rangkaian grafik 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Menambahkan Garis Tren Rata-rata Bergerak

```csharp
// Menambahkan garis tren rata-rata bergerak untuk rangkaian grafik 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Menambahkan Garis Tren Polinomial

```csharp
// Menambahkan garis tren polinomial untuk rangkaian grafik 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Menambahkan Garis Tren Daya

```csharp
// Menambahkan garis tren daya untuk rangkaian grafik 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Langkah 4: Simpan Presentasi

Setelah menambahkan garis tren ke bagan, simpan presentasinya.

```csharp
// Menyimpan presentasi
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil menambahkan berbagai garis tren ke grafik Anda menggunakan Aspose.Slides for .NET.

## Kesimpulan

Aspose.Slides untuk .NET adalah pustaka serbaguna yang memungkinkan Anda membuat dan memanipulasi grafik dengan mudah. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat menambahkan berbagai jenis garis tren ke grafik Anda, yang akan meningkatkan representasi visual data Anda.

### Tanya Jawab Umum

### Di mana saya dapat menemukan dokumentasi untuk Aspose.Slides for .NET?
Anda dapat mengakses dokumentasi [Di Sini](https://reference.aspose.com/slides/net/).

### Bagaimana cara mengunduh Aspose.Slides untuk .NET?
Anda dapat mengunduh Aspose.Slides untuk .NET dari halaman unduhan [Di Sini](https://releases.aspose.com/slides/net/).

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?
Ya, Anda dapat mencoba Aspose.Slides untuk .NET secara gratis dengan mengunjungi [tautan ini](https://releases.aspose.com/).

### Di mana saya dapat membeli Aspose.Slides untuk .NET?
Untuk membeli Aspose.Slides untuk .NET, kunjungi halaman pembelian [Di Sini](https://purchase.aspose.com/buy).

### Apakah saya memerlukan lisensi sementara untuk Aspose.Slides for .NET?
Anda dapat memperoleh lisensi sementara untuk Aspose.Slides untuk .NET dari [tautan ini](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}