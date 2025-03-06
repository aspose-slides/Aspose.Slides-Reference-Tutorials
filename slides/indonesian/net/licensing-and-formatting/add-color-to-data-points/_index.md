---
title: Pewarnaan Bagan dengan Aspose.Slides untuk .NET
linktitle: Tambahkan Warna ke Titik Data di Bagan
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menambahkan warna ke titik data dalam bagan dengan Aspose.Slides untuk .NET. Sempurnakan presentasi Anda secara visual dan libatkan audiens Anda secara efektif.
weight: 12
url: /id/net/licensing-and-formatting/add-color-to-data-points/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses penambahan warna pada titik data dalam bagan menggunakan Aspose.Slides untuk .NET. Aspose.Slides adalah perpustakaan yang kuat untuk bekerja dengan presentasi PowerPoint dalam aplikasi .NET. Menambahkan warna pada titik data dalam bagan dapat membuat presentasi Anda lebih menarik secara visual dan lebih mudah dipahami.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Anda perlu menginstal Visual Studio di komputer Anda.

2.  Aspose.Slides untuk .NET: Unduh dan instal Aspose.Slides untuk .NET dari[tautan unduhan](https://releases.aspose.com/slides/net/).

3. Pemahaman Dasar C#: Anda harus memiliki pengetahuan dasar tentang pemrograman C#.

4. Direktori Dokumen Anda: Ganti "Direktori Dokumen Anda" dalam kode dengan jalur sebenarnya ke direktori dokumen Anda.

## Mengimpor Namespace

Sebelum Anda dapat bekerja dengan Aspose.Slides untuk .NET, Anda perlu mengimpor namespace yang diperlukan. 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


Dalam contoh ini, kita akan menambahkan warna pada titik data dalam bagan menggunakan tipe bagan Sunburst.

```csharp
using (Presentation pres = new Presentation())
{
    // Jalur ke direktori dokumen.
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // Kode lainnya akan ditambahkan pada langkah-langkah berikut.
}
```

## Langkah 1: Mengakses Titik Data

Untuk menambahkan warna ke titik data tertentu dalam bagan, Anda perlu mengakses titik data tersebut. Dalam contoh ini, kami akan menargetkan titik data 3.

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## Langkah 2: Menyesuaikan Label Data

Sekarang, mari sesuaikan label data untuk titik data 0. Kita akan menyembunyikan nama kategori dan menampilkan nama rangkaian.

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## Langkah 3: Mengatur Format Teks dan Warna Isi

Kita dapat lebih menyempurnakan tampilan label data dengan mengatur format teks dan warna isian. Pada langkah ini, kita akan mengatur warna teks menjadi kuning untuk titik data 0.

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## Langkah 4: Menyesuaikan Warna Isi Titik Data

Sekarang, mari kita ubah warna isian titik data 9. Kita akan mengaturnya ke warna tertentu.

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## Langkah 5: Menyimpan Presentasi

Setelah menyesuaikan bagan, Anda dapat menyimpan presentasi dengan perubahannya.

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Selamat! Anda telah berhasil menambahkan warna ke titik data dalam bagan menggunakan Aspose.Slides untuk .NET. Hal ini dapat sangat meningkatkan daya tarik visual dan kejelasan presentasi Anda.

## Kesimpulan

Menambahkan warna pada titik data dalam bagan adalah cara ampuh untuk membuat presentasi Anda lebih menarik dan informatif. Dengan Aspose.Slides untuk .NET, Anda memiliki alat untuk membuat bagan yang menarik secara visual yang menyampaikan data Anda secara efektif.

## Pertanyaan yang Sering Diajukan (FAQ)

### Apa itu Aspose.Slide untuk .NET?
   Aspose.Slides for .NET adalah pustaka yang memungkinkan pengembang .NET bekerja dengan presentasi PowerPoint secara terprogram.

### Bisakah saya mengkustomisasi properti bagan lainnya menggunakan Aspose.Slides?
   Ya, Anda dapat menyesuaikan berbagai aspek bagan, seperti label data, font, warna, dan lainnya, menggunakan Aspose.Slides untuk .NET.

### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk .NET?
    Anda dapat menemukan dokumentasi terperinci di[tautan dokumentasi](https://reference.aspose.com/slides/net/).

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?
    Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.Slides untuk .NET?
    Untuk dukungan dan diskusi, kunjungi[Forum Aspose.Slide](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
