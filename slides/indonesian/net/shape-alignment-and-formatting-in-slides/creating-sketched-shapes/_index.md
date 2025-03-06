---
title: Buat Bentuk Sketsa yang Menakjubkan dengan Aspose.Slides
linktitle: Membuat Bentuk Sketsa di Slide Presentasi dengan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menambahkan bentuk sketsa kreatif ke slide presentasi Anda menggunakan Aspose.Slides untuk .NET. Tingkatkan daya tarik visual dengan mudah!
weight: 13
url: /id/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Selamat datang di panduan langkah demi langkah kami dalam membuat sketsa bentuk di slide presentasi menggunakan Aspose.Slides untuk .NET. Jika Anda ingin menambahkan sentuhan kreativitas pada presentasi Anda, bentuk sketsa memberikan estetika unik dan digambar tangan. Dalam tutorial ini, kami akan memandu Anda melalui prosesnya, memecahnya menjadi langkah-langkah sederhana untuk memastikan pengalaman yang lancar.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Slides untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET dengan IDE pilihan Anda.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan dalam proyek .NET Anda. Langkah ini memastikan bahwa Anda memiliki akses ke kelas dan fungsi yang diperlukan untuk bekerja dengan Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Langkah 1: Siapkan Proyek
Mulailah dengan membuat proyek .NET baru atau membuka proyek yang sudah ada. Pastikan untuk menyertakan Aspose.Slides dalam referensi proyek Anda.
## Langkah 2: Inisialisasi Aspose.Slide
Inisialisasi Aspose.Slides dengan menambahkan cuplikan kode berikut. Ini mengatur presentasi dan menentukan jalur keluaran untuk file presentasi dan gambar mini.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Lanjutkan ke langkah berikutnya...
}
```
## Langkah 3: Tambahkan Bentuk Sketsa
Sekarang, mari tambahkan bentuk sketsa ke slide. Dalam contoh ini, kita akan menambahkan persegi panjang dengan efek sketsa tangan bebas.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Ubah bentuk menjadi sketsa gaya tangan bebas
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Langkah 4: Hasilkan Gambar Kecil
Buat thumbnail slide untuk memvisualisasikan bentuk sketsa. Simpan thumbnail sebagai file PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Langkah 5: Simpan Presentasi
Simpan file presentasi dengan bentuk sketsa.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Itu dia! Anda telah berhasil membuat presentasi dengan bentuk sketsa menggunakan Aspose.Slides untuk .NET.
## Kesimpulan
Menambahkan bentuk sketsa ke slide presentasi Anda dapat meningkatkan daya tarik visual dan melibatkan audiens Anda. Dengan Aspose.Slides untuk .NET, prosesnya menjadi mudah, memungkinkan Anda melepaskan kreativitas Anda dengan mudah.
## FAQ
### 1. Bisakah saya menyesuaikan efek sketsa?
 Ya, Aspose.Slides untuk .NET menyediakan berbagai opsi penyesuaian untuk efek sketsa. Mengacu kepada[dokumentasi](https://reference.aspose.com/slides/net/) untuk informasi rinci.
### 2. Apakah tersedia uji coba gratis?
 Tentu! Anda dapat menjelajahi uji coba gratis Aspose.Slides untuk .NET[Di Sini](https://releases.aspose.com/).
### 3. Dimana saya bisa mendapatkan dukungan?
 Untuk bantuan atau pertanyaan apa pun, kunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
### 4. Bagaimana cara membeli Aspose.Slides untuk .NET?
 Untuk membeli Aspose.Slides untuk .NET, kunjungi[halaman pembelian](https://purchase.aspose.com/buy).
### 5. Apakah Anda menawarkan lisensi sementara?
 Ya, lisensi sementara tersedia[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
