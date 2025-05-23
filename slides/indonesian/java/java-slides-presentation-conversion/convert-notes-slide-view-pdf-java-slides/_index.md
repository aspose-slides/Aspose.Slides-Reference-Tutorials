---
"description": "Pelajari cara mengonversi presentasi PowerPoint dengan catatan ke PDF menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah kami dengan kode sumber."
"linktitle": "Konversi Tampilan Slide Catatan ke PDF di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Konversi Tampilan Slide Catatan ke PDF di Java Slides"
"url": "/id/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konversi Tampilan Slide Catatan ke PDF di Java Slides


## Pengantar untuk Mengonversi Tampilan Slide Catatan ke PDF di Java Slides

Dalam tutorial ini, kami akan memandu Anda melalui proses mengonversi presentasi PowerPoint dengan tampilan slide catatan ke dalam PDF menggunakan pustaka Aspose.Slides for Java. Pustaka ini menyediakan fitur-fitur canggih untuk bekerja dengan presentasi PowerPoint di Java.

## Prasyarat
1. Java Development Kit (JDK) terpasang.
2. Pustaka Aspose.Slides untuk Java ditambahkan ke proyek Anda.

## Langkah 1: Impor Kelas yang Diperlukan
Untuk memulai, Anda perlu mengimpor kelas yang diperlukan dari pustaka Aspose.Slides. Berikut kode untuk melakukannya:

```java
import com.aspose.slides.*;
```

## Langkah 2: Muat Presentasi PowerPoint
Anda harus sudah menyiapkan file presentasi PowerPoint Anda. Ganti `"Your Document Directory"` dengan jalur ke direktori tempat file presentasi Anda berada. Berikut kode untuk memuat presentasi:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Langkah 3: Konfigurasikan Opsi PDF
Sekarang, mari kita konfigurasikan opsi ekspor PDF. Secara khusus, kita akan mengatur posisi catatan ke "BottomFull" untuk menyertakan catatan di bawah slide dalam PDF. Berikut kodenya:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Anda dapat menyesuaikan pilihan PDF lainnya menurut kebutuhan Anda.

## Langkah 4: Simpan Presentasi sebagai PDF dengan Catatan
Terakhir, mari simpan presentasi sebagai file PDF, termasuk catatannya. Anda dapat menentukan nama file output (misalnya, `"Pdf_Notes_out.pdf"`) dan pilih format (`SaveFormat.Pdf`). Berikut kode untuk melakukannya:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Langkah 5: Bersihkan Sumber Daya
Jangan lupa untuk merilis sumber daya setelah Anda selesai dengan presentasi:

```java
if (presentation != null) presentation.dispose();
```

## Source Code Lengkap Untuk Mengubah Tampilan Slide Catatan ke PDF di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Membuat instance objek Presentasi yang mewakili file presentasi
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

Dalam tutorial ini, kami telah menjajaki cara mengonversi presentasi PowerPoint dengan tampilan slide catatan ke dalam PDF menggunakan pustaka Aspose.Slides for Java. Kami mengikuti panduan langkah demi langkah dengan kode sumber untuk mencapai konversi ini. Berikut adalah hal-hal penting:

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah posisi catatan dalam PDF?

Anda dapat mengubah posisi catatan dalam PDF dengan memodifikasi `setNotesPosition` argumen metode. Misalnya, Anda dapat mengaturnya menjadi `NotesPositions.RightFull` untuk memposisikan catatan di sisi kanan slide.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Bisakah saya menyesuaikan ekspor PDF lebih lanjut?

Ya, Anda dapat menyesuaikan ekspor PDF dengan menyesuaikan berbagai opsi di `PdfOptions` objek. Misalnya, Anda dapat mengatur kualitas, kompresi, dan parameter lainnya sesuai dengan kebutuhan Anda.

### Bagaimana saya bisa mendapatkan Aspose.Slides untuk Java?

Anda dapat mengunduh Aspose.Slides untuk Java dari situs web di [Di Sini](https://releases.aspose.com/slides/java/).

### Apakah ada persyaratan lisensi untuk menggunakan Aspose.Slides?

Ya, Aspose.Slides memerlukan lisensi yang valid untuk penggunaan komersial. Anda dapat memperoleh lisensi dari situs web Aspose.

### Di mana saya dapat menemukan lebih banyak dokumentasi dan contoh?

Anda dapat menemukan dokumentasi dan contoh lengkap untuk Aspose.Slides untuk Java di [Di Sini](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}