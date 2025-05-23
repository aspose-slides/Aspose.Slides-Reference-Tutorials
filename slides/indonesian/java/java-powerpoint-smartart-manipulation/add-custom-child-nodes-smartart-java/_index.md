---
"description": "Pelajari cara menambahkan simpul anak kustom ke SmartArt dalam presentasi PowerPoint menggunakan Java dengan Aspose.Slides. Sempurnakan slide Anda dengan grafis profesional dengan mudah."
"linktitle": "Menambahkan Node Anak Kustom di SmartArt menggunakan Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menambahkan Node Anak Kustom di SmartArt menggunakan Java"
"url": "/id/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Node Anak Kustom di SmartArt menggunakan Java

## Perkenalan
SmartArt adalah fitur hebat di PowerPoint yang memungkinkan pengguna membuat grafik yang tampak profesional dengan cepat dan mudah. Dalam tutorial ini, kita akan mempelajari cara menambahkan simpul anak kustom ke SmartArt menggunakan Java dengan Aspose.Slides.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda.
2. Aspose.Slides untuk Java: Unduh dan instal Aspose.Slides untuk Java dari [Di Sini](https://releases.aspose.com/slides/java/).

## Paket Impor
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.slides.*;
```
## Langkah 1: Muat Presentasi
Muat presentasi PowerPoint tempat Anda ingin menambahkan simpul anak kustom ke SmartArt:
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
Ubah lebar bentuk SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Langkah 5: Ubah Tinggi Bentuk
Ubah tinggi bentuk SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Langkah 6: Putar Bentuknya
Putar bentuk SmartArt:
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
Dalam tutorial ini, kita mempelajari cara menambahkan simpul anak kustom ke SmartArt menggunakan Java dengan Aspose.Slides. Dengan mengikuti langkah-langkah ini, Anda dapat menyempurnakan presentasi Anda dengan grafis kustom, membuatnya lebih menarik dan profesional.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menambahkan berbagai jenis tata letak SmartArt menggunakan Aspose.Slides untuk Java?
Ya, Aspose.Slides untuk Java mendukung berbagai tata letak SmartArt, memungkinkan Anda memilih salah satu yang paling sesuai dengan kebutuhan presentasi Anda.
### Apakah Aspose.Slides untuk Java kompatibel dengan berbagai versi PowerPoint?
Aspose.Slides untuk Java dirancang untuk bekerja lancar dengan berbagai versi PowerPoint, memastikan kompatibilitas dan konsistensi di seluruh platform.
### Dapatkah saya menyesuaikan tampilan bentuk SmartArt secara terprogram?
Tentu saja! Dengan Aspose.Slides untuk Java, Anda dapat secara terprogram menyesuaikan tampilan, ukuran, warna, dan tata letak bentuk SmartArt agar sesuai dengan preferensi desain Anda.
### Apakah Aspose.Slides untuk Java menyediakan dokumentasi dan dukungan?
Ya, Anda dapat menemukan dokumentasi lengkap dan akses ke forum dukungan komunitas di situs web Aspose.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk Java?
Ya, Anda dapat mengunduh versi uji coba gratis Aspose.Slides untuk Java dari situs web untuk menjelajahi fitur dan kemampuannya sebelum melakukan pembelian [Di Sini](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}