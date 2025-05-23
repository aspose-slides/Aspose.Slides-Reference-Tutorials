---
"date": "2025-04-17"
"description": "Pelajari cara membuat dan menyesuaikan diagram sunburst di PowerPoint dengan Aspose.Slides untuk Java. Panduan langkah demi langkah ini mencakup penyiapan, penyesuaian, dan aplikasi praktis."
"title": "Membuat dan Menyesuaikan Bagan Sunburst di PowerPoint menggunakan Aspose.Slides untuk Java"
"url": "/id/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat dan Menyesuaikan Bagan Sunburst di PowerPoint menggunakan Aspose.Slides untuk Java

## Perkenalan

Membuat presentasi yang menarik sering kali melibatkan penggabungan bagan yang menarik secara visual yang menyampaikan data secara efektif. Salah satu bagan tersebut adalah bagan sunburst, yang menawarkan cara unik untuk merepresentasikan data hierarkis dengan tata letak radialnya. Namun, menambahkan dan menyesuaikan bagan ini dapat menjadi tugas yang berat tanpa alat yang tepat. Panduan ini akan memandu Anda membuat dan memodifikasi bagan sunburst dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan lingkungan Anda untuk Aspose.Slides
- Membuat presentasi baru dengan bagan sunburst
- Menyesuaikan titik data dalam bagan
- Aplikasi nyata dari keterampilan ini

Mari selami bagaimana Anda dapat menyederhanakan proses ini menggunakan Aspose.Slides untuk Java.

## Prasyarat

Sebelum memulai, pastikan lingkungan pengembangan Anda sudah siap. Anda memerlukan:
- **Kit Pengembangan Java (JDK)** versi 16 atau lebih tinggi
- Sebuah **Lingkungan Pengembangan Terpadu (IDE)** seperti IntelliJ IDEA atau Eclipse
- Pengetahuan dasar tentang **Jawa** dan presentasi PowerPoint

## Menyiapkan Aspose.Slides untuk Java

### Ketergantungan Maven

Untuk memasukkan Aspose.Slides ke dalam proyek Anda, tambahkan dependensi berikut ke `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Ketergantungan Gradle

Jika Anda menggunakan Gradle, sertakan yang berikut ini di `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduh Langsung

Atau, unduh JAR terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

### Akuisisi Lisensi

Untuk menggunakan Aspose.Slides tanpa batasan evaluasi:
- **Uji Coba Gratis:** Mulailah dengan lisensi sementara untuk menjelajahi fitur lengkap.
- **Lisensi Sementara:** Minta lisensi sementara di [Situs web Aspose](https://purchase.aspose.com/temporary-license).
- **Pembelian:** Untuk proyek yang sedang berjalan, pertimbangkan untuk membeli langganan.

### Inisialisasi Dasar

Berikut ini cara menginisialisasi Aspose.Slides di aplikasi Java Anda:
```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Inisialisasi Aspose.Slides dengan lisensi jika tersedia
        Presentation pres = new Presentation();
        try {
            // Kode Anda di sini...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Panduan Implementasi

### Membuat Presentasi dan Menambahkan Bagan Sunburst

#### Ringkasan

Fitur ini memperagakan cara membuat presentasi PowerPoint dari awal dan menambahkan bagan sinar matahari.

#### Tangga:
##### Langkah 1: Inisialisasi Presentasi
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Ganti dengan jalur Anda
```

##### Langkah 2: Tambahkan Bagan Sunburst
Tambahkan bagan sinar matahari ke slide pertama pada posisi (100, 100) dengan ukuran (450x400).
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

##### Langkah 3: Simpan Presentasi
Simpan presentasi Anda untuk memastikan semua perubahan tersimpan.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Ubah Titik Data dalam Bagan

#### Ringkasan
Pelajari cara memodifikasi titik data, termasuk label dan warna, dalam bagan sinar matahari.

#### Tangga:
##### Langkah 1: Mengumpulkan Titik Data Akses
Akses kumpulan titik data seri pertama dari bagan.
```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

##### Langkah 2: Tunjukkan Nilai untuk Titik Data Tertentu
Ubah label untuk menampilkan nilai pada tingkat tertentu.
```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

##### Langkah 3: Ubah Format Label
Sesuaikan pengaturan label seperti visibilitas nama kategori dan warna teks.
```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

##### Langkah 4: Mengatur Warna Isi untuk Titik Data
Sesuaikan warna isian titik data tertentu.
```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

##### Langkah 5: Simpan Presentasi yang Dimodifikasi
Selalu simpan perubahan Anda untuk menyelesaikannya.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Aplikasi Praktis

1. **Analisis Bisnis:** Gunakan bagan sunburst untuk memvisualisasikan hierarki data yang kompleks, seperti data penjualan menurut wilayah dan kategori.
2. **Manajemen Proyek:** Menampilkan tugas proyek dipecah menjadi subtugas menggunakan bagan radial untuk memudahkan visualisasi.
3. **Pendidikan:** Mewakili modul kursus dan kuliahnya masing-masing dalam presentasi pendidikan.

## Pertimbangan Kinerja

- **Mengoptimalkan Penggunaan Sumber Daya:** Pastikan aplikasi Anda mengelola memori secara efisien, terutama saat menangani kumpulan data besar atau beberapa bagan.
- **Manajemen Memori Java:** Manfaatkan praktik terbaik seperti membuang objek segera untuk mencegah kebocoran memori.

## Kesimpulan

Membuat dan menyesuaikan diagram sunburst menggunakan Aspose.Slides untuk Java merupakan cara yang ampuh untuk menyempurnakan presentasi Anda. Dengan mengikuti panduan ini, Anda telah mempelajari dasar-dasar pengaturan lingkungan, penerapan fitur diagram, dan modifikasi titik data secara efektif.

**Langkah Berikutnya:**
- Jelajahi lebih banyak jenis bagan yang tersedia di Aspose.Slides.
- Bereksperimenlah dengan berbagai pilihan penyesuaian untuk bagan Anda.

**Ajakan Bertindak:** Cobalah menerapkan solusi ini dalam proyek presentasi Anda berikutnya untuk melihat bagaimana solusi ini dapat meningkatkan upaya visualisasi data Anda!

## Bagian FAQ

1. **Apa itu bagan sinar matahari?**
   - Bagan sunburst menampilkan data hierarkis secara radial, ideal untuk memamerkan hubungan bersarang.
2. **Bagaimana cara menginstal Aspose.Slides untuk Java menggunakan Maven?**
   - Tambahkan ketergantungan ke `pom.xml` file seperti yang ditunjukkan pada bagian pengaturan di atas.
3. **Bisakah saya memodifikasi tipe grafik lain dengan Aspose.Slides?**
   - Ya, Aspose.Slides mendukung berbagai jenis bagan seperti bagan kolom, garis, dan pai.
4. **Apa yang harus saya lakukan jika presentasi saya tidak tersimpan dengan benar?**
   - Pastikan jalur berkas Anda benar dan Anda memiliki izin menulis untuk direktori tersebut.
5. **Bagaimana saya bisa mendapatkan bantuan lebih lanjut dengan Aspose.Slides?**
   - Kunjungi [Forum Aspose](https://forum.aspose.com/c/slides/11) atau periksa dokumentasi di [Referensi Aspose.Slides](https://reference.aspose.com/slides/java/).

## Sumber daya
- **Dokumentasi:** [Referensi Aspose.Slides](https://reference.aspose.com/slides/java)
- **Forum:** [Forum Aspose](https://forum.aspose.com/c/slides)
- **Unduhan:** [Unduhan Aspose.Slides](https://releases.aspose.com/slides/java)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}