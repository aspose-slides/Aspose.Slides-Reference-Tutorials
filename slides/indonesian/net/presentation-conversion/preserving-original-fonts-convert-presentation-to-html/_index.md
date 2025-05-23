---
"description": "Pelajari cara mempertahankan font asli saat mengonversi presentasi ke HTML menggunakan Aspose.Slides for .NET. Pastikan konsistensi font dan dampak visual dengan mudah."
"linktitle": "Melestarikan Font Asli - Mengubah Presentasi ke HTML"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Melestarikan Font Asli - Mengubah Presentasi ke HTML"
"url": "/id/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Melestarikan Font Asli - Mengubah Presentasi ke HTML


Dalam panduan lengkap ini, kami akan memandu Anda melalui proses mempertahankan font asli saat mengonversi presentasi ke HTML menggunakan Aspose.Slides for .NET. Kami akan memberi Anda kode sumber C# yang diperlukan dan menjelaskan setiap langkah secara terperinci. Di akhir tutorial ini, Anda akan dapat memastikan bahwa font dalam dokumen HTML yang dikonversi tetap sesuai dengan presentasi asli.

## 1. Pendahuluan

Saat mengonversi presentasi PowerPoint ke HTML, sangat penting untuk mempertahankan font asli guna memastikan konsistensi visual konten Anda. Aspose.Slides for .NET menyediakan solusi hebat untuk mencapai hal ini. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah yang diperlukan untuk mempertahankan font asli selama proses konversi.

## 2. Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Visual Studio terinstal di komputer Anda.
- Pustaka Aspose.Slides untuk .NET ditambahkan ke proyek Anda.

## 3. Menyiapkan Proyek Anda

Untuk memulai, buat proyek baru di Visual Studio dan tambahkan pustaka Aspose.Slides untuk .NET sebagai referensi.

## 4. Memuat Presentasi

Gunakan kode berikut untuk memuat presentasi PowerPoint Anda:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Kode Anda di sini
}
```

Mengganti `"Your Document Directory"` dengan jalur ke berkas presentasi Anda.

## 5. Mengecualikan Font Default

Untuk mengecualikan font default seperti Calibri dan Arial, gunakan kode berikut:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Anda dapat menyesuaikan daftar ini sesuai kebutuhan.

## 6. Menanamkan Semua Font

Selanjutnya, kita akan menanamkan semua font dalam dokumen HTML. Ini memastikan bahwa font asli tetap dipertahankan. Gunakan kode berikut:

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

Mengganti `"output.html"` dengan nama file keluaran yang Anda inginkan.

## 8. Kesimpulan

Dalam tutorial ini, kami telah menunjukkan cara mempertahankan font asli saat mengonversi presentasi PowerPoint ke HTML menggunakan Aspose.Slides for .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa dokumen HTML yang dikonversi mempertahankan integritas visual presentasi asli.

## 9. Tanya Jawab Umum

### Q1: Dapatkah saya menyesuaikan daftar font yang dikecualikan?

Ya, Anda bisa. Ubah `fontNameExcludeList` array untuk menyertakan atau mengecualikan font tertentu sesuai kebutuhan Anda.

### Q2: Bagaimana jika saya tidak ingin menyematkan semua font?

Jika Anda ingin menyematkan hanya font tertentu, Anda dapat mengubah kode sebagaimana mestinya. Lihat dokumentasi Aspose.Slides for .NET untuk keterangan lebih rinci.

### Q3: Apakah ada persyaratan lisensi untuk menggunakan Aspose.Slides untuk .NET?

Ya, Anda mungkin memerlukan lisensi yang valid untuk menggunakan Aspose.Slides for .NET dalam proyek Anda. Lihat situs web Aspose untuk informasi lisensi.

### Q4: Dapatkah saya mengonversi format file lain ke HTML menggunakan Aspose.Slides untuk .NET?

Aspose.Slides untuk .NET terutama berfokus pada presentasi PowerPoint. Untuk mengonversi format file lain ke HTML, Anda mungkin perlu menjelajahi produk Aspose lain yang dirancang khusus untuk format tersebut.

### Q5: Di mana saya dapat mengakses sumber daya dan dukungan tambahan?

Anda dapat menemukan lebih banyak dokumentasi, tutorial, dan dukungan di situs web Aspose. Kunjungi [Dokumentasi Aspose.Slides untuk .NET](https://reference.aspose.com/slides/net/) untuk informasi lebih rinci.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}