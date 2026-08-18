---
date: '2026-06-03'
description: Pelajari cara mengekspor diagram ke Excel dan membuat diagram Java menggunakan
  Aspose.Slides untuk Java. Kuasai visualisasi data, slide laporan bisnis, dan pembuatan
  workbook.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Ekspor Diagram ke Excel dan Buat Diagram dengan Aspose.Slides
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ekspor Diagram ke Excel dan Buat Diagram dengan Aspose.Slides

**Menguasai Teknik Visualisasi Data dengan Aspose.Slides untuk Java**

Di lanskap yang didorong oleh data saat ini, *export chart to excel* secara programatik adalah keterampilan yang dapat mengubah angka mentah menjadi cerita visual yang menarik. Baik Anda membuat deck slide laporan bisnis atau dasbor analitik interaktif, Aspose.Slides untuk Java memberi Anda kemampuan untuk menghasilkan, menyesuaikan, dan mengekspor diagram langsung dari kode Anda. Dalam tutorial ini Anda akan belajar cara membuat objek diagram, mengekspor data diagram ke Excel, dan menautkan diagram ke workbook eksternal untuk manajemen data yang mulus.

## Jawaban Cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.Slides for Java (v25.4+).  
- **Bisakah saya mengekspor data diagram ke Excel?** Ya – gunakan `readWorkbookStream()` dan tulis byte ke file *.xlsx*.  
- **Versi Java apa yang diperlukan?** JDK 16 atau lebih tinggi.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi permanen diperlukan untuk produksi.  
- **Jenis diagram apa yang ditunjukkan?** Diagram Pie, tetapi pendekatan yang sama berlaku untuk Bar, Line, dan jenis diagram lainnya.

## Apa itu Aspose.Slides untuk Java?
Aspose.Slides untuk Java adalah API murni‑Java yang memungkinkan pengembang membuat, mengedit, dan mengonversi presentasi PowerPoint tanpa Microsoft Office. Ia menyediakan serangkaian kelas yang komprehensif untuk manipulasi slide, pembuatan diagram, dan konversi format, memungkinkan solusi pelaporan otomatis. Ia mendukung **lebih dari 50 jenis diagram**, pengikatan data penuh, dan ekspor Excel langsung, menjadikannya ideal untuk proyek **data visualization java**.

## Mengapa menggunakan Aspose.Slides untuk membuat diagram dan mengekspor diagram ke Excel?
Ekspor diagram ke Excel dengan cepat dan andal. Aspose.Slides menghilangkan kebutuhan instalasi Office, menawarkan **lebih dari 50 gaya diagram bawaan**, dan memproses presentasi **hingga 300 MB dalam kurang dari 30 detik** pada perangkat keras server standar. Anda juga mendapatkan pembuatan workbook Excel native, yang memungkinkan analis downstream bekerja dengan angka mentah tanpa menyalin‑tempel manual.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:

### Perpustakaan dan Versi yang Diperlukan
- **Aspose.Slides untuk Java** versi 25.4 atau lebih baru (mendukung JDK 16+)

### Persyaratan Penyiapan Lingkungan
- Java Development Kit (JDK) 16 atau lebih tinggi  
- IDE seperti IntelliJ IDEA atau Eclipse (atau editor teks apa pun yang Anda sukai)

### Prasyarat Pengetahuan
- Keterampilan pemrograman Java dasar  
- Familiaritas dengan alat build Maven atau Gradle

