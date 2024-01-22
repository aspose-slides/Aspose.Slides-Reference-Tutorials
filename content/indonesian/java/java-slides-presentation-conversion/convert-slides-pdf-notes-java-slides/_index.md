---
title: Konversikan Slide ke PDF dengan Catatan di Java Slides
linktitle: Konversikan Slide ke PDF dengan Catatan di Java Slides
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengonversi slide PowerPoint ke PDF dengan catatan di Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah untuk pengembang Java. Tingkatkan berbagi presentasi Anda.
type: docs
weight: 19
url: /id/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Pengantar Mengonversi Slide ke PDF dengan Catatan di Java

Dalam dunia presentasi digital, kemampuan untuk mengkonversi slide ke PDF dengan catatan yang menyertainya adalah fitur yang berharga. Pengembang Java dapat mencapai hal ini menggunakan pustaka Aspose.Slides for Java, yang menyediakan seperangkat alat canggih untuk bekerja dengan presentasi PowerPoint secara terprogram. Dalam panduan langkah demi langkah ini, kita akan mempelajari cara mengonversi slide ke PDF dengan catatan menggunakan Java dan Aspose.Slides untuk Java.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Slide untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

Sekarang setelah kita memiliki garis besarnya, mari selami penerapannya langkah demi langkah.
## Langkah 1: Menyiapkan Proyek

Pertama, buat proyek Java dan tambahkan pustaka Aspose.Slides for Java ke dependensi proyek Anda.

## Langkah 2: Memuat Presentasi

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Langkah 3: Membuat Presentasi Baru

```java
Presentation auxPresentation = new Presentation();
```

## Langkah 4: Menyalin Slide

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Langkah 5: Menyesuaikan Ukuran Slide

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Langkah 6: Mengonfigurasi Opsi PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Langkah 7: Menyimpan sebagai PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Kode Sumber Lengkap Untuk Mengonversi Slide ke PDF dengan Catatan di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance objek Presentasi yang mewakili file presentasi
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Mengatur Jenis dan Ukuran Slide
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentasi.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengonversi slide ke PDF dengan catatan di Java menggunakan Aspose.Slides untuk Java. Kami membahas pengaturan proyek, memuat presentasi, membuat presentasi baru, menyalin slide, menyesuaikan ukuran slide, mengonfigurasi opsi PDF, dan terakhir, menyimpan presentasi sebagai PDF dengan catatan.

## FAQ

### Bagaimana cara menginstal Aspose.Slides untuk Java?

Untuk menginstal Aspose.Slides untuk Java, ikuti langkah-langkah berikut:
1.  Unduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).
2. Tambahkan file JAR ke classpath proyek Java Anda.

### Bisakah saya menyesuaikan posisi catatan di PDF yang dihasilkan?

 Ya, Anda dapat menyesuaikan posisi catatan dengan memodifikasi`NotesPositions` enum dalam opsi PDF. Dalam tutorial ini, kami mengaturnya ke`BottomFull`, namun Anda juga dapat menjelajahi opsi lain.

### Apakah ada persyaratan lisensi untuk menggunakan Aspose.Slides untuk Java?

Ya, Aspose.Slides for Java adalah perpustakaan komersial, dan Anda mungkin perlu memperoleh lisensi untuk menggunakannya dalam produksi. Kunjungi situs web Aspose untuk detail lisensi.

### Bisakah saya mengonversi beberapa slide sekaligus?

Tentu! Anda dapat mengulang slide dalam presentasi Anda dan mengkloningnya ke dalam presentasi baru, memungkinkan Anda mengonversi beberapa slide ke PDF dengan catatan sekaligus.

### Di mana saya dapat menemukan lebih banyak dokumentasi untuk Aspose.Slides untuk Java?

 Anda dapat menemukan dokumentasi terperinci untuk Aspose.Slides untuk Java di situs:[Aspose.Slides untuk Referensi API Java](https://reference.aspose.com/slides/java/).