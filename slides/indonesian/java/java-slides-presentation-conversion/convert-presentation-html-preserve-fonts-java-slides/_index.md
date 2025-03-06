---
title: Mengonversi Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java
linktitle: Mengonversi Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Konversikan presentasi PowerPoint ke HTML sambil mempertahankan font asli menggunakan Aspose.Slides untuk Java.
weight: 14
url: /id/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengonversi Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java


## Pengantar Mengonversi Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java

Dalam tutorial ini, kita akan mempelajari cara mengonversi presentasi PowerPoint (PPTX) ke HTML sambil mempertahankan font asli menggunakan Aspose.Slides untuk Java. Ini akan memastikan bahwa HTML yang dihasilkan sangat mirip dengan tampilan presentasi aslinya.

## Langkah 1: Menyiapkan Proyek
Sebelum kita mendalami kodenya, pastikan Anda memiliki pengaturan yang diperlukan:

1. Unduh Aspose.Slides untuk Java: Jika Anda belum melakukannya, unduh dan sertakan perpustakaan Aspose.Slides untuk Java dalam proyek Anda.

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

// Muat presentasi
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

Dalam cuplikan kode ini:

-  Kami memuat input presentasi PowerPoint menggunakan`Presentation`.

- Kami mendefinisikan daftar font (`fontNameExcludeList`yang ingin kami kecualikan dari penyematan di HTML. Ini berguna untuk mengecualikan font umum seperti Calibri dan Arial guna mengurangi ukuran file.

-  Kami membuat sebuah instance dari`EmbedAllFontsHtmlController` dan meneruskan daftar pengecualian font ke sana.

-  Kami menciptakan`HtmlOptions` dan atur formatter HTML khusus menggunakan`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Terakhir, kami menyimpan presentasi sebagai HTML dengan opsi yang ditentukan.

## Kode Sumber Lengkap Untuk Mengubah Presentasi ke HTML dengan Mempertahankan Font Asli di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// kecualikan font presentasi default
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

Dalam tutorial ini, Anda telah mempelajari cara mengonversi presentasi PowerPoint ke HTML sambil mempertahankan font asli menggunakan Aspose.Slides untuk Java. Ini berguna bila Anda ingin menjaga ketelitian visual presentasi Anda saat membagikannya di web.

## FAQ

### Bagaimana cara mengunduh Aspose.Slides untuk Java?

 Anda dapat mengunduh Aspose.Slides untuk Java dari situs web Aspose. Mengunjungi[Di Sini](https://downloads.aspose.com/slides/java/) untuk mendapatkan versi terbaru.

### Bisakah saya menyesuaikan daftar font yang dikecualikan?

 Ya, Anda dapat menyesuaikannya`fontNameExcludeList` array untuk memasukkan atau mengecualikan font tertentu sesuai kebutuhan Anda.

### Apakah metode ini berfungsi untuk format PowerPoint lama seperti PPT?

Contoh kode ini dirancang untuk file PPTX. Jika Anda perlu mengonversi file PPT lama, Anda mungkin perlu melakukan penyesuaian pada kodenya.

### Bagaimana cara menyesuaikan keluaran HTML lebih lanjut?

 Anda dapat menjelajahi`HtmlOptions` kelas untuk menyesuaikan berbagai aspek keluaran HTML, seperti ukuran slide, kualitas gambar, dan banyak lagi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
