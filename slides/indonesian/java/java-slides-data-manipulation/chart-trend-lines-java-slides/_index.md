---
title: Garis Tren Bagan di Slide Java
linktitle: Garis Tren Bagan di Slide Java
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara menambahkan berbagai garis tren ke Java Slides menggunakan Aspose.Slides for Java. Panduan langkah demi langkah dengan contoh kode untuk visualisasi data yang efektif.
weight: 15
url: /id/java/data-manipulation/chart-trend-lines-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Pengantar Garis Tren Bagan di Slide Java: Panduan Langkah demi Langkah

Dalam panduan komprehensif ini, kita akan mempelajari cara membuat garis tren grafik di Java Slides menggunakan Aspose.Slides untuk Java. Garis tren bagan dapat menjadi tambahan berharga untuk presentasi Anda, membantu memvisualisasikan dan menganalisis tren data secara efektif. Kami akan memandu Anda melalui prosesnya dengan penjelasan yang jelas dan contoh kode.

## Prasyarat

Sebelum kita mulai membuat garis tren grafik, pastikan Anda memiliki prasyarat berikut:

- Lingkungan Pengembangan Jawa
- Aspose.Slide untuk Perpustakaan Java
- Editor Kode Pilihan Anda

## Langkah 1: Memulai

Mari kita mulai dengan menyiapkan lingkungan yang diperlukan dan membuat presentasi baru:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Membuat presentasi kosong
Presentation pres = new Presentation();
```

Kami telah menginisialisasi presentasi kami, dan sekarang kami siap untuk menambahkan bagan kolom berkerumun:

```java
// Membuat bagan kolom berkerumun
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Langkah 2: Menambahkan Garis Tren Eksponensial

Mari kita mulai dengan menambahkan garis tren eksponensial ke rangkaian grafik kita:

```java
// Menambahkan garis tren eksponensial untuk seri grafik 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Langkah 3: Menambahkan Garis Tren Linier

Selanjutnya, kita akan menambahkan garis tren linier ke rangkaian grafik kita:

```java
// Menambahkan garis tren linier untuk seri grafik 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Langkah 4: Menambahkan Garis Tren Logaritmik

Sekarang, mari tambahkan garis tren logaritmik ke rangkaian grafik yang berbeda:

```java
// Menambahkan garis tren logaritmik untuk seri grafik 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Langkah 5: Menambahkan Garis Tren Rata-Rata Bergerak

Kita juga dapat menambahkan garis tren moving average:

```java
// Menambahkan garis tren rata-rata bergerak untuk seri grafik 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Langkah 6: Menambahkan Garis Tren Polinomial

Menambahkan garis tren polinomial:

```java
// Menambahkan garis tren polinomial untuk seri grafik 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Langkah 7: Menambahkan Garis Tren Kekuatan

Terakhir, mari tambahkan garis tren kekuatan:

```java
// Menambahkan garis tren kekuatan untuk seri grafik 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Langkah 8: Menyimpan Presentasi

Sekarang kita telah menambahkan berbagai garis tren ke grafik kita, mari simpan presentasinya:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Selamat! Anda telah berhasil membuat presentasi dengan berbagai jenis garis tren di Java Slides menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap Untuk Garis Tren Bagan di Slide Java

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Membuat presentasi kosong
Presentation pres = new Presentation();
// Membuat bagan kolom berkerumun
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Menambahkan garis tren ponensial untuk seri grafik 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Menambahkan garis tren Linear untuk seri grafik 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Menambahkan garis tren Logaritmik untuk seri grafik 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Menambahkan garis tren MovingAverage untuk seri grafik 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Menambahkan garis tren Polinomial untuk seri grafik 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Menambahkan garis tren Kekuatan untuk seri grafik 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Menyimpan presentasi
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menambahkan berbagai jenis garis tren ke bagan di Slide Java menggunakan pustaka Aspose.Slides untuk Java. Baik Anda sedang mengerjakan analisis data atau membuat presentasi informatif, kemampuan memvisualisasikan tren dapat menjadi alat yang ampuh.

## FAQ

### Bagaimana cara mengubah warna garis tren di Aspose.Slides untuk Java?

 Untuk mengubah warna garis tren, Anda dapat menggunakan`getSolidFillColor().setColor(Color)` metode, seperti yang ditunjukkan pada contoh untuk menambahkan garis tren linier.

### Bisakah saya menambahkan beberapa garis tren ke satu rangkaian grafik?

Ya, Anda dapat menambahkan beberapa garis tren ke satu rangkaian grafik. Cukup hubungi`getTrendLines().add()` metode untuk setiap garis tren yang ingin Anda tambahkan.

### Bagaimana cara menghapus garis tren dari grafik di Aspose.Slides untuk Java?

 Untuk menghapus garis tren dari grafik, Anda dapat menggunakan`removeAt(int index)` metode, menentukan indeks garis tren yang ingin Anda hapus.

### Apakah mungkin untuk menyesuaikan tampilan persamaan garis tren?

 Ya, Anda dapat menyesuaikan tampilan persamaan garis tren menggunakan`setDisplayEquation(boolean)` metode, seperti yang ditunjukkan dalam contoh.

### Bagaimana saya bisa mengakses lebih banyak sumber daya dan contoh untuk Aspose.Slides untuk Java?

 Anda dapat mengakses sumber daya tambahan, dokumentasi, dan contoh untuk Aspose.Slides untuk Java di[Asumsikan situs web](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
