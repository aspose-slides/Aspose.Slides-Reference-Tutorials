---
title: Mengubah Data Objek OLE di Presentasi dengan Aspose.Slides
linktitle: Mengubah Data Objek OLE di Presentasi dengan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Jelajahi kekuatan Aspose.Slides untuk .NET dalam mengubah data objek OLE dengan mudah. Sempurnakan presentasi Anda dengan konten dinamis.
weight: 25
url: /id/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Membuat presentasi PowerPoint yang dinamis dan interaktif merupakan kebutuhan umum di dunia digital saat ini. Salah satu alat canggih untuk mencapai hal ini adalah Aspose.Slides untuk .NET, pustaka tangguh yang memungkinkan pengembang memanipulasi dan menyempurnakan presentasi PowerPoint secara terprogram. Dalam tutorial ini, kita akan mempelajari proses mengubah data objek OLE (Object Linking and Embedding) dalam slide presentasi menggunakan Aspose.Slides.
## Prasyarat
Sebelum Anda mulai bekerja dengan Aspose.Slides untuk .NET, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Pengembangan: Siapkan lingkungan pengembangan dengan .NET terinstal.
2.  Perpustakaan Aspose.Slides: Unduh dan instal perpustakaan Aspose.Slides untuk .NET. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/slides/net/).
3. Pemahaman Dasar: Biasakan diri Anda dengan konsep dasar pemrograman C# dan presentasi PowerPoint.
## Impor Namespace
Dalam proyek C# Anda, impor namespace yang diperlukan untuk menggunakan fungsionalitas Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek C# baru dan mengimpor perpustakaan Aspose.Slides. Pastikan proyek Anda dikonfigurasi dengan benar, dan Anda memiliki dependensi yang diperlukan.
## Langkah 2: Akses Presentasi dan Slide
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Langkah 3: Temukan Objek OLE
Telusuri semua bentuk di slide untuk menemukan bingkai objek OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Langkah 4: Baca dan Ubah Data Buku Kerja
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Membaca data objek di Buku Kerja
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Memodifikasi data buku kerja
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Mengubah data objek bingkai Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Langkah 5: Simpan Presentasi
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Kesimpulan
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengubah data objek OLE dalam slide presentasi menggunakan Aspose.Slides untuk .NET. Ini membuka banyak kemungkinan untuk membuat presentasi yang dinamis dan disesuaikan dengan kebutuhan spesifik Anda.
## Pertanyaan yang Sering Diajukan
### Apa itu Aspose.Slide untuk .NET?
Aspose.Slides untuk .NET adalah pustaka canggih yang memungkinkan pengembang bekerja dengan presentasi PowerPoint secara terprogram, sehingga memudahkan manipulasi dan peningkatan.
### Di mana saya dapat menemukan dokumentasi Aspose.Slides?
 Dokumentasi untuk Aspose.Slides untuk .NET dapat ditemukan[Di Sini](https://reference.aspose.com/slides/net/).
### Bagaimana cara mengunduh Aspose.Slides untuk .NET?
 Anda dapat mengunduh perpustakaan dari halaman rilis[Di Sini](https://releases.aspose.com/slides/net/).
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
 Untuk dukungan dan diskusi, kunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
