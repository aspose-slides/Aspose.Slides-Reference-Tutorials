---
"description": "Pelajari cara menambahkan warna ke titik data di slide Java menggunakan Aspose.Slides untuk Java."
"linktitle": "Menambahkan Warna ke Titik Data di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menambahkan Warna ke Titik Data di Java Slides"
"url": "/id/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Warna ke Titik Data di Java Slides


## Pengantar Menambahkan Warna ke Titik Data di Slide Java

Dalam tutorial ini, kami akan menunjukkan cara menambahkan warna ke titik data di slide Java menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah ini menyertakan contoh kode sumber untuk membantu Anda mencapai tugas ini.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

- Lingkungan Pengembangan Java
- Aspose.Slides untuk pustaka Java

## Langkah 1: Buat Presentasi Baru

Pertama, kita akan membuat presentasi baru menggunakan Aspose.Slides for Java. Presentasi ini akan berfungsi sebagai wadah untuk diagram kita.

```java
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan Sunburst

Sekarang, mari tambahkan bagan Sunburst ke presentasi. Kita tentukan jenis bagan, posisi, dan ukuran.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Langkah 3: Akses Titik Data

Untuk mengubah titik data pada grafik, kita perlu mengakses `IChartDataPointCollection` obyek.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Langkah 4: Kustomisasi Titik Data

Pada langkah ini, kita akan menyesuaikan titik data tertentu. Di sini, kita akan mengubah warna titik data dan mengonfigurasi pengaturan label.

```java
// Sesuaikan titik data 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Sesuaikan titik data 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Langkah 5: Simpan Presentasi

Terakhir, simpan presentasi dengan bagan yang disesuaikan.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil menambahkan warna ke titik data tertentu dalam slide Java menggunakan Aspose.Slides untuk Java.

## Source Code Lengkap Untuk Menambahkan Warna ke Titik Data di Java Slides

```java
Presentation pres = new Presentation();
try
{
	// Jalur ke direktori dokumen.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//YANG HARUS DILAKUKAN
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda mempelajari cara menambahkan warna ke titik data dalam slide Java menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan lebih lanjut diagram dan presentasi berdasarkan kebutuhan spesifik Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah warna titik data lainnya?

Untuk mengubah warna titik data lainnya, Anda dapat mengikuti pendekatan serupa seperti yang ditunjukkan pada Langkah 4. Akses titik data yang ingin Anda sesuaikan dan ubah pengaturan warna dan labelnya.

### Bisakah saya menyesuaikan aspek lain dari bagan?

Ya, Anda dapat menyesuaikan berbagai aspek bagan, termasuk font, label, judul, dan lainnya. Lihat [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/) untuk pilihan penyesuaian terperinci.

### Di mana saya dapat menemukan lebih banyak contoh dan dokumentasi?

Anda dapat menemukan lebih banyak contoh dan dokumentasi terperinci tentang penggunaan Aspose.Slides untuk Java di [Dokumentasi Aspose.Slides](https://reference.aspose.com/slides/java/) situs web.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}