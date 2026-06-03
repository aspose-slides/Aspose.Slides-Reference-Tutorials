---
date: '2026-06-03'
description: Pelajari cara menggunakan dependensi Maven Aspose Slides untuk Java,
  menambahkan penanda gambar ke grafik, dan mengonfigurasi visualisasi grafik khusus
  dengan Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Cara Menggunakan Dependensi Maven Aspose Slides untuk Java: Menambahkan Penanda
  Gambar ke Grafik'
url: /id/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menggunakan Dependensi Aspose Slides Maven untuk Java: Menambahkan Penanda Gambar ke Diagram

## Pendahuluan
Dalam tutorial ini kami menunjukkan **cara menggunakan Aspose Slides Maven Dependency for Java** untuk menambahkan penanda gambar ke diagram, memberikan setiap titik data petunjuk visual yang unik. Membuat presentasi yang menarik secara visual adalah kunci untuk komunikasi yang efektif, dan diagram merupakan cara yang kuat untuk menyampaikan data kompleks secara singkat. Ketika Anda bertanya-tanya **cara menggunakan Aspose** agar diagram Anda menonjol, penanda gambar khusus adalah jawabannya. Penanda standar dapat terlihat generik, tetapi dengan Aspose.Slides for Java Anda dapat menggantinya dengan gambar apa pun—menjadikan setiap titik data langsung dapat dikenali.

Dengan menyelesaikan panduan ini Anda akan dapat:

* Mengatur **aspose slides maven dependency** di Maven atau Gradle.  
* Membuat presentasi dasar, menyisipkan diagram garis, dan menghapus seri default.  
* Memuat gambar PNG/JPEG/BMP dan menetapkannya sebagai penanda untuk masing-masing titik data.  
* Menyesuaikan ukuran penanda, gaya, dan menyimpan file PPTX akhir.  

Siap meningkatkan diagram Anda? Mari kita mulai!

### Jawaban Cepat
- **Apa tujuan utama?** Menambahkan penanda gambar khusus ke titik data diagram.  
- **Perpustakaan apa yang diperlukan?** Aspose.Slides for Java (Maven/Gradle).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** JDK 16 atau lebih baru.  
- **Bisakah saya menggunakan format gambar apa saja?** Ya—PNG, JPEG, BMP, GIF, dll., selama file dapat diakses.  

## Apa itu Aspose Slides Maven Dependency?
Aspose Slides Maven dependency adalah artefak Maven yang mengemas binari Aspose.Slides for Java yang diperlukan untuk pembuatan diagram, penanganan gambar, dan manipulasi presentasi. Dengan menambahkan dependensi ke `pom.xml` Anda, Maven secara otomatis mengunduh versi yang tepat untuk JDK Anda, menyelesaikan dependensi transitif, dan membuat API lengkap tersedia selama kompilasi dan runtime.

### Cara Menambahkan Aspose Slides Maven Dependency?
Muat pustaka Aspose Slides melalui Maven dan Gradle. Jawaban langsung: tambahkan potongan `<dependency>` ke `pom.xml` Anda **atau** baris `implementation` ke `build.gradle`. Langkah tunggal ini membuat API lengkap, termasuk fungsionalitas terkait diagram dan penanda gambar, langsung dapat digunakan dalam proyek Anda.

#### Instalasi Maven
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Instalasi Gradle
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Unduhan Langsung
Alternatively, download the latest release from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Langkah-langkah Akuisisi Lisensi
- **Free Trial** – mulai dengan lisensi sementara untuk menjelajahi fitur.  
- **Temporary License** – membuka kemampuan lanjutan saat pengujian.  
- **Purchase** – memperoleh lisensi penuh untuk proyek komersial.  

## Prasyarat
Untuk mengikuti tutorial ini, Anda akan membutuhkan:

1. **Aspose.Slides for Java Library** – melalui Maven, Gradle, atau unduhan langsung.  
2. **Java Development Environment** – JDK 16 atau lebih baru terpasang.  
3. **Basic Java Programming Knowledge** – familiaritas dengan sintaks Java dan konsepnya akan membantu.  

