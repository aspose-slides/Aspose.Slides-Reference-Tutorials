---
title: Diagram Lingkaran di Slide Java
linktitle: Diagram Lingkaran di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara membuat Diagram Lingkaran yang menakjubkan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk pengembang Java.
weight: 23
url: /id/java/chart-data-manipulation/pie-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diagram Lingkaran di Slide Java


## Pengantar Membuat Diagram Lingkaran di Slide Java menggunakan Aspose.Slides

Dalam tutorial ini, kami akan menunjukkan cara membuat Pie Chart dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Kami akan memberi Anda petunjuk langkah demi langkah dan kode sumber Java untuk membantu Anda memulai. Panduan ini mengasumsikan Anda telah menyiapkan lingkungan pengembangan Anda dengan Aspose.Slides untuk Java.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Slides untuk Java di proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Impor Perpustakaan yang Diperlukan

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Pastikan untuk mengimpor kelas yang diperlukan dari perpustakaan Aspose.Slides.

## Langkah 2: Inisialisasi Presentasi

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";

// Buat instance kelas Presentasi yang mewakili file PPTX
Presentation presentation = new Presentation();
```

 Buat objek Presentasi baru untuk mewakili file PowerPoint Anda. Mengganti`"Your Document Directory"` dengan jalur sebenarnya tempat Anda ingin menyimpan presentasi.

## Langkah 3: Tambahkan Slide

```java
// Akses slide pertama
ISlide slide = presentation.getSlides().get_Item(0);
```

Dapatkan slide pertama presentasi di mana Anda ingin menambahkan Diagram Lingkaran.

## Langkah 4: Tambahkan Diagram Lingkaran

```java
// Tambahkan diagram lingkaran dengan data default
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Tambahkan Diagram Lingkaran ke slide pada posisi dan ukuran yang ditentukan.

## Langkah 5: Tetapkan Judul Bagan

```java
// Tetapkan judul bagan
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Tetapkan judul untuk Diagram Lingkaran. Anda dapat menyesuaikan judul sesuai kebutuhan.

## Langkah 6: Sesuaikan Data Bagan

```java
//Atur rangkaian pertama untuk menampilkan nilai
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;

// Mendapatkan lembar kerja data bagan
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Hapus seri dan kategori yang dihasilkan secara default
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Menambahkan kategori baru
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Menambahkan seri baru
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Mengisi data seri
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Sesuaikan data bagan dengan menambahkan kategori dan seri, serta mengatur nilainya. Dalam contoh ini, kami memiliki tiga kategori dan satu rangkaian dengan titik data yang sesuai.

## Langkah 7: Sesuaikan Sektor Diagram Lingkaran

```java
// Tetapkan warna sektor
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Sesuaikan tampilan setiap sektor
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Sesuaikan batas sektor
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Sesuaikan sektor lain dengan cara yang sama
```

Sesuaikan tampilan setiap sektor di Pie Chart. Anda dapat mengubah warna, gaya batas, dan properti visual lainnya.

## Langkah 8: Sesuaikan Label Data

```java
// Sesuaikan label data
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Sesuaikan label data untuk titik data lain dengan cara yang sama
```

Sesuaikan label data untuk setiap titik data di Diagram Lingkaran. Anda dapat mengontrol nilai mana yang ditampilkan pada grafik.

## Langkah 9: Tunjukkan Garis Pemimpin

```java
// Tampilkan garis pemimpin untuk bagan
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Aktifkan garis pemimpin untuk menghubungkan label data ke sektor terkait.

## Langkah 10: Atur Sudut Rotasi Diagram Lingkaran

```java
// Atur sudut rotasi untuk sektor Diagram Lingkaran
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Atur sudut rotasi untuk sektor Diagram Lingkaran. Dalam contoh ini, kami mengaturnya menjadi 180 derajat.

## Langkah 11: Simpan Presentasi

