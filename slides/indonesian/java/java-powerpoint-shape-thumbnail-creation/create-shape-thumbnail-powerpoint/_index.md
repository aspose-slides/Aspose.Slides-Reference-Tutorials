---
"description": "Pelajari cara membuat gambar mini bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah disediakan."
"linktitle": "Membuat Thumbnail Bentuk di PowerPoint"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Membuat Thumbnail Bentuk di PowerPoint"
"url": "/id/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Thumbnail Bentuk di PowerPoint

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara membuat gambar mini bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Aspose.Slides adalah pustaka canggih yang memungkinkan pengembang untuk bekerja dengan file PowerPoint secara terprogram, yang memungkinkan otomatisasi berbagai tugas, termasuk membuat gambar mini bentuk.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
- Java Development Kit (JDK) terinstal di sistem Anda.
- Pustaka Aspose.Slides untuk Java telah diunduh dan disiapkan di proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan dalam kode Java Anda untuk memanfaatkan fungsi Aspose.Slides. Sertakan pernyataan impor berikut di awal berkas Java Anda:
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
Mengganti `"Your Document Directory"` dengan jalur ke direktori yang berisi berkas PowerPoint Anda.
## Langkah 2: Membuat Instansiasi Objek Presentasi
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
Buat contoh baru dari `Presentation` kelas, yang meneruskan jalur ke file PowerPoint Anda sebagai parameter.
## Langkah 3: Hasilkan Gambar Mini Bentuk
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Ambil gambar mini bentuk yang diinginkan dari slide pertama presentasi.
## Langkah 4: Simpan Gambar Miniatur
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Simpan gambar mini yang dihasilkan ke disk dalam format PNG dengan nama file yang ditentukan.

## Kesimpulan
Sebagai kesimpulan, tutorial ini menunjukkan cara membuat gambar mini bentuk dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan cuplikan kode yang disediakan, Anda dapat membuat gambar mini bentuk secara terprogram dengan efisien.

## Pertanyaan yang Sering Diajukan
### Dapatkah saya membuat gambar mini untuk bentuk pada slide mana pun dalam presentasi?
Ya, Anda dapat mengubah kode untuk menargetkan bentuk pada slide mana pun dengan menyesuaikan indeks slide sebagaimana mestinya.
### Apakah Aspose.Slides mendukung format gambar lain untuk menyimpan gambar mini?
Ya, selain PNG, Aspose.Slides mendukung penyimpanan gambar mini dalam berbagai format gambar seperti JPEG, GIF, dan BMP.
### Apakah Aspose.Slides cocok untuk penggunaan komersial?
Ya, Aspose.Slides menawarkan lisensi komersial untuk bisnis dan organisasi. Anda dapat membeli lisensi dari [Di Sini](https://purchase.aspose.com/buy).
### Bisakah saya mencoba Aspose.Slides sebelum membeli?
Tentu saja! Anda dapat mengunduh versi uji coba gratis Aspose.Slides dari [Di Sini](https://releases.aspose.com/) untuk mengevaluasi fitur dan kemampuannya.
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides?
Jika Anda memiliki pertanyaan atau memerlukan bantuan dengan Aspose.Slides, Anda dapat mengunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk dukungan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}