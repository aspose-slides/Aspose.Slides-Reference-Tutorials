---
"description": "Pelajari cara menautkan video ke slide PowerPoint menggunakan Aspose.Slides for .NET. Panduan langkah demi langkah ini mencakup kode sumber dan kiat untuk membuat presentasi yang interaktif dan menarik dengan video yang ditautkan."
"linktitle": "Menghubungkan Video melalui Kontrol ActiveX"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Menghubungkan Video melalui Kontrol ActiveX di PowerPoint"
"url": "/id/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menghubungkan Video melalui Kontrol ActiveX di PowerPoint

Menghubungkan Video melalui Kontrol ActiveX dalam Presentasi menggunakan Aspose.Slides untuk .NET

Di Aspose.Slides for .NET, Anda dapat menautkan video ke slide presentasi secara terprogram menggunakan kontrol ActiveX. Ini memungkinkan Anda membuat presentasi interaktif di mana konten video dapat diputar langsung di dalam slide. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses menautkan video ke slide presentasi menggunakan Aspose.Slides for .NET.

## Prasyarat:
- Visual Studio (atau lingkungan pengembangan .NET lainnya)
- Pustaka Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/net/).

## Langkah 1: Buat Proyek Baru
Buat proyek baru di lingkungan pengembangan .NET pilihan Anda (misalnya, Visual Studio) dan tambahkan referensi ke pustaka Aspose.Slides untuk .NET.

## Langkah 2: Impor Namespace yang Diperlukan
Dalam proyek Anda, impor namespace yang diperlukan untuk bekerja dengan Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Langkah 3: Muat Presentasi
Muat presentasi PowerPoint tempat Anda ingin menambahkan video yang ditautkan:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Kode Anda untuk menambahkan video yang ditautkan akan ada di sini
}
```

## Langkah 4: Tambahkan Kontrol ActiveX
Buat contoh dari `IOleObjectFrame` antarmuka untuk menambahkan kontrol ActiveX ke slide:

```csharp
ISlide slide = presentation.Slides[0]; // Pilih slide tempat Anda ingin menambahkan video
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Pada kode di atas, kami menambahkan bingkai kontrol ActiveX berdimensi 640x480 ke slide. Kami menentukan ProgID untuk kontrol ActiveX ShockwaveFlash, yang umumnya digunakan untuk menyematkan video.

## Langkah 5: Mengatur Properti Kontrol ActiveX
Tetapkan properti kontrol ActiveX untuk menentukan sumber video yang ditautkan:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Ganti dengan jalur file video sebenarnya
oleObjectFrame.AlternativeText = "Linked Video";
```

Mengganti `"YourVideoPathHere"` dengan jalur sebenarnya ke berkas video Anda. `AlternativeText` Properti menyediakan deskripsi untuk video yang ditautkan.

## Langkah 6: Simpan Presentasi
Simpan presentasi yang dimodifikasi:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Tanya Jawab:

### Bagaimana cara menentukan ukuran dan posisi video yang ditautkan pada slide?
Anda dapat menyesuaikan dimensi dan posisi bingkai kontrol ActiveX menggunakan parameter `AddOleObjectFrame` metode. Keempat argumen numerik masing-masing mewakili koordinat X dan Y dari sudut kiri atas dan lebar serta tinggi bingkai.

### Dapatkah saya menautkan video dengan format berbeda menggunakan pendekatan ini?
Ya, Anda dapat menautkan video dengan berbagai format asalkan kontrol ActiveX yang sesuai tersedia untuk format tersebut. Misalnya, kontrol ActiveX ShockwaveFlash yang digunakan dalam panduan ini cocok untuk video Flash (SWF). Untuk format lain, Anda mungkin perlu menggunakan ProgID yang berbeda.

### Apakah ada batasan ukuran video yang ditautkan?
Ukuran video yang ditautkan dapat memengaruhi ukuran dan kinerja keseluruhan presentasi Anda. Sebaiknya optimalkan video Anda untuk pemutaran web sebelum menautkannya ke presentasi.

### Kesimpulan:
Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda dapat dengan mudah menautkan video melalui kontrol ActiveX dalam presentasi menggunakan Aspose.Slides for .NET. Fitur ini memungkinkan Anda membuat presentasi yang menarik dan interaktif yang menggabungkan konten multimedia dengan lancar.

Untuk detail lebih lanjut dan opsi lanjutan, Anda dapat merujuk ke [Dokumentasi Aspose.Slides untuk .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}