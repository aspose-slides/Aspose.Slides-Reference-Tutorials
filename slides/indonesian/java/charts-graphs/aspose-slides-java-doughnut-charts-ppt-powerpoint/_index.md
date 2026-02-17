---
date: '2026-02-17'
description: Pelajari cara membuat diagram donat di PowerPoint menggunakan Aspose.Slides
  for Java dan menambahkan titik data diagram secara programatis. Ikuti langkah‑langkah
  mudah serta contoh kode.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Buat diagram donat PowerPoint dengan Aspose.Slides untuk Java
url: /id/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

 So we translate.

Also translate bullet lists.

Make sure not to translate URLs inside markdown links.

Also keep the shortcodes at top and bottom.

Let's produce final content.

Check for any inline code like `pres.dispose()`, keep as is.

Translate sentences.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Diagram Donat di PowerPoint dengan Aspose.Slides untuk Java

## Pendahuluan
Membuat presentasi yang menarik sering kali memerlukan lebih dari sekadar teks dan gambar; diagram dapat secara signifikan meningkatkan alur cerita dengan memvisualisasikan data secara efektif. Namun, banyak pengembang mengalami kesulitan mengintegrasikan fitur diagram dinamis ke dalam file PowerPoint secara programatis. Tutorial ini menunjukkan cara **membuat diagram donat di PowerPoint** menggunakan Aspose.Slides untuk Java—sebuah alat yang kuat yang menggabungkan fleksibilitas dan kemudahan penggunaan.

**Apa yang Akan Anda Pelajari:**
- Cara menginisialisasi presentasi menggunakan Aspose.Slides untuk Java
- Panduan langkah‑demi‑langkah menambahkan diagram donat ke slide Anda
- Mengonfigurasi titik data dan menyesuaikan properti label
- Menyimpan presentasi yang telah dimodifikasi dengan fidelitas tinggi

Mari jelajahi bagaimana Anda dapat memanfaatkan fitur-fitur ini untuk meningkatkan presentasi Anda. Sebelum memulai, pastikan Anda familiar dengan konsep dasar pemrograman Java.

## Jawaban Cepat
- **Perpustakaan apa yang membuat diagram donat di PowerPoint?** Aspose.Slides untuk Java
- **Bisakah saya menambahkan titik data diagram secara programatis?** Ya, menggunakan API diagram
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose.Slides yang valid diperlukan
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru (klasifier JDK 16 ditampilkan)
- **Berapa banyak seri yang dapat saya tambahkan?** Contoh menambahkan hingga 15 seri, tetapi Anda dapat menyesuaikannya sesuai kebutuhan

## Apa itu diagram donat di PowerPoint?
Diagram donat adalah variasi dari diagram pai dengan pusat yang berlubang, memungkinkan Anda menampilkan beberapa seri data dalam cara yang kompak dan menarik secara visual. Ini ideal untuk menunjukkan hubungan bagian‑ke‑keseluruhan sambil menjaga desain tetap bersih.

## Mengapa menggunakan Aspose.Slides untuk Java dalam membuat diagram donat?
- **Kontrol penuh** atas tampilan diagram, data, dan tata letak tanpa membuka PowerPoint
- **Tanpa interop COM** – bekerja pada platform apa pun yang mendukung Java
- **Kinerja tinggi** untuk menghasilkan deck besar atau mengintegrasikan dengan layanan web
- **Kustomisasi kaya** seperti ledakan, ukuran lubang, sudut irisan, dan pemformatan label

## Prasyarat
- Pengetahuan dasar tentang pemrograman Java.
- IDE seperti IntelliJ IDEA atau Eclipse.
- Maven atau Gradle untuk manajemen dependensi.
- Lisensi Aspose.Slides untuk Java yang valid (versi percobaan gratis tersedia).

## Menyiapkan Aspose.Slides untuk Java
Pilih manajer dependensi yang sesuai dengan proyek Anda.

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

