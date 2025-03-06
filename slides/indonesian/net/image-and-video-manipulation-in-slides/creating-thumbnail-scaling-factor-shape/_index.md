---
title: Membuat Thumbnail dengan Faktor Penskalaan untuk Bentuk di Aspose.Slide
linktitle: Membuat Thumbnail dengan Faktor Penskalaan untuk Bentuk di Aspose.Slide
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara membuat gambar mini PowerPoint dengan batas tertentu menggunakan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
weight: 12
url: /id/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Selamat datang di panduan komprehensif kami tentang cara membuat gambar mini dengan batasan bentuk di Aspose.Slides untuk .NET. Aspose.Slides adalah perpustakaan canggih yang memungkinkan pengembang bekerja secara lancar dengan presentasi PowerPoint di aplikasi .NET mereka. Dalam tutorial ini, kita akan mempelajari proses pembuatan gambar mini dengan batasan khusus untuk bentuk dalam presentasi menggunakan Aspose.Slides.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Slides. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Miliki lingkungan pengembangan yang sesuai untuk .NET, seperti Visual Studio, yang disiapkan di mesin Anda.
## Impor Namespace
Di aplikasi .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## Langkah 1: Siapkan Presentasi
Mulailah dengan membuat instance kelas Presentasi yang mewakili file presentasi PowerPoint yang ingin Anda kerjakan:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Kode Anda untuk menghasilkan thumbnail ada di sini
}
```
## Langkah 2: Buat Gambar Skala Penuh
Di dalam blok Presentasi, buat gambar skala penuh dari bentuk yang ingin Anda buatkan thumbnail:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // Kode Anda untuk menyimpan gambar ada di sini
}
```
## Langkah 3: Simpan Gambar ke Disk
Simpan gambar yang dihasilkan ke disk, tentukan formatnya (dalam hal ini, PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara membuat gambar mini dengan batas bentuk menggunakan Aspose.Slides untuk .NET. Fitur ini bisa sangat berguna ketika Anda perlu menghasilkan gambar bentuk berukuran tertentu dalam presentasi PowerPoint Anda secara terprogram.
## Pertanyaan yang Sering Diajukan
### Q1: Dapatkah saya menggunakan Aspose.Slides dengan kerangka .NET lainnya?
Ya, Aspose.Slides kompatibel dengan berbagai kerangka .NET, memberikan fleksibilitas untuk integrasi ke berbagai jenis aplikasi.
### Q2: Apakah ada versi uji coba yang tersedia untuk Aspose.Slides?
 Ya, Anda dapat menjelajahi fungsionalitas Aspose.Slides dengan mengunduh versi uji coba[Di Sini](https://releases.aspose.com/).
### Q3: Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Slides?
 Anda dapat memperoleh lisensi sementara untuk Aspose.Slides dengan mengunjungi[Link ini](https://purchase.aspose.com/temporary-license/).
### Q4: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Slides?
 Untuk pertanyaan atau bantuan apa pun, silakan kunjungi forum dukungan Aspose.Slides[Di Sini](https://forum.aspose.com/c/slides/11).
### Q5: Bisakah saya membeli Aspose.Slides untuk .NET?
 Tentu! Untuk membeli Aspose.Slides untuk .NET, silakan kunjungi halaman pembelian[Di Sini](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
