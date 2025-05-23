---
"date": "2025-04-17"
"description": "Pelajari cara membuat diagram donat yang menakjubkan di Java dengan Aspose.Slides. Panduan komprehensif ini mencakup inisialisasi, konfigurasi data, dan penyimpanan presentasi."
"title": "Membuat Bagan Donat di Java menggunakan Aspose.Slides' Panduan Lengkap"
"url": "/id/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat Diagram Donat di Java Menggunakan Aspose.Slides: Panduan Langkah demi Langkah

## Perkenalan

Dalam lingkungan yang digerakkan oleh data saat ini, memvisualisasikan informasi secara efektif adalah kunci untuk meningkatkan pemahaman dan keterlibatan. Meskipun membuat bagan profesional secara terprogram mungkin tampak menantang, terutama dengan Java, panduan ini akan memandu Anda menggunakan Aspose.Slides untuk Java untuk membuat bagan Donat dengan mudah.

Dengan mengikuti langkah-langkah ini, pengembang akan memperoleh pengalaman langsung dalam memanipulasi slide presentasi dan mengintegrasikan visualisasi data dengan mulus.

**Poin-poin Utama:**
- Inisialisasi objek Presentasi menggunakan Aspose.Slides Java.
- Konfigurasikan data bagan dan kelola seri atau kategori yang ada.
- Tambahkan dan sesuaikan seri dan kategori untuk bagan Anda.
- Format dan tampilkan titik data secara efektif.
- Simpan presentasi Anda dalam berbagai format dengan mudah.

Sebelum memulai implementasi, pastikan Anda memiliki semua yang dibutuhkan untuk memulai.

## Prasyarat

Untuk mengikuti tutorial ini, pastikan Anda memiliki:

- **Pustaka yang dibutuhkan:**
  - Aspose.Slides untuk Java versi 25.4 atau yang lebih baru.
  
- **Pengaturan Lingkungan:**
  - JDK 16 atau lebih tinggi terinstal di sistem Anda.
  - IDE seperti IntelliJ IDEA, Eclipse, atau NetBeans.

- **Prasyarat Pengetahuan:**
  - Pemahaman dasar tentang konsep pemrograman Java.
  - Kemampuan mengelola dependensi pada proyek Maven atau Gradle.

## Menyiapkan Aspose.Slides untuk Java

Untuk mengintegrasikan Aspose.Slides ke dalam proyek Anda, ikuti langkah-langkah berikut berdasarkan alat pembuatan Anda:

**Pengaturan Maven:**
Tambahkan dependensi berikut ke `pom.xml` mengajukan:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Pengaturan Gradle:**
Sertakan hal berikut dalam formulir Anda `build.gradle` mengajukan:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Unduh Langsung:**
Atau, unduh versi terbaru langsung dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

### Mendapatkan Lisensi

Untuk menggunakan Aspose.Slides tanpa batasan evaluasi:
- **Uji Coba Gratis:** Mulailah dengan lisensi sementara untuk menjelajahi fitur lengkap.
- **Lisensi Sementara:** Dapatkan satu melalui [Situs web Aspose](https://purchase.aspose.com/temporary-license/).
- **Pembelian:** Pertimbangkan pembelian untuk penggunaan berkelanjutan.

Terapkan lisensi Anda di aplikasi Java Anda menggunakan:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Panduan Implementasi

### Inisialisasi Presentasi dan Bagan

#### Ringkasan
Mulailah dengan menginisialisasi objek presentasi dan menambahkan bagan Donat ke slide pertama.

**Langkah 1: Inisialisasi Presentasi**
Muat file PPTX yang ada atau buat yang baru:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Langkah 2: Tambahkan Bagan Donat**
Buat bagan pada slide pertama pada koordinat yang ditentukan:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Mengonfigurasi Buku Kerja Data Bagan dan Menghapus Seri/Kategori yang Ada

#### Ringkasan
Konfigurasikan buku kerja data bagan dan hapus seri atau kategori yang sudah ada sebelumnya.

**Langkah 1: Akses Buku Kerja Data Bagan**
Ambil buku kerja yang ditautkan dengan bagan Anda:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Langkah 2: Hapus Seri dan Kategori yang Ada**
Pastikan tidak ada titik data sisa:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Menambahkan Seri ke Bagan

#### Ringkasan
Isi bagan Anda dengan beberapa seri, masing-masing disesuaikan untuk tampilan dan perilaku.

**Langkah 1: Tambahkan Seri Secara Iteratif**
Ulangi indeks untuk menambahkan seri:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Sesuaikan seri
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Menambahkan Kategori dan Titik Data ke Bagan

#### Ringkasan
Konfigurasikan kategori dan tambahkan titik data dengan format khusus untuk label.

**Langkah 1: Tambahkan Kategori**
Ulangi indeks untuk setiap kategori:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Langkah 2: Tambahkan Titik Data ke Setiap Seri**
Ulangi setiap seri untuk kategori saat ini:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Pengaturan format titik data
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Pemformatan label untuk seri terakhir
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Sesuaikan opsi tampilan
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Sesuaikan posisi label
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Menyimpan Presentasi

#### Ringkasan
Setelah Anda mengonfigurasi bagan Anda, simpan presentasi ke direktori yang ditentukan.

**Langkah 1: Simpan Presentasi**
Gunakan `save` metode untuk menulis perubahan:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Anda kini telah mempelajari cara membuat dan menyesuaikan diagram Donat di Java menggunakan Aspose.Slides. Langkah-langkah ini menyediakan dasar untuk mengintegrasikan visualisasi data yang canggih ke dalam presentasi Anda.

**Langkah Berikutnya:**
- Bereksperimenlah dengan berbagai jenis bagan yang tersedia di Aspose.Slides.
- Jelajahi opsi penyesuaian tambahan seperti warna, font, dan gaya untuk memenuhi kebutuhan merek Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}