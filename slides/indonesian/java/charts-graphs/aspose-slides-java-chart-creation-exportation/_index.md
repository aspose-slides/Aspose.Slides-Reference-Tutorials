---
date: '2026-02-09'
description: Pelajari cara membuat diagram dan mengekspor diagram ke Excel menggunakan
  Aspose.Slides for Java. Kuasai visualisasi data, slide laporan bisnis, dan pembuatan
  workbook.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Cara Membuat Grafik dengan Aspose.Slides Java
url: /id/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Diagram Menggunakan Aspose.Slides untuk Java

**Kuasai Teknik Visualisasi Data dengan Aspose.Slides untuk Java**

Dalam lanskap yang didorong oleh data saat ini, *cara membuat diagram* secara programatik adalah keterampilan yang dapat mengubah angka mentah menjadi cerita visual yang menarik. Baik Anda sedang membuat deck slide laporan bisnis atau dasbor analitik interaktif, Aspose.Slides untuk Java memberi Anda kekuatan untuk menghasilkan, menyesuaikan, dan mengekspor diagram langsung dari kode Anda. Dalam tutorial ini Anda akan belajar cara membuat objek diagram, mengekspor data diagram ke Excel, dan menautkan diagram ke workbook eksternal untuk manajemen data yang mulus.

## Jawaban Cepat
- **Perpustakaan apa yang dibutuhkan?** Aspose.Slides untuk Java (v25.4+).  
- **Apakah saya dapat mengekspor data diagram ke Excel?** Ya – gunakan `readWorkbookStream()` dan tulis byte‑nya ke file *.xlsx*.  
- **Versi Java mana yang diperlukan?** JDK 16 atau lebih tinggi.  
- **Apakah saya memerlukan lisensi?** Lisensi percobaan gratis dapat digunakan untuk evaluasi; lisensi permanen diperlukan untuk produksi.  
- **Jenis diagram apa yang ditunjukkan?** Diagram Pie, tetapi pendekatan yang sama berlaku untuk Bar, Line, dan jenis diagram lainnya.

## Apa Itu Aspose.Slides untuk Java?
Aspose.Slides untuk Java adalah API murni‑Java yang memungkinkan pengembang membuat, mengedit, dan mengonversi presentasi PowerPoint tanpa Microsoft Office. Ia mendukung seluruh rangkaian jenis diagram, pengikatan data, dan kemampuan ekspor, menjadikannya ideal untuk proyek **data visualization java**.

## Mengapa Menggunakan Aspose.Slides untuk Membuat Diagram dan Mengekspor Diagram ke Excel?
- **Tanpa instalasi Office** – bekerja di server atau lingkungan cloud mana pun.  
- **Perpustakaan diagram kaya** – puluhan jenis diagram dan kontrol styling penuh.  
- **Ekspor Excel langsung** – menghasilkan workbook eksternal untuk analisis lanjutan.  
- **Berorientasi kinerja** – jejak memori rendah dan pemrosesan cepat untuk deck besar.

## Prasyarat
Sebelum kita melanjutkan, pastikan Anda memiliki hal‑hal berikut:

### Perpustakaan dan Versi yang Diperlukan
- **Aspose.Slides untuk Java** versi 25.4 atau lebih baru

### Persyaratan Penyiapan Lingkungan
- Java Development Kit (JDK) 16 atau lebih tinggi  
- IDE seperti IntelliJ IDEA atau Eclipse (atau editor teks pilihan Anda)

### Prasyarat Pengetahuan
- Keterampilan dasar pemrograman Java  
- Familiaritas dengan alat build Maven atau Gradle

