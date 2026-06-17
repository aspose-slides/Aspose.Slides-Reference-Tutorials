---
date: '2026-06-03'
description: Pelajari cara menambahkan diagram dengan aspose slides maven dependency,
  mengonfigurasi label data, dan menghasilkan diagram dinamis dalam presentasi Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Tambahkan dan Konfigurasikan Diagram dalam
  Presentasi Menggunakan Aspose.Slides untuk Java'
url: /id/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Tambahkan dan Konfigurasikan Diagram dalam Presentasi Menggunakan Aspose.Slides untuk Java

## Pendahuluan
The **aspose slides maven dependency** memungkinkan pengembang Java membuat, memodifikasi, dan memperkaya file PowerPoint secara programatis tanpa harus membuka PowerPoint itu sendiri. Dalam banyak skenario bisnis dan akademik, menyisipkan diagram secara manual memakan waktu dan rawan kesalahan. Tutorial ini menunjukkan langkah demi langkah cara menambahkan Bubble Chart, mengaitkan label data ke sel lembar kerja, dan menyimpan hasilnya—semua dengan memanfaatkan aspose slides maven dependency secara bersih dan dapat diulang.

**Apa yang Akan Anda Pelajari**
- Cara menambahkan diagram dengan aspose slides maven dependency
- Menyiapkan proyek Java menggunakan Maven atau Gradle
- Memuat presentasi yang ada dan menyisipkan Bubble Chart
- Mengonfigurasi label data menggunakan referensi sel (menambahkan label data pada diagram)
- Menyimpan file yang diperbarui untuk distribusi selanjutnya
- Kasus penggunaan dunia nyata seperti pembuatan diagram dinamis dan alur kerja pembuatan diagram presentasi

## Jawaban Cepat
- **Artifact Maven mana yang menambahkan kemampuan diagram?** `com.aspose:aspose-slides:25.4` (atau terbaru)  
- **Bisakah saya mengaitkan label data ke sel bergaya Excel?** Ya – gunakan `ChartDataLabel` dengan `setDataLabelFormat` dan referensi sel.  
- **Apakah lisensi diperlukan untuk produksi?** Lisensi penuh menghapus watermark evaluasi dan membuka semua fitur.  
- **Apakah ini akan bekerja pada Java 11+?** Tentu saja; perpustakaan ini kompatibel dengan Java 8 hingga Java 21.  
- **Berapa banyak tipe diagram yang didukung?** Lebih dari 70 tipe diagram berbeda, termasuk Bubble, Radar, dan Stock.

## Apa itu aspose slides maven dependency?
**aspose slides maven dependency** adalah paket yang kompatibel dengan Maven yang menyediakan API lengkap untuk membuat dan mengedit file PowerPoint (PPTX, PPT, ODP) dalam Java. Dengan menambahkan dependensi ini ke `pom.xml` atau `build.gradle` Anda, Anda mendapatkan akses ke lebih dari 70 tipe diagram, lebih dari 150 tata letak slide, dan kemampuan untuk memanipulasi bentuk, animasi, serta metadata tanpa harus menginstal Office.

## Mengapa menggunakan aspose slides maven dependency untuk otomatisasi diagram?
Aspose.Slides memproses dek slide beribu‑ribu dalam waktu kurang dari satu detik pada perangkat keras server standar, mendukung **lebih dari 70 tipe diagram**, dan dapat merender presentasi hingga **10.000 slide** tanpa memuat seluruh file ke memori. Kemampuan terukur ini menjadikannya ideal untuk pembuatan diagram dinamis tingkat perusahaan, di mana kinerja dan skalabilitas tidak dapat dinegosiasikan.

## Prasyarat
- **Java Development Kit (JDK)** 8 atau lebih baru (Java 11+ disarankan).  
- **Maven** 3.6+ **atau** **Gradle** 6+.  
- Perpustakaan **Aspose.Slides for Java** (aspose slides maven dependency, versi 25.4 atau lebih baru).  
- Pemahaman dasar tentang koleksi Java dan I/O file.  
- File lisensi evaluasi atau penuh (`license.json`) jika Anda berencana menjalankan kode di luar periode percobaan.

