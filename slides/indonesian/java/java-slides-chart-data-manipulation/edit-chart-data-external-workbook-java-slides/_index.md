---
"description": "Pelajari cara mengedit data bagan dalam buku kerja eksternal menggunakan Aspose.Slides untuk Java. Panduan langkah demi langkah dengan kode sumber."
"linktitle": "Edit Data Bagan di Buku Kerja Eksternal di Java Slides"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Edit Data Bagan di Buku Kerja Eksternal di Java Slides"
"url": "/id/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Edit Data Bagan di Buku Kerja Eksternal di Java Slides


## Pengantar untuk Mengedit Data Bagan di Buku Kerja Eksternal di Java Slides

Dalam panduan ini, kami akan menunjukkan cara mengedit data bagan dalam buku kerja eksternal menggunakan Aspose.Slides untuk Java. Anda akan mempelajari cara memodifikasi data bagan dalam presentasi PowerPoint secara terprogram. Pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Slides untuk Java di proyek Anda.

## Prasyarat

- Aspose.Slides untuk Java
- Lingkungan pengembangan Java

## Langkah 1: Muat Presentasi

Pertama, kita perlu memuat presentasi PowerPoint yang berisi grafik yang datanya ingin kita edit. Ganti `"Your Document Directory"` dengan jalur sebenarnya ke berkas presentasi Anda.

```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Langkah 2: Akses Bagan

Setelah presentasi dimuat, kita perlu mengakses diagram di dalam presentasi. Dalam contoh ini, kita asumsikan diagram ada di slide pertama dan merupakan bentuk pertama pada slide tersebut.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Langkah 3: Ubah Data Bagan

Sekarang, mari kita ubah data grafik. Kita akan fokus pada perubahan titik data tertentu dalam grafik. Dalam contoh ini, kita tetapkan nilai titik data pertama dalam seri pertama menjadi 100. Anda dapat menyesuaikan nilai ini sesuai kebutuhan.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Langkah 4: Simpan Presentasi

Setelah melakukan perubahan yang diperlukan pada data grafik, simpan presentasi yang dimodifikasi ke file baru. Anda dapat menentukan jalur dan format file output sesuai dengan kebutuhan Anda.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Langkah 5: Pembersihan

Jangan lupa membuang objek presentasi untuk melepaskan sumber daya apa pun.

```java
if (pres != null) pres.dispose();
```

Sekarang Anda telah berhasil mengedit data bagan dalam buku kerja eksternal dalam presentasi PowerPoint Anda menggunakan Aspose.Slides untuk Java. Anda dapat menyesuaikan kode ini agar sesuai dengan kebutuhan spesifik Anda dan mengintegrasikannya ke dalam aplikasi Java Anda.

## Kode Sumber Lengkap

```java
        // Perhatikan jalur ke buku kerja eksternal hampir tidak disimpan dalam presentasi
        // jadi silakan salin file externalWorkbook.xlsx dari direktori Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ sebelum menjalankan contoh
        // Jalur ke direktori dokumen.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Kesimpulan

Dalam panduan lengkap ini, kami telah menjajaki cara mengedit data bagan di buku kerja eksternal dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti petunjuk langkah demi langkah dan contoh kode sumber, Anda telah memperoleh pengetahuan dan keterampilan untuk memodifikasi data bagan secara terprogram dengan mudah.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menentukan bagan atau slide yang berbeda?

Untuk mengakses grafik atau slide yang berbeda, ubah indeks yang sesuai di `getSlides().get_Item()` Dan `getShapes().get_Item()` metode. Ingat bahwa pengindeksan dimulai dari 0.

### Bisakah saya mengedit data dalam beberapa bagan dalam presentasi yang sama?

Ya, Anda dapat mengedit data dalam beberapa bagan dalam presentasi yang sama dengan mengulangi langkah-langkah modifikasi data bagan untuk setiap bagan.

### Bagaimana jika saya ingin mengedit data dalam buku kerja eksternal dengan format berbeda?

Anda dapat mengadaptasi kode untuk menangani berbagai format buku kerja eksternal dengan menggunakan kelas dan metode Aspose.Cells yang sesuai untuk membaca dan menulis data dalam format tersebut.

### Bagaimana saya dapat mengotomatiskan proses ini untuk beberapa presentasi?

Anda dapat membuat loop untuk memproses beberapa presentasi, memuat masing-masing presentasi, membuat perubahan yang diinginkan, dan menyimpan presentasi yang dimodifikasi satu per satu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}