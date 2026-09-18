---
date: '2026-09-17'
description: Pelajari cara membuat bubble chart PowerPoint menggunakan Aspose.Slides
  for Java. Panduan ini menunjukkan cara menambahkan chart ke slide, mengonfigurasi
  bubble size, dan menyimpan PPTX secara efisien.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Pelajari cara membuat bubble chart PowerPoint menggunakan Aspose.Slides
  for Java. Tutorial ini menjelaskan cara menambahkan chart ke slide, menyesuaikan
  bubble sizes, dan menyimpan presentation secara efisien.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Buat bubble chart PowerPoint dengan Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Buat bubble chart PowerPoint dengan Aspose.Slides for Java
url: /id/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat diagram gelembung PowerPoint dengan Aspose.Slides untuk Java

## Pendahuluan
Jika Anda perlu **membuat diagram gelembung PowerPoint** secara programatis, Aspose.Slides untuk Java memberikan API bersih sisi‑server yang berfungsi tanpa Microsoft Office. Dalam tutorial ini Anda akan belajar cara menambahkan diagram ke slide, mengontrol ukuran gelembung, dan menyimpan PPTX akhir sambil mengelola sumber daya secara efisien. Langkah‑langkahnya diuraikan sehingga Anda dapat menyalin‑tempel kode ke proyek Java mana pun dan melihat hasilnya secara instan.

## Jawaban Cepat
- **Library apa yang saya perlukan?** Aspose.Slides for Java
- **Versi Java mana yang diperlukan?** JDK 16 atau lebih tinggi
- **Bagaimana cara menambahkan diagram gelembung?** Panggil `addChart(ChartType.Bubble, …)` pada slide
- **Bisakah saya mengubah ukuran gelembung?** Ya, via `setBubbleSizeScale()`
- **Bagaimana cara menyimpan file?** Gunakan `pres.save("Result.pptx", SaveFormat.Pptx)`

## Apa itu membuat diagram gelembung PowerPoint?
Membuat diagram gelembung di PowerPoint berarti secara programatis menghasilkan diagram di mana setiap titik data direpresentasikan oleh sebuah gelembung yang posisi X‑nya, posisi Y‑nya, dan ukurannya mengkodekan tiga dimensi data. Aspose.Slides untuk Java menangani rendering, sehingga Anda tidak memerlukan PowerPoint terpasang.

## Mengapa menggunakan Aspose.Slides untuk Java?
Aspose.Slides mendukung **50+ jenis diagram**, dapat memproses presentasi hingga **2 GB** tanpa memuat seluruh file ke memori, dan berjalan di platform apa pun yang mendukung Java 16+. Kemampuan terukur ini menjadikannya pilihan yang dapat diandalkan untuk pelaporan tingkat perusahaan.

## Prasyarat
- **Java Development Kit** 16 atau yang lebih baru terpasang.
- **Aspose.Slides for Java** library (tambahkan via Maven, Gradle, atau unduhan JAR langsung).
- Familiaritas dasar dengan sintaks Java dan pemrograman berorientasi objek.

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides, sertakan library dalam sistem build Anda.

### Maven
Tambahkan dependensi berikut ke `pom.xml` Anda:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Sertakan ini dalam `build.gradle` Anda:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Anda juga dapat memperoleh JAR terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Akuisisi Lisensi
- **Free trial** – jelajahi semua fitur tanpa biaya.  
- **Temporary license** – evaluasi diperpanjang untuk proyek yang lebih besar.  
- **Full license** – diperlukan untuk penerapan produksi.

### Inisialisasi dan Pengaturan Dasar
Kelas `Presentation` adalah titik masuk untuk membuat atau memuat file PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Panduan Implementasi
Berikut adalah panduan langkah‑demi‑langkah untuk membuat diagram gelembung dan mengelola sumber daya.

## Cara membuat diagram gelembung PowerPoint
Di bagian ini Anda akan mempelajari urutan panggilan API yang tepat untuk menghasilkan diagram gelembung, mengonfigurasi properti visualnya, dan menyimpan hasilnya sebagai file PPTX. Pendekatan ini bekerja untuk proyek Java apa pun yang menyertakan Aspose.Slides dan mengikuti penanganan sumber daya praktik terbaik.

Load the presentation, add a bubble chart, configure its appearance, and save the file.

### Jawaban Langsung
Buat `Presentation` baru, panggil `addChart(ChartType.Bubble, …)` pada slide yang diinginkan, sesuaikan skala ukuran gelembung dengan `setBubbleSizeScale(150)`, kemudian simpan menggunakan `pres.save("Result.pptx", SaveFormat.Pptx)`. Urutan ini menambahkan diagram gelembung yang berfungsi penuh hanya dalam beberapa baris Java.

