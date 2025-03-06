---
title: Tambahkan Garis Biasa ke Slide
linktitle: Tambahkan Garis Biasa ke Slide
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan garis polos ke slide PowerPoint secara terprogram menggunakan Aspose.Slides for Java. Tingkatkan produktivitas Anda dengan panduan langkah demi langkah ini.
weight: 14
url: /id/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Garis Biasa ke Slide

## Perkenalan
Aspose.Slides untuk Java adalah perpustakaan canggih yang memungkinkan pengembang Java bekerja dengan presentasi PowerPoint secara terprogram. Dengan Aspose.Slides, Anda dapat membuat, memodifikasi, dan mengonversi file PowerPoint dengan mudah, menghemat waktu dan tenaga Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan garis polos ke slide dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda
- Aspose.Slides untuk perpustakaan Java diunduh dan ditambahkan ke proyek Java Anda
- Pengetahuan dasar bahasa pemrograman Java

## Paket Impor
Untuk memulai, Anda perlu mengimpor paket yang diperlukan dalam kode Java Anda. Inilah cara Anda melakukannya:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## Langkah 1: Siapkan Lingkungan
 Pertama, buat proyek Java baru dan tambahkan pustaka Aspose.Slides for Java ke classpath proyek Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).
## Langkah 2: Buat Presentasi Baru
 Selanjutnya, buat instance`Presentation` kelas untuk membuat presentasi PowerPoint baru.
```java
Presentation pres = new Presentation();
```
## Langkah 3: Tambahkan Slide
Dapatkan slide pertama presentasi dan simpan dalam sebuah variabel.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Langkah 4: Tambahkan Bentuk Garis
Sekarang, tambahkan garis tipe bentuk otomatis ke slide.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Langkah 5: Simpan Presentasi
Terakhir, simpan presentasi ke disk.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Selamat! Anda telah berhasil menambahkan garis polos ke slide dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan Aspose.Slides, Anda dapat dengan mudah memanipulasi file PowerPoint secara terprogram, membuka banyak kemungkinan untuk aplikasi Java Anda.

## FAQ
### Bisakah saya menyesuaikan properti bentuk garis?
Ya, Anda dapat menyesuaikan berbagai properti seperti warna garis, lebar, gaya, dan lainnya menggunakan Aspose.Slides API.
### Apakah Aspose.Slides kompatibel dengan versi PowerPoint yang berbeda?
Ya, Aspose.Slides mendukung berbagai format PowerPoint, termasuk PPT, PPTX, dan lainnya, memastikan kompatibilitas di berbagai versi.
### Apakah Aspose.Slides memberikan dukungan untuk menambahkan bentuk lain selain garis?
Sangat! Aspose.Slides menawarkan berbagai jenis bentuk, termasuk persegi panjang, lingkaran, panah, dan banyak lagi.
### Bisakah saya menambahkan teks ke slide beserta bentuk garisnya?
Ya, Anda dapat menambahkan teks, gambar, dan konten lainnya ke slide menggunakan Aspose.Slides API.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides?
 Ya, Anda dapat mengunduh uji coba gratis Aspose.Slides dari[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
