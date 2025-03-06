---
title: Tutorial Menambahkan Bingkai Foto dengan Aspose.Slides .NET
linktitle: Menambahkan Bingkai Gambar dengan Tinggi Skala Relatif di Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menambahkan bingkai foto dengan tinggi skala relatif di Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah ini untuk presentasi yang lancar.
weight: 17
url: /id/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial Menambahkan Bingkai Foto dengan Aspose.Slides .NET

## Perkenalan
Aspose.Slides for .NET adalah pustaka canggih yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi presentasi PowerPoint dalam aplikasi .NET mereka dengan mudah. Dalam tutorial ini, kita akan mendalami proses menambahkan bingkai foto dengan tinggi skala relatif menggunakan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah ini untuk meningkatkan keterampilan membangun presentasi Anda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki yang berikut:
- Pengetahuan dasar bahasa pemrograman C#.
- Visual Studio atau lingkungan pengembangan C# pilihan lainnya diinstal.
- Aspose.Slides untuk perpustakaan .NET ditambahkan ke proyek Anda.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam kode C# Anda. Langkah ini memastikan bahwa Anda memiliki akses ke kelas dan fungsi yang disediakan oleh perpustakaan Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek C# baru di lingkungan pengembangan pilihan Anda. Pastikan untuk menambahkan pustaka Aspose.Slides for .NET ke proyek Anda dengan mereferensikannya.
## Langkah 2: Muat Presentasi dan Gambar
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //Muat Gambar yang akan ditambahkan dalam koleksi gambar presentasi
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Pada langkah ini, kita membuat objek presentasi baru dan memuat gambar yang ingin kita tambahkan ke presentasi.
## Langkah 3: Tambahkan Bingkai Foto ke Slide
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Sekarang, tambahkan bingkai foto ke slide pertama presentasi. Sesuaikan parameter seperti jenis bentuk, posisi, dan dimensi sesuai dengan kebutuhan Anda.
## Langkah 4: Atur Lebar dan Tinggi Skala Relatif
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Atur tinggi dan lebar skala relatif untuk bingkai foto untuk mencapai efek penskalaan yang diinginkan.
## Langkah 5: Simpan Presentasi
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Terakhir, simpan presentasi dengan bingkai foto tambahan dalam format keluaran yang ditentukan.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan bingkai foto dengan tinggi skala relatif menggunakan Aspose.Slides untuk .NET. Bereksperimenlah dengan berbagai gambar, posisi, dan skala untuk membuat presentasi menarik secara visual yang disesuaikan dengan kebutuhan Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menggunakan Aspose.Slides untuk .NET dengan bahasa pemrograman lain?
Aspose.Slides terutama mendukung bahasa .NET, namun Anda dapat menjelajahi produk Aspose lainnya untuk kompatibilitas dengan platform yang berbeda.
### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Slides untuk .NET?
 Mengacu kepada[dokumentasi](https://reference.aspose.com/slides/net/) untuk informasi lengkap dan contoh.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?
 Ya, Anda bisa mendapatkan[uji coba gratis](https://releases.aspose.com/) untuk mengevaluasi kemampuan perpustakaan.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
 Mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk mencari bantuan dari masyarakat dan para ahli Aspose.
### Di mana saya dapat membeli Aspose.Slides untuk .NET?
 Anda dapat membeli Aspose.Slides untuk .NET dari[halaman pembelian](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
