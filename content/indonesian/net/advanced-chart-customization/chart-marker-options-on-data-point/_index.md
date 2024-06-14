---
title: Menggunakan Opsi Penanda Bagan pada Titik Data di Aspose.Slides .NET
linktitle: Opsi Penanda Bagan pada Titik Data
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menyempurnakan bagan PowerPoint Anda menggunakan Aspose.Slides untuk .NET. Sesuaikan penanda titik data dengan gambar. Buat presentasi yang menarik.
type: docs
weight: 11
url: /id/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Saat bekerja dengan presentasi dan visualisasi data, Aspose.Slides for .NET menawarkan beragam fitur canggih untuk membuat, menyesuaikan, dan memanipulasi bagan. Dalam tutorial ini, kita akan mempelajari cara menggunakan opsi penanda bagan pada titik data untuk menyempurnakan presentasi bagan Anda. Panduan langkah demi langkah ini akan memandu Anda melalui prosesnya, mulai dari prasyarat dan mengimpor namespace, hingga memecah setiap contoh menjadi beberapa langkah.

## Prasyarat

Sebelum kita mendalami penggunaan opsi penanda bagan pada titik data, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Slides untuk .NET: Pastikan Anda telah menginstal Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/slides/net/).

- Contoh Presentasi: Untuk tutorial ini, kita akan menggunakan contoh presentasi bernama "Test.pptx." Anda harus memiliki presentasi ini di direktori dokumen Anda.

Sekarang, mari kita mulai dengan mengimpor namespace yang diperlukan.

## Impor Namespace

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Kami telah mengimpor namespace yang diperlukan dan menginisialisasi presentasi kami. Sekarang, mari lanjutkan menggunakan opsi penanda bagan pada titik data.

## Langkah 1: Membuat Bagan Default

```csharp

// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Membuat bagan default
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Kami membuat bagan default tipe "LineWithMarkers" pada slide pada lokasi dan ukuran tertentu.

## Langkah 2: Mendapatkan Indeks Lembar Kerja Data Bagan Default

```csharp
// Mendapatkan indeks lembar kerja data bagan default
int defaultWorksheetIndex = 0;
```

Di sini, kita memperoleh indeks lembar kerja data grafik default.

## Langkah 3: Mendapatkan Lembar Kerja Data Bagan

```csharp
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Kami mengambil buku kerja data bagan untuk digunakan dengan data bagan.

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
// Atur gambar untuk penanda
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Ambil seri grafik pertama
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

Kami menetapkan penanda gambar untuk titik data, sehingga Anda dapat menyesuaikan tampilan setiap titik data pada bagan.

## Langkah 6: Mengubah Ukuran Penanda Seri Bagan

```csharp
// Mengubah ukuran penanda seri bagan
series.Marker.Size = 15;
```

Di sini, kami menyesuaikan ukuran penanda rangkaian bagan agar menarik secara visual.

## Langkah 7: Menyimpan Presentasi

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Terakhir, kami menyimpan presentasi dengan pengaturan grafik baru.

## Kesimpulan

Aspose.Slides untuk .NET memberdayakan Anda untuk membuat presentasi grafik yang menakjubkan dengan berbagai opsi penyesuaian. Dalam tutorial ini, kami berfokus pada penggunaan opsi penanda bagan pada titik data untuk menyempurnakan representasi visual data Anda. Dengan Aspose.Slides untuk .NET, Anda dapat membawa presentasi Anda ke tingkat berikutnya, menjadikannya lebih menarik dan informatif.

Jika Anda memiliki pertanyaan atau memerlukan bantuan dengan Aspose.Slides untuk .NET, silakan kunjungi[Dokumentasi Aspose.Slide](https://reference.aspose.com/slides/net/) atau menghubungi[Asumsikan komunitas](https://forum.aspose.com/) untuk dukungan.

## Pertanyaan yang Sering Diajukan (FAQ)

### Bisakah saya menggunakan gambar khusus sebagai penanda titik data di Aspose.Slides untuk .NET?
Ya, Anda dapat menggunakan gambar khusus sebagai penanda titik data di Aspose.Slides untuk .NET, seperti yang ditunjukkan dalam tutorial ini.

### Bagaimana cara mengubah tipe bagan di Aspose.Slides untuk .NET?
 Anda dapat mengubah jenis bagan dengan menentukan jenis bagan lain`ChartType` saat membuat bagan, seperti "Batang", "Pai", atau "Area".

### Apakah Aspose.Slides for .NET kompatibel dengan PowerPoint versi terbaru?
Aspose.Slides untuk .NET dirancang untuk bekerja dengan berbagai format PowerPoint dan diperbarui secara berkala untuk menjaga kompatibilitas dengan versi PowerPoint terbaru.

### Di mana saya dapat menemukan lebih banyak tutorial dan sumber daya untuk Aspose.Slides untuk .NET?
 Anda dapat menjelajahi tutorial dan sumber daya tambahan di[Dokumentasi Aspose.Slide](https://reference.aspose.com/slides/net/).

### Apakah ada versi uji coba Aspose.Slides untuk .NET yang tersedia?
 Ya, Anda dapat mencoba Aspose.Slides untuk .NET dengan mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).