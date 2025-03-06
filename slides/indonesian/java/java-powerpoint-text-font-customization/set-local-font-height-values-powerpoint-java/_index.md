---
title: Tetapkan Nilai Tinggi Font Lokal di PowerPoint menggunakan Java
linktitle: Tetapkan Nilai Tinggi Font Lokal di PowerPoint menggunakan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyesuaikan ketinggian font dalam presentasi PowerPoint menggunakan Java dengan Aspose.Slides. Sempurnakan pemformatan teks di slide Anda dengan mudah.
weight: 17
url: /id/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam tutorial ini, Anda akan mempelajari cara memanipulasi ketinggian font di berbagai level dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Mengontrol ukuran font sangat penting untuk membuat presentasi yang menarik secara visual dan terstruktur. Kami akan membahas contoh langkah demi langkah untuk mengilustrasikan cara mengatur tinggi font untuk elemen teks yang berbeda.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda
-  Aspose.Slide untuk perpustakaan Java. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/slides/java/).
- Pemahaman dasar tentang pemrograman Java dan presentasi PowerPoint
## Paket Impor
Pastikan untuk menyertakan paket Aspose.Slides yang diperlukan dalam file Java Anda:
```java
import com.aspose.slides.*;
```
## Langkah 1: Inisialisasi Objek Presentasi
Pertama, buat objek presentasi PowerPoint baru:
```java
Presentation pres = new Presentation();
```
## Langkah 2: Tambahkan Bentuk dan Bingkai Teks
Tambahkan bentuk otomatis dengan bingkai teks ke slide pertama:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Langkah 3: Buat Bagian Teks
Tentukan bagian teks dengan tinggi font berbeda:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Langkah 4: Atur Ketinggian Font
Atur tinggi font pada level yang berbeda:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Langkah 5: Simpan Presentasi
Simpan presentasi yang dimodifikasi ke file:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Tutorial ini menunjukkan cara menyesuaikan ketinggian font dalam slide PowerPoint secara terprogram menggunakan Aspose.Slides untuk Java. Dengan memanipulasi ukuran font pada tingkat yang berbeda (lebar presentasi, paragraf, dan porsi), Anda dapat memperoleh kontrol yang tepat atas pemformatan teks dalam presentasi Anda.
## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides untuk Java adalah API yang kuat untuk memanipulasi presentasi PowerPoint secara terprogram.
### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk Java?
 Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/slides/java/).
### Bisakah saya mencoba Aspose.Slides untuk Java sebelum membeli?
 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk Java?
 Untuk dukungan, kunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
### Di mana saya dapat membeli lisensi Aspose.Slides untuk Java?
 Anda dapat membeli lisensi[Di Sini](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
