---
"description": "Pelajari cara mengatur format tanggal untuk sumbu kategori dalam bagan PowerPoint menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber."
"linktitle": "Mengatur Format Tanggal Untuk Sumbu Kategori di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Format Tanggal Untuk Sumbu Kategori di Java Slides"
"url": "/id/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Format Tanggal Untuk Sumbu Kategori di Java Slides


## Pengantar Pengaturan Format Tanggal Untuk Sumbu Kategori di Java Slides

Dalam tutorial ini, kita akan mempelajari cara mengatur format tanggal untuk sumbu kategori dalam bagan PowerPoint menggunakan Aspose.Slides untuk Java. Aspose.Slides untuk Java adalah pustaka canggih yang memungkinkan Anda membuat, memanipulasi, dan mengelola presentasi PowerPoint secara terprogram.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Slides untuk pustaka Java (Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).
2. Lingkungan pengembangan Java telah disiapkan.

## Langkah 1: Buat Presentasi PowerPoint

Pertama, kita perlu membuat presentasi PowerPoint tempat kita akan menambahkan diagram. Pastikan Anda telah mengimpor kelas Aspose.Slides yang diperlukan.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide

Sekarang, mari tambahkan diagram ke slide PowerPoint. Kita akan menggunakan diagram Area dalam contoh ini.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Langkah 3: Siapkan Data Bagan

Kita akan mengatur data dan kategori grafik. Dalam contoh ini, kita akan menggunakan kategori tanggal.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Menambahkan kategori tanggal
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Menambahkan seri data
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Langkah 4: Sesuaikan Sumbu Kategori
Sekarang, mari sesuaikan sumbu kategori untuk menampilkan tanggal dalam format tertentu (misalnya, yyyy).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Langkah 5: Simpan Presentasi
Terakhir, simpan presentasi PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil menetapkan format tanggal untuk sumbu kategori dalam bagan PowerPoint menggunakan Aspose.Slides untuk Java.

## Source Code Lengkap Untuk Setting Format Tanggal Untuk Kategori Axis di Java Slides

```java
	// Jalur ke direktori dokumen.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Kesimpulan

Anda telah berhasil menyesuaikan format tanggal untuk sumbu kategori dalam bagan Java Slides menggunakan Aspose.Slides untuk Java. Ini memungkinkan Anda untuk menyajikan nilai tanggal dalam format yang diinginkan pada bagan Anda. Jangan ragu untuk menjelajahi opsi penyesuaian lebih lanjut berdasarkan persyaratan khusus Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah format tanggal untuk sumbu kategori?

Untuk mengubah format tanggal untuk sumbu kategori, gunakan `setNumberFormat` metode pada sumbu kategori dan memberikan pola format tanggal yang diinginkan, seperti "yyyy-MM-dd" atau "MM/yyyy". Pastikan untuk mengatur `setNumberFormatLinkedToSource(false)` untuk mengesampingkan format default.

### Dapatkah saya menggunakan format tanggal yang berbeda untuk bagan yang berbeda dalam presentasi yang sama?

Ya, Anda dapat mengatur format tanggal yang berbeda untuk sumbu kategori dalam bagan yang berbeda dalam presentasi yang sama. Cukup sesuaikan sumbu kategori untuk setiap bagan sesuai kebutuhan.

### Bagaimana cara menambahkan lebih banyak titik data ke bagan?

Untuk menambahkan lebih banyak titik data ke grafik, gunakan `getDataPoints().addDataPointForLineSeries` metode pada rangkaian data dan memberikan nilai data.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}