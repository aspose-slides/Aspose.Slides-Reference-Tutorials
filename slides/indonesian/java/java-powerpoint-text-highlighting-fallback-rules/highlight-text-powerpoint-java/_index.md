---
title: Sorot Teks di PowerPoint dengan Java
linktitle: Sorot Teks di PowerPoint dengan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menyorot teks di PowerPoint menggunakan Aspose.Slides untuk Java. Otomatiskan dan tingkatkan presentasi dengan mudah menggunakan panduan terperinci kami.
weight: 10
url: /id/java/java-powerpoint-text-highlighting-fallback-rules/highlight-text-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sorot Teks di PowerPoint dengan Java

## Perkenalan
Di era digital saat ini, di mana komunikasi visual memainkan peran penting dalam presentasi bisnis dan materi pendidikan, kemampuan untuk memanipulasi dan menyempurnakan presentasi PowerPoint secara terprogram merupakan keuntungan yang signifikan. Aspose.Slides untuk Java memberdayakan pengembang dengan seperangkat alat canggih untuk mengintegrasikan dan memanipulasi slide PowerPoint dengan lancar menggunakan bahasa pemrograman Java. Baik Anda mengotomatiskan pembuatan presentasi, memodifikasi presentasi yang sudah ada, atau mengekstrak data dari slide, Aspose.Slides untuk Java menyediakan fungsionalitas yang diperlukan untuk mencapai tugas-tugas ini secara efisien.
## Prasyarat
Sebelum mulai menggunakan Aspose.Slides for Java untuk menyorot teks dalam presentasi PowerPoint, pastikan Anda telah menyiapkan prasyarat berikut:
-  Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda. Anda dapat mengunduhnya dari[Unduhan Kit Pengembangan Java SE](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Perpustakaan Aspose.Slides untuk Java: Dapatkan perpustakaan Aspose.Slides untuk Java dari[Unduh Halaman](https://releases.aspose.com/slides/java/)Ikuti petunjuk instalasi untuk menyiapkan perpustakaan di lingkungan pengembangan Anda.
- Lingkungan Pengembangan Terpadu (IDE): Pilih IDE pilihan Anda yang mendukung pengembangan Java, seperti IntelliJ IDEA, Eclipse, atau NetBeans.

## Paket Impor
Untuk mulai menyorot teks dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java, Anda perlu mengimpor paket yang diperlukan:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Langkah 1: Muat Presentasi
Pertama, muat presentasi PowerPoint di tempat Anda ingin menyorot teks.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SomePresentation.pptx");
```
 Mengganti`"Your Document Directory"` dengan jalur direktori sebenarnya tempat presentasi PowerPoint Anda (`SomePresentation.pptx`) terletak.
## Langkah 2: Sorot Teks
Sorot teks tertentu dalam bentuk pada slide. Di sini, kami menyorot kemunculan kata "judul" dan "kepada" dengan warna berbeda.
```java
// Menyorot kata 'judul' dengan warna Biru Muda
((AutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0))
    .getTextFrame().highlightText("title", new Color(PresetColor.LightBlue));
// Menyoroti kata 'ke' dengan warna Violet, seluruh kata saja
TextHighlightingOptions options = new TextHighlightingOptions();
options.setWholeWordsOnly(true);
((AutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0))
    .getTextFrame().highlightText("to", new Color(PresetColor.Violet), options);
```
Cuplikan kode ini menunjukkan cara menyorot teks dalam bentuk tertentu (`AutoShape`) di slide pertama (`get_Item(0)`).
## Langkah 3: Simpan Presentasi yang Dimodifikasi
Simpan presentasi yang dimodifikasi dengan teks yang disorot ke file baru.
```java
presentation.save(dataDir + "SomePresentation-out.pptx", SaveFormat.Pptx);
```
 Mengganti`"SomePresentation-out.pptx"` dengan nama yang diinginkan untuk file keluaran Anda.

## Kesimpulan
Kesimpulannya, penggunaan Aspose.Slides for Java menyederhanakan tugas memanipulasi presentasi PowerPoint secara terprogram. Dengan API komprehensifnya, pengembang dapat menyorot teks secara efisien, menyesuaikan slide, dan mengotomatiskan tugas presentasi untuk meningkatkan produktivitas.

## FAQ
### Apa itu Aspose.Slide untuk Java?
Aspose.Slides for Java adalah Java API yang memungkinkan pengembang membuat, memodifikasi, dan memanipulasi presentasi PowerPoint tanpa memerlukan instalasi Microsoft Office atau PowerPoint.
### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk Java?
 Anda dapat menemukan dokumentasinya[Di Sini](https://reference.aspose.com/slides/java/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Slides untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Dalam format apa Aspose.Slides for Java menyimpan presentasi?
Aspose.Slides untuk Java mendukung penyimpanan presentasi dalam berbagai format termasuk PPTX, PPT, PDF, dan banyak lagi.
### Apakah Aspose.Slides untuk Java kompatibel dengan Java SE Development Kit?
Ya, Aspose.Slides for Java kompatibel dengan Java SE Development Kit.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
