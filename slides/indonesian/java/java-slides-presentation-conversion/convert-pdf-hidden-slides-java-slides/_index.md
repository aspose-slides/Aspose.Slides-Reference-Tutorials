---
"description": "Pelajari cara mengonversi presentasi PowerPoint ke PDF dengan slide tersembunyi menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah kami dengan kode sumber untuk pembuatan PDF yang lancar."
"linktitle": "Konversi ke PDF dengan Slide Tersembunyi di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Konversi ke PDF dengan Slide Tersembunyi di Java Slides"
"url": "/id/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konversi ke PDF dengan Slide Tersembunyi di Java Slides


## Pengantar untuk Mengonversi Presentasi PowerPoint ke PDF dengan Slide Tersembunyi menggunakan Aspose.Slides untuk Java

Dalam panduan langkah demi langkah ini, Anda akan mempelajari cara mengonversi presentasi PowerPoint ke PDF sambil mempertahankan slide tersembunyi menggunakan Aspose.Slides untuk Java. Slide tersembunyi adalah slide yang tidak ditampilkan selama presentasi biasa tetapi dapat disertakan dalam output PDF. Kami akan memberi Anda kode sumber dan petunjuk terperinci untuk menyelesaikan tugas ini.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

1. Pustaka Aspose.Slides untuk Java: Pastikan Anda telah menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduhnya dari [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).

2. Lingkungan Pengembangan Java: Anda harus menginstal lingkungan pengembangan Java di sistem Anda.

## Langkah 1: Impor Aspose.Slides untuk Java

Pertama, Anda perlu mengimpor pustaka Aspose.Slides ke dalam proyek Java Anda. Pastikan Anda telah menambahkan pustaka tersebut ke jalur pembuatan proyek Anda.

```java
import com.aspose.slides.*;
```

## Langkah 2: Muat Presentasi PowerPoint

Anda akan mulai dengan memuat presentasi PowerPoint yang ingin Anda ubah ke PDF. Ganti `"Your Document Directory"` Dan `"HiddingSlides.pptx"` dengan jalur berkas yang sesuai.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Langkah 3: Konfigurasikan Opsi PDF

Konfigurasikan opsi PDF untuk menyertakan slide tersembunyi dalam output PDF. Anda dapat melakukannya dengan menyetel `setShowHiddenSlides` milik `PdfOptions` kelas ke `true`.

```java
// Membuat instance kelas PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Tentukan bahwa dokumen yang dihasilkan harus menyertakan slide tersembunyi
pdfOptions.setShowHiddenSlides(true);
```

## Langkah 4: Simpan Presentasi sebagai PDF

Sekarang, simpan presentasi ke file PDF dengan opsi yang ditentukan. Ganti `"PDFWithHiddenSlides_out.pdf"` dengan nama file keluaran yang Anda inginkan.

```java
// Simpan presentasi ke PDF dengan opsi yang ditentukan
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Langkah 5: Membersihkan Sumber Daya

Pastikan untuk merilis sumber daya yang digunakan oleh presentasi saat Anda selesai melakukannya.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Source Code Lengkap Untuk Konversi ke PDF dengan Slide Tersembunyi di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Membuat instance kelas PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Tentukan bahwa dokumen yang dihasilkan harus menyertakan slide tersembunyi
	pdfOptions.setShowHiddenSlides(true);
	// Simpan presentasi ke PDF dengan opsi yang ditentukan
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam panduan lengkap ini, Anda telah mempelajari cara mengonversi presentasi PowerPoint ke PDF sambil mempertahankan slide tersembunyi menggunakan Aspose.Slides untuk Java. Kami telah menyediakan tutorial langkah demi langkah beserta kode sumber yang diperlukan untuk menyelesaikan tugas ini dengan lancar.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyembunyikan slide dalam presentasi PowerPoint?

Untuk menyembunyikan slide dalam presentasi PowerPoint, ikuti langkah-langkah berikut:
1. Pilih slide yang ingin Anda sembunyikan dalam tampilan Slide Sorter.
2. Klik kanan pada slide yang dipilih.
3. Pilih "Sembunyikan Slide" dari menu konteks.

### Bisakah saya menampilkan kembali slide tersembunyi secara terprogram di Aspose.Slides untuk Java?

Ya, Anda dapat secara terprogram menampilkan kembali slide tersembunyi di Aspose.Slides untuk Java dengan mengatur `Hidden` milik `Slide` kelas ke `false`Berikut ini contohnya:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Ganti slideIndex dengan indeks slide tersembunyi
slide.setHidden(false);
```

### Bagaimana cara mengunduh Aspose.Slides untuk Java?

Anda dapat mengunduh Aspose.Slides untuk Java dari situs web Aspose. Kunjungi [Halaman unduhan Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/) untuk mendapatkan versi terbaru.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}