---
"description": "Kuasai pengorganisasian jenis tata letak bagan di SmartArt menggunakan Java dengan Aspose.Slides, tingkatkan visual presentasi dengan mudah."
"linktitle": "Mengatur Jenis Tata Letak Bagan di SmartArt menggunakan Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Jenis Tata Letak Bagan di SmartArt menggunakan Java"
"url": "/id/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Jenis Tata Letak Bagan di SmartArt menggunakan Java

## Perkenalan
Dalam tutorial ini, kita akan membahas proses pengaturan jenis tata letak bagan di SmartArt menggunakan Java, khususnya memanfaatkan pustaka Aspose.Slides. SmartArt dalam presentasi dapat meningkatkan daya tarik visual dan kejelasan data Anda, sehingga penting untuk menguasai manipulasinya.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) terinstal di sistem Anda.
2. Pustaka Aspose.Slides telah diunduh dan disiapkan. Jika Anda belum melakukannya, unduh dari [Di Sini](https://releases.aspose.com/slides/java/).
3. Pemahaman dasar tentang pemrograman Java.

## Paket Impor
Pertama, impor paket yang diperlukan:
```java
import com.aspose.slides.*;
```
Mari kita uraikan contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Inisialisasi Objek Presentasi
```java
Presentation presentation = new Presentation();
```
Membuat objek presentasi baru.
## Langkah 2: Tambahkan SmartArt ke Slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Tambahkan SmartArt ke slide yang diinginkan dengan dimensi dan jenis tata letak yang ditentukan.
## Langkah 3: Mengatur Tata Letak Bagan Organisasi
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Tetapkan jenis tata letak bagan organisasi. Dalam contoh ini, kami menggunakan tata letak Left Hanging.
## Langkah 4: Simpan Presentasi
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Simpan presentasi dengan tata letak bagan yang terorganisasi.

## Kesimpulan
Menguasai pengaturan jenis tata letak bagan di SmartArt menggunakan Java memungkinkan Anda membuat presentasi yang menarik secara visual dengan mudah. Dengan Aspose.Slides, prosesnya menjadi lebih mudah dan efisien, sehingga Anda dapat fokus pada pembuatan konten yang berdampak.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Slides kompatibel dengan berbagai lingkungan pengembangan Java?
Ya, Aspose.Slides kompatibel dengan berbagai lingkungan pengembangan Java, memastikan fleksibilitas bagi pengembang.
### Bisakah saya menyesuaikan tampilan elemen SmartArt menggunakan Aspose.Slides?
Tentu saja, Aspose.Slides menyediakan opsi penyesuaian yang luas untuk elemen SmartArt, yang memungkinkan Anda menyesuaikannya dengan kebutuhan spesifik Anda.
### Apakah Aspose.Slides menawarkan dokumentasi yang komprehensif untuk pengembang?
Ya, pengembang dapat merujuk ke dokumentasi terperinci yang disediakan oleh Aspose.Slides untuk Java, yang menawarkan wawasan tentang fungsionalitas dan penggunaannya.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides?
Ya, Anda dapat mengakses versi uji coba gratis Aspose.Slides untuk menjelajahi fitur-fiturnya sebelum membuat keputusan pembelian.
### Di mana saya dapat mencari dukungan untuk pertanyaan terkait Aspose.Slides?
Untuk bantuan atau pertanyaan apa pun mengenai Aspose.Slides, Anda dapat mengunjungi forum dukungan [Di Sini](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}