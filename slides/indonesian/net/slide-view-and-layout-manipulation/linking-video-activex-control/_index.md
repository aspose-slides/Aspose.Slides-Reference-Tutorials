---
title: Menautkan Video melalui Kontrol ActiveX di PowerPoint
linktitle: Menghubungkan Video melalui Kontrol ActiveX
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menautkan video ke slide PowerPoint menggunakan Aspose.Slides untuk .NET. Panduan langkah demi langkah ini mencakup kode sumber dan tips untuk membuat presentasi interaktif dan menarik dengan video tertaut.
weight: 12
url: /id/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

Menautkan Video melalui Kontrol ActiveX dalam Presentasi menggunakan Aspose.Slides untuk .NET

Di Aspose.Slides for .NET, Anda dapat menautkan video ke slide presentasi secara terprogram menggunakan kontrol ActiveX. Hal ini memungkinkan Anda membuat presentasi interaktif dimana konten video dapat diputar langsung di dalam slide. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses menautkan video ke slide presentasi menggunakan Aspose.Slides untuk .NET.

## Prasyarat:
- Visual Studio (atau lingkungan pengembangan .NET lainnya)
-  Aspose.Slides untuk perpustakaan .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).

## Langkah 1: Buat Proyek Baru
Buat proyek baru di lingkungan pengembangan .NET pilihan Anda (misalnya, Visual Studio) dan tambahkan referensi ke perpustakaan Aspose.Slides untuk .NET.

## Langkah 2: Impor Namespace yang Diperlukan
Dalam proyek Anda, impor namespace yang diperlukan untuk bekerja dengan Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Langkah 3: Muat Presentasi
Muat presentasi PowerPoint tempat Anda ingin menambahkan video tertaut:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Kode Anda untuk menambahkan video tertaut akan ditempatkan di sini
}
```

## Langkah 4: Tambahkan Kontrol ActiveX
 Buat sebuah instance dari`IOleObjectFrame` antarmuka untuk menambahkan kontrol ActiveX ke slide:

```csharp
ISlide slide = presentation.Slides[0]; // Pilih slide tempat Anda ingin menambahkan video
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Pada kode di atas, kami menambahkan bingkai kontrol ActiveX berdimensi 640x480 ke slide. Kami menentukan ProgID untuk kontrol ShockwaveFlash ActiveX, yang biasanya digunakan untuk menyematkan video.

## Langkah 5: Atur Properti Kontrol ActiveX
Atur properti kontrol ActiveX untuk menentukan sumber video tertaut:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Ganti dengan jalur file video sebenarnya
oleObjectFrame.AlternativeText = "Linked Video";
```

 Mengganti`"YourVideoPathHere"` dengan jalur sebenarnya ke file video Anda. Itu`AlternativeText` properti memberikan deskripsi untuk video yang ditautkan.

## Langkah 6: Simpan Presentasi
Simpan presentasi yang dimodifikasi:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## FAQ:

### Bagaimana cara menentukan ukuran dan posisi video tertaut pada slide?
Anda dapat menyesuaikan dimensi dan posisi bingkai kontrol ActiveX menggunakan parameter`AddOleObjectFrame` metode. Empat argumen numerik masing-masing mewakili koordinat X dan Y dari sudut kiri atas serta lebar dan tinggi bingkai.

### Bisakah saya menautkan video dengan format berbeda menggunakan pendekatan ini?
Ya, Anda dapat menautkan video dengan berbagai format selama kontrol ActiveX yang sesuai tersedia untuk format tersebut. Misalnya, kontrol ShockwaveFlash ActiveX yang digunakan dalam panduan ini cocok untuk video Flash (SWF). Untuk format lain, Anda mungkin perlu menggunakan ProgID yang berbeda.

### Apakah ada batasan ukuran video yang ditautkan?
Ukuran video yang tertaut mungkin memengaruhi ukuran dan performa presentasi Anda secara keseluruhan. Disarankan untuk mengoptimalkan video Anda untuk pemutaran web sebelum menghubungkannya ke presentasi.

### Kesimpulan:
Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda dapat dengan mudah menautkan video melalui kontrol ActiveX dalam presentasi menggunakan Aspose.Slides untuk .NET. Fitur ini memungkinkan Anda membuat presentasi menarik dan interaktif yang menggabungkan konten multimedia dengan lancar.

 Untuk detail lebih lanjut dan opsi lanjutan, Anda dapat merujuk ke[Aspose.Slides untuk dokumentasi .NET](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
