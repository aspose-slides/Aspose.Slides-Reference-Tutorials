---
title: Tambahkan Bingkai Foto Tinggi Skala Relatif di PowerPoint
linktitle: Tambahkan Bingkai Foto Tinggi Skala Relatif di PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan bingkai foto dengan tinggi skala relatif dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java, sehingga menyempurnakan konten visual Anda.
weight: 15
url: /id/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Bingkai Foto Tinggi Skala Relatif di PowerPoint

## Perkenalan
Dalam tutorial ini, Anda akan mempelajari cara menambahkan bingkai foto dengan tinggi skala relatif dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2. Aspose.Slides untuk perpustakaan Java diunduh dan ditambahkan ke proyek Java Anda.

## Paket Impor
Untuk memulai, impor paket yang diperlukan dalam proyek Java Anda:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Langkah 1: Siapkan Proyek Anda
Pertama, pastikan Anda telah menyiapkan direktori untuk proyek Anda, dan lingkungan Java Anda dikonfigurasi dengan benar.
## Langkah 2: Buat Instansiasi Objek Presentasi
Buat objek presentasi baru menggunakan Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Langkah 3: Muat Gambar yang akan Ditambahkan
Muat gambar yang ingin Anda tambahkan ke presentasi:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Langkah 4: Tambahkan Bingkai Foto ke Slide
Menambahkan bingkai foto ke slide dalam presentasi:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Langkah 5: Tetapkan Lebar dan Tinggi Skala Relatif
Atur lebar dan tinggi skala relatif untuk bingkai foto:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Langkah 6: Simpan Presentasi
Simpan presentasi dengan bingkai foto tambahan:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menambahkan bingkai foto dengan tinggi skala relatif dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Bereksperimenlah dengan nilai skala berbeda untuk mencapai tampilan gambar yang diinginkan.

## FAQ
### Bisakah saya menambahkan beberapa bingkai foto ke satu slide menggunakan metode ini?
Ya, Anda dapat menambahkan beberapa bingkai foto ke slide dengan mengulangi proses untuk setiap gambar.
### Apakah Aspose.Slides untuk Java kompatibel dengan semua versi PowerPoint?
Aspose.Slides for Java kompatibel dengan berbagai versi PowerPoint, memastikan fleksibilitas dalam membuat presentasi.
### Bisakah saya menyesuaikan posisi dan ukuran bingkai foto?
 Tentu saja, Anda dapat menyesuaikan parameter posisi dan ukuran di`addPictureFrame` metode yang sesuai dengan kebutuhan Anda.
### Apakah Aspose.Slides untuk Java mendukung format gambar lain selain JPEG?
Ya, Aspose.Slides untuk Java mendukung berbagai format gambar, termasuk PNG, GIF, BMP, dan lainnya.
### Apakah ada forum komunitas atau saluran dukungan yang tersedia untuk pengguna Aspose.Slides?
Ya, Anda dapat mengunjungi forum Aspose.Slides untuk pertanyaan, diskusi, atau bantuan apa pun terkait perpustakaan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
