---
"description": "Ubah presentasi PowerPoint ke HTML sambil mempertahankan font asli menggunakan Aspose.Slides untuk Java."
"linktitle": "Mengubah Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengubah Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java"
"url": "/id/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengubah Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java


## Pengantar Konversi Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengonversi presentasi PowerPoint (PPTX) ke HTML dengan tetap mempertahankan font asli menggunakan Aspose.Slides untuk Java. Ini akan memastikan bahwa HTML yang dihasilkan sangat mirip dengan tampilan presentasi asli.

## Langkah 1: Menyiapkan Proyek
Sebelum kita masuk ke kode, mari pastikan Anda telah menyiapkan pengaturan yang diperlukan:

1. Unduh Aspose.Slides untuk Java: Jika Anda belum melakukannya, unduh dan sertakan pustaka Aspose.Slides untuk Java dalam proyek Anda.

2. Buat Proyek Java: Siapkan proyek Java di IDE favorit Anda, dan pastikan Anda memiliki folder "lib" tempat Anda dapat meletakkan file JAR Aspose.Slides.

3. Impor Kelas yang Diperlukan: Impor kelas yang diperlukan di awal file Java Anda:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Langkah 2: Mengubah Presentasi ke HTML dengan Font Asli

Sekarang, mari kita ubah presentasi PowerPoint ke HTML sambil mempertahankan font aslinya:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Muat presentasinya
Presentation pres = new Presentation("input.pptx");

try {
    // Kecualikan font presentasi default seperti Calibri dan Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Buat opsi HTML dan atur pemformat HTML khusus
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Simpan presentasi sebagai HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Buang objek presentasi
    if (pres != null) pres.dispose();
}
```

Dalam potongan kode ini:

- Kami memuat presentasi PowerPoint input menggunakan `Presentation`.

- Kami mendefinisikan daftar font (`fontNameExcludeList`) yang ingin kita kecualikan dari penyematan di HTML. Ini berguna untuk mengecualikan font umum seperti Calibri dan Arial guna mengurangi ukuran file.

- Kami membuat sebuah contoh dari `EmbedAllFontsHtmlController` dan meneruskan daftar pengecualian font ke sana.

- Kami menciptakan `HtmlOptions` dan mengatur format HTML khusus menggunakan `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Terakhir, kami menyimpan presentasi sebagai HTML dengan opsi yang ditentukan.

## Source Code Lengkap Untuk Mengubah Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// mengecualikan font presentasi default
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengonversi presentasi PowerPoint ke HTML sambil mempertahankan font asli menggunakan Aspose.Slides untuk Java. Ini berguna saat Anda ingin mempertahankan ketepatan visual presentasi saat membagikannya di web.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengunduh Aspose.Slides untuk Java?

Anda dapat mengunduh Aspose.Slides untuk Java dari situs web Aspose. Kunjungi [Di Sini](https://downloads.aspose.com/slides/java/) untuk mendapatkan versi terbaru.

### Bisakah saya menyesuaikan daftar font yang dikecualikan?

Ya, Anda dapat menyesuaikan `fontNameExcludeList` array untuk menyertakan atau mengecualikan font tertentu sesuai kebutuhan Anda.

### Apakah metode ini berfungsi untuk format PowerPoint lama seperti PPT?

Contoh kode ini dirancang untuk file PPTX. Jika Anda perlu mengonversi file PPT lama, Anda mungkin perlu melakukan penyesuaian pada kode.

### Bagaimana saya dapat menyesuaikan keluaran HTML lebih lanjut?

Anda dapat menjelajahi `HtmlOptions` kelas untuk menyesuaikan berbagai aspek keluaran HTML, seperti ukuran slide, kualitas gambar, dan banyak lagi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}