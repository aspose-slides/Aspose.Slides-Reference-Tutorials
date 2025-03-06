---
title: Tambahkan Node Anak Kustom di SmartArt menggunakan Java
linktitle: Tambahkan Node Anak Kustom di SmartArt menggunakan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan node anak kustom ke SmartArt dalam presentasi PowerPoint menggunakan Java dengan Aspose.Slides. Sempurnakan slide Anda dengan grafis profesional dengan mudah.
weight: 11
url: /id/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
SmartArt adalah fitur canggih di PowerPoint yang memungkinkan pengguna membuat grafik tampak profesional dengan cepat dan mudah. Dalam tutorial ini, kita akan mempelajari cara menambahkan node anak kustom ke SmartArt menggunakan Java dengan Aspose.Slides.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda.
2.  Aspose.Slides for Java: Unduh dan instal Aspose.Slides for Java dari[Di Sini](https://releases.aspose.com/slides/java/).

## Paket Impor
Untuk memulai, impor paket yang diperlukan dalam proyek Java Anda:
```java
import com.aspose.slides.*;
```
## Langkah 1: Muat Presentasi
Muat presentasi PowerPoint tempat Anda ingin menambahkan node anak kustom ke SmartArt:
```java
String dataDir = "Your Document Directory";
// Muat presentasi yang diinginkan
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Langkah 2: Tambahkan SmartArt ke Slide
Sekarang, mari tambahkan SmartArt ke slide:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Langkah 3: Pindahkan Bentuk SmartArt
Pindahkan bentuk SmartArt ke posisi baru:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Langkah 4: Ubah Lebar Bentuk
Mengubah lebar bentuk SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Langkah 5: Ubah Tinggi Bentuk
Mengubah tinggi bentuk SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Langkah 6: Putar Bentuknya
Memutar bentuk SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Langkah 7: Simpan Presentasi
Terakhir, simpan presentasi yang dimodifikasi:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menambahkan node anak kustom ke SmartArt menggunakan Java dengan Aspose.Slides. Dengan mengikuti langkah-langkah ini, Anda dapat menyempurnakan presentasi Anda dengan grafis yang disesuaikan, menjadikannya lebih menarik dan profesional.
## FAQ
### Bisakah saya menambahkan tipe tata letak SmartArt yang berbeda menggunakan Aspose.Slides untuk Java?
Ya, Aspose.Slides for Java mendukung berbagai tata letak SmartArt, memungkinkan Anda memilih salah satu yang paling sesuai dengan kebutuhan presentasi Anda.
### Apakah Aspose.Slides untuk Java kompatibel dengan versi PowerPoint yang berbeda?
Aspose.Slides untuk Java dirancang untuk bekerja secara lancar dengan berbagai versi PowerPoint, memastikan kompatibilitas dan konsistensi di seluruh platform.
### Bisakah saya mengkustomisasi tampilan bentuk SmartArt secara terprogram?
Sangat! Dengan Aspose.Slides untuk Java, Anda dapat menyesuaikan tampilan, ukuran, warna, dan tata letak bentuk SmartArt secara terprogram agar sesuai dengan preferensi desain Anda.
### Apakah Aspose.Slides untuk Java menyediakan dokumentasi dan dukungan?
Ya, Anda dapat menemukan dokumentasi komprehensif dan akses ke forum dukungan komunitas di situs Aspose.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk Java?
 Ya, Anda dapat mengunduh Aspose.Slides for Java versi uji coba gratis dari situs web untuk menjelajahi fitur dan kemampuannya sebelum melakukan pembelian[Di Sini](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
