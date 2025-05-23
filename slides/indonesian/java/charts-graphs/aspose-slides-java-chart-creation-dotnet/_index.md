---
"date": "2025-04-17"
"description": "Pelajari cara membuat dan menyesuaikan diagram dalam presentasi .NET menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah ini untuk menyempurnakan visualisasi data presentasi Anda."
"title": "Aspose.Slides untuk Java; Membuat Bagan dalam Presentasi .NET"
"url": "/id/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Bagan dalam Presentasi .NET Menggunakan Aspose.Slides untuk Java
## Perkenalan
Membuat presentasi yang menarik sering kali melibatkan pengintegrasian representasi data visual seperti bagan untuk meningkatkan pemahaman dan keterlibatan audiens. Jika Anda seorang pengembang yang ingin menambahkan bagan yang dinamis dan dapat disesuaikan ke presentasi .NET Anda menggunakan Aspose.Slides untuk Java, tutorial ini dirancang khusus untuk Anda. Kami akan membahas cara menginisialisasi presentasi, menambahkan berbagai jenis bagan, mengelola data bagan, dan memformat data seri secara efektif.
**Apa yang Akan Anda Pelajari:**
- Cara mengatur dan menggunakan Aspose.Slides untuk Java di lingkungan .NET Anda.
- Inisialisasi presentasi baru menggunakan Aspose.Slides.
- Menambahkan dan menyesuaikan bagan dalam slide.
- Mengelola buku kerja data bagan.
- Memformat data seri, terutama menangani nilai negatif.
Transisi ke bagian prasyarat akan memastikan Anda siap mengikutinya dengan mudah.
## Prasyarat
Sebelum mulai membuat bagan dengan Aspose.Slides untuk Java, mari kita uraikan apa yang Anda perlukan:
### Pustaka dan Versi yang Diperlukan
Pastikan Anda memiliki dependensi berikut:
- **Aspose.Slides untuk Java**: Versi 25.4 atau lebih baru.
### Persyaratan Pengaturan Lingkungan
- Lingkungan pengembangan yang mendukung aplikasi .NET.
- Pemahaman dasar tentang konsep pemrograman Java.
### Prasyarat Pengetahuan
- Kemampuan membuat presentasi dalam konteks aplikasi .NET.
- Memahami dependensi Java dan pengelolaannya (Maven/Gradle).
## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides, Anda perlu memasukkannya sebagai dependensi dalam proyek Anda. Berikut cara melakukannya:
### Pakar
Tambahkan dependensi berikut ke `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Bahasa Inggris Gradle
Sertakan ini di dalam `build.gradle` mengajukan:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Unduh Langsung
Atau, Anda dapat mengunduh versi terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).
#### Langkah-langkah Memperoleh Lisensi
- **Uji Coba Gratis**: Mulailah dengan lisensi sementara untuk menjelajahi fitur.
- **Pembelian**Pertimbangkan untuk membeli lisensi untuk penggunaan yang luas.
#### Inisialisasi dan Pengaturan Dasar
Berikut ini cara menginisialisasi Aspose.Slides dalam kode Anda:
```java
import com.aspose.slides.Presentation;
// Inisialisasi objek Presentasi baru
Presentation pres = new Presentation();
try {
    // Logika Anda di sini...
} finally {
    if (pres != null) pres.dispose();
}
```
Pengaturan ini memastikan pengelolaan sumber daya ditangani secara efektif.
## Panduan Implementasi
Kami akan memandu Anda menerapkan fitur-fitur tersebut langkah demi langkah.
### Inisialisasi Presentasi
**Ringkasan:**
Pembuatan contoh presentasi akan menjadi dasar untuk semua operasi selanjutnya. Fitur ini menunjukkan cara memulai dari awal menggunakan Aspose.Slides.
#### Langkah 1: Impor Paket yang Diperlukan
```java
import com.aspose.slides.Presentation;
```
#### Langkah 2: Buat Objek Presentasi Baru
Berikut cara melakukannya:
```java
Presentation pres = new Presentation();
try {
    // Logika kode Anda di sini...
} finally {
    if (pres != null) pres.dispose(); // Memastikan sumber daya dibebaskan
}
```
*Ini memastikan bahwa objek presentasi dibuang dengan benar setelah digunakan, mencegah kebocoran memori.*
### Menambahkan Bagan ke Slide
**Ringkasan:**
Menambahkan bagan ke slide Anda dapat membuat visualisasi data lebih efektif dan menarik.
#### Langkah 1: Impor Paket yang Diperlukan
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```
#### Langkah 2: Inisialisasi Presentasi dan Tambahkan Bagan
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Logika tambahan untuk penyesuaian grafik...
} finally {
    if (pres != null) pres.dispose();
}
```
*Di sini, kami menambahkan bagan kolom berkelompok ke slide pertama pada koordinat dan dimensi yang ditentukan.*
### Buku Kerja Pengelolaan Data Bagan
**Ringkasan:**
Mengelola buku kerja data bagan Anda secara efisien memungkinkan Anda memanipulasi seri dan kategori dengan mudah.
#### Langkah 1: Impor Paket yang Diperlukan
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### Langkah 2: Akses dan Hapus Data Buku Kerja
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Hapus data yang ada
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Logika kustomisasi Anda di sini...
} finally {
    if (pres != null) pres.dispose();
}
```
*Membersihkan buku kerja sangat penting untuk memulai dengan keadaan bersih saat menambahkan seri dan kategori baru.*
### Menambahkan Seri dan Kategori ke Bagan
**Ringkasan:**
Fitur ini menunjukkan bagaimana Anda dapat menambahkan titik data yang bermakna dengan mengelola seri dan kategori.
#### Langkah 1: Tambahkan Seri dan Kategori
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Hapus seri dan kategori yang ada
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Tambahkan seri dan kategori baru
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Logika penyesuaian lebih lanjut...
} finally {
    if (pres != null) pres.dispose();
}
```
*Menambahkan seri dan kategori memungkinkan penyajian data yang lebih terorganisir.*
### Mengisi Data Seri dan Memformatnya
**Ringkasan:**
Isi bagan Anda dengan titik data dan format tampilannya untuk meningkatkan keterbacaan, terutama saat menangani nilai negatif.
#### Langkah 1: Mengisi Data Seri
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Tambahkan seri dan kategori (gunakan kembali logika sebelumnya)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format seri untuk nilai negatif
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Simpan presentasi
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Bagian ini menunjukkan cara mengisi data dan menerapkan format warna untuk visualisasi yang lebih baik.*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}