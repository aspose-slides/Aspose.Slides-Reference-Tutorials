---
title: Ubah Tata Letak SmartArt di PowerPoint dengan Java
linktitle: Ubah Tata Letak SmartArt di PowerPoint dengan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara memanipulasi tata letak SmartArt dalam presentasi PowerPoint menggunakan Java dengan Aspose.Slides untuk Java.
type: docs
weight: 19
url: /id/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara memanipulasi tata letak SmartArt dalam presentasi PowerPoint menggunakan Java. SmartArt adalah fitur canggih di PowerPoint yang memungkinkan pengguna membuat grafik yang menarik secara visual untuk berbagai tujuan, seperti mengilustrasikan proses, hierarki, hubungan, dan banyak lagi.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda.
2.  Perpustakaan Aspose.Slides: Unduh dan instal perpustakaan Aspose.Slides untuk Java dari[Di Sini](https://releases.aspose.com/slides/java/).
3. Pemahaman Dasar Java: Keakraban dengan dasar-dasar bahasa pemrograman Java akan sangat membantu.
4. Lingkungan Pengembangan Terintegrasi (IDE): Pilih IDE pilihan Anda, seperti Eclipse atau IntelliJ IDEA.

## Paket Impor
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Langkah 1: Siapkan Lingkungan Proyek Java Anda
Pastikan proyek Java Anda sudah diatur dengan benar di IDE pilihan Anda. Buat proyek Java baru dan sertakan pustaka Aspose.Slides dalam dependensi proyek Anda.
## Langkah 2: Buat Presentasi Baru
Buat instance objek Presentasi baru untuk membuat presentasi PowerPoint baru.
```java
Presentation presentation = new Presentation();
```
## Langkah 3: Tambahkan Grafik SmartArt
Tambahkan grafik SmartArt ke presentasi Anda. Tentukan posisi dan dimensi grafik SmartArt pada slide.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Langkah 4: Ubah Tata Letak SmartArt
Ubah tata letak grafik SmartArt ke tipe tata letak yang Anda inginkan.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Langkah 5: Simpan Presentasi
Simpan presentasi yang dimodifikasi ke direktori tertentu di sistem Anda.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Memanipulasi tata letak SmartArt dalam presentasi PowerPoint menggunakan Java adalah proses yang mudah dengan Aspose.Slides untuk Java. Dengan mengikuti tutorial ini, Anda dapat dengan mudah memodifikasi grafik SmartArt agar sesuai dengan kebutuhan presentasi Anda.
## FAQ
### Bisakah saya mengkustomisasi tampilan grafik SmartArt menggunakan Aspose.Slides untuk Java?
Ya, Anda dapat menyesuaikan berbagai aspek grafik SmartArt, seperti warna, gaya, dan efek.
### Apakah Aspose.Slides kompatibel dengan versi PowerPoint yang berbeda?
Aspose.Slides mendukung presentasi PowerPoint yang dibuat dalam berbagai versi PowerPoint, memastikan kompatibilitas di berbagai platform.
### Apakah Aspose.Slides menawarkan dukungan untuk bahasa pemrograman lain?
Ya, Aspose.Slides tersedia untuk berbagai bahasa pemrograman, termasuk .NET, Python, dan JavaScript.
### Bisakah saya membuat grafik SmartArt dari awal menggunakan Aspose.Slides?
Tentu saja, Anda dapat membuat grafik SmartArt secara terprogram atau memodifikasi grafik yang sudah ada untuk memenuhi kebutuhan Anda.
### Apakah ada forum komunitas tempat saya dapat mencari bantuan mengenai Aspose.Slides?
 Ya, Anda dapat mengunjungi forum Aspose.Slides[Di Sini](https://forum.aspose.com/c/slides/11) untuk bertanya dan terlibat dengan komunitas.