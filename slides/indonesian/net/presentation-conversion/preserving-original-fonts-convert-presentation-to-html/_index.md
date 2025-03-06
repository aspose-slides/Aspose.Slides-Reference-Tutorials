---
title: Mempertahankan Font Asli - Konversi Presentasi ke HTML
linktitle: Mempertahankan Font Asli - Konversi Presentasi ke HTML
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara mempertahankan font asli sambil mengonversi presentasi ke HTML menggunakan Aspose.Slides untuk .NET. Pastikan konsistensi font dan dampak visual dengan mudah.
weight: 14
url: /id/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Dalam panduan komprehensif ini, kami akan memandu Anda melalui proses mempertahankan font asli saat mengonversi presentasi ke HTML menggunakan Aspose.Slides untuk .NET. Kami akan memberi Anda kode sumber C# yang diperlukan dan menjelaskan setiap langkah secara detail. Di akhir tutorial ini, Anda akan dapat memastikan bahwa font dalam dokumen HTML Anda yang dikonversi tetap sesuai dengan presentasi aslinya.

## 1. Perkenalan

Saat mengonversi presentasi PowerPoint ke HTML, penting untuk mempertahankan font asli untuk memastikan konsistensi visual konten Anda. Aspose.Slides untuk .NET memberikan solusi ampuh untuk mencapai hal ini. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah yang diperlukan untuk mempertahankan font asli selama proses konversi.

## 2. Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Visual Studio diinstal pada mesin Anda.
- Aspose.Slides untuk perpustakaan .NET ditambahkan ke proyek Anda.

## 3. Menyiapkan Proyek Anda

Untuk memulai, buat proyek baru di Visual Studio dan tambahkan pustaka Aspose.Slides for .NET sebagai referensi.

## 4. Memuat Presentasi

Gunakan kode berikut untuk memuat presentasi PowerPoint Anda:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Kode Anda di sini
}
```

 Mengganti`"Your Document Directory"` dengan jalur ke file presentasi Anda.

## 5. Tidak termasuk Font Default

Untuk mengecualikan font default seperti Calibri dan Arial, gunakan kode berikut:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Anda dapat menyesuaikan daftar ini sesuai kebutuhan.

## 6. Menyematkan Semua Font

Selanjutnya, kita akan menyematkan semua font di dokumen HTML. Hal ini memastikan bahwa font asli dipertahankan. Gunakan kode berikut:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Menyimpan sebagai HTML

Sekarang, simpan presentasi sebagai dokumen HTML dengan font tertanam:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Mengganti`"output.html"` dengan nama file keluaran yang Anda inginkan.

## 8. Kesimpulan

Dalam tutorial ini, kami telah menunjukkan cara mempertahankan font asli saat mengonversi presentasi PowerPoint ke HTML menggunakan Aspose.Slides untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa dokumen HTML yang dikonversi mempertahankan integritas visual dari presentasi aslinya.

## 9. FAQ

### Q1: Dapatkah saya menyesuaikan daftar font yang dikecualikan?

 Ya kamu bisa. Ubah`fontNameExcludeList`array untuk menyertakan atau mengecualikan font tertentu sesuai dengan kebutuhan Anda.

### Q2: Bagaimana jika saya tidak ingin menyematkan semua font?

Jika Anda hanya ingin menyematkan font tertentu, Anda dapat mengubah kodenya sesuai dengan itu. Lihat dokumentasi Aspose.Slides untuk .NET untuk detail selengkapnya.

### Q3: Apakah ada persyaratan lisensi untuk menggunakan Aspose.Slides untuk .NET?

Ya, Anda mungkin memerlukan lisensi yang valid untuk menggunakan Aspose.Slides untuk .NET dalam proyek Anda. Lihat situs web Aspose untuk informasi lisensi.

### Q4: Bisakah saya mengonversi format file lain ke HTML menggunakan Aspose.Slides untuk .NET?

Aspose.Slides untuk .NET terutama berfokus pada presentasi PowerPoint. Untuk mengonversi format file lain ke HTML, Anda mungkin perlu menjelajahi produk Aspose lain yang disesuaikan untuk format tersebut.

### Q5: Di mana saya dapat mengakses sumber daya dan dukungan tambahan?

 Anda dapat menemukan lebih banyak dokumentasi, tutorial, dan dukungan di situs web Aspose. Mengunjungi[Aspose.Slide untuk Dokumentasi .NET](https://reference.aspose.com/slides/net/) untuk informasi rinci.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
