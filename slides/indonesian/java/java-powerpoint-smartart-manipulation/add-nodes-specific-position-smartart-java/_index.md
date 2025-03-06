---
title: Tambahkan Node pada Posisi Tertentu di SmartArt menggunakan Java
linktitle: Tambahkan Node pada Posisi Tertentu di SmartArt menggunakan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Temukan cara menambahkan node pada posisi tertentu di SmartArt menggunakan Java dengan Aspose.Slides. Buat presentasi dinamis dengan mudah.
weight: 16
url: /id/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses penambahan node pada posisi tertentu di SmartArt menggunakan Java dengan Aspose.Slides. SmartArt adalah fitur di PowerPoint yang memungkinkan Anda membuat diagram dan bagan yang menarik secara visual.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Slide untuk perpustakaan Java diunduh. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).
3. Pengetahuan dasar bahasa pemrograman Java.

## Paket Impor
Pertama, mari impor paket yang diperlukan dalam kode Java kita:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Langkah 1: Buat Instans Presentasi
Mulailah dengan membuat instance kelas Presentasi:
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
Akses node SmartArt pada indeks yang diinginkan:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Langkah 5: Tambahkan Node Anak pada Posisi Tertentu
Tambahkan node anak baru pada posisi tertentu di node induk:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Langkah 6: Tambahkan Teks ke Node
Atur teks untuk node yang baru ditambahkan:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Langkah 7: Simpan Presentasi
Simpan presentasi yang dimodifikasi:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Dalam tutorial ini, Anda mempelajari cara menambahkan node pada posisi tertentu di SmartArt menggunakan Java dengan Aspose.Slides. Dengan mengikuti langkah-langkah ini, Anda bisa memanipulasi bentuk SmartArt secara terprogram untuk membuat presentasi dinamis.
## FAQ
### Bisakah saya menambahkan beberapa node sekaligus?
Ya, Anda dapat menambahkan beberapa node secara terprogram dengan melakukan iterasi pada posisi yang diinginkan.
### Apakah Aspose.Slides kompatibel dengan semua versi PowerPoint?
Aspose.Slides mendukung berbagai format PowerPoint, memastikan kompatibilitas dengan sebagian besar versi.
### Bisakah saya mengkustomisasi tampilan node SmartArt?
Ya, Anda dapat menyesuaikan tampilan node, termasuk ukuran, warna, dan gayanya.
### Apakah Aspose.Slides menawarkan dukungan untuk bahasa pemrograman lain?
Ya, Aspose.Slides menyediakan perpustakaan untuk berbagai bahasa pemrograman, termasuk .NET dan Python.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides?
 Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
