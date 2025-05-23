---
"description": "Pelajari cara menambahkan garis polos ke slide PowerPoint secara terprogram menggunakan Aspose.Slides untuk Java. Tingkatkan produktivitas Anda dengan panduan langkah demi langkah ini."
"linktitle": "Tambahkan Garis Biasa ke Slide"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Tambahkan Garis Biasa ke Slide"
"url": "/id/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Garis Biasa ke Slide

## Perkenalan
Aspose.Slides untuk Java adalah pustaka canggih yang memungkinkan pengembang Java bekerja dengan presentasi PowerPoint secara terprogram. Dengan Aspose.Slides, Anda dapat membuat, memodifikasi, dan mengonversi file PowerPoint dengan mudah, sehingga menghemat waktu dan tenaga Anda. Dalam tutorial ini, kami akan memandu Anda melalui proses menambahkan garis polos ke slide dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) terinstal di sistem Anda
- Pustaka Aspose.Slides untuk Java diunduh dan ditambahkan ke proyek Java Anda
- Pengetahuan dasar bahasa pemrograman Java

## Paket Impor
Untuk memulai, Anda perlu mengimpor paket yang diperlukan ke dalam kode Java Anda. Berikut cara melakukannya:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## Langkah 1: Siapkan Lingkungan
Pertama, buat proyek Java baru dan tambahkan pustaka Aspose.Slides for Java ke classpath proyek Anda. Anda dapat mengunduh pustaka dari [Di Sini](https://releases.aspose.com/slides/java/).
## Langkah 2: Buat Presentasi Baru
Selanjutnya, buat instance `Presentation` kelas untuk membuat presentasi PowerPoint baru.
```java
Presentation pres = new Presentation();
```
## Langkah 3: Tambahkan Slide
Dapatkan slide pertama presentasi dan simpan dalam variabel.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Langkah 4: Tambahkan Bentuk Garis
Sekarang, tambahkan bentuk otomatis bertipe garis ke slide.
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

## Pertanyaan yang Sering Diajukan
### Bisakah saya menyesuaikan properti bentuk garis?
Ya, Anda dapat menyesuaikan berbagai properti seperti warna garis, lebar, gaya, dan lainnya menggunakan Aspose.Slides API.
### Apakah Aspose.Slides kompatibel dengan berbagai versi PowerPoint?
Ya, Aspose.Slides mendukung berbagai format PowerPoint, termasuk PPT, PPTX, dan lainnya, yang memastikan kompatibilitas di berbagai versi.
### Apakah Aspose.Slides menyediakan dukungan untuk menambahkan bentuk lain selain garis?
Tentu saja! Aspose.Slides menawarkan berbagai jenis bentuk, termasuk persegi panjang, lingkaran, panah, dan banyak lagi.
### Dapatkah saya menambahkan teks ke slide bersama dengan bentuk garis?
Ya, Anda dapat menambahkan teks, gambar, dan konten lainnya ke slide menggunakan Aspose.Slides API.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides?
Ya, Anda dapat mengunduh uji coba gratis Aspose.Slides dari [Di Sini](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}