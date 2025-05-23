---
"description": "Sempurnakan presentasi PowerPoint dengan Aspose.Slides untuk Java. Pelajari cara menyesuaikan ukuran font legenda dan lainnya dalam panduan langkah demi langkah kami."
"linktitle": "Legenda Ukuran Font di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Legenda Ukuran Font di Java Slides"
"url": "/id/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Legenda Ukuran Font di Java Slides


## Pengenalan Legenda Ukuran Font di Java Slides

Dalam tutorial ini, Anda akan mempelajari cara menyesuaikan ukuran font legenda dalam slide PowerPoint menggunakan Aspose.Slides untuk Java. Kami akan memberikan petunjuk langkah demi langkah dan kode sumber untuk menyelesaikan tugas ini.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Inisialisasi Presentasi

Pertama, impor kelas yang diperlukan dan inisialisasi presentasi PowerPoint Anda.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Mengganti `"Your Document Directory"` dengan jalur sebenarnya ke berkas PowerPoint Anda.

## Langkah 2: Tambahkan Bagan

Berikutnya, kita akan menambahkan bagan ke slide dan mengatur ukuran font legenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Dalam kode ini, kita membuat bagan kolom berkelompok pada slide pertama dan mengatur ukuran font teks legenda menjadi 20 poin. Anda dapat menyesuaikan `setFontHeight` nilai untuk mengubah ukuran font sesuai kebutuhan.

## Langkah 3: Sesuaikan Nilai Sumbu

Sekarang, mari kita sesuaikan nilai sumbu vertikal bagan.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Di sini, kami menetapkan nilai minimum dan maksimum untuk sumbu vertikal. Anda dapat mengubah nilai sesuai kebutuhan data Anda.

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi yang dimodifikasi ke file baru.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Kode ini menyimpan presentasi yang dimodifikasi sebagai "output.pptx" di direktori yang ditentukan.

## Source Code Lengkap Legenda Ukuran Font di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Anda telah berhasil menyesuaikan ukuran font legenda dalam slide PowerPoint Java menggunakan Aspose.Slides untuk Java. Anda dapat mengeksplorasi lebih lanjut kemampuan Aspose.Slides untuk membuat presentasi yang interaktif dan menarik secara visual.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah ukuran font teks legenda pada bagan?

Untuk mengubah ukuran font teks legenda dalam bagan, Anda dapat menggunakan kode berikut:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

Dalam kode ini, kita membuat grafik dan mengatur ukuran font teks legenda menjadi 20 poin. Anda dapat menyesuaikan `setFontHeight` nilai untuk mengubah ukuran font.

### Bisakah saya menyesuaikan properti legenda lainnya dalam bagan?

Ya, Anda dapat menyesuaikan berbagai properti legenda dalam bagan menggunakan Aspose.Slides. Beberapa properti umum yang dapat Anda sesuaikan meliputi pemformatan teks, posisi, visibilitas, dan banyak lagi. Misalnya, untuk mengubah posisi legenda, Anda dapat menggunakan:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Kode ini mengatur legenda agar muncul di bagian bawah bagan. Jelajahi dokumentasi Aspose.Slides untuk opsi penyesuaian lebih lanjut.

### Bagaimana cara menetapkan nilai minimum dan maksimum untuk sumbu vertikal dalam bagan?

Untuk menetapkan nilai minimum dan maksimum untuk sumbu vertikal dalam bagan, Anda dapat menggunakan kode berikut:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Di sini, kami menonaktifkan penskalaan sumbu otomatis dan menentukan nilai minimum dan maksimum untuk sumbu vertikal. Sesuaikan nilai sesuai kebutuhan untuk data bagan Anda.

### Di mana saya dapat menemukan informasi dan dokumentasi lebih lanjut untuk Aspose.Slides?

Anda dapat menemukan dokumentasi lengkap dan referensi API untuk Aspose.Slides for Java di situs web dokumentasi Aspose. Kunjungi [Di Sini](https://reference.aspose.com/slides/java/) untuk informasi terperinci tentang penggunaan perpustakaan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}