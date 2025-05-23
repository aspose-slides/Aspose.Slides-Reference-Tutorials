---
"description": "Buat Bagan Sunburst yang Menakjubkan di Java Slides dengan Aspose.Slides. Pelajari Pembuatan Bagan dan Manipulasi Data Langkah demi Langkah."
"linktitle": "Bagan Sunburst dalam Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Bagan Sunburst dalam Java Slides"
"url": "/id/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bagan Sunburst dalam Java Slides


## Pengenalan Grafik Sunburst di Java Slides dengan Aspose.Slides

Dalam tutorial ini, Anda akan mempelajari cara membuat bagan Sunburst dalam presentasi PowerPoint menggunakan Aspose.Slides for Java API. Bagan Sunburst adalah bagan radial yang digunakan untuk merepresentasikan data hierarkis. Kami akan memberikan petunjuk langkah demi langkah beserta kode sumbernya.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Impor Pustaka yang Diperlukan

Pertama, impor pustaka yang diperlukan untuk bekerja dengan Aspose.Slides dan buat bagan Sunburst di aplikasi Java Anda.

```java
import com.aspose.slides.*;
```

## Langkah 2: Inisialisasi Presentasi

Inisialisasi presentasi PowerPoint dan tentukan direktori tempat file presentasi Anda akan disimpan.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Langkah 3: Buat Bagan Sunburst

Buat bagan Sunburst pada slide. Kami tentukan posisi (X, Y) dan dimensi (lebar, tinggi) bagan.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Langkah 4: Siapkan Data Bagan

Hapus semua kategori dan data seri yang ada dari bagan, lalu buat buku kerja data untuk bagan tersebut.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Langkah 5: Tentukan Hirarki Bagan

Tentukan struktur hierarki bagan Sunburst. Anda dapat menambahkan cabang, batang, dan daun sebagai kategori.

```java
// Cabang 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Cabang 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Langkah 6: Tambahkan Data ke Bagan

Tambahkan titik data ke seri bagan Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Langkah 7: Simpan Presentasi

Terakhir, simpan presentasi dengan bagan Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Grafik Sunburst di Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//cabang 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//cabang 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara membuat bagan Sunburst dalam presentasi PowerPoint menggunakan API Aspose.Slides for Java. Anda telah melihat cara menginisialisasi presentasi, membuat bagan, menentukan hierarki bagan, menambahkan titik data, dan menyimpan presentasi. Kini Anda dapat menggunakan pengetahuan ini untuk membuat bagan Sunburst yang interaktif dan informatif dalam aplikasi Java Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan tampilan bagan Sunburst?

Anda dapat menyesuaikan tampilan bagan Sunburst dengan mengubah properti seperti warna, label, dan gaya. Lihat dokumentasi Aspose.Slides untuk opsi penyesuaian terperinci.

### Bisakah saya menambahkan lebih banyak titik data ke bagan?

Ya, Anda dapat menambahkan lebih banyak titik data ke grafik dengan menggunakan `series.getDataPoints().addDataPointForSunburstSeries()` metode untuk setiap titik data yang ingin Anda sertakan.

### Bagaimana cara menambahkan tooltip ke bagan Sunburst?

Untuk menambahkan keterangan alat ke bagan Sunburst, Anda dapat mengatur format label data untuk menampilkan informasi tambahan, seperti nilai atau deskripsi, saat mengarahkan kursor ke segmen bagan.

### Mungkinkah membuat grafik Sunburst interaktif dengan hyperlink?

Ya, Anda dapat membuat bagan Sunburst interaktif dengan hyperlink dengan menambahkan hyperlink ke elemen atau segmen bagan tertentu. Lihat dokumentasi Aspose.Slides untuk detail tentang cara menambahkan hyperlink.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}