## Cara menambahkan diagram ke slide menggunakan Aspose.Slides?
Muat presentasi target, buat bentuk diagram baru pada slide yang diinginkan, dan tentukan tipe diagram (Bubble dalam contoh ini). Seluruh operasi dapat dilakukan dalam **tiga baris kode singkat** setelah perpustakaan direferensikan, menjadikannya sempurna untuk prototipe cepat dan alur produksi.

### Langkah 1: Tambahkan aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Potongan kode ini mengambil API lengkap Aspose.Slides—termasuk dukungan diagram—langsung dari Maven Central.

### Langkah 2: Muat presentasi dan sisipkan Bubble Chart
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Langkah 3: Konfigurasikan seri data dan label diagram
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Langkah 4: Simpan presentasi yang dimodifikasi
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Cara mengonfigurasi label data menggunakan referensi sel?
Label data dapat diikat ke nilai sel eksternal, meniru fitur “Link to Cell” pada Excel. Pendekatan ini menghilangkan nilai yang dikodekan secara tetap dan memungkinkan **pembuatan diagram dinamis** di mana konten label diperbarui secara otomatis saat data dasar berubah. Dengan menautkan setiap label ke sel workbook tertentu, Anda memastikan setiap perubahan pada data sumber langsung tercermin dalam presentasi, mengurangi upaya pemeliharaan dan meminimalkan risiko informasi usang.

### Jawaban Langsung
Panggil `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` dan berikan `DataLabelFormat` yang merujuk ke alamat sel seperti `"Sheet1!A2"`. Aspose.Slides menyelesaikan referensi tersebut pada waktu berjalan, menyisipkan nilai sel saat ini ke dalam label diagram.

### Langkah‑demi‑langkah
1. Identifikasi seri yang ingin Anda beri label.  
2. Ambil objek `IDataLabel` untuk setiap titik data.  
3. Gunakan `setDataLabelFormat` dengan `DataLabelFormat` yang dikonfigurasi untuk `CellReference`.  
4. Opsional, sesuaikan font, warna, dan opsi tampilan.

## Cara menyimpan presentasi yang dimodifikasi?
Menyimpan adalah panggilan satu metode yang menulis objek `Presentation` dalam memori ke jalur file atau aliran output. Anda juga dapat memilih format output (PPTX, PDF, ODP) dengan memberikan enum `SaveFormat` yang sesuai. Operasi ini mengalirkan hasil langsung ke disk, melepaskan semua sumber daya native secara otomatis ketika instance `Presentation` ditutup atau keluar dari ruang lingkup, yang membantu menjaga penggunaan memori tetap rendah bahkan untuk dek besar.

### Jawaban Langsung
Panggil `presentation.save("output.pptx", SaveFormat.Pptx)`; perpustakaan mengalirkan hasil langsung ke disk, melepaskan semua sumber daya native secara otomatis ketika instance `Presentation` ditutup atau keluar dari ruang lingkup.

## Aplikasi Praktis
1. **Laporan Bisnis:** Menghasilkan diagram penjualan kuartalan secara otomatis dari dump basis data.  
2. **Kuliah Akademik:** Mengambil data riset langsung ke slide kuliah untuk setiap sesi kelas.  
3. **Presentasi Penjualan:** Membuat dasbor kinerja khusus klien secara cepat.  
4. **Manajemen Proyek:** Memvisualisasikan timeline gaya Gantt dengan label data dinamis.  
5. **Analitik Pemasaran:** Menyematkan KPI kampanye ke dalam presentasi yang diperbarui saat metrik baru tiba.

## Pertimbangan Kinerja
- **Manajemen Memori:** Gunakan try‑with‑resources atau `presentation.dispose()` eksplisit untuk membebaskan memori native dengan cepat.  
- **Dataset Besar:** Saat menangani lebih dari 10.000 titik data, isi data diagram melalui `ChartDataWorkbook` untuk menghindari memuat seluruh dataset ke objek Java.  
- **Keamanan Thread:** Setiap thread harus bekerja dengan instance `Presentation` masing‑masing; API tidak thread‑safe pada objek yang dibagikan.  

