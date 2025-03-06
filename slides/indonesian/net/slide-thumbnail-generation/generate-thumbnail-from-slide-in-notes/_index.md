---
title: Hasilkan Gambar Mini dari Slide di Catatan
linktitle: Hasilkan Gambar Mini dari Slide di Catatan
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara membuat gambar mini dari slide di bagian catatan presentasi Anda menggunakan Aspose.Slides untuk .NET. Tingkatkan konten visual Anda!
weight: 12
url: /id/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Dalam dunia presentasi modern, konten visual adalah rajanya. Membuat slide yang menarik sangat penting untuk komunikasi yang efektif. Salah satu cara untuk menyempurnakan presentasi Anda adalah dengan membuat thumbnail dari slide, terutama ketika Anda ingin menekankan detail spesifik atau berbagi ikhtisar. Aspose.Slides for .NET adalah alat canggih yang dapat membantu Anda mencapai hal ini dengan lancar. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses pembuatan gambar mini dari slide di bagian catatan presentasi menggunakan Aspose.Slides untuk .NET.

## Prasyarat

Sebelum kita mendalami detailnya, Anda harus memiliki prasyarat berikut:

### 1. Aspose.Slide untuk .NET

 Pastikan Anda telah menginstal dan menyiapkan Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).

### 2. Lingkungan .NET

Anda harus memiliki lingkungan pengembangan .NET yang siap di sistem Anda.

### 3. File Presentasi

 Memiliki file presentasi (misalnya,`ThumbnailFromSlideInNotes.pptx`) dari mana Anda ingin membuat thumbnail.

Sekarang, mari kita bagi prosesnya menjadi beberapa langkah:

## Langkah 1: Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Slides. Tambahkan kode berikut di awal skrip C# Anda:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Langkah 2: Muat Presentasi

 Selanjutnya, Anda perlu memuat file presentasi yang berisi slide dengan catatan. Gunakan kode berikut untuk membuat instance a`Presentation` kelas:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Kode Anda ada di sini
}
```

## Langkah 3: Akses Slide

Anda dapat memilih slide mana dalam presentasi yang ingin Anda buat thumbnailnya. Dalam contoh ini, kita akan mengakses slide pertama:

```csharp
ISlide sld = pres.Slides[0];
```

## Langkah 4: Tentukan Dimensi yang Diinginkan

Tentukan dimensi (lebar dan tinggi) untuk thumbnail yang ingin Anda buat. Contohnya:

```csharp
int desiredX = 1200; // Lebar
int desiredY = 800;  // Tinggi
```

## Langkah 5: Hitung Faktor Penskalaan

Untuk memastikan gambar mini sesuai dengan dimensi yang diinginkan, hitung faktor penskalaan sebagai berikut:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Langkah 6: Buat Gambar Kecil

Sekarang, buat thumbnail gambar skala penuh menggunakan faktor penskalaan yang dihitung:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Langkah 7: Simpan Gambar Kecil

Terakhir, simpan thumbnail yang dihasilkan sebagai gambar JPEG:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Itu dia! Anda telah berhasil membuat thumbnail dari slide di bagian catatan presentasi Anda menggunakan Aspose.Slides untuk .NET.

## Kesimpulan

Memasukkan gambar mini ke dalam presentasi Anda dapat meningkatkan daya tarik visual dan efektivitasnya secara signifikan. Aspose.Slides untuk .NET menjadikan proses ini mudah, memungkinkan Anda membuat thumbnail khusus dari slide Anda dengan mudah.

## FAQ (Pertanyaan yang Sering Diajukan)

### Dalam format apa saya dapat menyimpan thumbnail yang dihasilkan?
Anda dapat menyimpan gambar mini dalam berbagai format, termasuk JPEG, PNG, dan lainnya, bergantung pada kebutuhan Anda.

### Bisakah saya membuat thumbnail untuk beberapa slide sekaligus?
Ya, Anda dapat menelusuri slide dalam presentasi Anda dan membuat thumbnail untuk masing-masing slide.

### Apakah Aspose.Slides for .NET kompatibel dengan kerangka .NET yang berbeda?
Ya, Aspose.Slides untuk .NET kompatibel dengan berbagai kerangka .NET, termasuk .NET Core dan .NET Framework.

### Bisakah saya menyesuaikan tampilan thumbnail yang dihasilkan?
Sangat! Aspose.Slides for .NET menyediakan opsi untuk menyesuaikan tampilan thumbnail, seperti dimensi, kualitas, dan lainnya.

### Di mana saya bisa mendapatkan dukungan atau bantuan lebih lanjut dengan Aspose.Slides untuk .NET?
 Anda dapat menemukan bantuan dan terlibat dengan komunitas Aspose di[Asumsikan Forum Dukungan](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
