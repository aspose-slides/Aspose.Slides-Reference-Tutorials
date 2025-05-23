---
"description": "Ubah presentasi PowerPoint menjadi HTML dengan font tertanam menggunakan Aspose.Slides untuk .NET. Pertahankan orisinalitas dengan lancar."
"linktitle": "Konversi Presentasi ke HTML dengan Font Tertanam"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Konversi Presentasi ke HTML dengan Font Tertanam"
"url": "/id/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konversi Presentasi ke HTML dengan Font Tertanam


Di era digital saat ini, berbagi presentasi dan dokumen secara daring telah menjadi praktik umum. Namun, satu tantangan yang sering muncul adalah memastikan font Anda ditampilkan dengan benar saat mengonversi presentasi ke HTML. Tutorial langkah demi langkah ini akan memandu Anda melalui proses penggunaan Aspose.Slides for .NET untuk mengonversi presentasi ke HTML dengan font tertanam, memastikan dokumen Anda terlihat seperti yang Anda inginkan.

## Pengantar Aspose.Slides untuk .NET

Sebelum kita menyelami tutorialnya, mari kita perkenalkan Aspose.Slides for .NET secara singkat. Ini adalah pustaka canggih yang memungkinkan pengembang untuk bekerja dengan presentasi PowerPoint dalam aplikasi .NET. Dengan Aspose.Slides, Anda dapat membuat, memodifikasi, dan mengonversi file PowerPoint secara terprogram.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

- Aspose.Slides untuk .NET: Anda harus memasang pustaka Aspose.Slides di proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/net/).

## Langkah 1: Siapkan Proyek Anda

1. Buat proyek baru atau buka proyek yang sudah ada di lingkungan pengembangan .NET pilihan Anda.

2. Tambahkan referensi ke pustaka Aspose.Slides di proyek Anda.

3. Impor namespace yang diperlukan dalam kode Anda:

   ```csharp
   using Aspose.Slides;
   ```

## Langkah 2: Muat Presentasi Anda

Untuk memulai, Anda perlu memuat presentasi yang ingin Anda ubah ke HTML. Ganti `"Your Document Directory"` dengan direktori sebenarnya tempat file presentasi Anda berada.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Kode Anda ada di sini
}
```

## Langkah 3: Kecualikan Font Presentasi Default

Pada langkah ini, Anda dapat menentukan font presentasi default yang ingin Anda kecualikan dari penyematan. Ini dapat membantu mengoptimalkan ukuran file HTML yang dihasilkan.

```csharp
string[] fontNameExcludeList = { };
```

## Langkah 4: Pilih Pengontrol HTML

Sekarang, Anda memiliki dua opsi untuk menyematkan font di HTML:

### Opsi 1: Sematkan Semua Font

Untuk menanamkan semua font yang digunakan dalam presentasi, gunakan `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Opsi 2: Tautkan Semua Font

Untuk menautkan semua font yang digunakan dalam presentasi, gunakan `LinkAllFontsHtmlController`Anda harus menentukan direktori tempat font berada di sistem Anda.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Langkah 5: Tentukan Opsi HTML

Membuat sebuah `HtmlOptions` objek dan atur formater HTML ke yang Anda pilih pada langkah sebelumnya.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Gunakan embedFontsController untuk menyematkan semua font
};
```

## Langkah 6: Simpan sebagai HTML

Terakhir, simpan presentasi sebagai file HTML. Anda dapat memilih salah satu `SaveFataumat.Html` or `SaveFormat.Html5` Tergantung pada kebutuhan Anda.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Kesimpulan

Selamat! Anda telah berhasil mengonversi presentasi Anda ke HTML dengan font tertanam menggunakan Aspose.Slides for .NET. Ini memastikan bahwa font Anda akan ditampilkan dengan benar saat membagikan presentasi Anda secara daring.

Sekarang, Anda dapat dengan mudah membagikan presentasi Anda yang diformat dengan indah dengan percaya diri, karena tahu bahwa audiens Anda akan melihatnya persis seperti yang Anda inginkan.

Untuk informasi lebih lanjut dan referensi API terperinci, lihat [Dokumentasi Aspose.Slides untuk .NET](https://reference.aspose.com/slides/net/).

## Tanya Jawab Umum

### 1. Dapatkah saya mengonversi presentasi PowerPoint ke HTML menggunakan Aspose.Slides for .NET dalam mode batch?

Ya, Anda dapat mengonversi beberapa presentasi ke HTML secara batch menggunakan Aspose.Slides for .NET dengan mengulang seluruh file presentasi Anda dan menerapkan proses konversi ke masing-masing file.

### 2. Apakah ada cara untuk menyesuaikan tampilan keluaran HTML?

Tentu saja! Aspose.Slides untuk .NET menyediakan berbagai opsi untuk menyesuaikan tampilan dan format keluaran HTML, seperti menyesuaikan warna, font, dan tata letak.

### 3. Apakah ada batasan untuk menyematkan font dalam HTML menggunakan Aspose.Slides for .NET?

Meskipun Aspose.Slides untuk .NET menawarkan kemampuan penyematan font yang sangat baik, perlu diingat bahwa ukuran file HTML Anda dapat bertambah saat menyematkan font. Pastikan untuk mengoptimalkan pilihan font Anda untuk penggunaan web.

### 4. Dapatkah saya mengonversi presentasi PowerPoint ke format lain dengan Aspose.Slides untuk .NET?

Ya, Aspose.Slides untuk .NET mendukung berbagai format output, termasuk PDF, gambar, dan banyak lagi. Anda dapat dengan mudah mengonversi presentasi Anda ke format pilihan Anda.

### 5. Di mana saya dapat menemukan sumber daya dan dukungan tambahan untuk Aspose.Slides for .NET?

Anda dapat mengakses banyak sumber daya, termasuk dokumentasi, di [Referensi API Aspose.Slides untuk .NET](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}