## Menyiapkan Aspose.Slides untuk Java
Tambahkan pustaka ke proyek Anda menggunakan sistem build favorit Anda.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sebagai alternatif, Anda dapat [unduh versi terbaru secara langsung](https://releases.aspose.com/slides/java/).

### Langkah-langkah Akuisisi Lisensi
Aspose.Slides menawarkan lisensi percobaan gratis untuk menjelajahi semua kemampuannya. Anda juga dapat mengajukan lisensi sementara atau membeli satu untuk penggunaan jangka panjang. Ikuti langkah-langkah berikut:

1. Kunjungi [halaman Pembelian Aspose](https://purchase.aspose.com/buy) untuk mendapatkan lisensi Anda.  
2. Untuk percobaan gratis, unduh dari [Rilis](https://releases.aspose.com/slides/java/).  
3. Ajukan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

Setelah Anda memiliki file lisensi, inisialisasi dalam aplikasi Java Anda:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Panduan Langkah‑per‑Langkah

### Cara membuat diagram – Memuat Presentasi
Muat file PowerPoint yang ada sebelum Anda dapat menambahkan atau memodifikasi diagram.  
Kelas `Presentation` mewakili file PowerPoint dalam memori, menampilkan slide, shape, dan objek diagram.  
Muat file Anda dengan `new Presentation("input.pptx")`, kemudian kerja dengan slide pertama menggunakan `presentation.getSlides().get_Item(0)`. Selalu panggil `presentation.dispose()` dalam blok `finally` untuk melepaskan sumber daya native.

### Cara membuat diagram – Menambahkan Diagram Pie ke Slide
Sisipkan diagram Pie, sempurna untuk menampilkan data proporsional.  
Antarmuka `IChart` adalah titik masuk utama untuk manipulasi diagram; `addChart` membuat diagram baru pada slide target. Berikan jenis diagram (`ChartType.Pie`), koordinat X/Y, serta lebar/tinggi. Setelah dibuat, Anda dapat menyesuaikan judul, legenda, dan seri data melalui objek `ChartData`.

### Cara mengekspor diagram ke Excel – Mengekspor Data Diagram
Mengekspor data diagram memungkinkan analis bekerja dengan angka di Excel, memberikan wawasan yang lebih dalam.  
`readWorkbookStream()` mengembalikan workbook Excel dasar diagram sebagai array byte. Panggil `chart.getChartData().readWorkbookStream()` untuk mengambil workbook dan menulis array ini ke file bernama `externalWorkbook1.xlsx` menggunakan I/O Java standar. File Excel yang dihasilkan berisi data persis yang digunakan oleh diagram, siap untuk analisis lebih lanjut.

### Cara membuat diagram – Menetapkan Workbook Eksternal untuk Data Dinamis
Tautkan diagram ke workbook eksternal untuk memungkinkan pembaruan data secara langsung tanpa membangun ulang slide.  
`setExternalWorkbook()` mengikat diagram ke file Excel eksternal untuk pembaruan data dinamis. Gunakan `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` untuk mengikat diagram ke file eksternal. Ketika workbook Excel diedit, diagram secara otomatis mencerminkan perubahan saat presentasi dibuka kembali, mendukung skenario pelaporan dinamis.

## Aplikasi Praktis
Aspose.Slides menawarkan solusi serbaguna untuk berbagai skenario dunia nyata:

1. **Slide Laporan Bisnis:** Menghasilkan diagram kinerja kuartalan secara otomatis dari alur data Anda.  
2. **Presentasi Akademik:** Mengubah data penelitian menjadi visualisasi yang jelas tanpa pembuatan diagram manual.  
3. **Analisis Keuangan:** Mengekspor data diagram ke Excel untuk auditor memverifikasi angka, mengurangi kesalahan manual.  
4. **Analitik Pemasaran:** Memvisualisasikan metrik kampanye dan berbagi workbook yang dapat diedit dengan pemangku kepentingan untuk pengambilan keputusan kolaboratif.  
5. **Pembuatan Dashboard Otomatis:** Menggabungkan API pembuatan diagram dengan pekerjaan terjadwal untuk menghasilkan deck slide terkini setiap pagi.

## Masalah Umum & Pemecahan Masalah
- **`FileNotFoundException`** – Pastikan `dataDir` mengarah ke folder yang valid dan jalur output dapat ditulisi.  
- **Memory leaks** – Selalu panggil `presentation.dispose()` dalam blok `finally` untuk membebaskan sumber daya native.  
- **Diagram tidak muncul** – Pastikan indeks slide (`get_Item(0)`) sesuai dengan slide yang ada, dan dimensi diagram berada dalam batas slide.  
- **Ekspor Excel menghasilkan file kosong** – Pastikan diagram memang berisi seri data sebelum memanggil `readWorkbookStream()`.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan jenis diagram lain (mis., Bar, Line) dengan kode yang sama?**  
A: Ya. Ganti `ChartType.Pie` dengan nilai enum `ChartType` lainnya seperti `ChartType.Bar` atau `ChartType.Line`.

**Q: Apakah memungkinkan memperbarui workbook eksternal setelah diagram dibuat?**  
A: Tentu saja. Modifikasi file Excel secara langsung; diagram yang ditautkan akan mencerminkan perubahan saat presentasi dibuka kembali.

**Q: Apakah saya memerlukan lisensi terpisah untuk fitur ekspor Excel?**  
A: Tidak. Kemampuan ekspor Excel sudah termasuk dalam lisensi standar Aspose.Slides untuk Java.

**Q: Versi Java apa yang didukung?**  
A: Aspose.Slides untuk Java mendukung JDK 16 dan yang lebih baru; versi sebelumnya mungkin berfungsi tetapi tidak diuji secara resmi.

**Q: Bagaimana cara menyematkan workbook Excel yang dihasilkan ke dalam file PPTX?**  
A: Gunakan `chart.getChartData().setExternalWorkbook(null)` untuk menyematkan workbook, atau pertahankan tautan eksternal untuk pembaruan dinamis.

---

**Terakhir Diperbarui:** 2026-06-03  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Penulis:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat diagram di Java dengan Aspose.Slides – Tambah & Validasi Diagram](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Pulihkan Data Workbook dari Diagram PowerPoint Menggunakan Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Cara Memperbarui Rentang Data Diagram PowerPoint Menggunakan Aspose.Slides untuk Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}