## Menyiapkan Aspose.Slides untuk Java
Tambahkan perpustakaan ke proyek Anda menggunakan sistem build favorit.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Atau, Anda dapat [mengunduh versi terbaru secara langsung](https://releases.aspose.com/slides/java/).

### Langkah‑Langkah Akuisisi Lisensi
Aspose.Slides menawarkan lisensi percobaan gratis untuk menjelajahi semua kemampuannya. Anda juga dapat mengajukan lisensi sementara atau membeli lisensi untuk penggunaan jangka panjang. Ikuti langkah‑langkah berikut:

1. Kunjungi [halaman Pembelian Aspose](https://purchase.aspose.com/buy) untuk mendapatkan lisensi Anda.  
2. Untuk percobaan gratis, unduh dari [Rilis](https://releases.aspose.com/slides/java/).  
3. Ajukan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

Setelah Anda memiliki file lisensi, inisialisasi dalam aplikasi Java Anda:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Panduan Langkah‑per‑Langkah

### Cara membuat diagram – Memuat Presentasi
Memuat file PowerPoint yang sudah ada adalah langkah pertama sebelum Anda dapat menambah atau memodifikasi diagram.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**Penjelasan:**  
- `Presentation` mewakili file PowerPoint.  
- Selalu panggil `dispose()` untuk melepaskan sumber daya native.

### Cara membuat diagram – Menambahkan Diagram Pie ke Slide
Sekarang kita akan menyisipkan diagram Pie, yang sangat cocok untuk menampilkan data proporsional.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Penjelasan:**  
- `addChart` menyisipkan diagram ke slide pertama.  
- Parameter menentukan jenis diagram, posisi X/Y, dan ukuran.

### Cara mengekspor diagram ke Excel – Mengekspor Data Diagram
Mengekspor data diagram memungkinkan analis bekerja dengan angka di Excel, memberikan wawasan yang lebih mendalam.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Penjelasan:**  
- `readWorkbookStream()` mengekstrak workbook Excel yang mendasari diagram sebagai array byte.  
- Array byte ditulis ke `externalWorkbook1.xlsx`, menghasilkan file Excel yang siap pakai.

### Cara membuat diagram – Menetapkan Workbook Eksternal untuk Data Dinamis
Menautkan diagram ke workbook eksternal memungkinkan Anda memperbarui diagram hanya dengan mengedit file Excel.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Penjelasan:**  
- `setExternalWorkbook` mengikat diagram ke file Excel yang ditentukan, memungkinkan pembaruan data secara langsung tanpa harus membangun ulang slide.

## Aplikasi Praktis
Aspose.Slides menawarkan solusi serbaguna untuk berbagai skenario dunia nyata:

1. **Slide Laporan Bisnis:** Menghasilkan diagram kinerja kuartalan secara otomatis dari pipeline data Anda.  
2. **Presentasi Akademik:** Mengubah data riset menjadi visualisasi jelas tanpa membuat diagram secara manual.  
3. **Analisis Keuangan:** Mengekspor data diagram ke Excel agar auditor dapat memverifikasi angka.  
4. **Analitik Pemasaran:** Memvisualisasikan metrik kampanye dan berbagi workbook yang dapat diedit dengan pemangku kepentingan.

## Masalah Umum & Pemecahan Masalah
- **`FileNotFoundException`** – Pastikan `dataDir` mengarah ke folder yang valid dan jalur output dapat ditulisi.  
- **Kebocoran memori** – Selalu panggil `pres.dispose()` dalam blok `finally` untuk membebaskan sumber daya native.  
- **Diagram tidak muncul** – Pastikan indeks slide (`get_Item(0)`) sesuai dengan slide yang memang ada.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan jenis diagram lain (misalnya Bar, Line) dengan kode yang sama?**  
J: Ya. Ganti `ChartType.Pie` dengan nilai enum `ChartType` lain seperti `ChartType.Bar` atau `ChartType.Line`.

**T: Apakah memungkinkan memperbarui workbook eksternal setelah diagram dibuat?**  
J: Tentu saja. Modifikasi file Excel secara langsung; diagram yang ditautkan akan mencerminkan perubahan saat presentasi dibuka kembali.

**T: Apakah saya memerlukan lisensi terpisah untuk fitur ekspor Excel?**  
J: Tidak. Kemampuan ekspor Excel sudah termasuk dalam lisensi standar Aspose.Slides untuk Java.

**T: Versi Java mana yang didukung?**  
J: Aspose.Slides untuk Java mendukung JDK 16 dan yang lebih baru; versi lebih lama mungkin berfungsi tetapi tidak diuji secara resmi.

**T: Bagaimana cara menyematkan workbook Excel yang dihasilkan ke dalam file PPTX?**  
J: Gunakan `chart.getChartData().setExternalWorkbook(null)` untuk menyematkan workbook, atau pertahankan tautan eksternal untuk pembaruan dinamis.

---

**Terakhir Diperbarui:** 2026-02-09  
**Diuji Dengan:** Aspose.Slides untuk Java 25.4 (jdk16 classifier)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}