---
date: '2026-08-27'
description: Pelajari cara menghapus titik data diagram di PowerPoint menggunakan
  Aspose.Slides for Java. Tutorial langkah demi langkah ini menunjukkan cara menghapus
  nilai diagram secara programatis, praktik terbaik, dan penanganan seri yang efisien.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: Pelajari cara menghapus titik data diagram di PowerPoint menggunakan
  Aspose.Slides for Java. Ikuti petunjuk langkah demi langkah untuk mereset diagram
  secara programatis dengan efisien.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: Cara menghapus titik data diagram di PowerPoint dengan Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'Cara menghapus titik data pada diagram PowerPoint menggunakan Aspose.Slides
  for Java: panduan lengkap'
url: /id/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menghapus titik data pada diagram PowerPoint menggunakan Aspose.Slides untuk Java

## Pendahuluan

Dalam banyak alur kerja pelaporan Anda perlu **mengatur ulang diagram** tanpa membuat ulang tata letaknya. Baik Anda memperbarui dasbor, mengirimkan templat, atau mengotomatisasi laporan malam, mengetahui **cara menghapus titik data diagram** menghemat waktu dan mengurangi kesalahan. Tutorial ini menunjukkan cara menggunakan **Aspose.Slides for Java** untuk secara programatis menghapus titik tertentu atau seluruh seri, sambil mempertahankan gaya visual tetap.

**Apa yang akan Anda pelajari**
- Bagaimana Aspose.Slides memungkinkan Anda memanipulasi diagram PowerPoint dari Java.  
- Instruksi langkah demi langkah untuk menghapus titik data diagram dalam sebuah seri.  
- Tips praktik terbaik untuk kinerja dan lisensi.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Slides for Java (v25.4+).  
- **Metode mana yang benar‑benar menghapus titik data?** Menetapkan nilai sel X dan Y ke `null`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya – lisensi komersial menghapus batas percobaan.  
- **Apakah Java 16 didukung?** Tentu; perpustakaan ini bekerja dengan JDK 16 dan yang lebih baru.  
- **Bisakah saya menargetkan hanya satu seri?** Ya – iterasi seri spesifik yang ingin Anda hapus.

## Apa itu Aspose.Slides untuk Java?

Aspose.Slides untuk Java adalah API lengkap yang memungkinkan pembuatan, penyuntingan, dan konversi file PowerPoint tanpa Microsoft Office. Ia mendukung lebih dari 70 jenis diagram, lebih dari 150 format file, dan dapat memproses presentasi hingga 500 MB tanpa memuat seluruh file ke memori.

## Mengapa menghapus titik data diagram?

Menghapus titik data diagram memungkinkan Anda mempertahankan tata letak diagram yang ada—seperti warna, legenda, pengaturan sumbu, dan penanda—sementara mengganti nilai numerik yang mendasarinya. Pendekatan ini berguna ketika Anda perlu memperbarui diagram dengan data baru, menyediakan templat dengan placeholder kosong, atau menghasilkan dasbor dinamis yang sering berubah tanpa membangun ulang desain visual.

- Menyegarkan diagram dengan dataset baru sambil mempertahankan warna, legenda, dan pengaturan sumbu.  
- Mengirimkan templat yang berisi diagram kosong siap untuk input pengguna.  
- Membangun dasbor dinamis di mana data berubah secara sering.

## Cara menghapus titik data diagram di PowerPoint menggunakan Aspose.Slides untuk Java

Muat presentasi Anda, temukan diagramnya, dan atur setiap sel X dan Y titik data ke `null`. Operasi ini menghapus nilai numerik tetapi membiarkan seri, penanda, dan pemformatan tidak tersentuh. Seluruh proses biasanya selesai dalam kurang dari satu detik untuk PPTX standar dengan 10 slide.

### Jawaban Langsung
Untuk menghapus titik data diagram, buka PPTX dengan `new Presentation("input.pptx")`, ambil objek `IChart` target, iterasi melalui `IChartSeries` yang diinginkan, dan panggil `dataPoint.getXValue().setValue(null)` serta `dataPoint.getYValue().setValue(null)` untuk setiap titik. Akhirnya, simpan presentasi dengan `pres.save("output.pptx", SaveFormat.Pptx)`. Pendekatan ini secara programatis menghapus data sambil mempertahankan desain visual diagram.

### Penjelasan istilah
- `Presentation` adalah objek tingkat‑atas Aspose.Slides yang mewakili file PowerPoint dalam memori.  
- `IChart` adalah antarmuka yang memberikan akses ke seri, sumbu, dan pemformatan bentuk diagram.  
- `IChartSeries` mewakili satu seri dalam diagram dan berisi koleksi objek `IDataPoint`.  
- `IDataPoint` menyimpan nilai X dan Y individu untuk sebuah titik pada diagram.

