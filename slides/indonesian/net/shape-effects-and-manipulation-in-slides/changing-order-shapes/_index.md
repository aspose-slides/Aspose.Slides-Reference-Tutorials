---
title: Membentuk Kembali Slide Presentasi dengan Aspose.Slides untuk .NET
linktitle: Mengubah Urutan Bentuk di Slide Presentasi menggunakan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara membentuk ulang slide presentasi menggunakan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah ini untuk menyusun ulang bentuk dan meningkatkan daya tarik visual.
weight: 26
url: /id/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Membuat slide presentasi yang menarik secara visual merupakan aspek penting dari komunikasi yang efektif. Aspose.Slides untuk .NET memberdayakan pengembang untuk memanipulasi slide secara terprogram, menawarkan berbagai fungsi. Dalam tutorial ini, kita akan mempelajari proses mengubah urutan bentuk di slide presentasi menggunakan Aspose.Slides untuk .NET.
## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Slides untuk .NET: Pastikan Anda memiliki perpustakaan Aspose.Slides yang terintegrasi ke dalam proyek .NET Anda. Jika belum, Anda dapat mendownloadnya dari[halaman rilis](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang berfungsi dengan Visual Studio atau alat pengembangan .NET lainnya.
- Pemahaman Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.
## Impor Namespace
Dalam proyek C# Anda, sertakan namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Slides:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Langkah 1: Siapkan Proyek Anda
Buat proyek baru di Visual Studio atau lingkungan pengembangan .NET pilihan Anda. Pastikan Aspose.Slides untuk .NET direferensikan dalam proyek Anda.
## Langkah 2: Muat Presentasi
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Langkah 3: Akses Slide dan Bentuk
```csharp
ISlide slide = presentation.Slides[0];
```
## Langkah 4: Tambahkan Bentuk Baru
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Langkah 5: Ubah Teks dalam Bentuk
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Langkah 6: Tambahkan Bentuk Lain
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Langkah 7: Ubah Urutan Bentuk
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Langkah 8: Simpan Presentasi yang Dimodifikasi
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Ini melengkapi panduan langkah demi langkah untuk mengubah urutan bentuk di slide presentasi menggunakan Aspose.Slides untuk .NET.
## Kesimpulan
Aspose.Slides untuk .NET menyederhanakan tugas memanipulasi slide presentasi secara terprogram. Dengan mengikuti tutorial ini, Anda telah mempelajari cara menyusun ulang bentuk, memungkinkan Anda meningkatkan daya tarik visual presentasi Anda.
## FAQ
### T: Bisakah saya menggunakan Aspose.Slides untuk .NET di lingkungan Windows dan Linux?
J: Ya, Aspose.Slides untuk .NET kompatibel dengan lingkungan Windows dan Linux.
### T: Apakah ada pertimbangan lisensi untuk menggunakan Aspose.Slides dalam proyek komersial?
 J: Ya, Anda dapat menemukan detail lisensi dan opsi pembelian di[Halaman pembelian Aspose.Slide](https://purchase.aspose.com/buy).
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?
 A: Ya, Anda dapat menjelajahi fitur-fiturnya dengan[uji coba gratis](https://releases.aspose.com/) tersedia di situs web Aspose.Slides.
### T: Di mana saya dapat menemukan dukungan atau mengajukan pertanyaan terkait Aspose.Slides untuk .NET?
 J: Kunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk mendapatkan dukungan dan terlibat dengan masyarakat.
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Slides untuk .NET?
 A: Anda dapat memperoleh a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
