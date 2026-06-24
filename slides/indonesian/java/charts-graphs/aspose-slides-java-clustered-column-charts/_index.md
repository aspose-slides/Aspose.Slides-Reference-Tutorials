---
date: '2026-03-18'
description: Pelajari cara membuat diagram kolom berkelompok di Java dengan Aspose.Slides,
  cara menambahkan diagram, mengatur warna, dan menyimpan presentasi sebagai PPTX.
  Panduan langkah demi langkah dengan contoh kode.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Cara membuat diagram kolom berkelompok di Java dengan Aspose.Slides
url: /id/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara membuat diagram kolom berkelompok di Java dengan Aspose.Slides

## Pendahuluan
Membuat representasi data yang menarik secara visual sangat penting untuk presentasi bisnis yang berdampak, dan mempelajari **cara membuat diagram kolom berkelompok** secara programatik dapat menghemat Anda berjam‑jam kerja manual. Dalam tutorial ini Anda akan melihat **cara menambahkan diagram**, secara otomatis **mengatur warna**, dan akhirnya **menyimpan presentasi sebagai PPTX** menggunakan **Aspose.Slides for Java**. Kami akan membahas semua yang Anda perlukan—mulai dari menyiapkan pustaka hingga menambahkan diagram, menyesuaikan warna isi seri, dan menyimpan file.

### Apa yang akan Anda capai
- Instal dan konfigurasikan Aspose.Slides untuk Java  
- **Buat diagram kolom berkelompok** dalam presentasi baru  
- Terapkan warna isi seri secara otomatis (**how to set colors**)  
- **Simpan presentasi sebagai PPTX** ke disk (**how to save presentation**)  

Mari selesaikan prasyarat terlebih dahulu sebelum kita mulai membuat diagram.

## Jawaban Cepat
- **Apa kelas utama?** `Presentation` dari `com.aspose.slides`  
- **Bagaimana cara menambahkan diagram?** Gunakan `addChart(ChartType.ClusteredColumn, …)` pada koleksi shape slide (**how to add chart**)  
- **Bisakah saya mengatur warna secara otomatis?** Ya, panggil `setAutomaticSeriesColor(true)` pada setiap seri (**how to set colors**)  
- **Format apa yang digunakan untuk menyimpan?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi  

## Prasyarat
Sebelum memulai, pastikan Anda memiliki alat dan pengetahuan yang diperlukan:

### Perpustakaan dan Dependensi yang Diperlukan
Anda memerlukan pustaka Aspose.Slides untuk Java. Pastikan Anda menggunakan versi 25.4 dengan dukungan JDK16.

### Persyaratan Penyiapan Lingkungan
Lingkungan pengembangan Anda harus mendukung Java (sebaiknya JDK16) dan mampu membangun proyek menggunakan Maven atau Gradle.

### Prasyarat Pengetahuan
Familiaritas dengan pemrograman Java dasar, bekerja dengan pustaka melalui Maven/Gradle, dan pemahaman tentang presentasi PowerPoint akan sangat membantu.

## Menyiapkan Aspose.Slides untuk Java
Untuk mengintegrasikan Aspose.Slides ke dalam proyek Anda, ikuti petunjuk penyiapan di bawah ini:

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

