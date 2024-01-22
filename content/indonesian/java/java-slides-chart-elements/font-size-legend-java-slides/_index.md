---
title: Legenda Ukuran Font di Slide Java
linktitle: Legenda Ukuran Font di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Sempurnakan presentasi PowerPoint dengan Aspose.Slides untuk Java. Pelajari cara menyesuaikan ukuran font legenda dan lainnya di panduan langkah demi langkah kami.
type: docs
weight: 13
url: /id/java/chart-elements/font-size-legend-java-slides/
---

## Pengantar Legenda Ukuran Font di Slide Java

Dalam tutorial ini, Anda akan mempelajari cara menyesuaikan ukuran font legenda di slide PowerPoint menggunakan Aspose.Slides untuk Java. Kami akan memberikan petunjuk langkah demi langkah dan kode sumber untuk mencapai tugas ini.

## Prasyarat

 Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides untuk Java di proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Inisialisasi Presentasi

Pertama, impor kelas yang diperlukan dan inisialisasi presentasi PowerPoint Anda.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Mengganti`"Your Document Directory"` dengan jalur sebenarnya ke file PowerPoint Anda.

## Langkah 2: Tambahkan Bagan

Selanjutnya, kita akan menambahkan bagan ke slide dan mengatur ukuran font legenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 Dalam kode ini, kita membuat bagan kolom berkerumun pada slide pertama dan mengatur ukuran font teks legenda menjadi 20 poin. Anda dapat menyesuaikannya`setFontHeight`nilai untuk mengubah ukuran font sesuai kebutuhan.

## Langkah 3: Sesuaikan Nilai Sumbu

Sekarang, mari sesuaikan nilai sumbu vertikal bagan.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Di sini, kami menetapkan nilai minimum dan maksimum untuk sumbu vertikal. Anda dapat mengubah nilainya sesuai kebutuhan data Anda.

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

## Kode Sumber Lengkap Untuk Legenda Ukuran Font di Slide Java

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

Anda telah berhasil mengkustomisasi ukuran font legenda dalam slide Java PowerPoint menggunakan Aspose.Slides untuk Java. Anda dapat mengeksplorasi lebih jauh kemampuan Aspose.Slides untuk membuat presentasi yang interaktif dan menarik secara visual.

## FAQ

### Bagaimana cara mengubah ukuran font teks legenda dalam bagan?

Untuk mengubah ukuran font teks legenda dalam bagan, Anda dapat menggunakan kode berikut:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 Dalam kode ini, kita membuat bagan dan mengatur ukuran font teks legenda menjadi 20 poin. Anda dapat menyesuaikannya`setFontHeight`nilai untuk mengubah ukuran font.

### Bisakah saya mengkustomisasi properti legenda lainnya dalam bagan?

Ya, Anda dapat mengkustomisasi berbagai properti legenda dalam bagan menggunakan Aspose.Slides. Beberapa properti umum yang dapat Anda sesuaikan mencakup pemformatan teks, posisi, visibilitas, dan lainnya. Misalnya, untuk mengubah posisi legenda, Anda dapat menggunakan:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Kode ini mengatur legenda untuk muncul di bagian bawah grafik. Jelajahi dokumentasi Aspose.Slides untuk opsi penyesuaian lainnya.

### Bagaimana cara menetapkan nilai minimum dan maksimum untuk sumbu vertikal dalam grafik?

Untuk menetapkan nilai minimum dan maksimum sumbu vertikal dalam bagan, Anda dapat menggunakan kode berikut:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Di sini, kami menonaktifkan penskalaan sumbu otomatis dan menentukan nilai minimum dan maksimum untuk sumbu vertikal. Sesuaikan nilainya sesuai kebutuhan untuk data bagan Anda.

### Di mana saya dapat menemukan informasi dan dokumentasi lebih lanjut untuk Aspose.Slides?

Anda dapat menemukan dokumentasi komprehensif dan referensi API untuk Aspose.Slides untuk Java di situs web dokumentasi Aspose. Mengunjungi[Di Sini](https://reference.aspose.com/slides/java/) untuk informasi rinci tentang penggunaan perpustakaan.