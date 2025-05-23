---
"description": "Pelajari cara menambahkan berbagai garis tren ke Java Slides menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan contoh kode untuk visualisasi data yang efektif."
"linktitle": "Garis Tren Grafik di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Garis Tren Grafik di Slide Java"
"url": "/id/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Garis Tren Grafik di Slide Java


## Pengenalan Garis Tren Grafik di Java Slides: Panduan Langkah demi Langkah

Dalam panduan lengkap ini, kita akan menjelajahi cara membuat garis tren grafik di Java Slides menggunakan Aspose.Slides untuk Java. Garis tren grafik dapat menjadi tambahan yang berharga untuk presentasi Anda, membantu memvisualisasikan dan menganalisis tren data secara efektif. Kami akan memandu Anda melalui proses tersebut dengan penjelasan yang jelas dan contoh kode.

## Prasyarat

Sebelum kita mulai membuat garis tren grafik, pastikan Anda memiliki prasyarat berikut ini:

- Lingkungan Pengembangan Java
- Aspose.Slides untuk Pustaka Java
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

Kami telah menginisialisasi presentasi kami, dan sekarang kami siap untuk menambahkan bagan kolom berkelompok:

```java
// Membuat bagan kolom berkelompok
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Langkah 2: Menambahkan Garis Tren Eksponensial

Mari kita mulai dengan menambahkan garis tren eksponensial ke rangkaian grafik kita:

```java
// Menambahkan garis tren eksponensial untuk rangkaian grafik 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Langkah 3: Menambahkan Garis Tren Linier

Berikutnya, kita akan menambahkan garis tren linier ke rangkaian grafik kita:

```java
// Menambahkan garis tren linier untuk rangkaian grafik 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Langkah 4: Menambahkan Garis Tren Logaritmik

Sekarang, mari tambahkan garis tren logaritmik ke rangkaian grafik yang berbeda:

```java
// Menambahkan garis tren logaritmik untuk rangkaian grafik 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Langkah 5: Menambahkan Garis Tren Rata-rata Bergerak

Kita juga dapat menambahkan garis tren rata-rata bergerak:

```java
// Menambahkan garis tren rata-rata bergerak untuk rangkaian grafik 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Langkah 6: Menambahkan Garis Tren Polinomial

Menambahkan garis tren polinomial:

```java
// Menambahkan garis tren polinomial untuk rangkaian grafik 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Langkah 7: Menambahkan Garis Tren Daya

Terakhir, mari tambahkan garis tren daya:

```java
// Menambahkan garis tren daya untuk rangkaian grafik 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Langkah 8: Menyimpan Presentasi

Sekarang setelah kita menambahkan berbagai garis tren ke grafik kita, mari simpan presentasinya:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Selamat! Anda telah berhasil membuat presentasi dengan berbagai jenis garis tren di Java Slides menggunakan Aspose.Slides for Java.

## Source Code Lengkap Untuk Garis Tren Grafik di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat direktori jika belum ada.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Membuat presentasi kosong
Presentation pres = new Presentation();
// Membuat bagan kolom berkelompok
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Menambahkan garis tren potensial untuk rangkaian grafik 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Menambahkan garis tren linier untuk rangkaian grafik 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Menambahkan garis tren logaritmik untuk rangkaian grafik 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Menambahkan garis tren MovingAverage untuk rangkaian grafik 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Menambahkan garis tren Polinomial untuk rangkaian grafik 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Menambahkan garis tren Power untuk rangkaian grafik 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Menyimpan presentasi
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menambahkan berbagai jenis garis tren ke grafik di Java Slides menggunakan pustaka Aspose.Slides for Java. Baik Anda sedang mengerjakan analisis data atau membuat presentasi informatif, kemampuan untuk memvisualisasikan tren dapat menjadi alat yang ampuh.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah warna garis tren di Aspose.Slides untuk Java?

Untuk mengubah warna garis tren, Anda dapat menggunakan `getSolidFillColor().setColor(Color)` metode, seperti yang ditunjukkan dalam contoh untuk menambahkan garis tren linier.

### Bisakah saya menambahkan beberapa garis tren ke satu rangkaian grafik?

Ya, Anda dapat menambahkan beberapa garis tren ke satu rangkaian grafik. Cukup panggil `getTrendLines().add()` metode untuk setiap garis tren yang ingin Anda tambahkan.

### Bagaimana cara menghapus garis tren dari bagan di Aspose.Slides untuk Java?

Untuk menghapus garis tren dari grafik, Anda dapat menggunakan `removeAt(int index)` metode, menentukan indeks garis tren yang ingin Anda hapus.

### Apakah mungkin untuk menyesuaikan tampilan persamaan garis tren?

Ya, Anda dapat menyesuaikan tampilan persamaan garis tren menggunakan `setDisplayEquation(boolean)` metode, seperti yang ditunjukkan dalam contoh.

### Bagaimana saya dapat mengakses lebih banyak sumber daya dan contoh untuk Aspose.Slides untuk Java?

Anda dapat mengakses sumber daya tambahan, dokumentasi, dan contoh untuk Aspose.Slides untuk Java di [Situs web Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}