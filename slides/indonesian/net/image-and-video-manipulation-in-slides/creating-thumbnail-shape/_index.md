---
title: Buat Thumbnail Bentuk PowerPoint - Aspose.Slides .NET
linktitle: Membuat Thumbnail untuk Bentuk di Aspose.Slide
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara membuat gambar mini untuk bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk .NET. Panduan langkah demi langkah yang komprehensif untuk pengembang.
weight: 14
url: /id/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Aspose.Slides for .NET adalah perpustakaan canggih yang memberdayakan pengembang untuk bekerja secara lancar dengan presentasi PowerPoint. Salah satu fitur utamanya adalah kemampuan untuk menghasilkan thumbnail untuk bentuk dalam presentasi. Tutorial ini akan memandu Anda melalui proses pembuatan thumbnail untuk bentuk menggunakan Aspose.Slides untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Slides. Anda dapat mengunduhnya dari[halaman rilis](https://releases.aspose.com/slides/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai, seperti Visual Studio, dan miliki pemahaman dasar tentang pemrograman C#.
## Impor Namespace
Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam kode C# Anda. Namespace ini memfasilitasi komunikasi dengan perpustakaan Aspose.Slides. Tambahkan baris berikut di awal file C# Anda:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## Langkah 1: Siapkan Proyek Anda
Buat proyek C# baru di lingkungan pengembangan pilihan Anda. Pastikan perpustakaan Aspose.Slides direferensikan dalam proyek Anda.
## Langkah 2: Inisialisasi Presentasi
Buat instance kelas Presentasi untuk mewakili file PowerPoint. Berikan jalur ke file presentasi Anda di`dataDir` variabel.
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Kode Anda untuk pembuatan thumbnail ada di sini
}
```
## Langkah 3: Buat Gambar Skala Penuh
Hasilkan gambar skala penuh dari bentuk yang ingin Anda buat thumbnailnya. Dalam contoh ini, kita menggunakan bentuk pertama pada slide pertama (`presentation.Slides[0].Shapes[0]`).
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail())
{
    // Kode Anda untuk pembuatan thumbnail ada di sini
}
```
## Langkah 4: Simpan Gambar
Simpan gambar mini yang dihasilkan ke disk. Anda dapat memilih format di mana Anda ingin menyimpan gambar. Dalam contoh ini, kami menyimpannya dalam format PNG.
```csharp
bitmap.Save(dataDir + "Shape_thumbnail_out.png", ImageFormat.Png);
```
## Kesimpulan
Selamat! Anda telah berhasil membuat thumbnail untuk bentuk di Aspose.Slides untuk .NET. Fitur canggih ini menambah dimensi baru pada kemampuan Anda memanipulasi dan mengekstrak informasi dari presentasi PowerPoint.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya membuat thumbnail untuk berbagai bentuk dalam presentasi?
J: Ya, Anda dapat mengulang semua bentuk dalam slide dan membuat thumbnail untuk masing-masing bentuk.
### T: Apakah Aspose.Slides kompatibel dengan format file PowerPoint yang berbeda?
J: Aspose.Slides mendukung berbagai format file, termasuk PPTX, PPT, dan lainnya.
### T: Bagaimana cara menangani kesalahan saat pembuatan thumbnail?
J: Anda dapat menerapkan mekanisme penanganan kesalahan menggunakan blok coba-tangkap untuk mengelola pengecualian.
### T: Apakah ada batasan pada ukuran atau jenis bentuk yang boleh memiliki gambar mini?
J: Aspose.Slides memberikan fleksibilitas untuk membuat thumbnail untuk berbagai bentuk, termasuk kotak teks, gambar, dan lainnya.
### T: Dapatkah saya menyesuaikan ukuran dan resolusi gambar mini yang dihasilkan?
 A: Ya, Anda dapat menyesuaikan parameter saat memanggil`GetThumbnail` metode untuk mengontrol ukuran dan resolusi.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
