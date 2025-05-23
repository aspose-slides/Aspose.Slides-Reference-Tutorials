---
"date": "2025-04-17"
"description": "Pelajari cara membuat presentasi profesional menggunakan Aspose.Slides untuk Java. Panduan ini mencakup pengaturan lingkungan Anda, penambahan diagram kolom bertumpuk, dan penyesuaiannya agar lebih jelas."
"title": "Menguasai Grafik Kolom Bertumpuk di Java dengan Aspose.Slides&#58; Panduan Lengkap"
"url": "/id/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Menguasai Grafik Kolom Bertumpuk di Java dengan Aspose.Slides: Panduan Lengkap

## Perkenalan

Tingkatkan presentasi Anda dengan menggabungkan visualisasi data yang mendalam dengan kekuatan Aspose.Slides untuk Java. Membuat slide yang tampak profesional dengan bagan kolom bertumpuk mudah dilakukan, baik saat Anda menyiapkan laporan bisnis atau memamerkan statistik proyek.

Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Slides untuk Java guna membuat presentasi yang dinamis dan menambahkan diagram kolom bertumpuk yang menarik secara visual. Di akhir panduan ini, Anda akan dibekali dengan keterampilan yang dibutuhkan untuk:
- Siapkan lingkungan Anda untuk menggunakan Aspose.Slides
- Buat presentasi dari awal
- Tambahkan dan sesuaikan bagan kolom bertumpuk persentase
- Format sumbu grafik dan label data untuk kejelasan

Mari mulai membuat presentasi yang memikat audiens Anda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- **Kit Pengembangan Java (JDK):** Versi 8 atau lebih tinggi.
- **IDE:** Lingkungan Pengembangan Terpadu seperti IntelliJ IDEA atau Eclipse.
- **Maven/Gradle:** Untuk mengelola dependensi (opsional tetapi direkomendasikan).
- **Pengetahuan Dasar Java:** Kemampuan dengan konsep pemrograman Java.

## Menyiapkan Aspose.Slides untuk Java
Untuk memulai, Anda perlu menyertakan pustaka Aspose.Slides dalam proyek Anda. Berikut caranya:

**Pakar:**
Tambahkan ketergantungan ini ke `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradasi:**
Sertakan ini di dalam `build.gradle` mengajukan:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Unduh Langsung:**
Atau, unduh JAR terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

### Akuisisi Lisensi
Anda dapat memulai dengan uji coba gratis untuk menjelajahi fitur-fitur Aspose.Slides. Untuk menghilangkan batasan evaluasi, pertimbangkan untuk memperoleh lisensi sementara atau yang dibeli.
- **Uji Coba Gratis:** Akses fitur terbatas tanpa biaya langsung.
- **Lisensi Sementara:** Permintaan melalui [Situs Aspose](https://purchase.aspose.com/temporary-license/).
- **Pembelian:** Kunjungi halaman pembelian untuk akses penuh.

### Inisialisasi Dasar
Berikut ini cara menginisialisasi Aspose.Slides di aplikasi Java Anda:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Buat instance kelas Presentasi
        Presentation presentation = new Presentation();
        
        // Melakukan operasi pada objek presentasi
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Panduan Implementasi

### Membuat Presentasi dan Menambahkan Slide
**Ringkasan:**
Mulailah dengan membuat presentasi sederhana dengan slide awal. Ini adalah dasar untuk penyempurnaan lebih lanjut.

#### Langkah 1: Inisialisasi Objek Presentasi
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Buat contoh presentasi baru
        Presentation presentation = new Presentation();
        
        // Referensi ke slide pertama (dibuat otomatis)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Langkah 2: Simpan Presentasi
```java
// Simpan presentasi ke file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Menambahkan Bagan Kolom Bertumpuk Persentase ke Slide
**Ringkasan:**
Tingkatkan slide Anda dengan menambahkan bagan kolom bertumpuk persentase, yang memungkinkan perbandingan data dengan mudah.

#### Langkah 1: Inisialisasi dan Akses Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Lanjutkan untuk menambahkan grafik di langkah berikutnya
    }
}
```

#### Langkah 2: Tambahkan Bagan ke Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Menyesuaikan Format Angka Sumbu Bagan
**Ringkasan:**
Sesuaikan format angka sumbu vertikal bagan Anda agar lebih mudah dibaca.

#### Langkah 1: Tambahkan dan Akses Bagan
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Langkah 2: Atur Format Angka Kustom
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Menambahkan Seri dan Titik Data ke Bagan
**Ringkasan:**
Isi bagan Anda dengan rangkaian data, membuatnya informatif dan menarik secara visual.

#### Langkah 1: Inisialisasi Presentasi dan Bagan
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Langkah 2: Tambahkan Seri Data
```java
// Hapus seri yang ada dan tambahkan yang baru
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Tambahkan lebih banyak titik data sesuai kebutuhan
```

### Memformat Warna Isi Seri
**Ringkasan:**
Tingkatkan estetika bagan Anda dengan memformat warna isian setiap seri.

#### Langkah 1: Inisialisasi dan Akses Bagan
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Langkah 2: Atur Warna Isi
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Ulangi untuk seri lainnya dengan warna berbeda
```

### Memformat Label Data
**Ringkasan:**
Jadikan label data Anda lebih mudah dibaca dengan menyesuaikan formatnya.

#### Langkah 1: Akses Seri Bagan dan Titik Data
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Langkah 2: Kustomisasi Label Data
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Kesimpulan
Dengan mengikuti panduan ini, Anda telah mempelajari cara menyiapkan Aspose.Slides untuk Java dan membuat presentasi dinamis dengan bagan kolom dengan persentase yang ditumpuk. Sesuaikan bagan Anda lebih lanjut dengan menyesuaikan warna dan label agar sesuai dengan kebutuhan Anda.

Selamat membuat kode!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}