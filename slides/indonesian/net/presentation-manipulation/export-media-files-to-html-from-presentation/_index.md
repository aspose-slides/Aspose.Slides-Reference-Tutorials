---
title: Ekspor File Media ke HTML dari Presentasi
linktitle: Ekspor File Media ke HTML dari Presentasi
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Optimalkan berbagi presentasi Anda dengan Aspose.Slides untuk .NET! Pelajari cara mengekspor file media ke HTML dari presentasi Anda dalam panduan langkah demi langkah ini.
weight: 15
url: /id/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Dalam tutorial ini, kami akan memandu Anda melalui proses mengekspor file media ke HTML dari presentasi menggunakan Aspose.Slides untuk .NET. Aspose.Slides adalah API canggih yang memungkinkan Anda bekerja dengan presentasi PowerPoint secara terprogram. Di akhir panduan ini, Anda akan dapat mengubah presentasi Anda ke format HTML dengan mudah. Jadi, mari kita mulai!

## 1. Perkenalan

Presentasi PowerPoint sering kali berisi elemen multimedia seperti video, dan Anda mungkin perlu mengekspor presentasi ini ke format HTML agar kompatibel dengan web. Aspose.Slides untuk .NET menyediakan cara mudah untuk menyelesaikan tugas ini secara terprogram.

## 2. Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Slides untuk .NET: Anda harus menginstal perpustakaan Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).

## 3. Memuat Presentasi

Untuk memulai, Anda perlu memuat presentasi PowerPoint yang ingin Anda konversi ke HTML. Anda juga harus menentukan direktori keluaran tempat file HTML akan disimpan. Berikut kode untuk memuat presentasi:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Memuat presentasi
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Kode Anda di sini
}
```

## 4. Menyiapkan Opsi HTML

Sekarang, mari siapkan opsi HTML untuk konversi. Kami akan mengonfigurasi pengontrol HTML, pemformat HTML, dan format gambar slide. Kode ini akan memastikan bahwa file HTML Anda berisi komponen yang diperlukan untuk menampilkan elemen multimedia.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.contoh.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// Mengatur opsi HTML
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. Menyimpan File HTML

 Dengan opsi HTML yang dikonfigurasi, Anda sekarang dapat menyimpan file HTML. Itu`Save` metode objek presentasi akan menghasilkan file HTML dengan elemen multimedia yang tertanam.

```csharp
// Menyimpan file
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Kesimpulan

Selamat! Anda telah berhasil mengekspor file media ke HTML dari presentasi PowerPoint menggunakan Aspose.Slides untuk .NET. Hal ini memungkinkan Anda berbagi presentasi online dengan mudah dan memastikan elemen multimedia ditampilkan dengan benar.

## 7. Pertanyaan Umum

### Q1: Apakah Aspose.Slides untuk .NET merupakan perpustakaan gratis?
 A1: Aspose.Slides untuk .NET adalah perpustakaan komersial, tetapi Anda bisa mendapatkan uji coba gratis darinya[Di Sini](https://releases.aspose.com/) untuk mencobanya.

### Q2: Dapatkah saya menyesuaikan keluaran HTML lebih lanjut?
A2: Ya, Anda dapat menyesuaikan keluaran HTML dengan memodifikasi opsi HTML dalam kode.

### Q3: Apakah Aspose.Slides untuk .NET mendukung format ekspor lainnya?
A3: Ya, Aspose.Slides untuk .NET mendukung berbagai format ekspor, termasuk PDF, format gambar, dan banyak lagi.

### Q4: Di mana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
 A4: Anda dapat menemukan dukungan dan mengajukan pertanyaan di forum Aspose[Di Sini](https://forum.aspose.com/).

### Q5: Bagaimana cara membeli lisensi Aspose.Slides untuk .NET?
 A5: Anda dapat membeli lisensi dari[Link ini](https://purchase.aspose.com/buy).

Sekarang setelah Anda menyelesaikan tutorial ini, Anda memiliki keterampilan untuk mengekspor file media ke HTML dari presentasi PowerPoint menggunakan Aspose.Slides untuk .NET. Nikmati berbagi presentasi kaya multimedia Anda secara online!
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