```java
// Simpan presentasi dengan Pie Chart
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Simpan presentasi dengan Pie Chart ke direktori yang ditentukan.

## Kode Sumber Lengkap Untuk Diagram Lingkaran di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat instance kelas Presentasi yang mewakili file PPTX
Presentation presentation = new Presentation();
// Akses slide pertama
ISlide slides = presentation.getSlides().get_Item(0);
// Tambahkan bagan dengan data default
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Judul bagan pengaturan
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Setel seri pertama ke Tampilkan Nilai
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Mengatur indeks lembar data grafik
int defaultWorksheetIndex = 0;
// Mendapatkan lembar kerja data bagan
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Hapus seri dan kategori yang dihasilkan secara default
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Menambahkan kategori baru
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Menambahkan seri baru
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Sekarang mengisi data seri
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Tidak berfungsi di versi baru
// Menambahkan titik baru dan mengatur warna sektor
// seri.IsColorVaried = benar;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Menetapkan batas Sektor
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Menetapkan batas Sektor
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Menetapkan batas Sektor
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Buat label khusus untuk setiap kategori untuk seri baru
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(benar);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Menampilkan Garis Pemimpin untuk Bagan
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Mengatur Sudut Rotasi untuk Sektor Diagram Lingkaran
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Simpan presentasi dengan bagan
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Anda telah berhasil membuat Diagram Lingkaran dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan tampilan bagan dan label data sesuai dengan kebutuhan spesifik Anda. Tutorial ini memberikan contoh dasar, dan Anda dapat lebih menyempurnakan dan menyesuaikan grafik sesuai kebutuhan.

## FAQ

### Bagaimana cara mengubah warna masing-masing sektor di Diagram Lingkaran?

 Untuk mengubah warna masing-masing sektor dalam Diagram Lingkaran, Anda dapat menyesuaikan warna isian untuk setiap titik data. Dalam contoh kode yang diberikan, kami mendemonstrasikan cara mengatur warna isian untuk setiap sektor menggunakan`getSolidFillColor().setColor()` metode. Anda dapat mengubah nilai warna untuk mendapatkan tampilan yang diinginkan.

### Bisakah saya menambahkan lebih banyak kategori dan rangkaian data ke Diagram Lingkaran?

 Ya, Anda dapat menambahkan kategori dan rangkaian data tambahan ke Diagram Lingkaran. Untuk melakukan ini, Anda dapat menggunakan`getChartData().getCategories().add()` Dan`getChartData().getSeries().add()` metode, seperti yang ditunjukkan pada contoh. Cukup berikan data dan label yang sesuai untuk kategori dan rangkaian baru untuk memperluas bagan Anda.

### Bagaimana cara menyesuaikan tampilan label data?

 Anda dapat menyesuaikan tampilan label data menggunakan`getDataLabelFormat()` metode pada label setiap titik data. Dalam contoh tersebut, kami mendemonstrasikan cara menampilkan nilai pada label data menggunakan`getDataLabelFormat().setShowValue(true)`. Anda dapat menyesuaikan label data lebih lanjut dengan mengontrol nilai mana yang ditampilkan, menampilkan kunci legenda, dan menyesuaikan opsi pemformatan lainnya.

### Bisakah saya mengubah judul Diagram Lingkaran?

 Ya, Anda dapat mengubah judul Diagram Lingkaran. Dalam kode yang disediakan, kami mengatur judul grafik menggunakan`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Anda bisa menggantinya`"Sample Title"` dengan teks judul yang Anda inginkan.

### Bagaimana cara menyimpan presentasi yang dihasilkan dengan Pie Chart?

 Untuk menyimpan presentasi dengan Pie Chart, gunakan`presentation.save()` metode. Berikan jalur dan nama file yang diinginkan beserta format tempat Anda ingin menyimpan presentasi. Misalnya:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Pastikan untuk menentukan jalur dan format file yang benar.

### Bisakah saya membuat tipe bagan lain menggunakan Aspose.Slides untuk Java?

Ya, Aspose.Slides untuk Java mendukung berbagai jenis bagan, termasuk Bagan Batang, Bagan Garis, dan banyak lagi. Anda dapat membuat berbagai jenis bagan dengan mengubah`ChartType` saat menambahkan bagan. Lihat dokumentasi Aspose.Slides untuk detail selengkapnya tentang pembuatan berbagai jenis bagan.

### Bagaimana saya dapat menemukan informasi lebih lanjut dan contoh untuk bekerja dengan Aspose.Slides untuk Java?

 Untuk informasi lebih lanjut, dokumentasi terperinci, dan contoh tambahan, Anda dapat mengunjungi[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/). Ini menyediakan sumber daya yang komprehensif untuk membantu Anda menggunakan perpustakaan secara efektif.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
