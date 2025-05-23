---
"description": "Tingkatkan Properti Font Bagan di Slide Java dengan Aspose.Slides untuk Java. Sesuaikan ukuran, gaya, dan warna font untuk presentasi yang mengesankan."
"linktitle": "Properti Font untuk Bagan di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Properti Font untuk Bagan di Java Slides"
"url": "/id/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Properti Font untuk Bagan di Java Slides


## Pengenalan Properti Font untuk Bagan di Java Slides

Panduan ini akan memandu Anda dalam pengaturan properti font untuk bagan di Java Slides menggunakan Aspose.Slides. Anda dapat menyesuaikan ukuran font dan tampilan teks bagan untuk meningkatkan daya tarik visual presentasi Anda.

## Prasyarat

Sebelum memulai, pastikan Anda telah mengintegrasikan Aspose.Slides for Java API ke dalam proyek Anda. Jika belum, Anda dapat mengunduhnya dari [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).

## Langkah 1: Buat Presentasi

Pertama, buat presentasi baru menggunakan kode berikut:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan

Sekarang, mari tambahkan bagan kolom berkelompok ke presentasi Anda:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Di sini, kami menambahkan bagan kolom berkelompok ke slide pertama pada koordinat (100, 100) dengan lebar 500 satuan dan tinggi 400 satuan.

## Langkah 3: Sesuaikan Properti Font

Selanjutnya, kita akan menyesuaikan properti font pada diagram. Dalam contoh ini, kita akan mengatur ukuran font menjadi 20 untuk semua teks diagram:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Kode ini menetapkan ukuran font menjadi 20 poin untuk semua teks dalam bagan.

## Langkah 4: Tampilkan Label Data

Anda juga dapat menampilkan label data pada bagan menggunakan kode berikut:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Baris kode ini mengaktifkan label data untuk seri pertama dalam bagan, yang menampilkan nilai pada kolom bagan.

## Langkah 5: Simpan Presentasi

Terakhir, simpan presentasi dengan properti font bagan yang telah Anda sesuaikan:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Kode ini akan menyimpan presentasi ke direktori yang ditentukan dengan nama file "FontPropertiesForChart.pptx."

## Source Code Lengkap Untuk Properti Font untuk Bagan di Java Slides

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

Dalam tutorial ini, Anda telah mempelajari cara menyesuaikan properti font untuk bagan di Java Slides menggunakan Aspose.Slides untuk Java. Anda dapat menerapkan teknik ini untuk menyempurnakan tampilan bagan dan presentasi Anda. Jelajahi lebih banyak opsi di [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/).

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah warna font?

Untuk mengubah warna font untuk teks grafik, gunakan `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, mengganti `Color.RED` dengan warna yang diinginkan.

### Bisakah saya mengubah gaya font (tebal, miring, dll.)?

Ya, Anda dapat mengubah gaya font. Gunakan `chart.getTextFormat().getPortionFormat().setFontBold(true);` untuk membuat huruf menjadi tebal. Demikian pula, Anda dapat menggunakan `setFontItalic(true)` untuk membuatnya miring.

### Bagaimana cara menyesuaikan properti font untuk elemen bagan tertentu?

Untuk menyesuaikan properti font untuk elemen bagan tertentu, seperti label sumbu atau teks legenda, Anda dapat mengakses elemen tersebut dan mengatur properti fontnya menggunakan metode serupa seperti yang ditunjukkan di atas.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}