Jika Anda lebih suka mengunduh langsung, kunjungi halaman [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Akuisisi Lisensi
Anda dapat memulai dengan versi percobaan gratis untuk menjelajahi fitur Aspose.Slides. Untuk penggunaan jangka panjang, beli lisensi atau minta lisensi sementara dari [situs Aspose](https://purchase.aspose.com/temporary-license/). Ikuti petunjuk yang diberikan untuk menyiapkan lingkungan Anda dan menginisialisasi Aspose.Slides dalam aplikasi Anda.

## Cara membuat diagram donat PowerPoint menggunakan Aspose.Slides untuk Java
Berikut adalah panduan lengkap langkah‑demi‑langkah. Setiap blok kode dijelaskan tepat sebelumnya, sehingga Anda tahu persis apa yang terjadi.

### Langkah 1: Inisialisasi presentasi
Pertama, muat PPTX yang ada atau buat yang baru. Ini menyiapkan koleksi slide untuk modifikasi selanjutnya.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Langkah 2: Tambahkan diagram donat ke slide
Kami menambahkan bentuk diagram, menghapus seri/kategori default, dan mengatur properti visual dasar.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Langkah 3: Tambahkan titik data diagram dan sesuaikan label
Di sini kami mengisi kategori, menambahkan titik data untuk setiap seri, dan menyempurnakan tampilan label. Inilah saat kata kunci **add chart data points** berperan.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Langkah 4: Simpan presentasi yang telah diperbarui
Akhirnya, simpan perubahan ke file PPTX baru.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Aplikasi Praktis
Diagram donat dapat digunakan dalam berbagai skenario dunia nyata:
- **Laporan Keuangan:** Visualisasikan alokasi anggaran atau rincian pengeluaran.
- **Analisis Pasar:** Tampilkan distribusi pangsa pasar di antara pesaing.
- **Hasil Survei:** Sajikan data survei kategorikal dalam bentuk yang kompak.
- **Pembuatan Dashboard:** Kombinasikan dengan kueri basis data untuk menghasilkan slide yang memperbarui secara langsung.

## Pertimbangan Kinerja
- **Buang sumber daya**: Panggil `pres.dispose()` setelah selesai untuk membebaskan memori native.
- **Batasi jumlah diagram**: Menambahkan ratusan diagram dapat meningkatkan penggunaan memori; proses secara batch bila diperlukan.
- **Gunakan streaming**: Untuk kumpulan data besar, isi workbook langsung dari aliran alih-alih array dalam memori.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **Diagram muncul kosong** | Sel data tidak terisi dengan benar | Verifikasi bahwa referensi `workBook.getCell(...)` mengarah ke indeks baris/kolom yang tepat. |
| **Label saling tumpang tindih** | Terlalu banyak kategori dalam ruang terbatas | Tingkatkan `DoughnutHoleSize` atau sesuaikan `FirstSliceAngle`. |
| **OutOfMemoryError** | Presentasi besar tanpa membuang sumber daya | Panggil `pres.dispose()` setelah menyimpan dan pertimbangkan meningkatkan ukuran heap JVM. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Slides untuk Java dalam aplikasi komersial?**  
J: Ya, tetapi Anda memerlukan lisensi komersial yang valid. Versi percobaan gratis tersedia untuk evaluasi.

**T: Bagaimana cara menambahkan lebih dari 15 seri?**  
J: Tingkatkan batas loop pada langkah “Add Doughnut Chart” dan pastikan workbook data Anda memiliki cukup baris.

**T: Apakah memungkinkan mengubah ukuran lubang donat setelah dibuat?**  
J: Ya, panggil `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` kapan saja sebelum menyimpan.

**T: Bisakah saya mengekspor diagram sebagai gambar alih-alih PPTX?**  
J: Tentu. Gunakan `chart.getImage()` dan simpan `java.awt.image.BufferedImage` yang dikembalikan dalam format pilihan Anda.

**T: Apakah Aspose.Slides mendukung diagram animasi?**  
J: Animasi dapat ditambahkan melalui API `ISlide.getTimeline()`, meskipun hal ini berada di luar cakupan tutorial ini.

## Kesimpulan
Anda kini memiliki metode lengkap dan siap produksi untuk **membuat diagram donat di PowerPoint** dengan Aspose.Slides untuk Java, termasuk cara **menambahkan titik data diagram**, menyesuaikan label, dan menangani pertimbangan kinerja. Bereksperimenlah dengan warna, sumber data, dan tipe diagram yang berbeda untuk membuat presentasi Anda benar‑benar menonjol.

---

**Terakhir Diperbarui:** 2026-02-17  
**Diuji Dengan:** Aspose.Slides untuk Java 25.4 (klasifier JDK 16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}