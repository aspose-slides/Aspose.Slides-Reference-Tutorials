---
title: Menambahkan Stretch Offset ke Kiri di PowerPoint dengan Aspose.Slide
linktitle: Menambahkan Stretch Offset ke Kiri untuk Bingkai Gambar di Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menyempurnakan presentasi PowerPoint menggunakan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah kami untuk menambahkan offset regangan ke kiri untuk bingkai foto.
type: docs
weight: 14
url: /id/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## Perkenalan
Aspose.Slides for .NET adalah perpustakaan canggih yang memberdayakan pengembang untuk memanipulasi presentasi PowerPoint dengan mudah. Dalam tutorial ini, kita akan menjelajahi proses menambahkan offset regangan ke kiri untuk bingkai foto menggunakan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah ini untuk meningkatkan keterampilan Anda dalam bekerja dengan gambar dan bentuk dalam presentasi PowerPoint.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan. Jika tidak, unduh dari[Aspose.Slides untuk dokumentasi .NET](https://reference.aspose.com/slides/net/).
- Lingkungan Pengembangan: Memiliki lingkungan pengembangan yang berfungsi dengan kemampuan .NET.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan dalam proyek .NET Anda:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Langkah 1: Siapkan Proyek Anda
Buat proyek baru atau buka proyek yang sudah ada. Pastikan Anda memiliki perpustakaan Aspose.Slides yang direferensikan dalam proyek Anda.
## Langkah 2: Buat Objek Presentasi
 Buat instance`Presentation` kelas, mewakili file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Kode Anda untuk langkah selanjutnya akan ditempatkan di sini.
}
```
## Langkah 3: Dapatkan Slide Pertama
Ambil slide pertama dari presentasi:
```csharp
ISlide slide = pres.Slides[0];
```
## Langkah 4: Buat Instansiasi Gambar
Muat gambar yang ingin Anda gunakan:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Langkah 5: Tambahkan BentukOtomatis Persegi Panjang
Buat BentukOtomatis tipe Persegi Panjang:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Langkah 6: Atur Jenis Isian dan Mode Isi Gambar
Konfigurasikan tipe isian bentuk dan mode isian gambar:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Langkah 7: Atur Gambar untuk Mengisi Bentuk
Tentukan gambar untuk mengisi bentuk:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Langkah 8: Tentukan Stretch Offset
Tentukan offset gambar dari tepi kotak pembatas bentuk yang sesuai:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Langkah 9: Simpan Presentasi
Tulis file PPTX ke disk:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Selamat! Anda telah berhasil menambahkan offset regangan ke kiri untuk bingkai foto menggunakan Aspose.Slides untuk .NET.
## Kesimpulan
Dalam tutorial ini, kita menjelajahi proses memanipulasi bingkai foto dalam presentasi PowerPoint menggunakan Aspose.Slides untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda memperoleh wawasan dalam bekerja dengan gambar, bentuk, dan offset.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menerapkan offset regangan pada bentuk lain selain persegi panjang?
J: Meskipun tutorial ini berfokus pada persegi panjang, offset regangan dapat diterapkan ke berbagai bentuk yang didukung oleh Aspose.Slides.
### T: Bagaimana cara menyesuaikan offset regangan untuk efek yang berbeda?
J: Bereksperimenlah dengan nilai offset yang berbeda untuk mencapai dampak visual yang diinginkan. Sesuaikan nilai agar sesuai dengan kebutuhan spesifik Anda.
### T: Apakah Aspose.Slides kompatibel dengan kerangka .NET terbaru?
J: Aspose.Slides diperbarui secara berkala untuk memastikan kompatibilitas dengan versi kerangka .NET terbaru.
### T: Di mana saya dapat menemukan contoh dan sumber tambahan untuk Aspose.Slides?
 J: Jelajahi[Dokumentasi Aspose.Slide](https://reference.aspose.com/slides/net/) untuk contoh dan bimbingan yang komprehensif.
### T: Bisakah saya menerapkan beberapa offset regangan ke satu bentuk?
J: Ya, Anda dapat menggabungkan beberapa peregangan offset untuk mencapai efek visual yang kompleks dan dapat disesuaikan.