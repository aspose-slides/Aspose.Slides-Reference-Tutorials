---
"description": "Pelajari cara menyempurnakan aplikasi .NET Anda dengan Aspose.Slides. Tutorial ini memandu Anda menambahkan segmen ke bentuk geometri untuk presentasi yang menarik."
"linktitle": "Menambahkan Segmen ke Bentuk Geometri dalam Presentasi dengan Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Menguasai Visual - Menambahkan Segmen dengan Aspose.Slides di .NET"
"url": "/id/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menguasai Visual - Menambahkan Segmen dengan Aspose.Slides di .NET

## Perkenalan
Dalam dunia pengembangan .NET, membuat presentasi yang menarik secara visual merupakan persyaratan umum. Aspose.Slides untuk .NET adalah pustaka canggih yang memfasilitasi integrasi yang lancar dari kemampuan pembuatan presentasi yang tangguh ke dalam aplikasi .NET Anda. Tutorial ini berfokus pada aspek khusus dari desain presentasi – menambahkan segmen ke bentuk geometri.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang bahasa pemrograman C#.
- Visual Studio terinstal di komputer Anda.
- Pustaka Aspose.Slides untuk .NET diunduh dan dirujuk dalam proyek Anda.
## Mengimpor Ruang Nama
Dalam kode C# Anda, pastikan untuk mengimpor namespace yang diperlukan untuk mengakses fungsi Aspose.Slides. Tambahkan baris berikut ke kode Anda:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Sekarang, mari kita uraikan contoh tersebut menjadi beberapa langkah.
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek C# baru di Visual Studio. Pastikan Anda memiliki pustaka Aspose.Slides yang dirujuk dalam proyek Anda.
## Langkah 2: Buat Presentasi
Inisialisasi objek presentasi baru menggunakan pustaka Aspose.Slides. Ini akan berfungsi sebagai kanvas untuk bentuk geometri Anda.
```csharp
using (Presentation pres = new Presentation())
{
    // Kode Anda untuk membuat presentasi ada di sini
}
```
## Langkah 3: Tambahkan Bentuk Geometri
Buat bentuk geometri dalam presentasi. Misalnya, mari tambahkan persegi panjang ke slide pertama.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Langkah 4: Dapatkan Jalur Geometri
Ambil jalur geometri bentuk yang dibuat untuk memanipulasi segmennya.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## Langkah 5: Tambahkan Segmen
Tambahkan segmen (garis) ke jalur geometri. Dalam contoh ini, dua garis ditambahkan ke jalur.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Langkah 6: Tetapkan Jalur Geometri yang Diedit
Tetapkan jalur geometri yang dimodifikasi kembali ke bentuk untuk menerapkan perubahan.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Langkah 7: Simpan Presentasi
Simpan presentasi yang dimodifikasi ke lokasi yang diinginkan.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Dengan langkah-langkah ini, Anda telah berhasil menambahkan segmen ke bentuk geometri dalam presentasi menggunakan Aspose.Slides for .NET.
## Kesimpulan
Aspose.Slides untuk .NET memberdayakan pengembang untuk meningkatkan aplikasi mereka dengan kemampuan pembuatan presentasi tingkat lanjut. Menambahkan segmen ke bentuk geometri menyediakan sarana untuk menyesuaikan elemen visual presentasi Anda.
### Pertanyaan yang Sering Diajukan
### Bisakah saya menambahkan berbagai jenis bentuk menggunakan Aspose.Slides?
Ya, Aspose.Slides mendukung berbagai jenis bentuk, termasuk persegi panjang, lingkaran, dan bentuk geometri khusus.
### Apakah diperlukan lisensi untuk menggunakan Aspose.Slides di proyek saya?
Ya, lisensi yang valid diperlukan. Anda dapat memperoleh lisensi sementara untuk keperluan pengujian atau membeli lisensi penuh untuk produksi.
### Bagaimana saya bisa mendapatkan dukungan untuk pertanyaan terkait Aspose.Slides?
Kunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk dukungan dan diskusi komunitas.
### Apakah ada tutorial lain yang tersedia untuk Aspose.Slides?
Jelajahi [dokumentasi](https://reference.aspose.com/slides/net/) untuk panduan dan contoh yang lengkap.
### Dapatkah saya mencoba Aspose.Slides secara gratis sebelum membeli?
Ya, Anda dapat mengunduh uji coba gratis dari [Di Sini](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}