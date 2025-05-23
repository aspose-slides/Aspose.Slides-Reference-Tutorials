---
"description": "Pelajari cara menyembunyikan elemen bagan di Java Slides dengan Aspose.Slides untuk Java. Sesuaikan presentasi agar lebih jelas dan estetis dengan panduan langkah demi langkah dan kode sumber."
"linktitle": "Sembunyikan Informasi dari Bagan di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Sembunyikan Informasi dari Bagan di Java Slides"
"url": "/id/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sembunyikan Informasi dari Bagan di Java Slides


## Pengantar Menyembunyikan Informasi dari Bagan di Java Slides

Dalam tutorial ini, kita akan menjelajahi cara menyembunyikan berbagai elemen dari bagan di Java Slides menggunakan Aspose.Slides for Java API. Anda dapat menggunakan kode ini untuk menyesuaikan bagan sesuai kebutuhan untuk presentasi Anda.

## Langkah 1: Menyiapkan Lingkungan

Sebelum kita mulai, pastikan Anda telah menambahkan pustaka Aspose.Slides for Java ke proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 2: Buat Presentasi Baru

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 3: Menambahkan Bagan ke Slide

Kita akan menambahkan diagram garis dengan penanda ke slide, lalu melanjutkan dengan menyembunyikan berbagai elemen diagram.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Langkah 4: Sembunyikan Judul Bagan

Anda dapat menyembunyikan judul grafik sebagai berikut:

```java
chart.setTitle(false);
```

## Langkah 5: Sembunyikan Nilai Sumbu

Untuk menyembunyikan sumbu nilai (sumbu vertikal), gunakan kode berikut:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Langkah 6: Sembunyikan Sumbu Kategori

Untuk menyembunyikan sumbu kategori (sumbu horizontal), gunakan kode ini:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Langkah 7: Sembunyikan Legenda

Anda dapat menyembunyikan legenda grafik seperti ini:

```java
chart.setLegend(false);
```

## Langkah 8: Sembunyikan Garis Grid Utama

Untuk menyembunyikan garis kisi utama sumbu horizontal, Anda dapat menggunakan kode berikut:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Langkah 9: Hapus Seri

Jika Anda ingin menghapus semua seri dari bagan, Anda dapat menggunakan loop seperti ini:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Langkah 10: Kustomisasi Seri Bagan

Anda dapat menyesuaikan rangkaian diagram sesuai kebutuhan. Dalam contoh ini, kami mengubah gaya penanda, posisi label data, ukuran penanda, warna garis, dan gaya garis putus-putus:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Langkah 11: Simpan Presentasi

Terakhir, simpan presentasi ke sebuah file:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Selesai! Anda telah berhasil menyembunyikan berbagai elemen dari bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan lebih lanjut bagan dan presentasi sesuai kebutuhan khusus Anda.

## Source Code Lengkap Untuk Menyembunyikan Informasi dari Bagan di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Menyembunyikan Judul Bagan
	chart.setTitle(false);
	///Menyembunyikan sumbu Nilai
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Visibilitas Sumbu Kategori
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Menyembunyikan Legenda
	chart.setLegend(false);
	//Menyembunyikan MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Mengatur warna garis seri
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Kesimpulan

Dalam panduan langkah demi langkah ini, kami telah menjelajahi cara menyembunyikan berbagai elemen dari bagan di Java Slides menggunakan Aspose.Slides for Java API. Ini dapat sangat berguna saat Anda perlu menyesuaikan bagan untuk presentasi dan membuatnya lebih menarik secara visual atau disesuaikan dengan kebutuhan spesifik Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan tampilan elemen bagan lebih lanjut?

Anda dapat menyesuaikan berbagai properti elemen bagan seperti warna garis, warna isian, gaya penanda, dan lainnya dengan mengakses properti yang sesuai dari seri bagan, penanda, label, dan format.

### Bisakah saya menyembunyikan titik data tertentu dalam bagan?

Ya, Anda dapat menyembunyikan titik data tertentu dengan memanipulasi data dalam rangkaian diagram. Anda dapat menghapus titik data atau menyetel nilainya ke null untuk menyembunyikannya.

### Bagaimana cara menambahkan seri tambahan ke bagan?

Anda dapat menambahkan lebih banyak seri ke bagan dengan menggunakan `IChartData.getSeries().add` metode dan menentukan titik data untuk seri baru.

### Apakah mungkin untuk mengubah jenis grafik secara dinamis?

Ya, Anda dapat mengubah jenis bagan secara dinamis dengan membuat bagan baru dengan jenis yang diinginkan dan menyalin data dari bagan lama ke bagan baru.

### Bagaimana cara mengubah judul grafik dan label sumbu secara terprogram?

Anda dapat mengatur judul dan label bagan dan sumbu dengan mengakses propertinya masing-masing dan mengatur teks dan format yang diinginkan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}