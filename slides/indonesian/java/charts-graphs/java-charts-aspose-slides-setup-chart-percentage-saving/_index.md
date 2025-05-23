---
"date": "2025-04-17"
"description": "Pelajari cara membuat, menyesuaikan, dan menyimpan diagram dengan label persentase dalam presentasi Java menggunakan Aspose.Slides. Tingkatkan keterampilan presentasi Anda hari ini!"
"title": "Membuat dan Menyesuaikan Bagan dalam Presentasi Java Menggunakan Aspose.Slides"
"url": "/id/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat dan Menyesuaikan Bagan dalam Presentasi Java Menggunakan Aspose.Slides

## Perkenalan
Membuat presentasi yang menarik sering kali melibatkan lebih dari sekadar teks; presentasi memerlukan diagram dinamis yang menyampaikan informasi secara efektif. Jika Anda ingin menyempurnakan presentasi berbasis Java dengan fitur diagram canggih menggunakan Aspose.Slides, tutorial ini cocok untuk Anda. Kami akan memandu Anda membuat presentasi, menambahkan dan mengonfigurasi diagram, menghitung total, menampilkan label persentase, dan menyimpan pekerjaan Anda—semuanya hanya dalam beberapa langkah mudah.

**Apa yang Akan Anda Pelajari:**
- Cara membuat dan menyesuaikan presentasi dengan bagan menggunakan Aspose.Slides untuk Java
- Menghitung total kategori dalam bagan
- Menampilkan data sebagai label persentase pada grafik
- Menyimpan presentasi dengan fitur bagan yang disempurnakan

Mari kita bahas prasyarat yang Anda perlukan sebelum memulai.

## Prasyarat
Untuk mengikuti tutorial ini, pastikan Anda memiliki hal berikut:

- **Kit Pengembangan Java (JDK)**: Versi 8 atau lebih tinggi.
- **ide**Seperti IntelliJ IDEA, Eclipse, atau IDE apa pun yang mendukung Java.
- **Aspose.Slides untuk Pustaka Java**: Ini penting untuk menangani fitur presentasi.

### Pustaka dan Versi yang Diperlukan
Anda memerlukan Aspose.Slides untuk Java. Berikut cara memasukkannya ke dalam proyek Anda:

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

Atau, Anda dapat langsung mengunduh versi terbaru dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

### Pengaturan Lingkungan
Pastikan lingkungan pengembangan Anda dikonfigurasi untuk menggunakan JDK 8 atau yang lebih baru dan IDE Anda diatur untuk mengelola dependensi menggunakan Maven atau Gradle.

**Akuisisi Lisensi:**
- **Uji Coba Gratis**: Akses fitur dasar untuk tujuan pengujian.
- **Lisensi Sementara**: Uji fitur-fitur lanjutan tanpa batasan evaluasi.
- **Pembelian**:Untuk penggunaan komersial jangka panjang, pertimbangkan untuk membeli lisensi.

## Menyiapkan Aspose.Slides untuk Java
Mulailah dengan menyiapkan pustaka Aspose.Slides di proyek Java Anda. Berikut cara menginisialisasi dan mengonfigurasinya:

1. Tambahkan dependensi melalui Maven atau Gradle seperti yang ditunjukkan di atas.
2. Impor paket Aspose.Slides yang diperlukan:
   ```java
   import com.aspose.slides.*;
   ```

3. Inisialisasi baru `Presentation` contoh:
   ```java
   Presentation presentation = new Presentation();
   ```

Pengaturan ini akan memungkinkan Anda untuk mulai membuat presentasi secara terprogram.

## Panduan Implementasi

### Membuat dan Menyesuaikan Bagan dalam Presentasi Anda

#### Ringkasan
Membuat bagan melibatkan inisialisasi presentasi Anda, mengakses slide, dan menambahkan bagan dengan atribut tertentu seperti jenis, posisi, dan ukuran.

**Tangga:**
1. **Buat Contoh Presentasi**: Mulailah dengan membuat sebuah instance dari `Presentation` kelas.
2. **Akses Slide**: Ambil slide pertama menggunakan `get_Item(0)`.
3. **Tambahkan Bagan**: Menggunakan `addChart()` untuk menambahkan bagan kolom bertumpuk pada koordinat yang ditentukan dengan dimensi yang ditentukan.

```java
// Fitur: Buat Presentasi dengan Bagan
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Hitung Total untuk Kategori

#### Ringkasan
Perhitungan total kategori melibatkan pengulangan setiap seri pada bagan untuk menjumlahkan nilai per kategori.

**Tangga:**
1. **Inisialisasi Array**: Buat array untuk menampung nilai total.
2. **Beriterasi Melalui Kategori dan Seri**: Gunakan loop bersarang untuk mengumpulkan total untuk setiap kategori dari semua seri.

```java
// Fitur: Hitung Total untuk Kategori dalam Bagan
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Menampilkan Data sebagai Label Persentase pada Bagan

#### Ringkasan
Fitur ini berfokus pada konfigurasi label data untuk menampilkan nilai sebagai persentase, memberikan kejelasan dalam visualisasi.

**Tangga:**
1. **Konfigurasikan Label Seri**: Mengatur properti label seperti ukuran font dan visibilitas kunci legenda.
2. **Hitung Persentase**: Hitung persentase untuk setiap titik data berdasarkan nilai kategori total.
3. **Tetapkan Teks Label**: Format label untuk menampilkan persentase dengan dua titik desimal.

```java
// Fitur: Menampilkan Data sebagai Label Persentase pada Bagan
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Simpan Presentasi dengan Bagan

#### Ringkasan
Terakhir, simpan presentasi Anda ke jalur yang ditentukan dalam format PPTX.

**Tangga:**
1. **Metode Penyimpanan**:Gunakan `save()` metode pada `Presentation` contoh.
2. **Buang Sumber Daya**: Pastikan sumber daya dilepaskan setelah menyimpan.

```java
// Fitur: Simpan Presentasi dengan Bagan
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Aplikasi Praktis

1. **Pelaporan Keuangan**: Gunakan bagan untuk menampilkan persentase pertumbuhan pendapatan di seluruh departemen.
2. **Analisis Data Penjualan**: Visualisasikan data penjualan berdasarkan wilayah dengan label persentase untuk wawasan yang lebih jelas.
3. **Presentasi Pendidikan**: Tingkatkan presentasi akademis dengan statistik visual.
4. **Kampanye Pemasaran**: Menampilkan metrik kinerja kampanye sebagai visual yang menarik.
5. **Pertemuan Strategi Bisnis**: Gunakan bagan untuk menyampaikan data yang kompleks dalam diskusi perencanaan strategis.

## Pertimbangan Kinerja
- **Manajemen Memori**: Buang `Presentation` objek dengan segera untuk membebaskan sumber daya.
- **Optimalkan Pemuatan Grafik**Jika memungkinkan, hanya muat elemen bagan yang penting ke dalam memori.
- **Pemrosesan Batch**: Saat memproses beberapa presentasi, pertimbangkan untuk menanganinya secara massal untuk mengelola konsumsi sumber daya secara efektif.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}