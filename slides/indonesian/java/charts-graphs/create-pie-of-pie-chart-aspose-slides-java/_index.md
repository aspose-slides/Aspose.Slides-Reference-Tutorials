---
"date": "2025-04-17"
"description": "Pelajari cara membuat dan menyesuaikan diagram Pie of Pie menggunakan Aspose.Slides untuk Java. Panduan ini mencakup penyiapan, penerapan, dan aplikasi praktis."
"title": "Membuat Diagram Lingkaran di Java dengan Aspose.Slides&#58; Panduan Lengkap"
"url": "/id/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Diagram Lingkaran di Java dengan Aspose.Slides: Panduan Lengkap

## Bagan & Grafik

### Perkenalan

Dalam visualisasi data, diagram pai merupakan cara intuitif untuk merepresentasikan proporsi dalam suatu kumpulan data. Namun, saat menangani kumpulan data kompleks yang beberapa segmennya jauh lebih kecil daripada yang lain, diagram pai tradisional dapat menjadi berantakan dan sulit diinterpretasikan. Diagram pai mengatasi hal ini dengan membagi irisan kecil menjadi diagram sekunder, sehingga lebih mudah dibaca.

Dalam tutorial ini, Anda akan mempelajari cara membuat dan memanipulasi Pie of Pie Chart menggunakan Aspose.Slides untuk Java. Anda akan membahas cara menyiapkan lingkungan, membuat bagan, menyesuaikan properti seperti label data dan posisi split, serta menyimpan presentasi dalam format PPTX. Pada akhirnya, Anda akan menguasai fitur-fitur ini dengan aplikasi praktis dan kiat-kiat performa.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk Java
- Membuat Diagram Lingkaran
- Menyesuaikan properti bagan seperti label data dan konfigurasi split
- Menyimpan presentasi Anda ke disk

Siap untuk memulai? Mari kita lihat prasyaratnya terlebih dahulu!

## Prasyarat

Sebelum membuat Diagram Lingkaran, pastikan Anda memiliki:

### Pustaka, Versi, dan Dependensi yang Diperlukan:
- **Aspose.Slides untuk Java**: Penting untuk mengelola presentasi PowerPoint secara terprogram.

### Persyaratan Pengaturan Lingkungan:
- Java Development Kit (JDK) terinstal di komputer Anda. Kami sarankan untuk menggunakan JDK 16 atau yang lebih baru.
- Lingkungan Pengembangan Terpadu (IDE) seperti IntelliJ IDEA, Eclipse, atau NetBeans.

### Prasyarat Pengetahuan:
- Pemahaman dasar tentang pemrograman Java
- Keakraban dengan Maven atau Gradle untuk manajemen ketergantungan

## Menyiapkan Aspose.Slides untuk Java

### Informasi Instalasi:

**Pakar:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradasi:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Unduh Langsung**: Anda dapat mengunduh versi terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

### Langkah-langkah Memperoleh Lisensi:
- **Uji Coba Gratis**Mulailah dengan uji coba 30 hari untuk menjelajahi semua fitur.
- **Lisensi Sementara**Minta lisensi sementara untuk evaluasi lanjutan.
- **Pembelian**: Pertimbangkan untuk membeli lisensi jika Aspose.Slides memenuhi kebutuhan Anda.

### Inisialisasi dan Pengaturan Dasar

Setelah Anda menyiapkan perpustakaan di proyek Anda, inisialisasikan dengan membuat contoh `Presentation` kelas:

```java
Presentation presentation = new Presentation();
```

Ini menjadi dasar untuk menambahkan berbagai diagram ke slide Anda. Selanjutnya, mari kita lanjutkan dengan menerapkan Diagram Lingkaran.

## Panduan Implementasi

### Membuat Bagan 'Pie of Pie'

#### Ringkasan
Kita akan mulai dengan membuat sebuah instance dari `Presentation` dan tambahkan diagram Pie of Pie pada slide pertama. Diagram ini akan memvisualisasikan data secara efektif dengan memisahkan segmen yang lebih kecil menjadi pie sekunder, sehingga meningkatkan keterbacaan.

#### Langkah 1: Buat Contoh Kelas Presentasi
```java
// Buat presentasi baru
ePresentation presentation = new Presentation();
```
Kode ini menginisialisasi presentasi Anda di mana kita akan menambahkan bagan.

#### Langkah 2: Tambahkan Bagan 'Pie of Pie' pada Slide Pertama
```java
// Tambahkan diagram Pie of Pie ke slide pertama pada posisi (50, 50) dengan ukuran (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Di sini kami menentukan jenis grafik (`PieOfPie`) dan posisi serta dimensinya pada slide.

#### Langkah 3: Tetapkan Label Data untuk Menampilkan Nilai untuk Seri
```java
// Konfigurasikan label data untuk menampilkan nilai
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Langkah ini memastikan bahwa setiap segmen diagram lingkaran kita menampilkan nilai yang sesuai, membantu dalam interpretasi data yang cepat.

#### Langkah 4: Konfigurasikan Ukuran Pai Kedua dan Bagi Berdasarkan Persentase
```java
// Mengatur ukuran pai sekunder
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Membagi kue berdasarkan persentase
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Mengatur posisi split
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Konfigurasi ini memungkinkan Anda menyesuaikan bagaimana bagan Anda dibagi dan menampilkan segmen yang lebih kecil, meningkatkan kejelasan bagi pemirsa.

#### Langkah 5: Simpan Presentasi ke Disk dalam Format PPTX
```java
// Tentukan direktori keluaran
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Simpan presentasi\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}