- **`ChartType.Bubble`** mewakili jenis diagram gelembung.  
- **`addChart`** menyisipkan diagram baru dengan tipe yang ditentukan ke slide.  
- **`setBubbleSizeScale`** menyesuaikan ukuran keseluruhan gelembung dalam diagram.  
- **`SaveFormat.Pptx`** menentukan format file PPTX untuk penyimpanan.  

#### Implementasi Langkah‑demi‑Langkah
**1. Inisialisasi presentasi** – buat instance objek `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Add bubble chart** – insert the chart at the chosen coordinates.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` memberi tahu Aspose.Slides untuk membuat diagram gelembung.  
- Parameter numerik menentukan posisi X/Y serta lebar/tinggi dalam poin.

**3. Configure bubble size scale** – enlarge bubbles for better visual impact.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Mengatur skala ke **150 %** membuat setiap gelembung 1,5 × lebih besar daripada default.

**4. Save presentation** – write the PPTX to disk.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Tips Pemecahan Masalah
- Verifikasi izin menulis untuk folder output.  
- Pastikan JAR Aspose.Slides cocok dengan versi JDK yang Anda gunakan.

## Cara mengelola sumber daya PowerPoint secara efektif
Penanganan sumber daya yang efektif mencegah kebocoran memori dan menjaga jejak JVM tetap rendah, terutama saat memproses dek besar atau berjalan di lingkungan server. Ikuti pola di bawah ini untuk memastikan sumber daya native dibebaskan bahkan jika terjadi pengecualian.

Penanganan sumber daya yang efisien mencegah kebocoran memori, terutama saat memproses dek besar.

### Jawaban Langsung
Setelah Anda selesai bekerja dengan `Presentation`, selalu panggil `pres.dispose()` di dalam blok `try‑finally`; ini membebaskan sumber daya native dan memungkinkan JVM mengambil kembali memori dengan cepat.

- **`pres.dispose()`** membebaskan sumber daya native yang digunakan oleh presentasi.

**1. Buat dan modifikasi** – bekerja dengan presentasi sesuai kebutuhan.  
```java
Presentation pres = new Presentation();
```

**2. Buang sumber daya** – bebaskan memori setelah pemrosesan selesai.  
```java
if (pres != null) pres.dispose();
```

## Aplikasi Praktis
Diagram gelembung unggul dalam skenario di mana tiga dimensi data perlu divisualisasikan secara bersamaan:

1. **Market analysis** – ukuran gelembung mewakili pendapatan sementara sumbu X/Y menunjukkan pertumbuhan dan pangsa pasar.  
2. **Performance metrics** – bandingkan produktivitas karyawan (X), kepuasan (Y), dan dampak (ukuran).  
3. **Geographical data** – plot kota dengan populasi yang dikodekan dalam ukuran gelembung.  
4. **Project management** – visualisasikan garis waktu (X), biaya (Y), dan risiko (ukuran) pada satu slide.

## Pertimbangan Kinerja
- **Penggunaan sumber daya** – buang presentasi segera untuk menjaga penggunaan heap tetap rendah.  
- **Manajemen memori Java** – bungkus pekerjaan presentasi dalam `try‑finally` untuk menjamin pembuangan bahkan pada pengecualian.  
- **Tetap terbaru** – tingkatkan ke versi Aspose.Slides terbaru untuk mendapatkan manfaat dari optimasi kinerja dan perbaikan bug.

## Pertanyaan yang Sering Diajukan

**Q: Apa itu Aspose.Slides untuk Java?**  
A: Aspose.Slides untuk Java adalah library mandiri yang memungkinkan Anda membuat, mengedit, dan mengonversi file PowerPoint tanpa memerlukan Microsoft Office.

**Q: Bagaimana cara mengintegrasikan Aspose.Slides dengan proyek Java saya yang ada?**  
A: Tambahkan dependensi Maven atau Gradle yang ditunjukkan sebelumnya, atau letakkan JAR ke classpath Anda, kemudian impor `com.aspose.slides.*`.

**Q: Bisakah saya menggunakan Aspose.Slides untuk presentasi besar?**  
A: Ya, library ini secara efisien menangani presentasi hingga **2 GB** dan mendukung streaming untuk menghindari memuat seluruh file ke memori.

**Q: Jenis diagram apa yang tersedia selain diagram gelembung?**  
A: Lebih dari **50 jenis diagram** didukung, termasuk diagram batang, garis, pai, radar, dan waterfall.

**Q: Apakah ada dukungan bawaan untuk menata elemen diagram?**  
A: Tentu saja. Anda dapat menyesuaikan warna, font, batas, dan label data melalui objek `ChartSeries` dan `ChartTitle` pada diagram.

## Sumber Daya
- **Documentation**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Terakhir Diperbarui:** 2026-09-17  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑per‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java membuat diagram PowerPoint menggunakan Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Buat Diagram PowerPoint Java – Simpan Presentasi dengan Diagram Menggunakan Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}