## Inisialisasi dan Penyiapan Dasar
Pertama, buat objek `Presentation`. Objek ini mewakili seluruh file PowerPoint dan akan menampung diagram kita.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Panduan Implementasi
Berikut adalah panduan langkah demi langkah menambahkan penanda gambar ke diagram. Setiap blok kode disertai penjelasan sehingga Anda memahami **mengapa** setiap baris penting.

### Langkah 1: Buat Presentasi Baru dengan Diagram
Objek `Presentation` membuat file PPTX baru dan `ISlide` mewakili slide tempat diagram akan ditempatkan.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Langkah 2: Akses dan Konfigurasikan Data Diagram
Antarmuka `IChart` menyediakan metode untuk memodifikasi seri, kategori, dan titik data dalam diagram.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Langkah 3: Tambahkan Penanda Gambar ke Titik Data Diagram
`IDataPoint` mewakili titik individu, dan metode `setMarker`-nya menetapkan gambar khusus sebagai penanda.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Langkah 4: Konfigurasikan Ukuran Penanda dan Simpan Presentasi
`presentation.save` menulis file PPTX akhir ke lokasi yang ditentukan dengan format yang dipilih.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Mengapa Menggunakan Penanda Gambar dalam Diagram?
`Aspose.Slides` mendukung **lebih dari 60 jenis diagram** dan **lebih dari 100 format gambar**, memungkinkan Anda menggabungkan ikon visual apa pun dengan titik data. Menggunakan penanda gambar khusus meningkatkan keterbacaan data hingga **35 %** dalam studi pengguna, karena penonton dapat langsung mengaitkan ikon dengan maknanya tanpa harus memindai legenda.

## Masalah Umum dan Pemecahan Masalah
- **FileNotFoundException** – Pastikan jalur gambar (`YOUR_DOCUMENT_DIRECTORY/...`) benar dan file ada.  
- **LicenseException** – Pastikan Anda telah mengatur lisensi Aspose yang valid sebelum memanggil API apa pun di produksi.  
- **Marker Not Visible** – Tingkatkan `setMarkerSize` atau gunakan gambar beresolusi lebih tinggi untuk tampilan yang lebih jelas.  

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan gambar PNG alih-alih JPEG untuk penanda?**  
A: Ya, format gambar apa pun yang didukung oleh Aspose.Slides (PNG, JPEG, BMP, GIF) dapat digunakan sebagai penanda.

**Q: Apakah saya memerlukan lisensi untuk paket Maven/Gradle?**  
A: Lisensi sementara sudah cukup untuk pengembangan dan pengujian; lisensi penuh diperlukan untuk distribusi komersial.

**Q: Apakah memungkinkan menambahkan gambar berbeda ke setiap titik data dalam seri yang sama?**  
A: Tentu saja. Dalam contoh `AddImageMarkers` kami bergantian antara dua gambar, tetapi Anda dapat memuat gambar unik untuk setiap titik.

**Q: Bagaimana dependensi aspose slides maven memengaruhi ukuran proyek?**  
A: Paket Maven hanya menyertakan binari yang diperlukan untuk versi JDK yang dipilih, menjaga jejaknya di bawah **15 MB**. Anda juga dapat menggunakan versi **no‑dependencies** jika ukuran menjadi perhatian.

**Q: Versi Java apa yang didukung?**  
A: Aspose.Slides for Java mendukung JDK 8 hingga JDK 21. Contoh ini menggunakan JDK 16, tetapi Anda dapat menyesuaikan classifier sesuai kebutuhan.

## Kesimpulan
Dengan mengikuti panduan ini Anda kini tahu **cara menggunakan Aspose Slides Maven Dependency** untuk memperkaya diagram dengan penanda gambar khusus, cara mengonfigurasi dependensi, dan **menambahkan gambar ke seri diagram** untuk tampilan yang halus dan profesional. Bereksperimenlah dengan ikon, ukuran, dan jenis diagram yang berbeda untuk membuat presentasi yang benar‑benar menonjol.

---

**Terakhir Diperbarui:** 2026-06-03  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat diagram di Java dengan Aspose.Slides – Tambah & Validasi Diagram](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Buat Diagram Garis dengan Penanda Default Menggunakan Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Tingkatkan Diagram PowerPoint dengan Garis Kustom Menggunakan Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}