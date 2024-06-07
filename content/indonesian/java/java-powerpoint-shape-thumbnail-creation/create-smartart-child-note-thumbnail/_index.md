---
title: Buat Gambar Kecil Catatan Anak SmartArt
linktitle: Buat Gambar Kecil Catatan Anak SmartArt
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat thumbnail catatan anak SmartArt di Java dengan Aspose.Slides, menyempurnakan presentasi PowerPoint Anda dengan mudah.
type: docs
weight: 15
url: /id/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara membuat thumbnail catatan anak SmartArt di Java menggunakan Aspose.Slides. Aspose.Slides adalah Java API canggih yang memungkinkan pengembang bekerja dengan presentasi PowerPoint secara terprogram, memungkinkan mereka membuat, memodifikasi, dan memanipulasi slide dengan mudah.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2. Aspose.Slides untuk perpustakaan Java diunduh dan dikonfigurasi di proyek Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).

## Paket Impor
Pastikan untuk mengimpor paket yang diperlukan di kelas Java Anda:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Langkah 1: Siapkan Proyek Anda
Pastikan Anda telah menyiapkan dan mengonfigurasi proyek Java dengan pustaka Aspose.Slides.
## Langkah 2: Buat Presentasi
 Buat instance`Presentation` kelas untuk mewakili file PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Langkah 3: Tambahkan SmartArt
Tambahkan SmartArt ke slide presentasi Anda:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Langkah 4: Dapatkan Referensi Node
Dapatkan referensi sebuah node dengan menggunakan indeksnya:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Langkah 5: Dapatkan Gambar Kecil
Ambil gambar mini dari node SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Langkah 6: Simpan Gambar Kecil
Simpan gambar mini ke file:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Ulangi langkah-langkah ini untuk setiap simpul SmartArt sesuai kebutuhan dalam presentasi Anda.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara membuat thumbnail catatan anak SmartArt di Java menggunakan Aspose.Slides. Dengan pengetahuan ini, Anda dapat menyempurnakan presentasi PowerPoint Anda secara terprogram, menambahkan elemen yang menarik secara visual dengan mudah.
## FAQ
### Bisakah saya menggunakan Aspose.Slides untuk memanipulasi file PowerPoint yang ada?
Ya, Aspose.Slides memungkinkan Anda memodifikasi file PowerPoint yang ada, termasuk menambah, menghapus, atau mengedit slide dan isinya.
### Apakah Aspose.Slides mendukung ekspor slide ke format file yang berbeda?
Sangat! Aspose.Slides mendukung ekspor slide ke berbagai format, antara lain PDF, gambar, dan HTML.
### Apakah Aspose.Slides cocok untuk otomatisasi PowerPoint tingkat perusahaan?
Ya, Aspose.Slides dirancang untuk menangani tugas otomatisasi PowerPoint tingkat perusahaan secara efisien dan andal.
### Bisakah saya membuat diagram SmartArt yang kompleks secara terprogram dengan Aspose.Slides?
Tentu! Aspose.Slides memberikan dukungan komprehensif untuk membuat dan memanipulasi diagram SmartArt dengan berbagai kompleksitas.
### Apakah Aspose.Slides menawarkan dukungan teknis untuk pengembang?
 Ya, Aspose.Slides menyediakan dukungan teknis khusus untuk pengembang melalui mereka[forum](https://forum.aspose.com/c/slides/11) dan saluran lainnya.