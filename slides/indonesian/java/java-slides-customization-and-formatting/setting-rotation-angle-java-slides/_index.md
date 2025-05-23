---
"description": "Optimalkan slide Java Anda dengan Aspose.Slides untuk Java. Pelajari cara mengatur sudut rotasi untuk elemen teks. Panduan langkah demi langkah dengan kode sumber."
"linktitle": "Mengatur Sudut Rotasi pada Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Sudut Rotasi pada Java Slides"
"url": "/id/java/customization-and-formatting/setting-rotation-angle-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Sudut Rotasi pada Java Slides


## Pengenalan Pengaturan Sudut Rotasi di Java Slides

Dalam tutorial ini, kita akan mempelajari cara mengatur sudut rotasi teks dalam judul sumbu grafik menggunakan pustaka Aspose.Slides for Java. Dengan menyesuaikan sudut rotasi, Anda dapat menyesuaikan tampilan judul sumbu grafik agar lebih sesuai dengan kebutuhan presentasi Anda.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari situs web Aspose dan mengikuti petunjuk penginstalan yang tersedia dalam dokumentasinya.

## Langkah 1: Buat Presentasi

Pertama, Anda perlu membuat presentasi baru atau memuat presentasi yang sudah ada. Dalam contoh ini, kita akan membuat presentasi baru:

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Langkah 2: Tambahkan Bagan ke Slide

Berikutnya, kita akan menambahkan diagram ke slide. Dalam contoh ini, kita menambahkan diagram kolom berkelompok:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Langkah 3: Atur Sudut Rotasi untuk Judul Sumbu

Untuk mengatur sudut rotasi judul sumbu, Anda perlu mengakses judul sumbu vertikal diagram dan menyesuaikan sudut rotasinya. Berikut cara melakukannya:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

Dalam potongan kode ini, kami menyetel sudut rotasi ke 90 derajat, yang akan memutar teks secara vertikal. Anda dapat menyesuaikan sudut ke nilai yang diinginkan.

## Langkah 4: Simpan Presentasi

Terakhir, simpan presentasi ke file PowerPoint:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Source Code Lengkap Untuk Setting Sudut Rotasi di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengatur sudut rotasi untuk teks dalam judul sumbu grafik menggunakan Aspose.Slides untuk Java. Fitur ini memungkinkan Anda untuk menyesuaikan tampilan grafik Anda untuk membuat presentasi yang menarik secara visual. Bereksperimenlah dengan berbagai sudut rotasi untuk mendapatkan tampilan yang diinginkan untuk grafik Anda.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara mengubah sudut rotasi untuk elemen teks lain dalam slide?

Anda dapat mengubah sudut rotasi untuk elemen teks lainnya, seperti bentuk atau kotak teks, menggunakan pendekatan yang sama. Akses format teks elemen dan atur sudut rotasi sesuai kebutuhan.

### Bisakah saya memutar teks pada judul sumbu horizontal juga?

Ya, Anda dapat memutar teks pada judul sumbu horizontal dengan menyesuaikan sudut rotasi. Cukup atur sudut rotasi ke nilai yang diinginkan, seperti 90 derajat untuk teks vertikal atau 0 derajat untuk teks horizontal.

### Pilihan pemformatan apa lagi yang tersedia untuk judul bagan?

Aspose.Slides untuk Java menyediakan berbagai opsi pemformatan untuk judul bagan, termasuk gaya font, warna, dan perataan. Anda dapat menjelajahi dokumentasi untuk detail lebih lanjut tentang penyesuaian judul bagan.

### Dapatkah kita menganimasikan rotasi teks pada judul sumbu bagan?

Ya, Anda dapat menambahkan efek animasi ke elemen teks, termasuk judul sumbu bagan, menggunakan Aspose.Slides untuk Java. Lihat dokumentasi untuk informasi tentang cara menambahkan animasi ke presentasi Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}