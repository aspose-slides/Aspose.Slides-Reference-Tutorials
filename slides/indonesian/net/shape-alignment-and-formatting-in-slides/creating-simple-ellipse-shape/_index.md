---
title: Buat Bentuk Ellipse dengan Mudah dengan Aspose.Slides .NET
linktitle: Membuat Bentuk Elips Sederhana di Slide Presentasi dengan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara membuat bentuk elips yang menakjubkan di slide presentasi menggunakan Aspose.Slides untuk .NET. Langkah mudah untuk desain dinamis!
weight: 11
url: /id/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Dalam dunia desain presentasi yang dinamis, menggabungkan bentuk seperti elips dapat menambah sentuhan kreativitas dan profesionalisme. Aspose.Slides untuk .NET menawarkan solusi ampuh untuk memanipulasi file presentasi secara terprogram. Tutorial ini akan memandu Anda melalui proses pembuatan bentuk elips sederhana di slide presentasi menggunakan Aspose.Slides untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari[halaman rilis](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET di mesin Anda.
## Impor Namespace
Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Namespace ini menyediakan kelas dan metode penting yang diperlukan untuk bekerja dengan slide dan bentuk presentasi.
## Langkah 1: Siapkan Presentasi
Mulailah dengan membuat presentasi baru dan mengakses slide pertama. Tambahkan kode berikut untuk mencapai hal ini:
```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Kelas Presentasi Instantiate
using (Presentation pres = new Presentation())
{
    // Dapatkan slide pertama
    ISlide sld = pres.Slides[0];
```
Kode ini menginisialisasi presentasi baru dan memilih slide pertama untuk manipulasi lebih lanjut.
## Langkah 2: Tambahkan Bentuk Elips
 Sekarang, mari tambahkan bentuk elips ke slide menggunakan`AddAutoShape` metode:
```csharp
// Tambahkan bentuk otomatis tipe elips
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Baris kode ini membuat bentuk elips pada koordinat (50, 150) dengan lebar 150 satuan dan tinggi 50 satuan.
## Langkah 3: Simpan Presentasi
Terakhir, simpan presentasi yang dimodifikasi ke disk dengan nama file tertentu menggunakan kode berikut:
```csharp
// Tulis file PPTX ke disk
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Langkah ini memastikan bahwa perubahan Anda tetap ada, dan Anda bisa melihat presentasi yang dihasilkan dengan bentuk elips yang baru ditambahkan.
## Kesimpulan
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## FAQ
### Bisakah saya menyesuaikan bentuk elips lebih lanjut?
Ya, Anda dapat memodifikasi berbagai properti bentuk elips, seperti warna, ukuran, dan posisi, untuk memenuhi kebutuhan desain spesifik Anda.
### Apakah Aspose.Slides kompatibel dengan kerangka .NET terbaru?
Ya, Aspose.Slides diperbarui secara berkala untuk memastikan kompatibilitas dengan kerangka .NET terbaru.
### Di mana saya dapat menemukan lebih banyak tutorial dan contoh untuk Aspose.Slides?
 Mengunjungi[dokumentasi](https://reference.aspose.com/slides/net/) untuk panduan dan contoh yang komprehensif.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Slides?
 Ikuti[tautan lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk meminta izin sementara untuk tujuan pengujian.
### Butuh bantuan atau punya pertanyaan spesifik?
 Mengunjungi[Forum dukungan Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk mendapatkan bantuan dari masyarakat dan para ahli.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
