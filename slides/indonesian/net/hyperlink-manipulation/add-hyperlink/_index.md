---
title: Menambahkan Hyperlink ke Slide di .NET menggunakan Aspose.Slides
linktitle: Tambahkan Hyperlink ke Slide
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menambahkan hyperlink ke slide PowerPoint dengan Aspose.Slides untuk .NET. Sempurnakan presentasi Anda dengan elemen interaktif.
weight: 12
url: /id/net/hyperlink-manipulation/add-hyperlink/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Dalam dunia presentasi digital, interaktivitas adalah kuncinya. Menambahkan hyperlink ke slide Anda dapat membuat presentasi Anda lebih menarik dan informatif. Aspose.Slides for .NET adalah pustaka canggih yang memungkinkan Anda membuat, memodifikasi, dan memanipulasi presentasi PowerPoint secara terprogram. Dalam tutorial ini, kami akan menunjukkan cara menambahkan hyperlink ke slide Anda menggunakan Aspose.Slides untuk .NET. 

## Prasyarat

Sebelum kita mendalami cara menambahkan hyperlink ke slide, pastikan Anda memiliki prasyarat berikut:

1. Visual Studio: Anda harus menginstal Visual Studio di komputer Anda untuk menulis dan mengeksekusi kode .NET.

2. Aspose.Slides untuk .NET: Anda harus menginstal perpustakaan Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).

3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan bermanfaat.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda. Dalam hal ini, Anda memerlukan namespace berikut dari perpustakaan Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Sekarang, mari kita uraikan proses penambahan hyperlink ke slide menjadi beberapa langkah.

## Langkah 1: Inisialisasi Presentasi

Pertama, buat presentasi baru menggunakan Aspose.Slides. Inilah cara Anda melakukannya:

```csharp
using (Presentation presentation = new Presentation())
{
    // Kode Anda ada di sini
}
```

Kode ini menginisialisasi presentasi PowerPoint baru.

## Langkah 2: Tambahkan Bingkai Teks

Sekarang, mari tambahkan bingkai teks ke slide Anda. Bingkai teks ini akan berfungsi sebagai elemen yang dapat diklik di slide Anda. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Kode di atas membuat bentuk otomatis persegi panjang dan menambahkan bingkai teks dengan teks "Aspose: File Format APIs."

## Langkah 3: Tambahkan Hyperlink

Selanjutnya, mari tambahkan hyperlink ke bingkai teks yang Anda buat. Ini akan membuat teks dapat diklik.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

Pada langkah ini, kami menetapkan URL hyperlink ke "https://www.aspose.com/" dan memberikan tooltip untuk informasi tambahan. Anda juga dapat memformat tampilan hyperlink, seperti yang ditunjukkan di atas.

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi Anda dengan hyperlink yang ditambahkan.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Kode ini menyimpan presentasi sebagai "presentation-out.pptx."

Sekarang, Anda telah berhasil menambahkan hyperlink ke slide menggunakan Aspose.Slides untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara menambahkan hyperlink ke slide dalam presentasi PowerPoint menggunakan Aspose.Slides untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat membuat presentasi Anda lebih interaktif dan menarik, memberikan tautan berharga ke sumber daya atau informasi tambahan.

 Untuk informasi dan dokumentasi lebih rinci, kunjungi[Aspose.Slides untuk dokumentasi .NET](https://reference.aspose.com/slides/net/).

## FAQ

### 1. Bisakah saya menambahkan hyperlink ke bentuk lain selain bingkai teks?

Ya, Anda dapat menambahkan hyperlink ke berbagai bentuk seperti persegi panjang, gambar, dan lainnya menggunakan Aspose.Slides untuk .NET.

### 2. Bagaimana cara menghapus hyperlink dari bentuk di slide PowerPoint?

 Anda dapat menghapus hyperlink dari suatu bentuk dengan mengatur`HyperlinkClick` properti ke`null`.

### 3. Bisakah saya mengubah URL hyperlink secara dinamis di kode saya?

 Sangat! Anda dapat memperbarui URL hyperlink kapan saja dalam kode Anda dengan memodifikasi`Hyperlink` Properti.

### 4. Elemen interaktif apa lagi yang dapat saya tambahkan ke slide PowerPoint menggunakan Aspose.Slides?

Aspose.Slides menawarkan berbagai fitur interaktif, termasuk tombol aksi, elemen multimedia, dan animasi.

### 5. Apakah Aspose.Slides tersedia untuk bahasa pemrograman lain?

Ya, Aspose.Slides tersedia untuk berbagai bahasa pemrograman, termasuk Java dan Python.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
