---
"description": "Pelajari cara mengatur format isian poin dalam SmartArt menggunakan Java dengan Aspose.Slides. Panduan langkah demi langkah untuk manipulasi presentasi yang efisien."
"linktitle": "Mengatur Format Isian Bullet di SmartArt menggunakan Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Format Isian Bullet di SmartArt menggunakan Java"
"url": "/id/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Format Isian Bullet di SmartArt menggunakan Java

## Perkenalan
Dalam bidang pemrograman Java, manipulasi presentasi yang efisien merupakan persyaratan umum, terutama saat menangani elemen SmartArt. Aspose.Slides untuk Java muncul sebagai alat yang ampuh untuk tugas tersebut, menawarkan serangkaian fungsi untuk menangani presentasi secara terprogram. Dalam tutorial ini, kita akan mempelajari proses pengaturan format isian poin dalam SmartArt menggunakan Java dengan Aspose.Slides, langkah demi langkah.
## Prasyarat
Sebelum kita memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:
### Kit Pengembangan Java (JDK)
Anda perlu menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari [situs web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) dan ikuti petunjuk instalasi.
### Aspose.Slides untuk Java
Unduh dan instal Aspose.Slides untuk Java dari [tautan unduhan](https://releases.aspose.com/slides/java/)Ikuti petunjuk instalasi yang tersedia dalam dokumentasi untuk sistem operasi spesifik Anda.

## Paket Impor
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk pemahaman yang jelas tentang cara mengatur format isian poin dalam SmartArt menggunakan Java dengan Aspose.Slides.
## Langkah 1: Buat Objek Presentasi
```java
Presentation presentation = new Presentation();
```
Pertama, buat contoh baru kelas Presentasi, yang merepresentasikan presentasi PowerPoint.
## Langkah 2: Tambahkan SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Selanjutnya, tambahkan bentuk SmartArt ke slide. Baris kode ini menginisialisasi bentuk SmartArt baru dengan dimensi dan tata letak yang ditentukan.
## Langkah 3: Akses Node SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Sekarang, akses simpul pertama (atau simpul yang diinginkan) dalam bentuk SmartArt untuk mengubah propertinya.
## Langkah 4: Atur Format Isi Poin
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Di sini, kami memeriksa apakah format isian poin didukung. Jika ya, kami memuat berkas gambar dan mengaturnya sebagai isian poin untuk simpul SmartArt.
## Langkah 5: Simpan Presentasi
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Terakhir, simpan presentasi yang dimodifikasi ke lokasi yang ditentukan.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengatur format isian poin dalam SmartArt menggunakan Java dengan Aspose.Slides. Kemampuan ini membuka banyak kemungkinan untuk presentasi yang dinamis dan menarik secara visual dalam aplikasi Java.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menggunakan Aspose.Slides untuk Java untuk membuat presentasi dari awal?
Tentu saja! Aspose.Slides menyediakan API yang komprehensif untuk membuat, memodifikasi, dan memanipulasi presentasi sepenuhnya melalui kode.
### Apakah Aspose.Slides kompatibel dengan berbagai versi PowerPoint?
Ya, Aspose.Slides memastikan kompatibilitas dengan berbagai versi Microsoft PowerPoint, memungkinkan integrasi yang mulus ke dalam alur kerja Anda.
### Bisakah saya menyesuaikan elemen SmartArt di luar format isian poin?
Memang, Aspose.Slides memberdayakan Anda untuk menyesuaikan setiap aspek bentuk SmartArt, termasuk tata letak, gaya, konten, dan banyak lagi.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk Java?
Ya, Anda dapat menjelajahi fitur-fitur Aspose.Slides dengan uji coba gratis. Cukup unduh dari [situs web](https://releases.aspose.com/slides/java/) dan mulai menjelajah.
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides untuk Java?
Untuk pertanyaan atau bantuan apa pun, Anda dapat mengunjungi forum Aspose.Slides di [tautan ini](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}