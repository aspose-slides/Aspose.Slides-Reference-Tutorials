---
date: '2026-01-17'
description: Pelajari cara menambahkan seri ke diagram dan menyesuaikan diagram kolom
  bertumpuk dalam presentasi .NET menggunakan Aspose.Slides untuk Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Tambahkan Seri ke Diagram dengan Aspose.Slides untuk Java di .NET
url: /id/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Menguasai Kustomisasi Diagram dalam Presentasi .NET Menggunakan Aspose.Slides untuk Java

## Pendahuluan
Dalam dunia presentasi berbasis data, diagram merupakan alat penting yang mengubah angka mentah menjadi cerita visual yang menarik. Ketika Anda perlu **add series to chart** secara programatis, terutama di dalam file presentasi .NET, tugas tersebut dapat terasa menakutkan. Untungnya, **Aspose.Slides for Java** menyediakan API yang kuat dan tidak bergantung pada bahasa yang memudahkan pembuatan dan kustomisasi diagram—bahkan ketika format target Anda adalah .NET PPTX.

Dalam tutorial ini Anda akan menemukan cara **add series to chart**, cara **how to add chart** tipe stacked column, dan cara menyempurnakan aspek visual seperti lebar celah. Pada akhirnya, Anda dapat menghasilkan slide dinamis yang kaya data, tampak rapi dan profesional.

**Apa yang Akan Anda Pelajari**
- Cara membuat presentasi kosong menggunakan Aspose.Slides  
- Cara **add stacked column chart** ke sebuah slide  
- Cara **add series to chart** dan mendefinisikan kategori  
- Cara mengisi data poin dan menyesuaikan pengaturan visual  

Mari siapkan lingkungan pengembangan Anda.

## Jawaban Cepat
- **Apa kelas utama untuk memulai sebuah presentasi?** `Presentation`  
- **Metode mana yang menambahkan diagram ke slide?** `slide.getShapes().addChart(...)`  
- **Bagaimana cara menambahkan seri baru?** `chart.getChartData().getSeries().add(...)`  
- **Apakah Anda dapat mengubah lebar celah antara batang?** Ya, dengan menggunakan `setGapWidth()` pada grup seri  
- **Apakah saya memerlukan lisensi untuk produksi?** Ya, lisensi Aspose.Slides for Java yang valid diperlukan  

## Apa itu “add series to chart”?
Menambahkan seri ke diagram berarti menyisipkan kumpulan data baru yang akan dirender diagram sebagai elemen visual terpisah (misalnya batang, garis, atau irisan baru). Setiap seri dapat memiliki nilai, warna, dan formatnya sendiri, memungkinkan Anda membandingkan beberapa kumpulan data berdampingan.

## Mengapa menggunakan Aspose.Slides untuk Java untuk memodifikasi presentasi .NET?
- **Cross‑platform**: Tulis kode Java sekali dan targetkan file PPTX yang digunakan oleh aplikasi .NET.  
- **No COM or Office dependencies**: Berfungsi di server, pipeline CI, dan kontainer.  
- **Rich chart API**: Mendukung lebih dari 50 tipe diagram, termasuk diagram kolom bertumpuk.  

## Prasyarat
1. Perpustakaan **Aspose.Slides for Java** (versi 25.4 atau lebih baru).  
2. Alat build Maven atau Gradle, atau unduhan JAR manual.  
3. Pengetahuan dasar Java dan pemahaman tentang struktur PPTX.  

## Menyiapkan Aspose.Slides untuk Java
### Instalasi Maven
Tambahkan dependensi berikut ke `pom.xml` Anda:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalasi Gradle
Sertakan baris ini dalam file `build.gradle` Anda:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduhan Langsung
Sebagai alternatif, unduh JAR terbaru dari halaman rilis resmi: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Perolehan Lisensi**  
Mulailah dengan percobaan gratis dengan mengunduh lisensi sementara dari [di sini](https://purchase.aspose.com/temporary-license/). Untuk penggunaan produksi, beli lisensi penuh untuk membuka semua fitur.

## Panduan Implementasi Langkah‑per‑Langkah
Di bawah setiap langkah Anda akan menemukan cuplikan kode singkat (tidak diubah dari tutorial asli) diikuti oleh penjelasan tentang apa yang dilakukannya.

### Langkah 1: Buat Presentasi Kosong
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*Kami memulai dengan file PPTX bersih, yang memberi kami kanvas untuk menambahkan diagram.*

### Langkah 2: Tambahkan Diagram Kolom Bertumpuk ke Slide
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Metode `addChart` membuat **add stacked column chart** dan menempatkannya di pojok kiri‑atas slide.*

### Langkah 3: Tambahkan Seri ke Diagram (Tujuan Utama)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Di sini kami **add series to chart** – setiap pemanggilan membuat seri data baru yang akan muncul sebagai grup kolom terpisah.*

### Langkah 4: Tambahkan Kategori ke Diagram
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Kategori berfungsi sebagai label sumbu X, memberikan makna pada setiap kolom.*

### Langkah 5: Isi Data Seri
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Data poin memberikan setiap seri nilai numeriknya, yang akan dirender diagram sebagai tinggi batang.*

### Langkah 6: Atur Lebar Celah untuk Grup Seri Diagram
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Menyesuaikan lebar celah meningkatkan keterbacaan, terutama ketika banyak kategori hadir.*

## Contoh Penggunaan Umum
- **Financial reporting** – bandingkan pendapatan kuartalan antar unit bisnis.  
- **Project dashboards** – tampilkan persentase penyelesaian tugas per tim.  
- **Marketing analytics** – visualisasikan kinerja kampanye berdampingan.  

## Tips Kinerja
- **Reuse the `Presentation` object** saat membuat beberapa diagram untuk mengurangi beban memori.  
- **Limit the number of data points** hanya pada yang diperlukan untuk cerita visual.  
- **Dispose of objects** (`presentation.dispose()`) setelah menyimpan untuk membebaskan sumber daya.  

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menambahkan tipe diagram lain selain stacked column?**  
A: Ya, Aspose.Slides mendukung line, pie, area, dan banyak tipe diagram lainnya.  

**Q: Apakah saya memerlukan lisensi terpisah untuk output .NET?**  
A: Tidak, lisensi Java yang sama berfungsi untuk semua format output, termasuk file PPTX .NET.  

**Q: Bagaimana cara mengubah palet warna diagram?**  
A: Gunakan `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` dan atur `Color` yang diinginkan.  

**Q: Apakah memungkinkan menambahkan label data secara programatis?**  
A: Tentu saja. Panggil `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` untuk menampilkan nilai.  

**Q: Bagaimana jika saya perlu memperbarui presentasi yang sudah ada?**  
A: Muat file dengan `new Presentation("existing.pptx")`, modifikasi diagram, dan simpan kembali.  

## Kesimpulan
Anda kini memiliki panduan lengkap, end‑to‑end tentang cara **add series to chart**, membuat **stacked column chart**, dan menyempurnakan tampilannya dalam presentasi .NET menggunakan Aspose.Slides untuk Java. Bereksperimenlah dengan berbagai tipe diagram, warna, dan sumber data untuk membangun laporan visual yang menarik dan memukau pemangku kepentingan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-17  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose