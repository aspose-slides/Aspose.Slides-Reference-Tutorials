---
title: Konversikan Presentasi ke HTML dengan Font Tersemat
linktitle: Konversikan Presentasi ke HTML dengan Font Tersemat
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Konversikan presentasi PowerPoint ke HTML dengan font tersemat menggunakan Aspose.Slides untuk .NET. Pertahankan orisinalitas dengan mulus.
weight: 13
url: /id/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Di era digital saat ini, berbagi presentasi dan dokumen secara online telah menjadi praktik umum. Namun, salah satu tantangan yang sering muncul adalah memastikan font Anda ditampilkan dengan benar saat mengonversi presentasi ke HTML. Tutorial langkah demi langkah ini akan memandu Anda melalui proses penggunaan Aspose.Slides untuk .NET untuk mengonversi presentasi ke HTML dengan font tersemat, memastikan dokumen Anda terlihat sesuai keinginan Anda.

## Pengantar Aspose.Slides untuk .NET

Sebelum kita mendalami tutorialnya, mari kita perkenalkan secara singkat Aspose.Slides untuk .NET. Ini adalah perpustakaan canggih yang memungkinkan pengembang untuk bekerja dengan presentasi PowerPoint dalam aplikasi .NET. Dengan Aspose.Slides, Anda dapat membuat, memodifikasi, dan mengonversi file PowerPoint secara terprogram.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

-  Aspose.Slides untuk .NET: Anda harus menginstal pustaka Aspose.Slides di proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).

## Langkah 1: Siapkan Proyek Anda

1. Buat proyek baru atau buka proyek yang sudah ada di lingkungan pengembangan .NET pilihan Anda.

2. Tambahkan referensi ke perpustakaan Aspose.Slides di proyek Anda.

3. Impor namespace yang diperlukan dalam kode Anda:

   ```csharp
   using Aspose.Slides;
   ```

## Langkah 2: Muat Presentasi Anda

 Untuk memulai, Anda perlu memuat presentasi yang ingin Anda konversi ke HTML. Mengganti`"Your Document Directory"` dengan direktori sebenarnya tempat file presentasi Anda berada.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Kode Anda ada di sini
}
```

## Langkah 3: Kecualikan Font Presentasi Default

Pada langkah ini, Anda bisa menentukan font presentasi default apa pun yang ingin Anda kecualikan dari penyematan. Hal ini dapat membantu mengoptimalkan ukuran file HTML yang dihasilkan.

```csharp
string[] fontNameExcludeList = { };
```

## Langkah 4: Pilih Pengontrol HTML

Sekarang, Anda memiliki dua opsi untuk menyematkan font di HTML:

### Opsi 1: Sematkan Semua Font

 Untuk menyematkan semua font yang digunakan dalam presentasi, gunakan`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Opsi 2: Tautkan Semua Font

 Untuk menautkan ke semua font yang digunakan dalam presentasi, gunakan`LinkAllFontsHtmlController`. Anda harus menentukan direktori tempat font berada di sistem Anda.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Langkah 5: Tentukan Opsi HTML

 Buat sebuah`HtmlOptions` objek dan atur formatter HTML ke yang Anda pilih pada langkah sebelumnya.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Gunakan embedFontsController untuk menyematkan semua font
};
```

## Langkah 6: Simpan sebagai HTML

 Terakhir, simpan presentasi sebagai file HTML. Anda dapat memilih salah satunya`SaveFormat.Html` atau`SaveFormat.Html5` tergantung pada kebutuhan Anda.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Kesimpulan

Selamat! Anda telah berhasil mengonversi presentasi Anda ke HTML dengan font yang disematkan menggunakan Aspose.Slides untuk .NET. Ini memastikan bahwa font Anda akan ditampilkan dengan benar saat berbagi presentasi Anda secara online.

Sekarang, Anda dapat dengan mudah berbagi presentasi yang diformat dengan indah dengan percaya diri, mengetahui bahwa audiens Anda akan melihatnya persis seperti yang Anda inginkan.

 Untuk informasi lebih lanjut dan referensi API terperinci, lihat[Aspose.Slides untuk dokumentasi .NET](https://reference.aspose.com/slides/net/).

## FAQ

### 1. Bisakah saya mengonversi presentasi PowerPoint ke HTML menggunakan Aspose.Slides untuk .NET dalam mode batch?

Ya, Anda dapat mengonversi beberapa presentasi ke HTML secara batch menggunakan Aspose.Slides untuk .NET dengan mengulang file presentasi Anda dan menerapkan proses konversi ke masing-masing presentasi.

### 2. Apakah ada cara untuk menyesuaikan tampilan keluaran HTML?

Tentu! Aspose.Slides for .NET menyediakan berbagai opsi untuk menyesuaikan tampilan dan format output HTML, seperti menyesuaikan warna, font, dan tata letak.

### 3. Apakah ada batasan untuk menyematkan font dalam HTML menggunakan Aspose.Slides untuk .NET?

Meskipun Aspose.Slides untuk .NET menawarkan kemampuan penyematan font yang luar biasa, perlu diingat bahwa ukuran file HTML Anda mungkin bertambah saat menyematkan font. Pastikan untuk mengoptimalkan pilihan font Anda untuk penggunaan web.

### 4. Bisakah saya mengonversi presentasi PowerPoint ke format lain dengan Aspose.Slides untuk .NET?

Ya, Aspose.Slides untuk .NET mendukung berbagai format output, termasuk PDF, gambar, dan lainnya. Anda dapat dengan mudah mengonversi presentasi Anda ke format pilihan Anda.

### 5. Di mana saya dapat menemukan sumber daya tambahan dan dukungan untuk Aspose.Slides untuk .NET?

 Anda dapat mengakses banyak sumber daya, termasuk dokumentasi, di[Aspose.Slides untuk Referensi .NET API](https://reference.aspose.com/slides/net/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
