---
"date": "2025-04-17"
"description": "Pelajari cara menyempurnakan bagan Anda di Aspose.Slides untuk Java dengan menambahkan penanda gambar khusus. Tingkatkan keterlibatan dengan presentasi yang berbeda secara visual."
"title": "Master Aspose.Slides Java&#58; Menambahkan Penanda Gambar ke Bagan"
"url": "/id/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Menguasai Aspose.Slides Java: Menambahkan Penanda Gambar ke Bagan

## Perkenalan
Membuat presentasi yang menarik secara visual adalah kunci komunikasi yang efektif, dan bagan merupakan alat yang ampuh untuk menyampaikan data yang kompleks secara ringkas. Penanda bagan standar terkadang tidak cukup untuk membuat data Anda menonjol. Dengan Aspose.Slides untuk Java, Anda dapat menyempurnakan bagan dengan menambahkan gambar khusus sebagai penanda, sehingga membuatnya lebih menarik dan informatif.

Dalam tutorial ini, kita akan mempelajari cara mengintegrasikan penanda gambar ke dalam bagan Anda menggunakan pustaka Aspose.Slides di Java. Dengan menguasai teknik-teknik ini, Anda akan dapat membuat presentasi yang menarik perhatian dengan elemen visualnya yang unik.

**Apa yang Akan Anda Pelajari:**
- Cara mengatur Aspose.Slides untuk Java
- Membuat presentasi dan bagan dasar
- Menambahkan penanda gambar ke titik data bagan
- Mengonfigurasi pengaturan penanda untuk visualisasi optimal

Siap untuk meningkatkan grafik Anda? Mari selami prasyaratnya sebelum memulai!

### Prasyarat
Untuk mengikuti tutorial ini, Anda memerlukan:
1. **Aspose.Slides untuk Pustaka Java**: Dapatkan melalui dependensi Maven atau Gradle atau dengan mengunduh langsung dari Aspose.
2. **Lingkungan Pengembangan Java**Pastikan JDK 16 terinstal di komputer Anda.
3. **Pengetahuan Dasar Pemrograman Java**:Keakraban dengan sintaksis dan konsep Java akan bermanfaat.

## Menyiapkan Aspose.Slides untuk Java
Sebelum masuk ke kode, mari siapkan lingkungan pengembangan kita dengan pustaka yang diperlukan.

### Instalasi Maven
Tambahkan dependensi berikut ke `pom.xml` mengajukan:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalasi Gradle
Sertakan ini di dalam `build.gradle` mengajukan:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduh Langsung
Atau, unduh rilis terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

#### Langkah-langkah Memperoleh Lisensi
- **Uji Coba Gratis**: Mulailah dengan lisensi sementara untuk menjelajahi fitur Aspose.Slides.
- **Lisensi Sementara**: Akses fitur-fitur lanjutan dengan memperoleh lisensi sementara.
- **Pembelian**:Untuk penggunaan jangka panjang, pertimbangkan untuk membeli lisensi penuh.

### Inisialisasi dan Pengaturan Dasar
Inisialisasi `Presentation` objek untuk mulai membuat slide:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Kode Anda untuk menambahkan slide dan bagan ada di sini.
    }
}
```

## Panduan Implementasi
Sekarang, mari kita uraikan proses penambahan penanda gambar ke rangkaian bagan Anda.

### Membuat Presentasi Baru dengan Bagan
Pertama, kita memerlukan slide tempat kita dapat menambahkan grafik kita:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Inisialisasi objek Presentasi
        Presentation presentation = new Presentation();

        // Dapatkan slide pertama dari koleksi
        ISlide slide = presentation.getSlides().get_Item(0);

        // Tambahkan diagram garis default dengan penanda ke slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Akses dan Konfigurasikan Data Bagan
Berikutnya, kita akan mengakses lembar kerja data bagan kita untuk mengelola seri:

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

        // Hapus seri yang ada dan tambahkan yang baru
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Tambahkan Penanda Gambar ke Titik Data Bagan
Sekarang untuk bagian yang menarik—menambahkan gambar sebagai penanda:

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

        // Memuat dan menambahkan gambar sebagai penanda
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Tambahkan titik data dengan gambar sebagai penanda
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

### Konfigurasikan Penanda Seri Bagan dan Simpan Presentasi
Terakhir, mari sesuaikan ukuran penanda untuk visibilitas yang lebih baik dan simpan presentasi kita:

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

        // Memuat dan menambahkan gambar sebagai penanda (contoh menggunakan jalur placeholder)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Kesimpulan
Dengan mengikuti panduan ini, Anda telah mempelajari cara menyempurnakan bagan Anda di Aspose.Slides for Java dengan menambahkan penanda gambar khusus. Pendekatan ini dapat meningkatkan keterlibatan dan kejelasan presentasi Anda secara signifikan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}