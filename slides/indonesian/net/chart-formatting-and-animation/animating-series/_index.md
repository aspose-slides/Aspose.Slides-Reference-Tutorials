---
title: Menganimasikan Seri Bagan dengan Aspose.Slides untuk .NET
linktitle: Seri Animasi dalam Bagan
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menganimasikan rangkaian bagan dengan Aspose.Slides untuk .NET. Libatkan audiens Anda dengan presentasi dinamis. Mulai sekarang!
weight: 12
url: /id/net/chart-formatting-and-animation/animating-series/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Apakah Anda ingin menambahkan kesan menarik pada presentasi Anda dengan bagan animasi? Aspose.Slides untuk .NET hadir untuk membuat bagan Anda menjadi hidup. Dalam panduan langkah demi langkah ini, kami akan menunjukkan kepada Anda cara menganimasikan rangkaian dalam bagan menggunakan Aspose.Slides untuk .NET. Namun sebelum kita mendalami tindakannya, mari kita bahas prasyaratnya.

## Prasyarat

Agar berhasil menganimasikan rangkaian dalam bagan menggunakan Aspose.Slides untuk .NET, Anda memerlukan hal berikut:

### 1. Aspose.Slide untuk Perpustakaan .NET

 Pastikan Anda telah menginstal perpustakaan Aspose.Slides untuk .NET. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Aspose.Slide untuk situs web .NET](https://releases.aspose.com/slides/net/).

### 2. Presentasi yang Ada dengan Bagan

Siapkan presentasi PowerPoint (PPTX) dengan bagan yang ada yang ingin Anda animasikan.

Sekarang kita telah memenuhi prasyaratnya, mari kita bagi prosesnya menjadi serangkaian langkah untuk menganimasikan rangkaian bagan.


## Langkah 1: Impor Namespace yang Diperlukan

Anda harus mengimpor namespace yang diperlukan dalam kode C# Anda agar berfungsi dengan Aspose.Slides untuk .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Langkah 2: Muat Presentasi yang Ada

Pada langkah ini, muat presentasi PowerPoint (PPTX) yang sudah ada yang berisi bagan yang ingin Anda animasikan.

```csharp
// Jalur ke direktori dokumen
string dataDir = "Your Document Directory";

// Buat instance kelas Presentasi yang mewakili file presentasi
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Kode Anda ada di sini
}
```

## Langkah 3: Dapatkan Referensi Objek Bagan

Untuk bekerja dengan bagan dalam presentasi Anda, Anda perlu mendapatkan referensi ke objek bagan:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Langkah 4: Animasikan Seri

Sekarang, saatnya menambahkan efek animasi ke rangkaian grafik Anda. Kami akan menambahkan efek fade-in ke seluruh diagram dan membuat setiap rangkaian muncul satu per satu.

```csharp
// Animasikan bagan
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Tambahkan animasi ke setiap seri
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Langkah 5: Simpan Presentasi yang Dimodifikasi

Setelah Anda menambahkan efek animasi ke bagan Anda, simpan presentasi yang dimodifikasi ke disk.

```csharp
//Simpan presentasi yang dimodifikasi
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Itu dia! Anda telah berhasil menganimasikan serial dalam bagan menggunakan Aspose.Slides untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami telah memandu Anda melalui proses menganimasikan rangkaian dalam bagan menggunakan Aspose.Slides untuk .NET. Dengan perpustakaan canggih ini, Anda dapat membuat presentasi menarik dan dinamis yang memikat audiens Anda.

 Jika Anda memiliki pertanyaan atau memerlukan bantuan lebih lanjut, jangan ragu untuk menghubungi komunitas Aspose.Slides di mereka[forum dukungan](https://forum.aspose.com/).

## FAQ

### Bisakah saya menganimasikan elemen bagan lain selain seri menggunakan Aspose.Slides untuk .NET?
Ya, Anda dapat menganimasikan berbagai elemen bagan, termasuk titik data, sumbu, dan legenda, menggunakan Aspose.Slides untuk .NET.

### Apakah Aspose.Slides for .NET kompatibel dengan PowerPoint versi terbaru?
Aspose.Slides untuk .NET mendukung berbagai versi PowerPoint, termasuk PowerPoint 2007 dan yang lebih baru, memastikan kompatibilitas dengan versi terbaru.

### Bisakah saya menyesuaikan efek animasi untuk setiap rangkaian grafik satu per satu?
Ya, Anda dapat menyesuaikan efek animasi untuk setiap rangkaian bagan untuk membuat presentasi yang unik dan menarik.

### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk .NET?
 Ya, Anda dapat mencoba perpustakaan dengan uji coba gratis dari[Aspose.Slide untuk situs web .NET](https://releases.aspose.com/).

### Di mana saya dapat membeli lisensi Aspose.Slides untuk .NET?
 Anda dapat memperoleh lisensi Aspose.Slides untuk .NET dari halaman pembelian[Di Sini](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
