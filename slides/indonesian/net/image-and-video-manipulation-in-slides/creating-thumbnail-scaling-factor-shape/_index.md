---
"description": "Pelajari cara membuat gambar mini PowerPoint dengan batasan tertentu menggunakan Aspose.Slides for .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar."
"linktitle": "Membuat Thumbnail dengan Faktor Skala untuk Bentuk di Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Membuat Thumbnail dengan Faktor Skala untuk Bentuk di Aspose.Slides"
"url": "/id/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Thumbnail dengan Faktor Skala untuk Bentuk di Aspose.Slides

## Perkenalan
Selamat datang di panduan lengkap kami tentang cara membuat gambar mini dengan batas untuk bentuk di Aspose.Slides untuk .NET. Aspose.Slides adalah pustaka canggih yang memungkinkan pengembang bekerja dengan lancar dengan presentasi PowerPoint di aplikasi .NET mereka. Dalam tutorial ini, kita akan mempelajari proses pembuatan gambar mini dengan batas tertentu untuk bentuk dalam presentasi menggunakan Aspose.Slides.
## Prasyarat
Sebelum kita memulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Slides untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.Slides. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang sesuai untuk .NET, seperti Visual Studio, di komputer Anda.
## Mengimpor Ruang Nama
Di aplikasi .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## Langkah 1: Siapkan Presentasi
Mulailah dengan membuat kelas Presentasi yang mewakili berkas presentasi PowerPoint yang ingin Anda gunakan:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Kode Anda untuk membuat gambar mini ada di sini
}
```
## Langkah 2: Buat Gambar Skala Penuh
Di dalam blok Presentasi, buat gambar skala penuh dari bentuk yang ingin Anda buat gambar mininya:
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
Selamat! Anda telah berhasil mempelajari cara membuat gambar mini dengan batas untuk bentuk menggunakan Aspose.Slides for .NET. Fitur ini dapat sangat berguna saat Anda perlu membuat gambar bentuk berukuran tertentu dalam presentasi PowerPoint Anda secara terprogram.
## Pertanyaan yang Sering Diajukan
### Q1: Dapatkah saya menggunakan Aspose.Slides dengan framework .NET lainnya?
Ya, Aspose.Slides kompatibel dengan berbagai kerangka kerja .NET, memberikan fleksibilitas untuk integrasi ke dalam berbagai jenis aplikasi.
### Q2: Apakah ada versi uji coba yang tersedia untuk Aspose.Slides?
Ya, Anda dapat menjelajahi fungsionalitas Aspose.Slides dengan mengunduh versi uji coba [Di Sini](https://releases.aspose.com/).
### Q3: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Slides?
Anda dapat memperoleh lisensi sementara untuk Aspose.Slides dengan mengunjungi [tautan ini](https://purchase.aspose.com/temporary-license/).
### Q4: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Slides?
Untuk pertanyaan atau bantuan apa pun, jangan ragu untuk mengunjungi forum dukungan Aspose.Slides [Di Sini](https://forum.aspose.com/c/slides/11).
### Q5: Dapatkah saya membeli Aspose.Slides untuk .NET?
Tentu saja! Untuk membeli Aspose.Slides untuk .NET, silakan kunjungi halaman pembelian [Di Sini](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}