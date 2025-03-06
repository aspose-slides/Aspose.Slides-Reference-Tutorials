---
title: Menambahkan Garis Biasa ke Slide Presentasi menggunakan Aspose.Slides
linktitle: Menambahkan Garis Biasa ke Slide Presentasi menggunakan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Sempurnakan presentasi PowerPoint Anda di .NET menggunakan Aspose.Slides. Ikuti panduan langkah demi langkah kami untuk menambahkan garis polos dengan mudah.
weight: 16
url: /id/net/shape-effects-and-manipulation-in-slides/adding-plain-lines/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Membuat presentasi PowerPoint yang menarik dan menarik secara visual sering kali melibatkan penggabungan berbagai bentuk dan elemen. Jika Anda bekerja dengan .NET, Aspose.Slides adalah alat canggih yang menyederhanakan prosesnya. Tutorial ini berfokus pada menambahkan garis polos ke slide presentasi menggunakan Aspose.Slides untuk .NET. Ikuti terus untuk menyempurnakan presentasi Anda dengan panduan yang mudah diikuti ini.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman .NET.
- Menginstal Visual Studio atau lingkungan pengembangan .NET pilihan lainnya.
-  Aspose.Slides untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/slides/net/).
## Impor Namespace
Di proyek .NET Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Langkah 1: Siapkan Direktori Dokumen
Mulailah dengan menentukan jalur ke direktori dokumen Anda:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Langkah 2: Buat instance Kelas PresentationEx
 Buat sebuah instance dari`Presentation` kelas, mewakili file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Kode Anda untuk langkah selanjutnya akan ditempatkan di sini.
}
```
## Langkah 3: Dapatkan Slide Pertama
Akses slide pertama presentasi:
```csharp
ISlide sld = pres.Slides[0];
```
## Langkah 4: Tambahkan Garis Autoshape
Tambahkan bentuk otomatis garis ke slide:
```csharp
sld.Shapes.AddAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
Sesuaikan parameter (kiri, atas, lebar, tinggi) berdasarkan kebutuhan Anda.
## Langkah 5: Simpan Presentasi
Simpan presentasi yang dimodifikasi ke disk:
```csharp
pres.Save(dataDir + "LineShape1_out.pptx", SaveFormat.Pptx);
```
Ini menyimpulkan panduan langkah demi langkah tentang menambahkan garis polos ke slide presentasi menggunakan Aspose.Slides untuk .NET.
## Kesimpulan
Memasukkan garis sederhana ke dalam presentasi PowerPoint Anda dapat meningkatkan daya tarik visual secara signifikan. Aspose.Slides untuk .NET menyediakan cara mudah untuk mencapai hal ini. Bereksperimenlah dengan berbagai bentuk dan elemen untuk menciptakan presentasi yang menawan.
## FAQ
### T: Dapatkah saya menyesuaikan tampilan garis?
A: Ya, Anda dapat menyesuaikan warna, ketebalan, dan gaya menggunakan Aspose.Slides API.
### T: Apakah Aspose.Slides kompatibel dengan kerangka .NET terbaru?
J: Tentu saja, Aspose.Slides mendukung kerangka .NET terbaru.
### T: Di mana saya dapat menemukan contoh dan dokumentasi lainnya?
 J: Jelajahi dokumentasinya[Di Sini](https://reference.aspose.com/slides/net/).
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Slides?
 Sebuah kunjungan[Di Sini](https://purchase.aspose.com/temporary-license/) untuk izin sementara.
### T: Menghadapi masalah? Di mana saya bisa mendapatkan dukungan?
 J: Cari bantuan di[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
