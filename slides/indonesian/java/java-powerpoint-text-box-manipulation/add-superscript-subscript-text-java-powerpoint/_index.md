---
title: Tambahkan Teks Superskrip dan Subskrip di Java PowerPoint
linktitle: Tambahkan Teks Superskrip dan Subskrip di Java PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan teks superskrip dan subskrip dalam presentasi Java PowerPoint menggunakan Aspose.Slides untuk Java. Sempurna untuk menyempurnakan slide Anda.
weight: 13
url: /id/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Membuat presentasi PowerPoint yang menarik dan informatif sering kali memerlukan penggunaan fitur pemformatan seperti teks superskrip dan subskrip. Tutorial ini akan memandu Anda melalui proses memasukkan teks superskrip dan subskrip ke dalam presentasi Java PowerPoint Anda menggunakan Aspose.Slides untuk Java.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Slide untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).
- Lingkungan Pengembangan Terpadu (IDE) seperti IntelliJ IDEA atau Eclipse yang disiapkan untuk pengembangan Java.
- Keakraban dasar dengan pemrograman Java dan presentasi PowerPoint.

## Paket Impor
Pertama, impor paket yang diperlukan dari Aspose.Slides untuk Java:
```java
import com.aspose.slides.*;
```
## Langkah 1: Siapkan Presentasi
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Langkah 2: Akses Slide
```java
// Dapatkan slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
```
## Langkah 3: Buat Kotak Teks
```java
// Buat BentukOtomatis untuk dijadikan kotak teks
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Langkah 4: Tambahkan Teks Superskrip
```java
// Buat paragraf untuk teks utama
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Buat bagian untuk teks superskrip
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Tetapkan escapement untuk superskrip
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Tambahkan paragraf utama dengan superskrip ke kotak teks
textFrame.getParagraphs().add(mainParagraph);
```
## Langkah 5: Tambahkan Teks Subskrip
```java
// Buat paragraf lain untuk teks subskrip
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Buat bagian untuk teks subskrip
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Tetapkan escapement untuk subskrip
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Tambahkan paragraf subskrip ke kotak teks
textFrame.getParagraphs().add(subscriptParagraph);
```
## Langkah 6: Simpan Presentasi
```java
// Simpan presentasi
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara menyempurnakan presentasi Java PowerPoint Anda dengan teks superskrip dan subskrip menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat membuat slide yang lebih menarik secara visual dan informatif yang mengomunikasikan konten Anda secara efektif.

## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides untuk Java adalah perpustakaan tangguh yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi presentasi PowerPoint secara terprogram.
### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Slides untuk Java?
 Dokumentasi terperinci dapat ditemukan[Di Sini](https://reference.aspose.com/slides/java/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Slides untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Bisakah saya mencoba Aspose.Slides untuk Java secara gratis?
 Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### Di mana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk Java?
 Untuk dukungan dan diskusi, kunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
