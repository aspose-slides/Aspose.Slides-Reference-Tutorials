---
title: Konversikan Tampilan Slide Catatan ke PDF di Slide Java
linktitle: Konversikan Tampilan Slide Catatan ke PDF di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengonversi presentasi PowerPoint dengan catatan menjadi PDF menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah kami dengan kode sumber.
weight: 16
url: /id/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Mengonversi Tampilan Slide Catatan ke PDF di Slide Java

Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi presentasi PowerPoint dengan tampilan slide catatan menjadi PDF menggunakan pustaka Aspose.Slides untuk Java. Perpustakaan ini menyediakan fitur canggih untuk bekerja dengan presentasi PowerPoint di Java.

## Prasyarat
1. Kit Pengembangan Java (JDK) diinstal.
2. Aspose.Slides untuk perpustakaan Java ditambahkan ke proyek Anda.

## Langkah 1: Impor Kelas yang Diperlukan
Untuk memulai, Anda harus mengimpor kelas yang diperlukan dari perpustakaan Aspose.Slides. Berikut kode untuk melakukan itu:

```java
import com.aspose.slides.*;
```

## Langkah 2: Muat Presentasi PowerPoint
 Anda harus menyiapkan file presentasi PowerPoint Anda. Mengganti`"Your Document Directory"` dengan jalur ke direktori tempat file presentasi Anda berada. Berikut kode untuk memuat presentasi:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Langkah 3: Konfigurasikan Opsi PDF
Sekarang, mari konfigurasikan opsi ekspor PDF. Secara khusus, kami akan mengatur posisi catatan ke "BottomFull" untuk menyertakan catatan di bawah slide dalam PDF. Berikut kodenya:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Anda dapat menyesuaikan opsi PDF lainnya sesuai kebutuhan Anda.

## Langkah 4: Simpan Presentasi sebagai PDF dengan Catatan
 Terakhir, mari simpan presentasi sebagai file PDF, termasuk catatannya. Anda dapat menentukan nama file keluaran (misalnya,`"Pdf_Notes_out.pdf"`) dan pilih formatnya (`SaveFormat.Pdf`). Berikut kode untuk melakukan itu:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Langkah 5: Bersihkan Sumber Daya
Jangan lupa untuk melepaskan sumber daya setelah Anda selesai dengan presentasi:

```java
if (presentation != null) presentation.dispose();
```

## Kode Sumber Lengkap Untuk Mengonversi Tampilan Slide Catatan ke PDF di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance objek Presentasi yang mewakili file presentasi
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Menyimpan presentasi ke catatan PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara mengonversi presentasi PowerPoint dengan tampilan slide catatan menjadi PDF menggunakan pustaka Aspose.Slides untuk Java. Kami mengikuti panduan langkah demi langkah dengan kode sumber untuk mencapai konversi ini. Berikut adalah kesimpulan utamanya:

## FAQ

### Bagaimana cara mengubah posisi catatan di PDF?

 Anda dapat mengubah posisi catatan di PDF dengan memodifikasi`setNotesPosition` argumen metode. Misalnya, Anda dapat menyetelnya ke`NotesPositions.RightFull` untuk menempatkan catatan di sisi kanan slide.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Bisakah saya menyesuaikan ekspor PDF lebih lanjut?

 Ya, Anda dapat menyesuaikan ekspor PDF dengan menyesuaikan berbagai opsi di`PdfOptions` obyek. Misalnya, Anda dapat mengatur kualitas, kompresi, dan parameter lainnya sesuai kebutuhan Anda.

### Bagaimana saya bisa mendapatkan Aspose.Slides untuk Java?

 Anda dapat mengunduh Aspose.Slides untuk Java dari situs web di[Di Sini](https://releases.aspose.com/slides/java/).

### Apakah ada persyaratan lisensi untuk menggunakan Aspose.Slides?

Ya, Aspose.Slides memerlukan lisensi yang valid untuk penggunaan komersial. Anda dapat memperoleh lisensi dari situs Aspose.

### Di mana saya dapat menemukan lebih banyak dokumentasi dan contoh?

 Anda dapat menemukan dokumentasi dan contoh komprehensif untuk Aspose.Slides untuk Java di[Di Sini](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
