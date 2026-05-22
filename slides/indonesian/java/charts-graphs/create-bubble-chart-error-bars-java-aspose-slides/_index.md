---
date: '2026-03-04'
description: Pelajari cara menambahkan error bar khusus ke diagram gelembung dengan
  Aspose.Slides untuk Java. Panduan ini mencakup pembuatan diagram, mengonfigurasi
  error bar per titik, dan menyimpan presentasi.
keywords:
- Bubble Chart Java
- Custom Error Bars Aspose.Slides
- Java Data Visualization
title: Cara Menambahkan Batang Kesalahan Kustom ke Diagram Gelembung di Java Menggunakan
  Aspose.Slides
url: /id/java/charts-graphs/create-bubble-chart-error-bars-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menambahkan Error Bars Kustom ke Bubble Chart di Java Menggunakan Aspose.Slides

Membuat presentasi yang jelas dan berbasis data sering kali berarti melampaui grafik sederhana. Dengan mempelajari **cara menambahkan error bars kustom** ke bubble chart, Anda memberi audiens wawasan tentang variabilitas dan tingkat kepercayaan untuk setiap titik data. Dalam tutorial ini Anda akan melihat cara menyiapkan proyek Java dengan Aspose.Slides, menambahkan bubble chart ke slide, mengonfigurasi error bars per titik, dan akhirnya menyimpan hasilnya sebagai file PowerPoint.

## Jawaban Cepat
- **Perpustakaan apa yang diperlukan?** Aspose.Slides for Java (versi terbaru).  
- **Tipe chart mana yang mendukung error bars kustom?** Bubble chart (`ChartType.Bubble`).  
- **Apakah error bars dapat diatur per titik data?** Ya – gunakan `ErrorBarsCustomValues` untuk nilai plus/minus X/Y.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengujian; lisensi penuh menghapus batas evaluasi.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk contoh dasar.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki:

- **Java Development Kit (JDK):** Versi 8 atau lebih tinggi.  
- **Aspose.Slides for Java:** Tambahkan pustaka ke proyek Anda (lihat cuplikan Maven/Gradle di bawah).  
- **IDE:** IntelliJ IDEA, Eclipse, NetBeans, atau editor apa pun yang Anda sukai.

### Perpustakaan dan Dependensi yang Diperlukan

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Anda juga dapat mengunduh JAR terbaru dari halaman rilis resmi: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Perolehan Lisensi

- Mulailah dengan percobaan gratis untuk menjelajahi semua fitur.  
- Minta lisensi sementara untuk pengujian tanpa batas.  
- Beli lisensi runtime penuh untuk penggunaan produksi.

## Menyiapkan Aspose.Slides untuk Java

Setelah pustaka berada di classpath Anda, inisialisasi objek presentasi. Blok ini membuat kanvas bersih untuk chart.

```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Panduan Implementasi

### Fitur 1: Tambahkan Chart ke Slide dan Buat Bubble Chart

**Mengapa menambahkan chart ke slide?**  
Menyematkan chart langsung ke slide memungkinkan Anda menjaga konteks visual bersama teks atau gambar di sekitarnya, menjadikan presentasi lebih kohesif.

#### Langkah 1: Impor Kelas yang Diperlukan
```java
import com.aspose.slides.*;
```

#### Langkah 2: Tambahkan Bubble Chart ke Slide Pertama
```java
// Access the first slide
ISlide slide = presentation.getSlides().get_Item(0);

// Create a bubble chart on the slide
IChart chart = slide.getShapes().addChart(
    ChartType.Bubble, 50, 50, 400, 300, true);
```
- `ChartType.Bubble` memberi tahu Aspose bahwa kami menginginkan bubble chart.  
- Koordinat `(50, 50)` dan ukuran `(400, 300)` menempatkan chart dengan baik pada slide.

### Fitur 2: Konfigurasikan Error Bars

Error bars memberikan penonton petunjuk visual tentang keandalan setiap titik. Kami akan membuatnya terlihat dan mengaturnya untuk menggunakan nilai kustom.

#### Langkah 3: Akses Seri Pertama
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Langkah 4: Aktifkan dan Atur Error Bars Kustom
```java
// Accessing error bar formats
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();

