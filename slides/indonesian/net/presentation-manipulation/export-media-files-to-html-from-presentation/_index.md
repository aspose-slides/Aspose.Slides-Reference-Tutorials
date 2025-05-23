---
"description": "Optimalkan pembagian presentasi Anda dengan Aspose.Slides untuk .NET! Pelajari cara mengekspor berkas media ke HTML dari presentasi Anda dalam panduan langkah demi langkah ini."
"linktitle": "Ekspor File Media ke HTML dari Presentasi"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Ekspor File Media ke HTML dari Presentasi"
"url": "/id/net/presentation-manipulation/export-media-files-to-html-from-presentation/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ekspor File Media ke HTML dari Presentasi


Dalam tutorial ini, kami akan memandu Anda melalui proses mengekspor berkas media ke HTML dari presentasi menggunakan Aspose.Slides untuk .NET. Aspose.Slides adalah API canggih yang memungkinkan Anda bekerja dengan presentasi PowerPoint secara terprogram. Di akhir panduan ini, Anda akan dapat mengonversi presentasi Anda ke format HTML dengan mudah. Jadi, mari kita mulai!

## 1. Pendahuluan

Presentasi PowerPoint sering kali berisi elemen multimedia seperti video, dan Anda mungkin perlu mengekspor presentasi ini ke format HTML agar kompatibel dengan web. Aspose.Slides for .NET menyediakan cara mudah untuk menyelesaikan tugas ini secara terprogram.

## 2. Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Aspose.Slides untuk .NET: Anda harus menginstal pustaka Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/net/).

## 3. Memuat Presentasi

Untuk memulai, Anda perlu memuat presentasi PowerPoint yang ingin Anda ubah ke HTML. Anda juga perlu menentukan direktori keluaran tempat file HTML akan disimpan. Berikut kode untuk memuat presentasi:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Memuat presentasi
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Kode Anda di sini
}
```

## 4. Mengatur Opsi HTML

Sekarang, mari kita atur opsi HTML untuk konversi. Kita akan mengonfigurasi pengontrol HTML, pemformat HTML, dan format gambar slide. Kode ini akan memastikan bahwa berkas HTML Anda berisi komponen yang diperlukan untuk menampilkan elemen multimedia.

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

Dengan opsi HTML yang dikonfigurasi, Anda sekarang dapat menyimpan file HTML. `Save` metode objek presentasi akan menghasilkan berkas HTML dengan elemen multimedia yang tertanam.

```csharp
// Menyimpan file
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Kesimpulan

Selamat! Anda telah berhasil mengekspor file media ke HTML dari presentasi PowerPoint menggunakan Aspose.Slides for .NET. Ini memungkinkan Anda untuk berbagi presentasi secara daring dengan mudah dan memastikan bahwa elemen multimedia ditampilkan dengan benar.

## 7. Tanya Jawab Umum

### Q1: Apakah Aspose.Slides untuk .NET pustaka gratis?
A1: Aspose.Slides untuk .NET adalah pustaka komersial, tetapi Anda bisa mendapatkan uji coba gratis dari [Di Sini](https://releases.aspose.com/) untuk mencobanya.

### Q2: Bisakah saya menyesuaikan output HTML lebih lanjut?
A2: Ya, Anda dapat menyesuaikan keluaran HTML dengan memodifikasi opsi HTML dalam kode.

### Q3: Apakah Aspose.Slides untuk .NET mendukung format ekspor lain?
A3: Ya, Aspose.Slides untuk .NET mendukung berbagai format ekspor, termasuk PDF, format gambar, dan banyak lagi.

### Q4: Di mana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
A4: Anda dapat menemukan dukungan dan mengajukan pertanyaan di forum Aspose [Di Sini](https://forum.aspose.com/).

### Q5: Bagaimana cara membeli lisensi Aspose.Slides untuk .NET?
A5: Anda dapat membeli lisensi dari [tautan ini](https://purchase.aspose.com/buy).

Setelah menyelesaikan tutorial ini, Anda memiliki keterampilan untuk mengekspor file media ke HTML dari presentasi PowerPoint menggunakan Aspose.Slides for .NET. Nikmati berbagi presentasi kaya multimedia Anda secara online!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}