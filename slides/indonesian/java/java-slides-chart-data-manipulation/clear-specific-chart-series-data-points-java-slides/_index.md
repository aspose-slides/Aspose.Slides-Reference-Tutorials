---
"description": "Pelajari cara menghapus titik data tertentu dari rangkaian bagan di Java Slides dengan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber untuk manajemen visualisasi data yang efektif."
"linktitle": "Hapus Titik Data Seri Bagan Tertentu Data dalam Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Hapus Titik Data Seri Bagan Tertentu Data dalam Slide Java"
"url": "/id/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hapus Titik Data Seri Bagan Tertentu Data dalam Slide Java


## Pengantar untuk Menghapus Titik Data Seri Bagan Tertentu Data dalam Slide Java

Dalam tutorial ini, kami akan memandu Anda melalui proses penghapusan titik data tertentu dari rangkaian bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Ini dapat berguna saat Anda ingin menghapus titik data tertentu dari bagan untuk memperbarui atau memodifikasi visualisasi data Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah mengintegrasikan pustaka Aspose.Slides for Java ke dalam proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Muat Presentasi

Pertama, kita perlu memuat presentasi PowerPoint yang berisi grafik yang ingin Anda ubah. Ganti `"Your Document Directory"` dengan jalur sebenarnya ke berkas presentasi Anda.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## Langkah 2: Akses Bagan

Selanjutnya, kita akan mengakses diagram dari slide. Dalam contoh ini, kita asumsikan diagram berada pada slide pertama (slide pada indeks 0). Anda dapat menyesuaikan indeks slide sesuai kebutuhan.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## Langkah 3: Hapus Titik Data Spesifik

Sekarang, kita akan mengulangi titik data dari seri pertama bagan dan menghapus nilai X dan Y-nya.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

Kode ini mengulang setiap titik data dalam seri pertama (indeks 0) dan menetapkan nilai X dan Y ke `null`, secara efektif membersihkan titik data.

## Langkah 4: Hapus Titik Data yang Dihapus

Untuk memastikan titik data yang dihapus dihilangkan dari seri, kami akan menghapus seluruh seri.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

Kode ini menghapus semua titik data dari seri pertama.

## Langkah 5: Simpan Presentasi yang Dimodifikasi

Terakhir, kita akan menyimpan presentasi yang sudah dimodifikasi ke file baru.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## Source Code Lengkap Untuk Data Poin Seri Grafik Spesifik Yang Jelas di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
try
{
	ISlide sl = pres.getSlides().get_Item(0);
	IChart chart = (IChart) sl.getShapes().get_Item(0);
	for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
	{
		dataPoint.getXValue().getAsCell().setValue(null);
		dataPoint.getYValue().getAsCell().setValue(null);
	}
	chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
	pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam panduan ini, Anda telah mempelajari cara menghapus titik data tertentu dari rangkaian bagan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Ini dapat berguna saat Anda perlu memperbarui atau mengubah data bagan secara dinamis dalam aplikasi Java Anda. Jika Anda memiliki pertanyaan lebih lanjut atau memerlukan bantuan tambahan, silakan lihat [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menghapus titik data tertentu dari rangkaian bagan di Aspose.Slides untuk Java?

Untuk menghapus titik data tertentu dari rangkaian bagan di Aspose.Slides untuk Java, ikuti langkah-langkah berikut:

1. Muat presentasi.
2. Akses bagan pada slide.
3. Ulangi titik data seri yang diinginkan dan hapus nilai X dan Y-nya.
4. Hapus seluruh seri untuk membuang titik data yang dihapus.
5. Simpan presentasi yang telah dimodifikasi.

### Bisakah saya menghapus titik data dari beberapa seri dalam bagan yang sama?

Ya, Anda dapat menghapus titik data dari beberapa seri dalam bagan yang sama dengan mengulangi titik data setiap seri dan menghapusnya satu per satu.

### Apakah ada cara untuk menghapus titik data berdasarkan kondisi atau kriteria?

Ya, Anda dapat menghapus titik data berdasarkan suatu kondisi dengan menambahkan logika kondisional dalam loop yang berulang melalui titik data tersebut. Anda dapat memeriksa nilai titik data dan memutuskan apakah akan menghapusnya atau tidak berdasarkan kriteria Anda.

### Bagaimana cara menambahkan titik data baru ke rangkaian bagan menggunakan Aspose.Slides untuk Java?

Untuk menambahkan titik data baru ke rangkaian grafik, Anda dapat menggunakan `addDataPoint` metode seri. Cukup buat titik data baru dan tambahkan ke seri menggunakan metode ini.

### Di mana saya dapat menemukan informasi lebih lanjut tentang Aspose.Slides untuk Java?

Anda dapat menemukan dokumentasi dan contoh yang lengkap di [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}