### Implementasi langkah demi langkah

1. **Muat presentasi** – buat instance `Presentation` yang menunjuk ke file sumber Anda.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **Akses slide dan diagram** – ambil slide (biasanya indeks 0) dan cast bentuk pertama ke `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **Iterasi melalui seri target** – pilih seri yang ingin Anda hapus (misalnya, `chart.getChartData().getSeries().get_Item(0)`) dan lakukan loop pada titik datanya, mengatur nilai sel X dan Y menjadi `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **Simpan presentasi yang dimodifikasi** – tulis perubahan ke file baru atau timpa file asli.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## Menyiapkan Aspose.Slides untuk Java

### Instalasi Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Instalasi Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### Unduhan Langsung

Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Perolehan Lisensi

To use Aspose.Slides beyond its trial limitations:
- Dapatkan lisensi **percobaan gratis**.  
- Ajukan **lisensi sementara** untuk evaluasi.  
- Beli **lisensi komersial** untuk penggunaan produksi.

#### Inisialisasi dan pengaturan dasar

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## Aplikasi praktis

Clearing chart data points is useful in many real‑world scenarios:

1. **Alur penyegaran data** – ganti angka usang dengan analitik terbaru tanpa membangun ulang tata letak diagram.  
2. **Distribusi templat** – sediakan templat PowerPoint yang berisi diagram kosong siap untuk input pengguna.  
3. **Dasbor dinamis** – hasilkan presentasi malam yang menarik data dari API, menghapus nilai lama terlebih dahulu.  
4. **Pekerjaan pelaporan otomatis** – integrasikan logika penghapusan ke dalam pipeline CI/CD untuk pembuatan laporan otomatis.

## Pertimbangan kinerja

- **Buang objek**: Panggil `pres.dispose()` setelah menyimpan untuk melepaskan sumber daya native.  
- **Pemrosesan batch**: Gunakan kembali satu instance `License` pada banyak file untuk meminimalkan beban.  
- **Penyesuaian JVM**: Tingkatkan ukuran heap (`-Xmx2g` atau lebih tinggi) saat menangani presentasi lebih besar dari 200 MB.  
- **Mode efisien memori**: Aspose.Slides dapat men-stream file PPTX besar, memungkinkan pemrosesan hingga 10 000 slide tanpa pemuatan penuh ke memori.

## Pertanyaan yang sering diajukan

**Q: Apakah saya memerlukan lisensi untuk build pengembangan?**  
A: Lisensi percobaan gratis sudah cukup untuk pengembangan dan pengujian. Lisensi komersial diperlukan untuk penerapan produksi.

**Q: Apakah Aspose.Slides untuk Java mendukung fitur PowerPoint 2016/2019?**  
A: Ya, perpustakaan ini sepenuhnya mendukung fitur PPTX modern, termasuk jenis diagram lanjutan dan SmartArt.

**Q: Bisakah saya menghapus titik data pada diagram yang menggunakan sumbu sekunder?**  
A: Tentu – cukup referensikan seri yang termasuk dalam sumbu sekunder dan atur titik datanya menjadi `null` seperti dijelaskan di atas.

**Q: Apakah memungkinkan menghapus hanya nilai Y sambil mempertahankan label X?**  
A: Ya. Panggil `dataPoint.getYValue().setValue(null)` dan biarkan sel X tidak diubah.

**Q: Bagaimana saya dapat mengotomatisasi ini untuk banyak presentasi?**  
A: Bungkus kode penghapusan dalam loop yang mengiterasi direktori file PPTX, menerapkan logika yang sama pada setiap file.

## Sumber Daya

- [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/java/)
- [Unduh Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/)
- [Beli Lisensi](https://purchase.aspose.com/buy)
- [Versi Percobaan Gratis](https://releases.aspose.com/slides/java/)
- [Aplikasi Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- [Forum Komunitas Aspose](https://forum.aspose.com/c/slides/11)

Dengan sumber daya ini Anda siap mulai menghapus titik data diagram dalam aplikasi Java Anda. Selamat coding!

---

**Last Updated:** 2026-08-27  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose

## Tutorial Terkait

- [Cara Mengedit Data Diagram PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Komprehensif](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Cara Menambahkan Diagram ke PowerPoint Menggunakan Aspose.Slides untuk Java: Panduan Langkah‑per‑Langkah](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Menghapus Titik Data Seri Diagram Spesifik dalam Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}