**Unduhan Langsung**  
Bagi yang lebih suka mengunduh langsung, kunjungi [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Langkah-langkah Akuisisi Lisensi
- **Free Trial**: Mulai dengan percobaan gratis untuk menjelajahi fitur.  
- **Temporary License**: Dapatkan lisensi sementara untuk menguji tanpa batasan.  
- **Purchase**: Untuk penggunaan berkelanjutan, beli lisensi penuh.

**Inisialisasi dan Penyiapan Dasar**  
Inisialisasi Aspose.Slides sebagai berikut:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Cara Menambahkan Diagram Kolom Berkelompok
Menambahkan diagram adalah langkah fungsional pertama. Bagian ini menjelaskan **cara menambahkan diagram** menggunakan API.

### Fitur 1: Membuat Diagram Kolom Berkelompok
Mari buat diagram kolom berkelompok menggunakan Aspose.Slides untuk Java. Fitur ini memungkinkan Anda menambahkan diagram yang menarik secara visual ke slide Anda dengan mudah.

#### Gambaran Umum
Di bagian ini, kami akan menginisialisasi presentasi baru dan menyisipkan diagram kolom berkelompok ke slide pertama.

**Langkah 1: Inisialisasi Presentasi**  
Buat objek `Presentation` untuk mulai bekerja dengan file PowerPoint:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Langkah 2: Tambahkan Diagram Kolom Berkelompok**  
Tambahkan diagram pada koordinat yang ditentukan (100, 50) dan dimensi (600 × 400):
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Langkah 3: Bersihkan Sumber Daya**  
Selalu buang sumber daya untuk mencegah kebocoran memori:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Cara Mengatur Warna untuk Diagram
Tingkatkan daya tarik visual dengan secara otomatis menerapkan warna isi seri (**how to set colors**).

### Fitur 2: Mengatur Warna Isi Seri Otomatis
Atur warna seri setiap diagram secara otomatis untuk tampilan yang serasi.

#### Gambaran Umum
Atur warna seri setiap diagram secara otomatis untuk tampilan yang serasi.

**Langkah 1: Akses Diagram dan Iterasi Seri**  
Setelah membuat diagram Anda, akses diagram tersebut dan iterasi melalui serinya:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Langkah 2: Manajemen Sumber Daya**  
Buang objek presentasi setelah selesai:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Cara Menyimpan Presentasi sebagai PPTX
Setelah diagram terlihat bagus, Anda ingin menyimpan file (**how to save presentation**).

### Fitur 3: Menyimpan Presentasi ke Disk
Akhirnya, simpan pekerjaan Anda dengan mudah menggunakan Aspose.Slides.

#### Gambaran Umum
Simpan presentasi yang telah diedit dalam format dan lokasi yang diinginkan.

**Langkah 1: Tentukan Jalur Output**  
Tentukan di mana Anda ingin menyimpan file:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Langkah 2: Simpan Presentasi**  
Gunakan metode `save` dari objek `Presentation`:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Aplikasi Praktis
- **Financial Reports**: Visualisasikan pendapatan kuartalan dengan jelas.  
- **Marketing Data Analysis**: Tampilkan hasil kampanye menggunakan visual yang menarik.  
- **Project Management**: Lacak tonggak dan kemajuan secara visual dalam pertemuan tim.

## Pertimbangan Kinerja
Saat bekerja dengan Aspose.Slides, pertimbangkan praktik terbaik berikut:

- Kelola memori secara efektif dengan membuang objek `Presentation` secara cepat.  
- Optimalkan ukuran file saat menyimpan presentasi untuk menghemat ruang disk.  
- Gunakan struktur data yang efisien untuk seri diagram guna meningkatkan kinerja.

## Kesimpulan
Selamat! Anda telah mempelajari cara **membuat diagram kolom berkelompok**, secara otomatis **mengatur warna**, dan **menyimpan presentasi sebagai PPTX** menggunakan Aspose.Slides untuk Java. Keterampilan ini tidak hanya meningkatkan presentasi Anda tetapi juga mempermudah proses representasi data visual.

**Langkah Selanjutnya:**  
Jelajahi fitur lebih lanjut seperti menyesuaikan elemen diagram, menambahkan label data, atau mengintegrasikan dengan sumber data eksternal untuk memperluas kemampuan proyek Anda.

## Bagian FAQ
1. **How do I install Aspose.Slides for a specific JDK version?**  
   - Gunakan dependensi Maven/Gradle dengan menentukan `classifier` seperti yang ditunjukkan pada bagian penyiapan.
2. **What if my presentation doesn't save correctly?**  
   - Pastikan Anda memiliki izin menulis ke direktori output dan jalur file sudah benar.
3. **Can I create other types of charts using Aspose.Slides for Java?**  
   - Tentu saja! Jelajahi opsi `ChartType` seperti diagram Pie, Bar, atau Line.
4. **How do I handle large datasets in my chart?**  
   - Optimalkan struktur data dan pertimbangkan pra‑pemrosesan data Anda sebelum memvisualisasikannya.
5. **Where can I find more examples of using Aspose.Slides for Java?**  
   - Kunjungi [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) untuk panduan lengkap dan contoh kode.

## Sumber Daya
- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy a License](https://purchase.aspose.com/buy)  
- **Free Trial**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary License**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Terakhir Diperbarui:** 2026-03-18  
**Diuji Dengan:** Aspose.Slides 25.4 (JDK16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}