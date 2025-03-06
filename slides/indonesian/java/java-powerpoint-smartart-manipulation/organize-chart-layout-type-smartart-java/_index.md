---
title: Atur Tipe Tata Letak Bagan di SmartArt menggunakan Java
linktitle: Atur Tipe Tata Letak Bagan di SmartArt menggunakan Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Kuasai pengorganisasian tipe tata letak bagan di SmartArt menggunakan Java dengan Aspose.Slides, tingkatkan visual presentasi dengan mudah.
weight: 13
url: /id/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam tutorial ini, kita akan memandu proses pengorganisasian tipe tata letak bagan di SmartArt menggunakan Java, khususnya memanfaatkan pustaka Aspose.Slides. SmartArt dalam presentasi dapat meningkatkan daya tarik visual dan kejelasan data Anda secara signifikan, sehingga penting untuk menguasai manipulasinya.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Pustaka Aspose.Slides diunduh dan disiapkan. Jika Anda belum melakukannya, unduh dari[Di Sini](https://releases.aspose.com/slides/java/).
3. Pemahaman dasar pemrograman Java.

## Paket Impor
Pertama, impor paket yang diperlukan:
```java
import com.aspose.slides.*;
```
Mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Inisialisasi Objek Presentasi
```java
Presentation presentation = new Presentation();
```
Buat objek presentasi baru.
## Langkah 2: Tambahkan SmartArt ke Slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Tambahkan SmartArt ke slide yang diinginkan dengan dimensi dan tipe tata letak tertentu.
## Langkah 3: Tetapkan Tata Letak Bagan Organisasi
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Tetapkan jenis tata letak bagan organisasi. Dalam contoh ini, kami menggunakan tata letak Gantung Kiri.
## Langkah 4: Simpan Presentasi
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Simpan presentasi dengan tata letak bagan yang terorganisir.

## Kesimpulan
Menguasai pengorganisasian tipe tata letak bagan di SmartArt menggunakan Java memberdayakan Anda untuk membuat presentasi yang menarik secara visual dengan mudah. Dengan Aspose.Slides, prosesnya menjadi efisien dan efisien, memungkinkan Anda fokus pada pembuatan konten yang berdampak.
## FAQ
### Apakah Aspose.Slides kompatibel dengan lingkungan pengembangan Java yang berbeda?
Ya, Aspose.Slides kompatibel dengan berbagai lingkungan pengembangan Java, memastikan fleksibilitas bagi pengembang.
### Bisakah saya mengkustomisasi tampilan elemen SmartArt menggunakan Aspose.Slides?
Tentu saja, Aspose.Slides menyediakan opsi penyesuaian yang luas untuk elemen SmartArt, memungkinkan Anda menyesuaikannya dengan kebutuhan spesifik Anda.
### Apakah Aspose.Slides menawarkan dokumentasi komprehensif untuk pengembang?
Ya, pengembang dapat merujuk ke dokumentasi terperinci yang disediakan oleh Aspose.Slides untuk Java, yang menawarkan wawasan tentang fungsi dan penggunaannya.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides?
Ya, Anda dapat mengakses Aspose.Slides versi uji coba gratis untuk menjelajahi fitur-fiturnya sebelum membuat keputusan pembelian.
### Di mana saya dapat mencari dukungan untuk pertanyaan terkait Aspose.Slides?
 Untuk bantuan atau pertanyaan apa pun mengenai Aspose.Slides, Anda dapat mengunjungi forum dukungan[Di Sini](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
