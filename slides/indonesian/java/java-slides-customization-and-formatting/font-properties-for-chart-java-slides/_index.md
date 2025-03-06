---
title: Properti Font untuk Bagan di Slide Java
linktitle: Properti Font untuk Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Tingkatkan Properti Font Bagan di Slide Java dengan Aspose.Slides untuk Java. Sesuaikan ukuran font, gaya, dan warna untuk presentasi yang berdampak.
weight: 11
url: /id/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Properti Font untuk Bagan di Slide Java


## Pengantar Properti Font untuk Bagan di Slide Java

Panduan ini akan memandu Anda dalam mengatur properti font untuk bagan di Java Slides menggunakan Aspose.Slides. Anda dapat menyesuaikan ukuran font dan tampilan teks bagan untuk meningkatkan daya tarik visual presentasi Anda.

## Prasyarat

 Sebelum memulai, pastikan Anda memiliki Aspose.Slides for Java API yang terintegrasi ke dalam proyek Anda. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi

Pertama, buat presentasi baru menggunakan kode berikut:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan

Sekarang, mari tambahkan bagan kolom berkerumun ke presentasi Anda:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Di sini, kami menambahkan bagan kolom berkerumun pada slide pertama pada koordinat (100, 100) dengan lebar 500 unit dan tinggi 400 unit.

## Langkah 3: Sesuaikan Properti Font

Selanjutnya, kita akan menyesuaikan properti font pada grafik. Dalam contoh ini, kami mengatur ukuran font menjadi 20 untuk semua teks bagan:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Kode ini menetapkan ukuran font menjadi 20 poin untuk semua teks dalam bagan.

## Langkah 4: Tampilkan Label Data

Anda juga dapat menampilkan label data pada bagan menggunakan kode berikut:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Baris kode ini mengaktifkan label data untuk rangkaian pertama dalam bagan, menampilkan nilai pada kolom bagan.

## Langkah 5: Simpan Presentasi

Terakhir, simpan presentasi dengan properti font bagan kustom Anda:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Kode ini akan menyimpan presentasi ke direktori tertentu dengan nama file "FontPropertiesForChart.pptx."

## Kode Sumber Lengkap Untuk Properti Font untuk Bagan di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengkustomisasi properti font untuk bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda dapat menerapkan teknik ini untuk menyempurnakan tampilan bagan dan presentasi Anda. Jelajahi opsi lainnya di[Aspose.Slides untuk dokumentasi Java](https://reference.aspose.com/slides/java/).

## FAQ

### Bagaimana cara mengubah warna font?

 Untuk mengubah warna font pada teks bagan, gunakan`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , menggantikan`Color.RED` dengan warna yang diinginkan.

### Bisakah saya mengubah gaya font (tebal, miring, dll.)?

 Ya, Anda dapat mengubah gaya font. Menggunakan`chart.getTextFormat().getPortionFormat().setFontBold(true);` untuk membuat font menjadi tebal. Demikian pula, Anda dapat menggunakan`setFontItalic(true)` untuk membuatnya miring.

### Bagaimana cara menyesuaikan properti font untuk elemen bagan tertentu?

Untuk mengkustomisasi properti font untuk elemen bagan tertentu, seperti label sumbu atau teks legenda, Anda dapat mengakses elemen tersebut dan mengatur properti fontnya menggunakan metode serupa seperti yang ditunjukkan di atas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
