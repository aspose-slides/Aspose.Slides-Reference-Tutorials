---
date: '2026-02-17'
description: Pelajari cara menambahkan diagram lingkaran ke presentasi PowerPoint
  menggunakan Aspose.Slides for Java. Ikuti panduan langkah demi langkah ini untuk
  membuat dan menyesuaikan diagram lingkaran profesional.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Cara menambahkan diagram lingkaran di PowerPoint dengan Aspose.Slides untuk
  Java
url: /id/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Buat dan Sesuaikan Diagram Lingkaran di PowerPoint Menggunakan Aspose.Slides untuk Java

## Introduction

Apakah Anda kesulitan memvisualisasikan data secara efektif dalam presentasi PowerPoint Anda? **Menambahkan slide diagram lingkaran PowerPoint** dapat langsung mengubah angka mentah menjadi cerita visual yang jelas. Dengan Aspose.Slides untuk Java, Anda dapat secara programatis **menambahkan file diagram lingkaran PowerPoint**, memberi Anda kontrol penuh atas desain dan data tanpa harus membuka PowerPoint secara manual. Dalam tutorial ini kami akan membimbing Anda melalui seluruh proses—dari menyiapkan pustaka hingga menyesuaikan titik data individual—sehingga Anda dapat menghasilkan slide yang halus dan berbasis data dalam hitungan menit.

### Quick Answers
- **Perpustakaan apa yang saya butuhkan?** Aspose.Slides untuk Java (versi terbaru).  
- **Bisakah saya membuat diagram tanpa PowerPoint terpasang?** Ya, API berfungsi sepenuhnya offline.  
- **Versi Java mana yang diperlukan?** JDK 16 atau yang lebih baru disarankan.  
- **Bagaimana cara mengubah warna irisan?** Gunakan metode `setFillType` dan `setSolidFillColor` pada titik data.  
- **Apakah lisensi wajib?** Versi percobaan dapat digunakan untuk pengembangan; lisensi permanen menghilangkan batas evaluasi.

### What You’ll Learn
- Cara **menambahkan diagram lingkaran PowerPoint** secara programatis dengan Java.  
- Cara menyesuaikan ledakan irisan, warna, dan properti visual lainnya.  
- Praktik terbaik untuk manajemen sumber daya dan kinerja saat menangani presentasi besar.

## Why add pie chart PowerPoint using Aspose.Slides for Java?
Menyematkan diagram lingkaran langsung dari kode memungkinkan Anda menghasilkan laporan terkini, mengotomatisasi dasbor bulanan, atau membuat dek slide yang dipersonalisasi secara cepat. Ini menghilangkan kesalahan salin‑tempel manual, memastikan konsistensi antar presentasi, dan terintegrasi dengan mulus ke back‑end Java yang ada.

## Prerequisites

Sebelum memulai, pastikan Anda memiliki:

- **Pustaka Aspose.Slides untuk Java** – tutorial ini merujuk pada versi 25.4 (rilis terbaru pada saat penulisan).  
- Sebuah **Java Development Kit (JDK)** yang kompatibel – JDK 16+ lebih disarankan.  
- Pemahaman dasar tentang **Maven** atau **Gradle** untuk manajemen dependensi.  

## Setting Up Aspose.Slides for Java

Untuk memulai, sertakan pustaka Aspose.Slides dalam proyek Anda.

### Maven
Tambahkan dependensi ini ke file `pom.xml` Anda:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Sertakan yang berikut dalam file `build.gradle` Anda:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sebagai alternatif, unduh versi terbaru langsung dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensing
Untuk menggunakan Aspose.Slides tanpa batasan:

