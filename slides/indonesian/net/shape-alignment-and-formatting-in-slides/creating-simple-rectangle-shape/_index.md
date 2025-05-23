---
"description": "Jelajahi dunia presentasi PowerPoint yang dinamis dengan Aspose.Slides for .NET. Pelajari cara membuat bentuk persegi panjang yang menarik dalam slide dengan panduan langkah demi langkah ini."
"linktitle": "Membuat Bentuk Persegi Panjang Sederhana dalam Slide Presentasi menggunakan Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Membuat Bentuk Persegi Panjang dengan Aspose.Slides untuk .NET"
"url": "/id/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Bentuk Persegi Panjang dengan Aspose.Slides untuk .NET

## Perkenalan
Jika Anda ingin menyempurnakan aplikasi .NET Anda dengan presentasi PowerPoint yang dinamis dan menarik secara visual, Aspose.Slides for .NET adalah solusi yang tepat untuk Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan bentuk persegi panjang sederhana dalam slide presentasi menggunakan Aspose.Slides for .NET.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Visual Studio: Pastikan Anda telah menginstal Visual Studio di mesin pengembangan Anda.
- Aspose.Slides untuk .NET: Unduh dan instal pustaka Aspose.Slides untuk .NET dari [Di Sini](https://releases.aspose.com/slides/net/).
- Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# sangatlah penting.
## Mengimpor Ruang Nama
Dalam proyek C# Anda, mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Langkah 1: Siapkan Proyek
Mulailah dengan membuat proyek C# baru di Visual Studio. Pastikan Aspose.Slides for .NET direferensikan dengan benar di proyek Anda.
## Langkah 2: Inisialisasi Objek Presentasi
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Kode Anda untuk langkah berikutnya akan diletakkan di sini.
}
```
## Langkah 3: Dapatkan Slide Pertama
```csharp
ISlide sld = pres.Slides[0];
```
## Langkah 4: Tambahkan BentukOtomatis Persegi Panjang
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Kode ini menambahkan bentuk persegi panjang pada koordinat (50, 150) dengan lebar 150 dan tinggi 50.
## Langkah 5: Simpan Presentasi
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Langkah ini menyimpan presentasi dengan bentuk persegi panjang yang ditambahkan ke direktori yang ditentukan.
## Kesimpulan
Selamat! Anda telah berhasil membuat bentuk persegi panjang sederhana dalam slide presentasi menggunakan Aspose.Slides for .NET. Ini baru permulaan – Aspose.Slides menawarkan berbagai fitur untuk lebih menyesuaikan dan menyempurnakan presentasi Anda.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menggunakan Aspose.Slides untuk .NET di lingkungan Windows dan Linux?
Ya, Aspose.Slides untuk .NET bersifat platform-independen dan dapat digunakan di lingkungan Windows dan Linux.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?
Ya, Anda bisa mendapatkan uji coba gratis [Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
Kunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk dukungan komunitas.
### Bisakah saya membeli lisensi sementara untuk Aspose.Slides for .NET?
Ya, Anda dapat membeli lisensi sementara [Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi untuk Aspose.Slides for .NET?
Lihat dokumentasi [Di Sini](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}