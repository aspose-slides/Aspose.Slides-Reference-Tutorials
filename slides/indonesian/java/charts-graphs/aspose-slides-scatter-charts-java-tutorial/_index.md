---
date: '2026-02-24'
description: Pelajari cara menyesuaikan diagram sebar menggunakan Aspose.Slides untuk
  Java. Panduan ini memandu Anda melalui pembuatan, penataan, dan penyimpanan diagram
  sebar dinamis dalam presentasi Anda.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Sesuaikan Diagram Sebar Aspose di Java
url: /id/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

 we keep markdown formatting.

Let's construct final output.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Sesuaikan Diagram Sebar Aspose di Java

Dalam tutorial ini Anda akan belajar cara **customize scatter chart aspose** dengan pustaka Aspose.Slides for Java yang kuat. Kami akan membahas cara menyiapkan proyek Anda, membuat diagram sebar, menyesuaikan tipe seri dan penanda, dan akhirnya menyimpan presentasi. Pada akhir tutorial, Anda akan dapat menghasilkan diagram sebar berpenampilan profesional secara programatis dan menyesuaikan setiap detail visual agar sesuai dengan merek atau kebutuhan pelaporan Anda.

## Jawaban Cepat
- **Library apa yang saya butuhkan?** Aspose.Slides for Java (v25.4+).  
- **Versi Java mana yang didukung?** JDK 8 atau lebih tinggi.  
- **Bisakah saya mengubah bentuk penanda?** Ya – gunakan `MarkerStyleType` untuk memilih bintang, lingkaran, dll.  
- **Bagaimana cara menyimpan file?** Panggil `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Apakah lisensi diperlukan?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.

## Apa itu “customize scatter chart aspose”?
Menyesuaikan diagram sebar dengan Aspose berarti mendefinisikan data, tampilan, dan perilaku diagram secara programatis—semua mulai dari koordinat titik hingga simbol penanda—tanpa membuka PowerPoint secara manual. Pendekatan ini ideal untuk pelaporan otomatis, presentasi berbasis data, atau skenario apa pun yang memerlukan visualisasi berulang dengan kualitas tinggi.

## Mengapa menyesuaikan diagram sebar dengan Aspose.Slides?
- **Kontrol penuh** – ubah tipe seri, gaya penanda, warna, dan lainnya melalui kode Java.  
- **Otomatisasi** – hasilkan puluhan diagram secara langsung untuk dasbor atau laporan batch.  
- **Lintas‑platform** – bekerja pada sistem operasi apa pun yang mendukung Java, tanpa memerlukan instalasi Office.  
- **Kinerja** – API ringan yang menangani set data besar secara efisien.

## Prasyarat

Untuk mengikuti tutorial ini, pastikan Anda memiliki:

- **Aspose.Slides for Java** (v25.4 atau lebih baru).  
- **Java Development Kit (JDK)** 8 + terpasang.  
- Maven atau Gradle untuk manajemen dependensi (atau Anda dapat mengunduh JAR secara manual).  
- Pengetahuan dasar Java dan familiaritas dengan alat build pilihan Anda.

## Menyiapkan Aspose.Slides untuk Java

Integrasikan pustaka ke dalam proyek Anda menggunakan salah satu metode di bawah ini.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Atau dapatkan rilis terbaru dari [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Perolehan Lisensi
- **Free Trial** – evaluasi 30 hari.  
- **Temporary License** – periode pengujian yang diperpanjang.  
- **Full License** – penggunaan produksi dengan dukungan premium.

## Panduan Langkah‑per‑Langkah untuk Menyesuaikan Scatter Chart Aspose

### 1️⃣ Siapkan folder untuk file presentasi Anda
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Mengapa ini penting:* Memastikan folder output ada mencegah `FileNotFoundException` saat Anda menyimpan PPTX nanti.

### 2️⃣ Buat presentasi baru dan ambil slide pertama
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Sebuah `Presentation` baru memberi Anda kanvas bersih; slide pertama adalah tempat kami akan menempatkan diagram.

### 3️⃣ Tambahkan diagram sebar dengan garis halus
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` membuat diagram sebar dengan garis halus, sempurna untuk visualisasi tren.

### 4️⃣ Bersihkan semua seri default dan tambahkan milik Anda
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Menghapus seri default memberi Anda kontrol penuh atas data yang ditampilkan.

### 5️⃣ Isi seri pertama dengan titik data
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` mengambil sel nilai X dan sel nilai Y, membangun plot sebar titik demi titik.

### 6️⃣ Sesuaikan tipe seri dan tampilan penanda
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Di sini kami **customize the scatter chart aspose** dengan beralih ke garis lurus, memperbesar penanda, dan memilih simbol yang berbeda (bintang vs. lingkaran) untuk kejelasan visual.

### 7️⃣ Simpan presentasi
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Menyimpan sebagai `Pptx` mempertahankan semua penyesuaian diagram dan membuat file siap untuk dibagikan atau diedit lebih lanjut.

## Contoh Penggunaan Umum untuk Diagram Sebar yang Disesuaikan
- **Dasbor keuangan** – plot harga saham vs. volume.  
- **Penelitian ilmiah** – menampilkan pengukuran eksperimental dengan penanda kesalahan.  
- **Manajemen proyek** – membandingkan upaya yang direncanakan vs. aktual pada setiap tugas.  

## Tips Kinerja
- Buang objek `Presentation` (`pres.dispose()`) setelah menyimpan untuk membebaskan sumber daya native.  
- Untuk set data besar, isi workbook terlebih dahulu lalu hubungkan seri untuk menghindari penyegaran UI berulang.  
- Gunakan kembali satu instance `IChartDataWorkbook` saat menambahkan banyak seri.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah warna penanda?
Gunakan `series.getMarker().getFillFormat().setFillColor(Color)` dimana `Color` adalah instance dari `java.awt.Color` (misalnya, `Color.RED`).

### Bisakah saya menambahkan lebih dari dua seri ke diagram sebar?
Tentu saja. Ulangi pemanggilan `chart.getChartData().getSeries().add(...)` untuk setiap seri tambahan dan isi titik datanya sesuai.

### Apakah memungkinkan menetapkan legenda khusus untuk setiap seri?
Ya. Setelah membuat seri, panggil `series.getLegend().setText("Your Legend Text")` untuk mengganti nama default.

### Bagaimana saya dapat mengekspor diagram sebagai gambar alih-alih PPTX?
Panggil `chart.getImage().save("chart.png", ImageFormat.Png)` setelah mengonfigurasi diagram. Ini memberi Anda file PNG terpisah.

### Bagaimana jika saya perlu memberi animasi pada titik sebar?
Aspose.Slides mendukung efek animasi. Gunakan `chart.getTimeline().getMainSequence().addEffect(...)` untuk menambahkan animasi masuk atau penekanan pada diagram atau seri individu.

---

**Terakhir Diperbarui:** 2026-02-24  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}