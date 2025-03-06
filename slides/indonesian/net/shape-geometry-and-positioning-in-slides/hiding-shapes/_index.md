---
title: Sembunyikan Bentuk di PowerPoint dengan Tutorial Aspose.Slides .NET
linktitle: Menyembunyikan Bentuk di Slide Presentasi dengan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menyembunyikan bentuk di slide PowerPoint menggunakan Aspose.Slides untuk .NET. Sesuaikan presentasi secara terprogram dengan panduan langkah demi langkah ini.
weight: 21
url: /id/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sembunyikan Bentuk di PowerPoint dengan Tutorial Aspose.Slides .NET

## Perkenalan
Dalam dunia presentasi yang dinamis, penyesuaian adalah kuncinya. Aspose.Slides untuk .NET memberikan solusi ampuh untuk memanipulasi presentasi PowerPoint secara terprogram. Salah satu persyaratan umum adalah kemampuan untuk menyembunyikan bentuk tertentu dalam slide. Tutorial ini akan memandu Anda melalui proses menyembunyikan bentuk di slide presentasi menggunakan Aspose.Slides untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Slides. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan pilihan Anda untuk .NET.
- Pengetahuan Dasar C#: Biasakan diri Anda dengan C# karena contoh kode yang diberikan dalam bahasa ini.
## Impor Namespace
Untuk mulai bekerja dengan Aspose.Slides, impor namespace yang diperlukan dalam proyek C# Anda. Ini memastikan bahwa Anda memiliki akses ke kelas dan metode yang diperlukan.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Sekarang, mari kita pecahkan kode contoh menjadi beberapa langkah untuk pemahaman yang jelas dan ringkas.
## Langkah 1: Siapkan Proyek Anda
Buat proyek C# baru dan pastikan untuk menyertakan perpustakaan Aspose.Slides.
## Langkah 2: Buat Presentasi
 Buat instance`Presentation` kelas, mewakili file PowerPoint. Tambahkan slide dan dapatkan referensi ke sana.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Langkah 3: Tambahkan Bentuk ke Slide
Tambahkan bentuk otomatis ke slide, seperti persegi panjang dan bulan, dengan dimensi tertentu.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Langkah 4: Sembunyikan Bentuk Berdasarkan Teks Alternatif
Tentukan teks alternatif dan sembunyikan bentuk yang cocok dengan teks ini.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Langkah 5: Simpan Presentasi
Simpan presentasi yang dimodifikasi ke disk dalam format PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Kesimpulan
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## FAQ
### Apakah Aspose.Slides kompatibel dengan .NET Core?
Ya, Aspose.Slides mendukung .NET Core, memberikan fleksibilitas dalam lingkungan pengembangan Anda.
### Bisakah saya menyembunyikan bentuk berdasarkan kondisi selain teks alternatif?
Sangat! Anda dapat menyesuaikan logika persembunyian berdasarkan berbagai atribut seperti tipe bentuk, warna, atau posisi.
### Di mana saya dapat menemukan dokumentasi Aspose.Slides tambahan?
 Jelajahi dokumentasinya[Di Sini](https://reference.aspose.com/slides/net/)untuk informasi mendalam dan contoh.
### Apakah lisensi sementara tersedia untuk Aspose.Slides?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/)untuk tujuan pengujian.
### Bagaimana saya bisa mendapatkan dukungan komunitas untuk Aspose.Slides?
 Bergabunglah dengan komunitas Aspose.Slides di[forum](https://forum.aspose.com/c/slides/11) untuk diskusi dan bantuan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
