---
"description": "Pelajari cara menambahkan bingkai gambar dengan tinggi skala relatif di Aspose.Slides for .NET. Ikuti panduan langkah demi langkah ini untuk presentasi yang lancar."
"linktitle": "Menambahkan Bingkai Gambar dengan Tinggi Skala Relatif di Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Tutorial Menambahkan Bingkai Foto dengan Aspose.Slides .NET"
"url": "/id/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial Menambahkan Bingkai Foto dengan Aspose.Slides .NET

## Perkenalan
Aspose.Slides untuk .NET adalah pustaka canggih yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi presentasi PowerPoint dalam aplikasi .NET mereka dengan mudah. Dalam tutorial ini, kita akan menyelami proses penambahan bingkai foto dengan tinggi skala relatif menggunakan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah ini untuk meningkatkan keterampilan Anda dalam membuat presentasi.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang bahasa pemrograman C#.
- Visual Studio atau lingkungan pengembangan C# pilihan lainnya telah terpasang.
- Pustaka Aspose.Slides untuk .NET ditambahkan ke proyek Anda.
## Mengimpor Ruang Nama
Mulailah dengan mengimpor namespace yang diperlukan ke dalam kode C# Anda. Langkah ini memastikan bahwa Anda memiliki akses ke kelas dan fungsi yang disediakan oleh pustaka Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Langkah 1: Siapkan Proyek Anda
Mulailah dengan membuat proyek C# baru di lingkungan pengembangan pilihan Anda. Pastikan untuk menambahkan pustaka Aspose.Slides for .NET ke proyek Anda dengan merujuknya.
## Langkah 2: Muat Presentasi dan Gambar
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Muat Gambar yang akan ditambahkan ke koleksi gambar presentasi
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Pada langkah ini, kita membuat objek presentasi baru dan memuat gambar yang ingin kita tambahkan ke presentasi.
## Langkah 3: Tambahkan Bingkai Gambar ke Slide
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Sekarang, tambahkan bingkai foto ke slide pertama presentasi. Sesuaikan parameter seperti jenis bentuk, posisi, dan dimensi sesuai kebutuhan Anda.
## Langkah 4: Mengatur Skala Lebar dan Tinggi Relatif
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Atur tinggi dan lebar skala relatif untuk bingkai gambar untuk mencapai efek skala yang diinginkan.
## Langkah 5: Simpan Presentasi
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Terakhir, simpan presentasi dengan bingkai gambar tambahan dalam format keluaran yang ditentukan.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan bingkai gambar dengan tinggi skala relatif menggunakan Aspose.Slides untuk .NET. Bereksperimenlah dengan berbagai gambar, posisi, dan skala untuk membuat presentasi yang menarik secara visual sesuai dengan kebutuhan Anda.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menggunakan Aspose.Slides untuk .NET dengan bahasa pemrograman lain?
Aspose.Slides terutama mendukung bahasa .NET, tetapi Anda dapat menjelajahi produk Aspose lainnya untuk kompatibilitas dengan platform lain.
### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Slides for .NET?
Mengacu kepada [dokumentasi](https://reference.aspose.com/slides/net/) untuk informasi dan contoh yang lengkap.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?
Ya, Anda bisa mendapatkannya [uji coba gratis](https://releases.aspose.com/) untuk mengevaluasi kemampuan perpustakaan.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
Kunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk mencari bantuan dari komunitas dan pakar Aspose.
### Di mana saya dapat membeli Aspose.Slides untuk .NET?
Anda dapat membeli Aspose.Slides untuk .NET dari [halaman pembelian](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}