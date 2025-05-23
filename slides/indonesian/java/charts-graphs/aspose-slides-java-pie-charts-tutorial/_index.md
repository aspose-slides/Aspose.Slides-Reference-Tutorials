---
"date": "2025-04-17"
"description": "Pelajari cara membuat dan menyesuaikan diagram pai menggunakan Aspose.Slides untuk Java. Tutorial ini mencakup semuanya mulai dari pengaturan hingga penyesuaian tingkat lanjut."
"title": "Membuat Diagram Lingkaran di Java dengan Aspose.Slides&#58; Panduan Lengkap"
"url": "/id/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Diagram Lingkaran dengan Aspose.Slides untuk Java: Tutorial Lengkap

## Perkenalan
Membuat presentasi yang dinamis dan menarik secara visual sangat penting untuk menyampaikan informasi yang berdampak. Dengan Aspose.Slides untuk Java, Anda dapat dengan mudah mengintegrasikan diagram kompleks seperti diagram pai ke dalam slide Anda, sehingga meningkatkan visualisasi data dengan mudah. Panduan lengkap ini akan memandu Anda melalui proses pembuatan dan penyesuaian diagram pai menggunakan Aspose.Slides Java, sehingga dapat menyelesaikan tantangan presentasi umum dengan mudah.

**Apa yang Akan Anda Pelajari:**
- Inisialisasi presentasi dan menambahkan slide.
- Membuat dan mengonfigurasi diagram lingkaran pada slide Anda.
- Menetapkan judul bagan, label data, dan warna.
- Mengoptimalkan kinerja dan mengelola sumber daya secara efektif.
- Mengintegrasikan Aspose.Slides ke dalam proyek Java menggunakan Maven atau Gradle.

Mari kita mulai dengan memastikan Anda memiliki semua alat dan pengetahuan yang diperlukan untuk mengikutinya!

## Prasyarat
Sebelum menyelami tutorial ini, pastikan Anda telah menyiapkan pengaturan berikut:

### Pustaka, Versi, dan Ketergantungan yang Diperlukan
- **Aspose.Slides untuk Java**Pastikan Anda memiliki versi 25.4 atau yang lebih baru.
- **Kit Pengembangan Java (JDK)**: Diperlukan versi 16 atau lebih tinggi.

### Persyaratan Pengaturan Lingkungan
- Lingkungan pengembangan dengan Java terinstal dan dikonfigurasi.
- Lingkungan Pengembangan Terpadu (IDE) seperti IntelliJ IDEA, Eclipse, atau NetBeans.

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman Java.
- Kemampuan menggunakan Maven atau Gradle untuk manajemen ketergantungan.

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides di proyek Java Anda, Anda perlu menambahkan pustaka tersebut sebagai dependensi. Berikut ini cara melakukannya menggunakan berbagai alat pembuatan:

**Pakar**
Tambahkan cuplikan ini ke `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Bahasa Inggris Gradle**
Sertakan hal berikut dalam formulir Anda `build.gradle` mengajukan:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Unduh Langsung**
Jika Anda memilih untuk tidak menggunakan alat build, unduh rilis terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

### Langkah-langkah Memperoleh Lisensi
- **Uji Coba Gratis**Mulailah dengan uji coba gratis untuk menjelajahi fitur Aspose.Slides.
- **Lisensi Sementara**: Dapatkan lisensi sementara untuk penggunaan jangka panjang tanpa batasan.
- **Pembelian**: Pertimbangkan untuk membeli jika Anda membutuhkan akses jangka panjang.

**Inisialisasi dan Pengaturan Dasar**
Untuk mulai menggunakan Aspose.Slides, inisialisasi proyek Anda dengan membuat objek presentasi baru:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Panduan Implementasi
Sekarang mari kita uraikan proses penambahan dan penyesuaian diagram lingkaran menjadi langkah-langkah yang dapat dikelola.

### Inisialisasi Presentasi dan Slide
Mulailah dengan menyiapkan presentasi baru dan mengakses slide pertama. Ini adalah kanvas untuk membuat diagram:
```java
import com.aspose.slides.*;

// Buat contoh presentasi baru.
Presentation presentation = new Presentation();
// Akses slide pertama dalam presentasi.
islide slides = presentation.getSlides().get_Item(0);
```

### Tambahkan Diagram Lingkaran ke Slide
Masukkan diagram lingkaran ke posisi yang ditentukan dengan kumpulan data default:
```java
import com.aspose.slides.*;

// Tambahkan diagram lingkaran pada posisi (100, 100) dengan ukuran (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Tetapkan Judul Bagan
Sesuaikan bagan Anda dengan mengatur dan memusatkan judul:
```java
import com.aspose.slides.*;

// Tambahkan judul pada diagram lingkaran.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurasikan Label Data untuk Seri
Pastikan label data menampilkan nilai untuk kejelasan:
```java
import com.aspose.slides.*;

// Menampilkan nilai data pada seri pertama.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Siapkan Lembar Kerja Data Bagan
Siapkan lembar kerja data bagan Anda dengan menghapus seri dan kategori yang ada:
```java
import com.aspose.slides.*;

// Siapkan buku kerja data bagan.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Tambahkan Kategori ke Bagan
Tentukan kategori untuk diagram lingkaran Anda:
```java
import com.aspose.slides.*;

// Tambahkan kategori baru.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Tambahkan Seri dan Isi Titik Data
Buat seri dan isi dengan titik data:
```java
import com.aspose.slides.*;

// Tambahkan seri baru dan tetapkan namanya.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Sesuaikan Warna dan Batas Seri
Tingkatkan daya tarik visual dengan mengatur warna dan menyesuaikan batas:
```java
import com.aspose.slides.*;

// Tetapkan warna bervariasi untuk sektor seri.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Ulangi untuk titik data lainnya dengan warna dan gaya yang berbeda.
```

### Konfigurasikan Label Data Kustom
Sempurnakan label untuk setiap titik data:
```java
import com.aspose.slides.*;

// Konfigurasikan label khusus.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Aktifkan garis pemimpin untuk label.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Atur Sudut Rotasi dan Simpan Presentasi
Selesaikan diagram lingkaran Anda dengan mengatur sudut rotasi dan menyimpan presentasi:
```java
import com.aspose.slides.*;

// Mengatur sudut rotasi.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Simpan presentasi ke sebuah berkas.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara membuat dan menyesuaikan diagram pai menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat menyempurnakan presentasi Anda dengan visualisasi data yang menarik secara visual. Jika Anda memiliki pertanyaan atau memerlukan bantuan lebih lanjut, jangan ragu untuk menghubungi kami.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}