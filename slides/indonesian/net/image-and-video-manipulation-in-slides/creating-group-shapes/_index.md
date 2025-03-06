---
title: Aspose.Slides - Membuat Bentuk Grup di .NET
linktitle: Membuat Bentuk Grup di Slide Presentasi dengan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara membuat bentuk grup di PowerPoint dengan Aspose.Slides untuk .NET. Ikuti panduan langkah demi langkah kami untuk presentasi yang menarik secara visual.
weight: 11
url: /id/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Membuat Bentuk Grup di .NET

## Perkenalan
Jika Anda ingin meningkatkan daya tarik visual slide presentasi Anda dan mengatur konten dengan lebih efisien, menggabungkan bentuk grup adalah solusi yang ampuh. Aspose.Slides for .NET menyediakan cara yang mulus untuk membuat dan memanipulasi bentuk grup dalam presentasi PowerPoint Anda. Dalam tutorial ini, kita akan memandu proses pembuatan bentuk grup menggunakan Aspose.Slides, membaginya menjadi langkah-langkah yang mudah diikuti.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:
-  Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Slides. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan kerja dengan IDE yang kompatibel dengan .NET, seperti Visual Studio.
- Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.
## Impor Namespace
Dalam proyek C# Anda, mulailah dengan mengimpor namespace yang diperlukan:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Langkah 1: Buat Instansiasi Kelas Presentasi

 Buat sebuah instance dari`Presentation` kelas dan tentukan direktori tempat dokumen Anda disimpan:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Lanjutkan dengan langkah-langkah berikut dalam blok penggunaan ini
}
```

## Langkah 2: Akses Slide Pertama

Ambil slide pertama dari presentasi:

```csharp
ISlide sld = pres.Slides[0];
```

## Langkah 3: Mengakses Koleksi Bentuk

Akses koleksi bentuk pada slide:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Langkah 4: Menambahkan Bentuk Grup

Tambahkan bentuk grup ke slide:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Langkah 5: Menambahkan Bentuk Di Dalam Bentuk Grup

Isi bentuk grup dengan bentuk individual:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Langkah 6: Menambahkan Bingkai Bentuk Grup

Tentukan bingkai untuk seluruh bentuk grup:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Langkah 7: Simpan Presentasi

Simpan presentasi yang dimodifikasi ke direktori yang Anda tentukan:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Ulangi langkah-langkah ini di aplikasi C# Anda agar berhasil membuat bentuk grup di slide presentasi Anda menggunakan Aspose.Slides.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi proses pembuatan bentuk grup dengan Aspose.Slides untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat meningkatkan daya tarik visual dan organisasi presentasi PowerPoint Anda.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Slides kompatibel dengan .NET versi terbaru?
 Ya, Aspose.Slides diperbarui secara berkala untuk mendukung versi .NET terbaru. Periksalah[dokumentasi](https://reference.aspose.com/slides/net/) untuk detail kompatibilitas.
### Bisakah saya mencoba Aspose.Slides sebelum membeli?
 Sangat! Anda dapat mengunduh versi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk pertanyaan terkait Aspose.Slides?
Kunjungi Aspose.Slide[forum](https://forum.aspose.com/c/slides/11) untuk dukungan dan diskusi komunitas.
### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Slides?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat membeli lisensi penuh untuk Aspose.Slides?
 Anda dapat membeli lisensi dari[halaman pembelian](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
