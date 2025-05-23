---
"description": "Pelajari cara menyembunyikan bentuk di slide PowerPoint menggunakan Aspose.Slides for .NET. Sesuaikan presentasi secara terprogram dengan panduan langkah demi langkah ini."
"linktitle": "Menyembunyikan Bentuk dalam Slide Presentasi dengan Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Menyembunyikan Bentuk di PowerPoint dengan Tutorial Aspose.Slides .NET"
"url": "/id/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menyembunyikan Bentuk di PowerPoint dengan Tutorial Aspose.Slides .NET

## Perkenalan
Dalam dunia presentasi yang dinamis, kustomisasi adalah kuncinya. Aspose.Slides for .NET menyediakan solusi yang hebat untuk memanipulasi presentasi PowerPoint secara terprogram. Salah satu persyaratan umum adalah kemampuan untuk menyembunyikan bentuk tertentu dalam slide. Tutorial ini akan memandu Anda melalui proses menyembunyikan bentuk dalam slide presentasi menggunakan Aspose.Slides for .NET.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Aspose.Slides untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.Slides. Anda dapat mengunduhnya [Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan pilihan Anda untuk .NET.
- Pengetahuan Dasar C#: Biasakan diri Anda dengan C# karena contoh kode yang disediakan dalam bahasa ini.
## Mengimpor Ruang Nama
Untuk mulai bekerja dengan Aspose.Slides, impor namespace yang diperlukan dalam proyek C# Anda. Ini memastikan bahwa Anda memiliki akses ke kelas dan metode yang diperlukan.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Sekarang, mari kita uraikan kode contoh tersebut menjadi beberapa langkah agar pemahamannya jelas dan ringkas.
## Langkah 1: Siapkan Proyek Anda
Buat proyek C# baru dan pastikan untuk menyertakan pustaka Aspose.Slides.
## Langkah 2: Buat Presentasi
Membuat contoh `Presentation` kelas, yang mewakili berkas PowerPoint. Tambahkan slide dan dapatkan referensinya.
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
Selamat! Anda telah berhasil menyembunyikan bentuk dalam presentasi Anda menggunakan Aspose.Slides for .NET. Ini membuka banyak kemungkinan untuk membuat slide yang dinamis dan disesuaikan secara terprogram.
---
## Tanya Jawab Umum
### Apakah Aspose.Slides kompatibel dengan .NET Core?
Ya, Aspose.Slides mendukung .NET Core, memberikan fleksibilitas dalam lingkungan pengembangan Anda.
### Bisakah saya menyembunyikan bentuk berdasarkan kondisi selain teks alternatif?
Tentu saja! Anda dapat menyesuaikan logika penyembunyian berdasarkan berbagai atribut seperti jenis bentuk, warna, atau posisi.
### Di mana saya dapat menemukan dokumentasi Aspose.Slides tambahan?
Jelajahi dokumentasi [Di Sini](https://reference.aspose.com/slides/net/) untuk informasi dan contoh yang mendalam.
### Apakah lisensi sementara tersedia untuk Aspose.Slides?
Ya, Anda bisa mendapatkan lisensi sementara [Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.
### Bagaimana saya bisa mendapatkan dukungan komunitas untuk Aspose.Slides?
Bergabunglah dengan komunitas Aspose.Slides di [forum](https://forum.aspose.com/c/slides/11) untuk diskusi dan bantuan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}