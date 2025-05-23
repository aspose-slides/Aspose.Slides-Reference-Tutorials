---
"description": "Sempurnakan Bagan Anda dengan Aspose.Slides untuk Java. Pelajari cara mengatur sumbu posisi di slide Java, membuat presentasi yang memukau, dan menyesuaikan tata letak bagan dengan mudah."
"linktitle": "Mengatur Posisi Sumbu di Slide Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengatur Posisi Sumbu di Slide Java"
"url": "/id/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengatur Posisi Sumbu di Slide Java


## Pengantar Pengaturan Posisi Sumbu di Aspose.Slides untuk Java

Dalam tutorial ini, kita akan mempelajari cara mengatur sumbu posisi dalam bagan menggunakan Aspose.Slides untuk Java. Memposisikan sumbu dapat berguna saat Anda ingin menyesuaikan tampilan dan tata letak bagan. Kita akan membuat bagan kolom berkelompok dan menyesuaikan posisi sumbu horizontal di antara kategori.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menginstal dan mengatur pustaka Aspose.Slides for Java di proyek Java Anda. Anda dapat mengunduh pustaka tersebut dari [Di Sini](https://releases.aspose.com/slides/java/).

## Langkah 1: Membuat Presentasi

Pertama, mari buat presentasi baru untuk digunakan:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Pastikan untuk mengganti `"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Menambahkan Bagan

Selanjutnya, kita akan menambahkan bagan kolom berkelompok ke slide. Kita tentukan jenis bagan, posisi (koordinat x, y), dan dimensi (lebar dan tinggi) bagan:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Di sini, kami telah menambahkan bagan kolom berkelompok pada posisi (50, 50) dengan lebar 450 dan tinggi 300. Anda dapat menyesuaikan nilai-nilai ini sesuai kebutuhan.

## Langkah 3: Mengatur Posisi Sumbu

Untuk mengatur sumbu posisi antar kategori, Anda dapat menggunakan kode berikut:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Kode ini mengatur sumbu horizontal yang akan ditampilkan di antara kategori, yang dapat berguna untuk tata letak bagan tertentu.

## Langkah 4: Menyimpan Presentasi

Terakhir, mari simpan presentasi dengan bagan:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

Mengganti `"AsposeClusteredColumnChart.pptx"` dengan nama berkas yang Anda inginkan.

Selesai! Anda telah berhasil membuat bagan kolom berkelompok dan mengatur sumbu posisi antarkategori menggunakan Aspose.Slides untuk Java.

## Kode Sumber Lengkap
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Kesimpulan

Dalam tutorial ini, kami telah mempelajari cara mengatur sumbu posisi dalam bagan menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda telah mempelajari cara membuat bagan kolom berkelompok dan menyesuaikan tampilannya dengan memposisikan sumbu horizontal di antara kategori. Aspose.Slides untuk Java menyediakan fitur-fitur canggih untuk bekerja dengan bagan dan presentasi, menjadikannya alat yang berharga bagi pengembang Java.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan grafik lebih lanjut?

Anda dapat menyesuaikan berbagai aspek bagan, termasuk seri data, judul bagan, legenda, dan banyak lagi. Lihat [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/) untuk petunjuk dan contoh terperinci.

### Bisakah saya mengubah jenis grafik?

Ya, Anda dapat mengubah jenis grafik dengan memodifikasi `ChartType` parameter saat menambahkan bagan. Aspose.Slides untuk Java mendukung berbagai jenis bagan seperti bagan batang, bagan garis, dan lainnya.

### Di mana saya dapat menemukan lebih banyak contoh dan dokumentasi?

Anda dapat menemukan dokumentasi lengkap dan lebih banyak contoh di [Dokumentasi Aspose.Slides untuk Java](https://reference.aspose.com/slides/java/) halaman.

Ingatlah untuk membuang objek presentasi saat Anda selesai menggunakannya untuk membebaskan sumber daya sistem:

```java
if (pres != null) pres.dispose();
```

Sekian tutorial kali ini. Anda telah mempelajari cara mengatur sumbu posisi dalam diagram menggunakan Aspose.Slides untuk Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}