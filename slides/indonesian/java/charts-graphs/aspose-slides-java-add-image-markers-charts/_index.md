---
date: '2026-01-11'
description: Pelajari cara menggunakan Aspose Slides untuk Java, tambahkan penanda
  gambar ke diagram, dan konfigurasikan dependensi Maven Aspose Slides untuk visualisasi
  diagram khusus.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Cara Menggunakan Aspose Slides Java: Menambahkan Penanda Gambar ke Grafik'
url: /id/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menggunakan Aspose Slides Java: Menambahkan Penanda Gambar ke Diagram

## Pendahuluan
Membuat presentasi yang menarik secara visual adalah kunci untuk komunikasi yang efektif, dan diagram merupakan alat yang kuat untuk menyampaikan data kompleks secara singkat. Ketika Anda bertanya-tanya **bagaimana cara menggunakan Aspose** untuk membuat diagram Anda menonjol, penanda gambar khusus adalah jawabannya. Penanda standar dapat terlihat generik, tetapi dengan Aspose.Slides for Java Anda dapat menggantinya dengan gambar apa pun—menjadikan setiap titik data langsung dikenali.

Dalam tutorial ini, kami akan memandu Anda melalui seluruh proses menambahkan penanda gambar ke diagram garis, mulai dari menyiapkan **Aspose Slides Maven dependency** hingga memuat gambar dan menerapkannya ke titik data. Pada akhir tutorial Anda akan merasa nyaman dengan **cara menambahkan penanda**, cara **menambahkan gambar ke seri diagram**, dan Anda akan memiliki contoh kode yang siap dijalankan.

**Apa yang Akan Anda Pelajari**
- Cara menyiapkan Aspose.Slides for Java (termasuk Maven/Gradle)
- Membuat presentasi dasar dan diagram
- Menambahkan penanda gambar ke titik data diagram
- Mengonfigurasi ukuran dan gaya penanda untuk visualisasi optimal

Siap meningkatkan diagram Anda? Mari kita selami prasyarat sebelum memulai!

### Jawaban Cepat
- **Apa tujuan utama?** Menambahkan penanda gambar khusus ke titik data diagram.  
- **Perpustakaan apa yang diperlukan?** Aspose.Slides for Java (Maven/Gradle).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** JDK 16 atau lebih baru.  
- **Bisakah saya menggunakan format gambar apa saja?** Ya—PNG, JPEG, BMP, dll., selama file dapat diakses.

### Prasyarat
Untuk mengikuti tutorial ini, Anda memerlukan:
1. **Aspose.Slides for Java Library** – dapatkan melalui Maven, Gradle, atau unduhan langsung.  
2. **Lingkungan Pengembangan Java** – JDK 16 atau lebih baru terpasang.  
3. **Pengetahuan Dasar Pemrograman Java** – familiaritas dengan sintaks dan konsep Java akan membantu.

## Apa itu Aspose Slides Maven Dependency?
Dependensi Maven mengambil binary yang tepat untuk versi Java Anda. Menambahkannya ke `pom.xml` Anda memastikan perpustakaan tersedia pada waktu kompilasi dan runtime.

### Instalasi Maven
Tambahkan dependensi berikut ke file `pom.xml` Anda:

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
Sebagai alternatif, unduh rilis terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Langkah-langkah Akuisisi Lisensi
- **Free Trial** – mulai dengan lisensi sementara untuk menjelajahi fitur.  
- **Temporary License** – membuka kemampuan lanjutan saat pengujian.  
- **Purchase** – dapatkan lisensi penuh untuk proyek komersial.

## Inisialisasi dan Pengaturan Dasar
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
Kami menambahkan diagram garis dengan penanda default ke slide pertama.

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

### Langkah 2: Akses dan Konfigurasi Data Diagram
Kami menghapus semua seri default dan menambahkan seri kami sendiri, menyiapkan lembar kerja untuk titik data khusus.

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
Di sini kami mendemonstrasikan **cara menambahkan penanda** menggunakan gambar. Ganti jalur placeholder dengan lokasi sebenarnya dari gambar Anda.

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

### Langkah 4: Konfigurasi Ukuran Penanda dan Simpan Presentasi  
Kami menyesuaikan gaya penanda untuk visibilitas yang lebih baik dan menulis file PPTX akhir.

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

## Masalah Umum dan Pemecahan Masalah
- **FileNotFoundException** – Pastikan jalur gambar (`YOUR_DOCUMENT_DIRECTORY/...`) benar dan file ada.  
- **LicenseException** – Pastikan Anda telah mengatur lisensi Aspose yang valid sebelum memanggil API apa pun di produksi.  
- **Marker Not Visible** – Tingkatkan `setMarkerSize` atau gunakan gambar beresolusi lebih tinggi untuk tampilan yang lebih jelas.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan gambar PNG alih-alih JPEG untuk penanda?**  
A: Ya, format gambar apa pun yang didukung oleh Aspose.Slides (PNG, JPEG, BMP, GIF) dapat digunakan sebagai penanda.

**T: Apakah saya memerlukan lisensi untuk paket Maven/Gradle?**  
A: Lisensi sementara cukup untuk pengembangan dan pengujian; lisensi penuh diperlukan untuk distribusi komersial.

**T: Apakah memungkinkan menambahkan gambar berbeda ke setiap titik data dalam seri yang sama?**  
A: Tentu saja. Dalam contoh `AddImageMarkers` kami bergantian antara dua gambar, tetapi Anda dapat memuat gambar unik untuk setiap titik.

**T: Bagaimana `aspose slides maven dependency` memengaruhi ukuran proyek?**  
A: Paket Maven hanya menyertakan binary yang diperlukan untuk versi JDK yang dipilih, sehingga jejaknya tetap wajar. Anda juga dapat menggunakan versi **no‑dependencies** jika ukuran menjadi perhatian.

**T: Versi Java apa yang didukung?**  
A: Aspose.Slides for Java mendukung JDK 8 hingga JDK 21. Contoh ini menggunakan JDK 16, tetapi Anda dapat menyesuaikan classifier sesuai kebutuhan.

## Kesimpulan
Dengan mengikuti panduan ini Anda kini tahu **cara menggunakan Aspose** untuk memperkaya diagram dengan penanda gambar khusus, cara mengonfigurasi **Aspose Slides Maven dependency**, dan cara **menambahkan gambar ke seri diagram** untuk tampilan yang halus dan profesional. Bereksperimenlah dengan ikon, ukuran, dan tipe diagram yang berbeda untuk membuat presentasi yang benar‑benar menonjol.

---

**Terakhir Diperbarui:** 2026-01-11  
**Diuji Dengan:** Aspose.Slides for Java 25.4 (jdk16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}