## Masalah Umum dan Solusinya
- **Masalah:** “File lisensi tidak ditemukan.”  
  **Solusi:** Tempatkan `license.json` di classpath dan panggil `License license = new License(); license.setLicense("license.json");` sebelum menggunakan API apa pun.  
- **Masalah:** Diagram muncul kosong setelah disimpan.  
  **Solusi:** Pastikan workbook data diagram disimpan bersama presentasi (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Masalah:** Label data menampilkan error “#REF!”.  
  **Solusi:** Verifikasi bahwa string referensi sel cocok dengan nama lembar dan alamat yang tepat, serta workbook yang dirujuk terlampir pada diagram.  

## Pertanyaan yang Sering Diajukan

**Q:** Bisakah saya menambahkan tipe diagram lain selain Bubble?  
**A:** Ya, enumerasi `ChartType` mencakup line, bar, pie, radar, stock, dan lebih dari 70 tipe tambahan.

**Q:** Apakah aspose slides maven dependency bekerja dengan OpenJDK?  
**A:** Tentu saja; sepenuhnya kompatibel dengan OpenJDK 8‑21 dan berjalan di semua sistem operasi utama.

**Q:** Bagaimana cara menyematkan diagram dari file Excel yang ada?  
**A:** Muat workbook Excel dengan `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, kemudian kaitkan `ChartDataWorkbook` diagram ke workbook tersebut sebelum mengatur referensi sel.

**Q:** Apakah ada batasan jumlah diagram per slide?  
**A:** Praktis tidak—Aspose.Slides dapat menangani puluhan diagram per slide, hanya dibatasi oleh memori yang tersedia.

**Q:** Format apa yang dapat saya ekspor untuk presentasi akhir?  
**A:** PPTX, PPT, ODP, PDF, XPS, HTML, dan bahkan format gambar seperti PNG dan JPEG didukung.

## Sumber Daya
- [Rilis Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/) – unduh binari perpustakaan terbaru.  
- [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/java/) – referensi API komprehensif dan panduan.  
- [Unduh Aspose.Slides untuk Java](https://releases.aspose.com/slides/java/) – halaman unduhan langsung untuk paket Maven/Gradle.  
- [Beli Lisensi](https://purchase.aspose.com/buy) – dapatkan lisensi komersial penuh.  
- [Uji Coba Gratis](https://releases.aspose.com/slides/java/) – mulai dengan uji coba untuk mengevaluasi fitur.  
- [Lisensi Sementara](https://purchase.aspose.com/temporary-license/) – minta kunci sementara untuk evaluasi yang diperpanjang.  
- [Forum Dukungan Aspose](https://forum.aspose.com/c/slides/11) – dapatkan bantuan dari komunitas dan insinyur Aspose.

## Kesimpulan
Anda kini memiliki panduan lengkap end‑to‑end untuk menggunakan **aspose slides maven dependency** dalam menambahkan, mengonfigurasi, dan menyimpan diagram pada presentasi Java. Dengan mengikuti langkah‑langkah di atas, Anda dapat mengotomatisasi pembuatan diagram, mengaitkan label data ke nilai sel langsung, dan menghasilkan deck profesional dalam skala besar. Bereksperimenlah dengan tipe diagram lain, jelajahi API animasi, dan integrasikan alur kerja ini ke dalam pipeline pelaporan Anda untuk dampak maksimal.

---  
**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Tutorial Terkait

- [Cara Membuat dan Mengonfigurasi Presentasi dengan Aspose.Slides Java&#58; Panduan Langkah demi Langkah](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Buat PPTX Java dengan Aspose.Slides Maven – Panduan Otomasi](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Cara Membuat Diagram di Java dengan Aspose.Slides: Panduan Komprehensif](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}