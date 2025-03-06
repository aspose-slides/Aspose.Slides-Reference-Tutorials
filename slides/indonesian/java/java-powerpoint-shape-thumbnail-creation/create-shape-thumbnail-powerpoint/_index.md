---
title: Buat Bentuk Thumbnail di PowerPoint
linktitle: Buat Bentuk Thumbnail di PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat gambar mini bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah disediakan.
weight: 14
url: /id/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara membuat thumbnail bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Aspose.Slides adalah pustaka canggih yang memungkinkan pengembang bekerja dengan file PowerPoint secara terprogram, memungkinkan otomatisasi berbagai tugas, termasuk menghasilkan thumbnail bentuk.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Slides untuk perpustakaan Java diunduh dan disiapkan di proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan dalam kode Java Anda untuk memanfaatkan fungsi Aspose.Slides. Sertakan pernyataan import berikut di awal file Java Anda:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Langkah 1: Tentukan Direktori Dokumen
```java
String dataDir = "Your Document Directory";
```
 Mengganti`"Your Document Directory"` dengan jalur ke direktori yang berisi file PowerPoint Anda.
## Langkah 2: Buat Instansiasi Objek Presentasi
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Buat instance baru dari`Presentation` kelas, meneruskan jalur ke file PowerPoint Anda sebagai parameter.
## Langkah 3: Hasilkan Gambar Kecil Bentuk
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Ambil thumbnail bentuk yang diinginkan dari slide pertama presentasi.
## Langkah 4: Simpan Gambar Kecil
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Simpan gambar thumbnail yang dihasilkan ke disk dalam format PNG dengan nama file yang ditentukan.

## Kesimpulan
Sebagai kesimpulan, tutorial ini menunjukkan cara membuat thumbnail bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan cuplikan kode yang disediakan, Anda dapat membuat thumbnail bentuk secara terprogram secara efisien.

## FAQ
### Bisakah saya membuat thumbnail untuk bentuk pada slide mana pun dalam presentasi?
Ya, Anda dapat memodifikasi kode untuk menargetkan bentuk pada slide mana pun dengan menyesuaikan indeks slide.
### Apakah Aspose.Slides mendukung format gambar lain untuk menyimpan thumbnail?
Ya, selain PNG, Aspose.Slides mendukung penyimpanan thumbnail dalam berbagai format gambar seperti JPEG, GIF, dan BMP.
### Apakah Aspose.Slides cocok untuk penggunaan komersial?
 Ya, Aspose.Slides menawarkan lisensi komersial untuk bisnis dan organisasi. Anda dapat membeli lisensi dari[Di Sini](https://purchase.aspose.com/buy).
### Bisakah saya mencoba Aspose.Slides sebelum membeli?
 Sangat! Anda dapat mengunduh Aspose.Slides versi uji coba gratis dari[Di Sini](https://releases.aspose.com/) untuk mengevaluasi fitur dan kemampuannya.
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides?
 Jika Anda memiliki pertanyaan atau memerlukan bantuan dengan Aspose.Slides, Anda dapat mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk dukungan.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
