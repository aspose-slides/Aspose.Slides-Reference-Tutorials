---
"description": "Pelajari cara memperoleh gambar bagan di Java Slides menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah ini menyediakan kode sumber dan kiat untuk integrasi yang lancar."
"linktitle": "Dapatkan Gambar Bagan di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Dapatkan Gambar Bagan di Java Slides"
"url": "/id/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dapatkan Gambar Bagan di Java Slides


## Pengantar untuk Mendapatkan Gambar Bagan di Java Slides

Aspose.Slides untuk Java adalah pustaka canggih yang memungkinkan Anda bekerja dengan presentasi PowerPoint secara terprogram. Dengan pustaka ini, Anda dapat membuat, memanipulasi, dan mengekstrak berbagai elemen dari presentasi, termasuk bagan. Salah satu persyaratan umum adalah memperoleh gambar bagan dari slide, dan kami akan menunjukkan cara melakukannya dalam panduan ini.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) terinstal di sistem Anda.
- Pustaka Aspose.Slides untuk Java diunduh dan dikonfigurasikan dalam proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Siapkan Proyek Anda

Mulailah dengan membuat proyek Java di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda. Pastikan Anda telah menambahkan pustaka Aspose.Slides for Java ke dependensi proyek Anda.

## Langkah 2: Inisialisasi Presentasi

Untuk memulai, Anda perlu menginisialisasi presentasi PowerPoint. Dalam contoh ini, kami berasumsi Anda memiliki file PowerPoint bernama "test.pptx" di direktori dokumen Anda.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Langkah 3: Tambahkan Bagan dan Dapatkan Gambar

Selanjutnya, Anda dapat menambahkan diagram ke slide dan memperoleh gambarnya. Dalam contoh ini, kita akan menambahkan diagram kolom berkelompok.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

Dalam cuplikan kode ini, kami membuat bagan kolom berkelompok pada slide pertama presentasi dan kemudian memperoleh gambar mininya. Gambar tersebut disimpan sebagai "image.png" di direktori yang ditentukan.

## Source Code Lengkap Untuk Mendapatkan Gambar Grafik di Java Slides

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Memperoleh gambar bagan dari Java Slides menggunakan Aspose.Slides untuk Java merupakan proses yang mudah. Dengan kode yang disediakan, Anda dapat dengan mudah mengintegrasikan fungsionalitas ini ke dalam aplikasi Java Anda, sehingga Anda dapat bekerja dengan presentasi PowerPoint secara efektif.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menginstal Aspose.Slides untuk Java?

Menginstal Aspose.Slides untuk Java sangatlah mudah. Anda dapat mengunduh pustaka dari [Di Sini](https://releases.aspose.com/slides/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

### Dapatkah saya menyesuaikan bagan sebelum mendapatkan gambarnya?

Ya, Anda dapat menyesuaikan tampilan, data, dan properti bagan lainnya sebelum memperoleh gambarnya. Aspose.Slides untuk Java menyediakan opsi yang luas untuk penyesuaian bagan.

### Fitur apa lagi yang ditawarkan Aspose.Slides untuk Java?

Aspose.Slides untuk Java menawarkan berbagai fitur untuk bekerja dengan presentasi PowerPoint, termasuk pembuatan slide, manipulasi teks, penyuntingan bentuk, dan banyak lagi. Anda dapat menjelajahi dokumentasi untuk informasi terperinci.

### Apakah Aspose.Slides untuk Java cocok untuk penggunaan komersial?

Ya, Aspose.Slides untuk Java dapat digunakan untuk tujuan komersial. Aplikasi ini menyediakan opsi lisensi yang melayani pengembang perorangan dan perusahaan.

### Bisakah saya menyimpan gambar bagan dalam format yang berbeda?

Tentu saja! Anda dapat menyimpan gambar grafik dalam berbagai format, seperti JPEG atau GIF, dengan menentukan ekstensi file yang sesuai di `ImageIO.write` metode.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}