- Mulailah dengan **versi percobaan gratis** untuk mengevaluasi API.  
- Minta **lisensi sementara** untuk pengujian lanjutan di halaman [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Beli langganan penuh melalui [Purchase page](https://purchase.aspose.com/buy).

## How to add pie chart PowerPoint using Aspose.Slides for Java

Berikut adalah panduan langkah demi langkah yang menunjukkan cara membuat dan menyesuaikan diagram lingkaran.

### Step 1: Initialize the Presentation
Pertama, buat objek `Presentation` baru. Ini mewakili file PowerPoint kosong.
```java
Presentation pres = new Presentation();
```

### Step 2: Add the Pie Chart
Sisipkan diagram lingkaran ke slide pertama. Koordinat (50, 50) dan ukuran (600 × 400) cocok untuk slide standar 16:9.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Step 3: Save the Presentation
Simpan presentasi ke disk. Ganti `YOUR_OUTPUT_DIRECTORY` dengan folder tempat Anda ingin menyimpan file.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Step 4: Clean Up Resources
Dispose objek `Presentation` untuk membebaskan sumber daya native.
```java
if (pres != null) pres.dispose();
```

## Customizing Data Point Explosion and Color

Menyesuaikan irisan individual membuat diagram Anda lebih mudah dibaca, terutama ketika Anda ingin menyoroti nilai tertentu.

### Step 1: Load an Existing Presentation (or reuse the one you just created)
Muat presentasi yang sudah ada (atau gunakan kembali yang baru saja Anda buat).
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Step 2: Access the Chart and Target Data Point
Di sini kami mengambil titik data kedua (indeks 1) dari seri pertama.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Step 3: Apply Explosion and Color
Pisahkan irisan secara visual dan ubah warna isi menjadi biru.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Step 4: Save and Dispose
Simpan dan Dispose.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Practical Applications
- **Laporan Penjualan:** Sorot produk terlaris dengan irisan yang meledak.  
- **Analisis Anggaran:** Beri warna berbeda pada departemen untuk perbandingan visual cepat.  
- **Slide Edukasi:** Pecah konsep kompleks menjadi segmen diagram yang mudah dipahami.

## Performance Considerations
- **Dispose objek** segera untuk menghindari kebocoran memori, terutama saat menghasilkan banyak slide dalam loop.  
- **Pantau penggunaan heap** untuk presentasi besar; pertimbangkan streaming output dengan overload `Save` yang menerima `OutputStream`.  
- Tetap gunakan **JDK 16+** untuk memanfaatkan perbaikan garbage‑collection terbaru.

## Conclusion
Anda kini memiliki alur kerja lengkap dan siap produksi untuk **menambahkan file diagram lingkaran PowerPoint** menggunakan Aspose.Slides untuk Java. Bereksperimenlah dengan jarak ledakan, warna, dan set data yang berbeda untuk menyesuaikan merek Anda. Saat siap, jelajahi tipe diagram lain—batang, garis, atau sebar—untuk membangun dasbor analitik lengkap di dalam PowerPoint.

## FAQ Section
1. **Apa keuntungan utama menggunakan Aspose.Slides untuk Java?**  
   - Ini menyederhanakan pembuatan dan manipulasi file PowerPoint secara programatis, menawarkan beragam fitur.  
2. **Bisakah saya menyesuaikan tipe diagram lain dengan Aspose.Slides?**  
   - Tentu saja! Aspose.Slides mendukung berbagai tipe diagram seperti diagram batang, garis, dan sebar.  
3. **Bagaimana cara menangani banyak slide saat membuat diagram?**  
   - Akses setiap slide dengan indeks menggunakan metode `get_Item()` untuk menerapkan perubahan pada slide yang berbeda.  
4. **Bagaimana jika diagram lingkaran saya tidak tampil dengan benar setelah penyesuaian?**  
   - Verifikasi koordinat dan dimensi yang digunakan dalam `addChart()`, pastikan mereka sesuai dengan tata letak slide Anda.  
5. **Di mana saya dapat menemukan fitur lanjutan untuk Aspose.Slides?**  
   - Jelajahi [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) untuk mempelajari fungsionalitas dan opsi tambahan.

## Resources
- **Dokumentasi:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Unduh Pustaka:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Beli Lisensi:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Percobaan Gratis:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Lisensi Sementara:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Forum Dukungan:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}