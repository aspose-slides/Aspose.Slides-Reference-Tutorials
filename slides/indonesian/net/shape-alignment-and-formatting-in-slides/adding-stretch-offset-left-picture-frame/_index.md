---
"description": "Pelajari cara menyempurnakan presentasi PowerPoint menggunakan Aspose.Slides for .NET. Ikuti panduan langkah demi langkah kami untuk menambahkan offset peregangan ke kiri untuk bingkai gambar."
"linktitle": "Menambahkan Stretch Offset ke Kiri untuk Bingkai Gambar di Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Menambahkan Stretch Offset ke Kiri di PowerPoint dengan Aspose.Slide"
"url": "/id/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Stretch Offset ke Kiri di PowerPoint dengan Aspose.Slide

## Perkenalan
Aspose.Slides for .NET adalah pustaka hebat yang memungkinkan pengembang memanipulasi presentasi PowerPoint dengan mudah. Dalam tutorial ini, kita akan menjelajahi proses penambahan offset peregangan di sebelah kiri untuk bingkai gambar menggunakan Aspose.Slides for .NET. Ikuti panduan langkah demi langkah ini untuk meningkatkan keterampilan Anda dalam bekerja dengan gambar dan bentuk dalam presentasi PowerPoint.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Aspose.Slides untuk .NET: Pastikan Anda telah menginstal pustaka tersebut. Jika belum, unduh dari [Dokumentasi Aspose.Slides untuk .NET](https://reference.aspose.com/slides/net/).
- Lingkungan Pengembangan: Miliki lingkungan pengembangan yang berfungsi dengan kemampuan .NET.
## Mengimpor Ruang Nama
Mulailah dengan mengimpor namespace yang diperlukan dalam proyek .NET Anda:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Langkah 1: Siapkan Proyek Anda
Buat proyek baru atau buka proyek yang sudah ada. Pastikan Anda memiliki pustaka Aspose.Slides yang dirujuk dalam proyek Anda.
## Langkah 2: Buat Objek Presentasi
Membuat contoh `Presentation` kelas, yang mewakili file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Kode Anda untuk langkah selanjutnya akan diletakkan di sini.
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
Buat AutoShape bertipe Persegi Panjang:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Langkah 6: Atur Jenis Isi dan Mode Isi Gambar
Konfigurasikan jenis isian bentuk dan mode isian gambar:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Langkah 7: Atur Gambar untuk Mengisi Bentuk
Tentukan gambar untuk mengisi bentuk:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Langkah 8: Tentukan Offset Peregangan
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
Selamat! Anda telah berhasil menambahkan stretch offset di sebelah kiri untuk bingkai gambar menggunakan Aspose.Slides for .NET.
## Kesimpulan
Dalam tutorial ini, kami mengeksplorasi proses memanipulasi bingkai gambar dalam presentasi PowerPoint menggunakan Aspose.Slides for .NET. Dengan mengikuti panduan langkah demi langkah, Anda telah memperoleh wawasan tentang cara bekerja dengan gambar, bentuk, dan offset.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menerapkan stretch offset ke bentuk lain selain persegi panjang?
A: Meskipun tutorial ini berfokus pada persegi panjang, stretch offset dapat diterapkan ke berbagai bentuk yang didukung oleh Aspose.Slides.
### T: Bagaimana saya dapat menyesuaikan peregangan untuk efek yang berbeda-beda?
A: Lakukan eksperimen dengan nilai offset yang berbeda untuk mendapatkan dampak visual yang diinginkan. Sesuaikan nilai tersebut agar sesuai dengan kebutuhan spesifik Anda.
### T: Apakah Aspose.Slides kompatibel dengan kerangka kerja .NET terbaru?
A: Aspose.Slides diperbarui secara berkala untuk memastikan kompatibilitas dengan versi kerangka kerja .NET terbaru.
### T: Di mana saya dapat menemukan contoh dan sumber tambahan untuk Aspose.Slides?
A: Jelajahi [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/net/) untuk contoh dan panduan yang komprehensif.
### T: Dapatkah saya menerapkan beberapa stretch offset ke bentuk yang tunggal?
A: Ya, Anda dapat menggabungkan beberapa peregangan offset untuk mencapai efek visual yang kompleks dan disesuaikan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}