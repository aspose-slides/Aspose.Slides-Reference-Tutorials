---
title: Konversikan ke PDF dengan Slide Tersembunyi di Java Slides
linktitle: Konversikan ke PDF dengan Slide Tersembunyi di Java Slides
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengonversi presentasi PowerPoint ke PDF dengan slide tersembunyi menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah kami dengan kode sumber untuk pembuatan PDF yang lancar.
type: docs
weight: 27
url: /id/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

## Pengantar Mengonversi Presentasi PowerPoint ke PDF dengan Slide Tersembunyi menggunakan Aspose.Slides untuk Java

Dalam panduan langkah demi langkah ini, Anda akan mempelajari cara mengonversi presentasi PowerPoint ke PDF sambil mempertahankan slide tersembunyi menggunakan Aspose.Slides untuk Java. Slide tersembunyi adalah slide yang tidak ditampilkan selama presentasi biasa tetapi dapat dimasukkan dalam keluaran PDF. Kami akan memberi Anda kode sumber dan petunjuk terperinci untuk mencapai tugas ini.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1.  Perpustakaan Aspose.Slides untuk Java: Pastikan Anda telah menyiapkan perpustakaan Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduhnya dari[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/).

2. Lingkungan Pengembangan Java: Anda harus menginstal lingkungan pengembangan Java di sistem Anda.

## Langkah 1: Impor Aspose.Slides untuk Java

Pertama, Anda perlu mengimpor perpustakaan Aspose.Slides ke proyek Java Anda. Pastikan Anda telah menambahkan perpustakaan ke jalur pembangunan proyek Anda.

```java
import com.aspose.slides.*;
```

## Langkah 2: Muat Presentasi PowerPoint

 Anda akan mulai dengan memuat presentasi PowerPoint yang ingin Anda konversi ke PDF. Mengganti`"Your Document Directory"` Dan`"HiddingSlides.pptx"` dengan jalur file yang sesuai.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Langkah 3: Konfigurasikan Opsi PDF

Konfigurasikan opsi PDF untuk menyertakan slide tersembunyi dalam keluaran PDF. Anda dapat melakukan ini dengan mengatur`setShowHiddenSlides` properti dari`PdfOptions` kelas ke`true`.

```java
// Buat instance kelas PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Tentukan bahwa dokumen yang dihasilkan harus menyertakan slide tersembunyi
pdfOptions.setShowHiddenSlides(true);
```

## Langkah 4: Simpan Presentasi sebagai PDF

 Sekarang, simpan presentasi ke file PDF dengan opsi yang ditentukan. Mengganti`"PDFWithHiddenSlides_out.pdf"` dengan nama file keluaran yang Anda inginkan.

```java
// Simpan presentasi ke PDF dengan opsi tertentu
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Langkah 5: Pembersihan Sumber Daya

Pastikan untuk melepaskan sumber daya yang digunakan oleh presentasi setelah Anda selesai menggunakannya.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Kode Sumber Lengkap Untuk Konversi ke PDF dengan Slide Tersembunyi di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Buat instance kelas PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Tentukan bahwa dokumen yang dihasilkan harus menyertakan slide tersembunyi
	pdfOptions.setShowHiddenSlides(true);
	// Simpan presentasi ke PDF dengan opsi tertentu
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam panduan komprehensif ini, Anda telah mempelajari cara mengonversi presentasi PowerPoint ke PDF sambil mempertahankan slide tersembunyi menggunakan Aspose.Slides untuk Java. Kami telah memberi Anda tutorial langkah demi langkah bersama dengan kode sumber yang diperlukan untuk menyelesaikan tugas ini dengan lancar.

## FAQ

### Bagaimana cara menyembunyikan slide dalam presentasi PowerPoint?

Untuk menyembunyikan slide dalam presentasi PowerPoint, ikuti langkah-langkah berikut:
1. Pilih slide yang ingin Anda sembunyikan dalam tampilan Pengurut Slide.
2. Klik kanan pada slide yang dipilih.
3. Pilih "Sembunyikan Slide" dari menu konteks.

### Bisakah saya secara terprogram menampilkan slide tersembunyi di Aspose.Slides untuk Java?

 Ya, Anda dapat menampilkan slide tersembunyi secara terprogram di Aspose.Slides untuk Java dengan mengatur`Hidden` properti dari`Slide` kelas ke`false`. Berikut ini contohnya:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Ganti slideIndex dengan indeks slide tersembunyi
slide.setHidden(false);
```

### Bagaimana cara mengunduh Aspose.Slides untuk Java?

 Anda dapat mengunduh Aspose.Slides untuk Java dari situs web Aspose. Mengunjungi[Aspose.Slide untuk halaman unduh Java](https://releases.aspose.com/slides/java/) untuk mendapatkan versi terbaru.