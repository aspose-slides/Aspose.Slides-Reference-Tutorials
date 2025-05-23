---
"description": "Pelajari cara menambahkan bentuk sketsa kreatif ke slide presentasi Anda menggunakan Aspose.Slides for .NET. Tingkatkan daya tarik visual dengan mudah!"
"linktitle": "Membuat Bentuk Sketsa dalam Slide Presentasi dengan Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Buat Bentuk Sketsa yang Menakjubkan dengan Aspose.Slides"
"url": "/id/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Buat Bentuk Sketsa yang Menakjubkan dengan Aspose.Slides

## Perkenalan
Selamat datang di panduan langkah demi langkah kami tentang membuat bentuk sketsa dalam slide presentasi menggunakan Aspose.Slides untuk .NET. Jika Anda ingin menambahkan sentuhan kreativitas pada presentasi Anda, bentuk sketsa memberikan estetika yang unik dan digambar dengan tangan. Dalam tutorial ini, kami akan memandu Anda melalui prosesnya, membaginya menjadi beberapa langkah sederhana untuk memastikan pengalaman yang lancar.
## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Aspose.Slides untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.Slides untuk .NET. Anda dapat mengunduhnya [Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET dengan IDE pilihan Anda.
## Mengimpor Ruang Nama
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
## Langkah 2: Inisialisasi Aspose.Slides
Inisialisasi Aspose.Slides dengan menambahkan potongan kode berikut. Ini akan menyiapkan presentasi dan menentukan jalur keluaran untuk berkas presentasi dan gambar mini.
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
Sekarang, mari tambahkan bentuk sketsa ke slide. Dalam contoh ini, kita akan menambahkan persegi panjang dengan efek sketsa bebas.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Ubah bentuk menjadi sketsa gaya tangan bebas
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Langkah 4: Hasilkan Gambar Mini
Buat thumbnail slide untuk memvisualisasikan bentuk yang dibuat sketsa. Simpan thumbnail sebagai file PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Langkah 5: Simpan Presentasi
Simpan berkas presentasi dengan bentuk yang dibuat sketsanya.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Selesai! Anda telah berhasil membuat presentasi dengan bentuk sketsa menggunakan Aspose.Slides for .NET.
## Kesimpulan
Menambahkan bentuk sketsa ke slide presentasi Anda dapat meningkatkan daya tarik visual dan menarik perhatian audiens Anda. Dengan Aspose.Slides untuk .NET, prosesnya menjadi mudah, memungkinkan Anda untuk melepaskan kreativitas Anda dengan mudah.
## Tanya Jawab Umum
### 1. Bisakah saya menyesuaikan efek sketsa?
Ya, Aspose.Slides untuk .NET menyediakan berbagai opsi penyesuaian untuk efek sketsa. Lihat [dokumentasi](https://reference.aspose.com/slides/net/) untuk informasi lebih rinci.
### 2. Apakah ada uji coba gratis yang tersedia?
Tentu saja! Anda dapat mencoba uji coba gratis Aspose.Slides untuk .NET [Di Sini](https://releases.aspose.com/).
### 3. Di mana saya bisa mendapatkan dukungan?
Untuk bantuan atau pertanyaan, kunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Bagaimana cara membeli Aspose.Slides untuk .NET?
Untuk membeli Aspose.Slides untuk .NET, kunjungi [halaman pembelian](https://purchase.aspose.com/buy).
### 5. Apakah Anda menawarkan lisensi sementara?
Ya, lisensi sementara tersedia [Di Sini](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}