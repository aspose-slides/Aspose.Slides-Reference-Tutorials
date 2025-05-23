---
"description": "Pelajari cara menambahkan dan menghapus hyperlink di Aspose.Slides untuk .NET. Sempurnakan presentasi Anda dengan tautan interaktif dengan mudah."
"linktitle": "Manipulasi Hyperlink di Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Manipulasi Hyperlink di Aspose.Slides"
"url": "/id/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Manipulasi Hyperlink di Aspose.Slides


Hyperlink merupakan elemen penting dalam presentasi, karena menyediakan cara mudah untuk menavigasi antar slide atau mengakses sumber daya eksternal. Aspose.Slides for .NET menawarkan fitur canggih untuk menambahkan dan menghapus hyperlink di slide presentasi Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses manipulasi hyperlink menggunakan Aspose.Slides for .NET. Kami akan membahas cara menambahkan hyperlink ke slide dan menghapus hyperlink dari slide. Jadi, mari kita mulai!

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk .NET: Anda harus menginstal dan mengatur pustaka Aspose.Slides untuk .NET. Anda dapat menemukan dokumentasinya [Di Sini](https://reference.aspose.com/slides/net/) dan mengunduhnya dari [tautan ini](https://releases.aspose.com/slides/net/).

2. Direktori Dokumen Anda: Anda memerlukan direktori tempat menyimpan berkas presentasi Anda. Pastikan untuk menentukan jalur ke direktori ini dalam kode Anda.

3. Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#.

Sekarang setelah Anda memiliki prasyarat yang dibutuhkan, mari beralih ke panduan langkah demi langkah untuk manipulasi hyperlink menggunakan Aspose.Slides untuk .NET.

## Menambahkan Hyperlink ke Slide

### Langkah 1: Inisialisasi Presentasi

Untuk memulai, Anda perlu menginisialisasi presentasi menggunakan Aspose.Slides. Anda dapat melakukannya dengan kode berikut:

```csharp
using (Presentation presentation = new Presentation())
{
    // Kode Anda di sini
}
```

### Langkah 2: Tambahkan Bingkai Teks

Sekarang, mari tambahkan bingkai teks ke slide. Kode ini membuat bentuk persegi panjang dengan teks:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Langkah 3: Tambahkan Hyperlink

Selanjutnya, Anda akan menambahkan hyperlink ke teks dalam bentuk yang Anda buat. Berikut cara melakukannya:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi Anda dengan hyperlink yang ditambahkan:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Selamat! Anda telah berhasil menambahkan hyperlink ke slide menggunakan Aspose.Slides for .NET.

## Menghapus Hyperlink dari Slide

### Langkah 1: Inisialisasi Presentasi

Untuk menghapus hyperlink dari slide, Anda perlu membuka presentasi yang ada:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Langkah 2: Hapus Hyperlink

Sekarang, hapus semua hyperlink dari presentasi menggunakan kode berikut:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Langkah 3: Simpan Presentasi

Setelah menghapus hyperlink, simpan presentasinya:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil menghapus hyperlink dari slide menggunakan Aspose.Slides for .NET.

Sebagai kesimpulan, Aspose.Slides untuk .NET menyediakan cara yang efisien untuk memanipulasi hyperlink dalam presentasi Anda, sehingga memungkinkan Anda membuat slide yang interaktif dan menarik. Apakah Anda ingin menambahkan hyperlink ke sumber daya eksternal atau menghapusnya, Aspose.Slides menyederhanakan proses dan meningkatkan kemampuan Anda dalam membuat presentasi.

Terima kasih telah bergabung dengan kami dalam tutorial manipulasi hyperlink di Aspose.Slides untuk .NET ini. Jika Anda memiliki pertanyaan atau memerlukan bantuan lebih lanjut, jangan ragu untuk menjelajahi [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/net/) atau hubungi komunitas Aspose di [forum dukungan](https://forum.aspose.com/).

---

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara memanipulasi hyperlink dalam presentasi menggunakan Aspose.Slides untuk .NET. Kita membahas tentang penambahan dan penghapusan hyperlink, yang memungkinkan Anda membuat presentasi yang dinamis dan interaktif. Aspose.Slides menyederhanakan proses, sehingga memudahkan Anda untuk menyempurnakan slide Anda dengan hyperlink ke sumber daya eksternal.

Apakah Anda memiliki pertanyaan lain tentang penggunaan Aspose.Slides atau aspek lain dalam desain presentasi? Lihat FAQ di bawah ini untuk mendapatkan informasi lebih lanjut.

## FAQ (Pertanyaan yang Sering Diajukan)

### Apa keuntungan utama menggunakan Aspose.Slides untuk .NET?
Aspose.Slides untuk .NET menawarkan berbagai fitur untuk membuat, memanipulasi, dan mengonversi presentasi. Aplikasi ini menyediakan seperangkat alat yang lengkap untuk menambahkan konten, animasi, dan interaksi ke slide Anda.

### Bisakah saya menambahkan hyperlink ke objek selain teks di Aspose.Slides?
Ya, Aspose.Slides memungkinkan Anda menambahkan hyperlink ke berbagai objek, termasuk bentuk, gambar, dan teks, memberi Anda fleksibilitas dalam membuat presentasi interaktif.

### Apakah Aspose.Slides kompatibel dengan berbagai format file PowerPoint?
Tentu saja. Aspose.Slides mendukung berbagai format PowerPoint, termasuk PPT, PPTX, PPS, dan banyak lagi. Aplikasi ini memastikan kompatibilitas dengan berbagai versi Microsoft PowerPoint.

### Di mana saya dapat menemukan sumber daya dan dukungan tambahan untuk Aspose.Slides?
Untuk dokumentasi mendalam dan dukungan komunitas, kunjungi [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/net/) dan [Forum dukungan Aspose](https://forum.aspose.com/).

### Bagaimana cara memperoleh lisensi sementara untuk Aspose.Slides?
Jika Anda memerlukan lisensi sementara untuk Aspose.Slides, Anda bisa mendapatkannya [Di Sini](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}