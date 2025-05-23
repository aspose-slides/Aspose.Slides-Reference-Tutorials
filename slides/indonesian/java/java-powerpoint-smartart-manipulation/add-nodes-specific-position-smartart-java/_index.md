---
"description": "Temukan cara menambahkan node pada posisi tertentu di SmartArt menggunakan Java dengan Aspose.Slides. Buat presentasi dinamis dengan mudah."
"linktitle": "Menambahkan Node pada Posisi Tertentu di SmartArt menggunakan Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menambahkan Node pada Posisi Tertentu di SmartArt menggunakan Java"
"url": "/id/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Node pada Posisi Tertentu di SmartArt menggunakan Java

## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses penambahan node pada posisi tertentu di SmartArt menggunakan Java dengan Aspose.Slides. SmartArt adalah fitur di PowerPoint yang memungkinkan Anda membuat diagram dan bagan yang menarik secara visual.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) terinstal di sistem Anda.
2. Aspose.Slides untuk pustaka Java telah diunduh. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).
3. Pengetahuan dasar tentang bahasa pemrograman Java.

## Paket Impor
Pertama, mari impor paket yang diperlukan ke dalam kode Java kita:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Langkah 1: Buat Contoh Presentasi
Mulailah dengan membuat contoh kelas Presentasi:
```java
Presentation pres = new Presentation();
```
## Langkah 2: Akses Slide Presentasi
Akses slide tempat Anda ingin menambahkan SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Langkah 3: Tambahkan Bentuk SmartArt
Tambahkan bentuk SmartArt ke slide:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Langkah 4: Akses Node SmartArt
Akses simpul SmartArt pada indeks yang diinginkan:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Langkah 5: Tambahkan Node Anak pada Posisi Tertentu
Tambahkan simpul anak baru pada posisi tertentu di simpul induk:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Langkah 6: Tambahkan Teks ke Node
Tetapkan teks untuk simpul yang baru ditambahkan:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Langkah 7: Simpan Presentasi
Simpan presentasi yang dimodifikasi:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Dalam tutorial ini, Anda mempelajari cara menambahkan node pada posisi tertentu di SmartArt menggunakan Java dengan Aspose.Slides. Dengan mengikuti langkah-langkah ini, Anda dapat memanipulasi bentuk SmartArt secara terprogram untuk membuat presentasi yang dinamis.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menambahkan beberapa node sekaligus?
Ya, Anda dapat menambahkan beberapa node secara terprogram dengan mengulangi posisi yang diinginkan.
### Apakah Aspose.Slides kompatibel dengan semua versi PowerPoint?
Aspose.Slides mendukung berbagai format PowerPoint, memastikan kompatibilitas dengan sebagian besar versi.
### Bisakah saya menyesuaikan tampilan simpul SmartArt?
Ya, Anda dapat menyesuaikan tampilan node, termasuk ukuran, warna, dan gayanya.
### Apakah Aspose.Slides menawarkan dukungan untuk bahasa pemrograman lain?
Ya, Aspose.Slides menyediakan pustaka untuk berbagai bahasa pemrograman, termasuk .NET dan Python.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides?
Ya, Anda dapat mengunduh versi uji coba gratis dari [Di Sini](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}