// Making error bars visible
errBarX.setVisible(true);
errBarY.setVisible(true);

// Setting custom value types for more detailed control
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

### Fitur 3: Atur Error Bars untuk Titik Data (Error Bars Per Point)

Sekarang kami akan menetapkan nilai margin error unik untuk setiap bubble, memperlihatkan **error bars per point**.

#### Langkah 5: Konfigurasikan Koleksi Data Point
```java
IChartDataPointCollection points = series.getDataPoints();

// Configuring custom values for error bars
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Loop through each data point
for (int i = 0; i < points.size(); i++) {
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```
*Menggunakan nilai kustom memungkinkan Anda mendefinisikan rentang error secara tepat untuk setiap bubble, yang penting untuk analisis ilmiah atau keuangan.*

### Fitur 4: Simpan Presentasi

```java
String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";

// Saving the presentation
presentation.save(YOUR_DOCUMENT_DIRECTORY + "/ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

## Aplikasi Praktis

Menambahkan error bars kustom ke bubble chart sangat berguna dalam banyak skenario dunia nyata:

1. **Penelitian Ilmiah:** Menampilkan ketidakpastian pengukuran untuk setiap hasil eksperimen.  
2. **Analitik Bisnis:** Memvisualisasikan rentang perkiraan untuk penjualan atau pangsa pasar.  
3. **Pendidikan:** Menunjukkan konsep statistik seperti interval kepercayaan.

## Pertimbangan Kinerja

- Hapus objek `Presentation` segera untuk membebaskan sumber daya native.  
- Batasi jumlah data point jika Anda menghasilkan chart secara massal; dataset yang sangat besar dapat meningkatkan waktu render.  
- Gunakan kembali objek chart saat membuat beberapa slide untuk mengurangi overhead.

## Masalah Umum dan Solusinya

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **ErrorBarsCustomValues returns `null`** | Seri belum memiliki data point. | Tambahkan data point terlebih dahulu atau pastikan seri terisi sebelum mengonfigurasi error bars. |
| **Chart not visible on slide** | Dimensi chart ditempatkan di luar batas slide. | Sesuaikan koordinat X/Y serta lebar/tinggi agar sesuai dengan ukuran slide. |
| **License exception** | Menggunakan versi percobaan tanpa lisensi yang valid. | Terapkan lisensi sementara atau penuh sebelum menyimpan presentasi. |

## Pertanyaan yang Sering Diajukan

**Q: Apa itu Aspose.Slides untuk Java?**  
A: Ini adalah API yang kuat yang memungkinkan Anda membuat, memodifikasi, dan mengonversi file PowerPoint secara programatis tanpa Microsoft Office.

**Q: Bisakah saya menggunakan Aspose.Slides tanpa lisensi?**  
A: Ya, percobaan gratis dapat digunakan untuk pengembangan dan pengujian, namun akan menambahkan watermark evaluasi dan membatasi beberapa fitur.

**Q: Bagaimana cara memperbarui ke versi terbaru Aspose.Slides?**  
A: Periksa halaman rilis resmi [Aspose releases page](https://releases.aspose.com/slides/java/) dan perbarui dependensi Maven/Gradle Anda sesuai.

**Q: Mengapa menambahkan error bars kustom ke bubble chart?**  
A: Mereka menyampaikan variabilitas atau kepercayaan untuk setiap titik data, mengubah visualisasi scatter sederhana menjadi cerita yang lebih kaya dan informatif.

**Q: Bisakah saya menyesuaikan tipe chart lain dengan error bars?**  
A: Tentu saja. Aspose.Slides mendukung error bars untuk line, bar, column, dan banyak tipe chart lainnya.

---

**Terakhir Diperbarui:** 2026-03-04  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}