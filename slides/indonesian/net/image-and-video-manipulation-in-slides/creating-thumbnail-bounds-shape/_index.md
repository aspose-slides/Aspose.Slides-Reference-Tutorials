---
title: Membuat Thumbnail dengan Batas untuk Bentuk di Aspose.Slide
linktitle: Membuat Thumbnail dengan Batas untuk Bentuk di Aspose.Slide
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Buka kekuatan Aspose.Slides untuk .NET! Pelajari cara membuat thumbnail bentuk dengan mudah dan berbatas menggunakan panduan langkah demi langkah kami.
type: docs
weight: 10
url: /id/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/
---
## Perkenalan
Jika Anda seorang pengembang .NET yang mencari solusi tangguh untuk membuat gambar mini dengan batas bentuk dalam presentasi PowerPoint, Aspose.Slides untuk .NET adalah alat bantu Anda. Pustaka canggih ini memberikan integrasi yang lancar, memungkinkan Anda memanipulasi dan mengekstrak informasi berharga dari file PowerPoint secara efisien. Dalam tutorial ini, kita akan memandu proses pembuatan thumbnail dengan batas untuk suatu bentuk menggunakan Aspose.Slides.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Slides for .NET Library: Unduh dan instal perpustakaan Aspose.Slides for .NET dari[Di Sini](https://releases.aspose.com/slides/net/).
2. Direktori Dokumen Anda: Ganti "Direktori Dokumen Anda" di cuplikan kode dengan jalur sebenarnya ke direktori dokumen Anda.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Slides. Tambahkan kode berikut di awal proyek Anda:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
Sekarang, mari kita bagi kode yang diberikan menjadi beberapa langkah untuk pemahaman yang komprehensif:
## Langkah 1: Buat Instansiasi Kelas Presentasi
```csharp
string dataDir = "Your Documents Directory";
// Buat instance kelas Presentasi yang mewakili file presentasi
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Objek presentasi sekarang siap untuk manipulasi lebih lanjut.
}
```
 Pada langkah ini, kami menginisialisasi Aspose.Slides`Presentation` kelas, mewakili file presentasi PowerPoint. Itu`using` pernyataan memastikan pembuangan sumber daya dengan benar setelah blok keluar.
## Langkah 2: Buat Gambar Bentuk Terikat
```csharp
// Buat gambar bentuk terikat Penampilan
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // Objek bitmap sekarang berisi gambar mini dengan batas tertentu.
}
```
 Langkah ini melibatkan pembuatan gambar mini suatu bentuk dengan batas tertentu. Di Sini,`ShapeThumbnailBounds.Appearance` digunakan untuk menentukan batas penampilan. Sesuaikan parameter (1, 1) sesuai dengan kebutuhan Anda.
## Langkah 3: Simpan Gambar ke Disk
```csharp
//Simpan gambar ke disk dalam format PNG
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```
Pada langkah terakhir ini, gambar thumbnail yang dihasilkan disimpan ke disk dalam format PNG. Anda dapat menyesuaikan nama dan format file berdasarkan preferensi Anda.
Sekarang, Anda telah berhasil membuat thumbnail dengan batas untuk suatu bentuk menggunakan Aspose.Slides untuk .NET! Proses ini efisien dan dapat diintegrasikan dengan mulus ke dalam proyek .NET Anda untuk menangani presentasi PowerPoint.
## Kesimpulan
Aspose.Slides untuk .NET menyederhanakan proses bekerja dengan presentasi PowerPoint, memberikan pengembang alat canggih untuk tugas-tugas seperti membuat gambar mini dengan batasan bentuk. Dengan mengikuti panduan langkah demi langkah ini, Anda mendapatkan wawasan tentang cara memanfaatkan perpustakaan ini secara efisien untuk proyek .NET Anda.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Slides kompatibel dengan kerangka .NET terbaru?
Ya, Aspose.Slides diperbarui secara berkala untuk memastikan kompatibilitas dengan versi kerangka .NET terbaru.
### Bisakah saya menggunakan Aspose.Slides untuk proyek komersial?
 Sangat! Aspose.Slides menawarkan opsi lisensi untuk penggunaan individu dan komersial. Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk menjelajahi detail perizinan.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/)untuk menjelajahi fitur sebelum melakukan pembelian.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides?
 Mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk terhubung dengan komunitas dan mencari bantuan dari pengembang berpengalaman.
### Bisakah saya mendapatkan lisensi sementara untuk Aspose.Slides?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk kebutuhan proyek jangka pendek.