---
"description": "Pelajari cara menyempurnakan bagan PowerPoint Anda menggunakan Aspose.Slides for .NET. Sesuaikan penanda titik data dengan gambar. Buat presentasi yang menarik."
"linktitle": "Opsi Penanda Bagan pada Titik Data"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Menggunakan Opsi Penanda Bagan pada Titik Data di Aspose.Slides .NET"
"url": "/id/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menggunakan Opsi Penanda Bagan pada Titik Data di Aspose.Slides .NET


Saat bekerja dengan presentasi dan visualisasi data, Aspose.Slides for .NET menawarkan berbagai fitur canggih untuk membuat, menyesuaikan, dan memanipulasi bagan. Dalam tutorial ini, kita akan menjelajahi cara menggunakan opsi penanda bagan pada titik data untuk menyempurnakan presentasi bagan Anda. Panduan langkah demi langkah ini akan memandu Anda melalui prosesnya, mulai dari prasyarat dan mengimpor namespace, hingga memecah setiap contoh menjadi beberapa langkah.

## Prasyarat

Sebelum kita mulai menggunakan opsi penanda grafik pada titik data, pastikan Anda memiliki prasyarat berikut:

- Aspose.Slides untuk .NET: Pastikan Anda telah menginstal Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari [situs web](https://releases.aspose.com/slides/net/).

- Contoh Presentasi: Untuk tutorial ini, kami akan menggunakan contoh presentasi bernama "Test.pptx." Anda harus memiliki presentasi ini di direktori dokumen Anda.

Sekarang, mari kita mulai dengan mengimpor namespace yang diperlukan.

## Mengimpor Ruang Nama

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Kami telah mengimpor namespace yang diperlukan dan menginisialisasi presentasi kami. Sekarang, mari kita lanjutkan untuk menggunakan opsi penanda bagan pada titik data.

## Langkah 1: Membuat Bagan Default

```csharp

// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Membuat grafik default
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Kami membuat bagan default bertipe "LineWithMarkers" pada slide pada lokasi dan ukuran yang ditentukan.

## Langkah 2: Mendapatkan Indeks Lembar Kerja Data Grafik Default

```csharp
// Mendapatkan indeks lembar kerja data grafik default
int defaultWorksheetIndex = 0;
```

Di sini kita memperoleh indeks lembar kerja data bagan default.

## Langkah 3: Mendapatkan Lembar Kerja Data Bagan

```csharp
// Mendapatkan lembar kerja data grafik
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Kami mengambil buku kerja data bagan untuk bekerja dengan data bagan.

## Langkah 4: Memodifikasi Seri Bagan

```csharp
// Hapus seri demo
chart.ChartData.Series.Clear();

// Tambahkan seri baru
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Pada langkah ini, kami menghapus seri demo yang ada dan menambahkan seri baru bernama "Seri 1" ke bagan.

## Langkah 5: Mengatur Isi Gambar untuk Titik Data

```csharp
// Mengatur gambar untuk penanda
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Ambil rangkaian grafik pertama
IChartSeries series = chart.ChartData.Series[0];

// Tambahkan titik data baru dengan isian gambar
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Kami menetapkan penanda gambar untuk titik-titik data, sehingga Anda dapat menyesuaikan tampilan setiap titik data pada bagan.

## Langkah 6: Mengubah Ukuran Penanda Seri Bagan

```csharp
// Mengubah ukuran penanda seri grafik
series.Marker.Size = 15;
```

Di sini, kami menyesuaikan ukuran penanda seri bagan agar menarik secara visual.

## Langkah 7: Menyimpan Presentasi

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Terakhir, kami menyimpan presentasi dengan pengaturan grafik baru.

## Kesimpulan

Aspose.Slides untuk .NET memungkinkan Anda membuat presentasi bagan yang memukau dengan berbagai opsi penyesuaian. Dalam tutorial ini, kami berfokus pada penggunaan opsi penanda bagan pada titik data untuk menyempurnakan representasi visual data Anda. Dengan Aspose.Slides untuk .NET, Anda dapat membawa presentasi Anda ke tingkat berikutnya, membuatnya lebih menarik dan informatif.

Jika Anda memiliki pertanyaan atau memerlukan bantuan dengan Aspose.Slides untuk .NET, jangan ragu untuk mengunjungi [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/net/) atau hubungi [Komunitas Aspose](https://forum.aspose.com/) untuk dukungan.

## Pertanyaan yang Sering Diajukan (FAQ)

### Dapatkah saya menggunakan gambar khusus sebagai penanda titik data di Aspose.Slides untuk .NET?
Ya, Anda dapat menggunakan gambar kustom sebagai penanda titik data di Aspose.Slides untuk .NET, seperti yang ditunjukkan dalam tutorial ini.

### Bagaimana cara mengubah jenis bagan di Aspose.Slides untuk .NET?
Anda dapat mengubah jenis grafik dengan menentukan jenis yang berbeda `ChartType` saat membuat bagan, seperti "Batang," "Pai," atau "Luas."

### Apakah Aspose.Slides untuk .NET kompatibel dengan versi PowerPoint terbaru?
Aspose.Slides untuk .NET dirancang untuk bekerja dengan berbagai format PowerPoint dan diperbarui secara berkala untuk menjaga kompatibilitas dengan versi PowerPoint terbaru.

### Di mana saya dapat menemukan lebih banyak tutorial dan sumber daya untuk Aspose.Slides for .NET?
Anda dapat menjelajahi tutorial dan sumber daya tambahan di [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/net/).

### Apakah ada versi uji coba Aspose.Slides untuk .NET yang tersedia?
Ya, Anda dapat mencoba Aspose.Slides untuk .NET dengan mengunduh versi uji coba gratis dari [Di Sini](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}