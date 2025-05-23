---
"date": "2025-04-17"
"description": "Pelajari cara membuat diagram sebar dinamis menggunakan Aspose.Slides untuk Java. Sempurnakan presentasi Anda dengan fitur diagram yang dapat disesuaikan."
"title": "Membuat dan Menyesuaikan Grafik Sebar di Java dengan Aspose.Slides"
"url": "/id/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat dan Menyesuaikan Grafik Sebar di Java dengan Aspose.Slides

Sempurnakan presentasi Anda dengan menambahkan diagram sebar dinamis menggunakan Java dengan Aspose.Slides. Tutorial komprehensif ini akan memandu Anda dalam menyiapkan direktori, menginisialisasi presentasi, membuat diagram sebar, mengelola data diagram, menyesuaikan jenis dan penanda seri, serta menyimpan pekerjaan Anda—semuanya dengan mudah.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan direktori untuk menyimpan file presentasi
- Menginisialisasi dan memanipulasi presentasi menggunakan Aspose.Slides
- Membuat diagram sebaran pada slide
- Mengelola dan menambahkan data ke rangkaian bagan
- Menyesuaikan jenis dan penanda seri bagan
- Menyimpan presentasi Anda dengan modifikasi

Mari kita mulai dengan memastikan Anda memiliki prasyarat yang diperlukan.

## Prasyarat

Untuk mengikuti tutorial ini, pastikan Anda memiliki:
- **Aspose.Slides untuk Java**: Diperlukan versi 25.4 atau yang lebih baru.
- **Kit Pengembangan Java (JDK)**: Diperlukan JDK 8 atau yang lebih tinggi.
- Pengetahuan dasar tentang pemrograman Java dan keakraban dengan alat pembangun Maven atau Gradle.

## Menyiapkan Aspose.Slides untuk Java

Sebelum kita mulai membuat kode, integrasikan Aspose.Slides ke dalam proyek Anda menggunakan salah satu metode berikut:

### Pakar
Sertakan ketergantungan ini dalam `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Bahasa Inggris Gradle
Tambahkan baris ini ke Anda `build.gradle` mengajukan:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Atau, unduh Aspose.Slides terbaru untuk Java dari [Rilis Aspose](https://releases.aspose.com/slides/java/).

#### Akuisisi Lisensi
- **Uji Coba Gratis**: Mulailah dengan uji coba gratis 30 hari untuk menjelajahi fitur-fitur.
- **Lisensi Sementara**: Dapatkan lisensi sementara untuk pengujian lanjutan.
- **Pembelian**: Beli lisensi untuk akses dan dukungan penuh.

Sekarang, inisialisasi Aspose.Slides di aplikasi Java Anda dengan menambahkan impor yang diperlukan seperti yang ditunjukkan di bawah ini.

## Panduan Implementasi

### Pengaturan Direktori
Pertama, pastikan direktori kita ada untuk menyimpan file presentasi. Langkah ini mencegah terjadinya kesalahan saat menyimpan file.

#### Buat Direktori jika Tidak Ada
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Buat direktori
    new File(dataDir).mkdirs();
}
```
Potongan kode ini memeriksa direktori tertentu dan membuatnya jika tidak ada. Ia menggunakan `File.exists()` untuk memverifikasi keberadaan dan `File.mkdirs()` untuk membuat direktori.

### Inisialisasi Presentasi

Berikutnya, inisialisasi objek presentasi Anda di mana Anda akan menambahkan diagram sebar.

#### Inisialisasi Presentasi Anda
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Di Sini, `new Presentation()` membuat presentasi kosong. Kita mengakses slide pertama untuk langsung mengerjakannya.

### Pembuatan Bagan
Berikutnya adalah membuat diagram sebar pada slide yang telah kita inisialisasi.

#### Tambahkan Bagan Sebar ke Slide
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Potongan kode ini menambahkan diagram sebaran dengan garis-garis halus ke slide pertama. Parameter menentukan posisi dan ukuran diagram.

### Manajemen Data Bagan
Sekarang mari kelola data bagan kita dengan menghapus seri yang ada dan menambahkan yang baru.

#### Kelola Seri Bagan
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Menambahkan seri baru ke bagan
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Bagian ini menghapus data yang ada dan menambahkan dua seri baru ke diagram sebaran kami.

### Penambahan Titik Data untuk Seri Pencar
Untuk memvisualisasikan data kami, kami menambahkan titik ke setiap seri pada diagram sebar.

#### Tambahkan Titik Data
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Kami menggunakan `addDataPointForScatterSeries()` untuk menambahkan titik data ke seri pertama kita. Parameter menentukan nilai X dan Y.

### Tipe Seri dan Modifikasi Penanda
Sesuaikan tampilan bagan Anda dengan mengubah jenis dan gaya penanda di setiap seri.

#### Kustomisasi Seri
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Memodifikasi seri kedua
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Perubahan ini menyesuaikan jenis seri untuk menggunakan garis lurus dan penanda. Kami juga mengatur ukuran dan simbol penanda untuk pembedaan visual.

### Menyimpan Presentasi
Terakhir, simpan presentasi Anda dengan semua modifikasi yang dibuat.

#### Simpan Presentasi Anda
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Menggunakan `SaveFormat.Pptx` untuk menentukan format PowerPoint guna menyimpan berkas Anda. Langkah ini penting untuk menyimpan semua perubahan.

## Aplikasi Praktis
Berikut ini beberapa kasus penggunaan di dunia nyata:
1. **Analisis Keuangan**: Gunakan diagram sebar untuk menampilkan tren saham dari waktu ke waktu.
2. **Riset ilmiah**: Mewakili titik data eksperimen untuk analisis.
3. **Manajemen Proyek**: Visualisasikan alokasi sumber daya dan metrik kemajuan.

Mengintegrasikan Aspose.Slides ke dalam sistem Anda memungkinkan Anda mengotomatiskan pembuatan laporan, meningkatkan produktivitas dan akurasi.

## Pertimbangan Kinerja
Untuk kinerja optimal:
- Kelola penggunaan memori dengan membuang presentasi setelah menyimpan.
- Gunakan struktur data yang efisien untuk kumpulan data besar.
- Minimalkan operasi yang membutuhkan banyak sumber daya dalam loop.

Praktik terbaik memastikan pelaksanaan yang lancar bahkan dengan manipulasi bagan yang rumit.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara menyiapkan direktori, menginisialisasi presentasi Aspose.Slides, membuat dan menyesuaikan diagram sebar, mengelola data seri, memodifikasi penanda, dan menyimpan pekerjaan Anda. Untuk lebih mengeksplorasi kemampuan Aspose.Slides, pertimbangkan untuk mempelajari fitur yang lebih canggih seperti animasi dan transisi slide.

**Langkah Berikutnya**: Bereksperimenlah dengan berbagai jenis bagan atau integrasikan teknik ini ke dalam proyek Java yang lebih besar.

## Tanya Jawab Umum

### Bagaimana cara mengubah warna penanda?
Untuk mengubah warna penanda, gunakan `series.getMarker().getFillFormat().setFillColor(ColorObject)`, Di mana `ColorObject` adalah warna yang Anda inginkan.

### Bisakah saya menambahkan lebih dari dua seri ke diagram sebar?
Ya, Anda dapat menambahkan seri sebanyak yang diperlukan dengan mengulangi proses penambahan seri dan titik data baru.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}