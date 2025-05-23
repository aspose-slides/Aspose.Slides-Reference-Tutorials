---
"date": "2025-04-17"
"description": "Pelajari cara membuat dan mengekspor diagram menggunakan Aspose.Slides di Java. Kuasai teknik visualisasi data dengan panduan langkah demi langkah dan contoh kode."
"title": "Aspose.Slides Java&#58; Membuat dan Mengekspor Bagan untuk Visualisasi Data"
"url": "/id/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Membuat dan Mengekspor Grafik Menggunakan Aspose.Slides Java

**Teknik Visualisasi Data Master dengan Aspose.Slides untuk Java**

Dalam lanskap yang digerakkan oleh data saat ini, visualisasi data yang efektif sangat penting untuk membuat keputusan yang tepat. Mengintegrasikan fungsi bagan ke dalam aplikasi Java Anda dapat mengubah data mentah menjadi cerita visual yang menarik. Tutorial ini akan memandu Anda membuat dan mengekspor bagan menggunakan Aspose.Slides untuk Java, memastikan presentasi Anda informatif dan menarik secara visual.

**Apa yang Akan Anda Pelajari:**
- Memuat dan memanipulasi file presentasi dengan mudah
- Tambahkan berbagai jenis grafik ke slide Anda
- Ekspor data bagan ke buku kerja eksternal dengan mudah
- Tetapkan jalur buku kerja eksternal untuk manajemen data yang efisien

Mari kita mulai!

## Prasyarat
Sebelum memulai, pastikan Anda telah menyiapkan pengaturan berikut:

### Pustaka dan Versi yang Diperlukan
- **Aspose.Slides untuk Java** versi 25.4 atau lebih baru

### Persyaratan Pengaturan Lingkungan
- Java Development Kit (JDK) 16 atau lebih tinggi
- Editor kode atau IDE seperti IntelliJ IDEA atau Eclipse

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman Java
- Keakraban dengan sistem build Maven atau Gradle

## Menyiapkan Aspose.Slides untuk Java
Untuk mulai menggunakan Aspose.Slides, Anda perlu menyertakannya dalam proyek Anda. Berikut caranya:

**Pakar**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Bahasa Inggris Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Atau, Anda bisa [unduh versi terbaru secara langsung](https://releases.aspose.com/slides/java/).

### Langkah-langkah Memperoleh Lisensi
Aspose.Slides menawarkan lisensi uji coba gratis untuk menjelajahi semua kemampuannya. Anda juga dapat mengajukan lisensi sementara atau membeli lisensi untuk penggunaan jangka panjang. Ikuti langkah-langkah berikut:
1. Kunjungi [Halaman Pembelian Aspose](https://purchase.aspose.com/buy) untuk mendapatkan lisensi Anda.
2. Untuk uji coba gratis, unduh dari [Rilis](https://releases.aspose.com/slides/java/).
3. Ajukan permohonan lisensi sementara [Di Sini](https://purchase.aspose.com/temporary-license/).

Setelah Anda memiliki file lisensi, inisialisasikan dalam aplikasi Java Anda:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Panduan Implementasi
### Fitur 1: Memuat Presentasi
Memuat presentasi adalah langkah pertama untuk tugas manipulasi apa pun.

#### Ringkasan
Fitur ini menunjukkan cara memuat berkas PowerPoint yang ada menggunakan Aspose.Slides untuk Java.

#### Implementasi Langkah demi Langkah
**Tambahkan Bagan ke Slide**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Tetapkan jalur ke direktori dokumen Anda
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Memuat presentasi yang ada
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Bersihkan sumber daya
        if (pres != null) pres.dispose();
    }
}
```
**Penjelasan:**
- `Presentation` diinisialisasi dengan jalur ke Anda `.pptx` mengajukan.
- Selalu buang `Presentation` keberatan terhadap sumber daya gratis.

### Fitur 2: Tambahkan Bagan ke Slide
Menambahkan bagan dapat meningkatkan penyajian data secara signifikan.

#### Ringkasan
Fitur ini menunjukkan cara menambahkan diagram Pai ke slide pertama presentasi.

#### Implementasi Langkah demi Langkah
**Tambahkan Bagan ke Slide**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Tetapkan jalur ke direktori dokumen Anda
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Tambahkan diagram Pai pada posisi (50, 50) dengan lebar 400 dan tinggi 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Penjelasan:**
- `addChart` Metode ini digunakan untuk menyisipkan diagram Pai.
- Parameternya meliputi jenis bagan dan posisi/ukurannya pada slide.

### Fitur 3: Ekspor Data Bagan ke Buku Kerja Eksternal
Mengekspor data memungkinkan analisis lebih lanjut di luar PowerPoint.

#### Ringkasan
Fitur ini menunjukkan cara mengekspor data bagan dari presentasi ke buku kerja Excel eksternal.

#### Implementasi Langkah demi Langkah
**Ekspor Data**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Atur jalur ke direktori dokumen dan direktori keluaran Anda
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Akses bagan slide pertama
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Tentukan jalur untuk buku kerja eksternal
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Ekspor data grafik ke aliran Excel
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
- `readWorkbookStream` mengekstrak data grafik.
- Data ditulis ke file Excel menggunakan `FileOutputStream`.

### Fitur 4: Mengatur Buku Kerja Eksternal untuk Data Bagan
Menghubungkan bagan ke buku kerja eksternal dapat memperlancar pengelolaan data.

#### Ringkasan
Fitur ini menunjukkan pengaturan jalur buku kerja eksternal untuk menyimpan data bagan.

#### Implementasi Langkah demi Langkah
**Tetapkan Jalur Buku Kerja Eksternal**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Tetapkan jalur ke direktori dokumen Anda
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Akses bagan slide pertama
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Tentukan dan atur jalur untuk buku kerja eksternal
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Penjelasan:**
- `setExternalWorkbook` menghubungkan bagan ke berkas Excel, yang memungkinkan pembaruan data yang dinamis.

## Aplikasi Praktis
Aspose.Slides menawarkan solusi serbaguna untuk berbagai skenario:

1. **Laporan Bisnis:** Buat laporan terperinci dengan bagan langsung dari aplikasi Java.
2. **Presentasi Akademis:** Tingkatkan konten pendidikan dengan bagan interaktif.
3. **Analisis Keuangan:** Ekspor data keuangan ke Excel untuk analisis mendalam.
4. **Analisis Pemasaran:** Visualisasikan kinerja kampanye menggunakan bagan dinamis.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}