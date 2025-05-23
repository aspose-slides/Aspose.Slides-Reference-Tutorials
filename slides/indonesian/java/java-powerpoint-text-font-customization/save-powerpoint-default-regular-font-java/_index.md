---
"description": "Pelajari cara memanipulasi presentasi PowerPoint secara terprogram menggunakan Aspose.Slides untuk Java. Kuasai penanganan PowerPoint di Java dengan tutorial langkah demi langkah."
"linktitle": "Menyimpan PowerPoint dengan Font Reguler Default menggunakan Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Menyimpan PowerPoint dengan Font Reguler Default menggunakan Java"
"url": "/id/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Menyimpan PowerPoint dengan Font Reguler Default menggunakan Java

## Perkenalan
Dalam bidang pengembangan Java, membuat dan memanipulasi presentasi PowerPoint secara terprogram dapat meningkatkan produktivitas dan opsi penyesuaian secara signifikan. Aspose.Slides untuk Java adalah pustaka tangguh yang memberdayakan pengembang untuk menangani file PowerPoint secara efisien, menawarkan serangkaian fitur lengkap mulai dari modifikasi sederhana hingga presentasi yang rumit.
## Prasyarat
Sebelum mulai menggunakan Aspose.Slides untuk Java, pastikan Anda telah menyiapkan prasyarat berikut:
1. Java Development Kit (JDK): Aspose.Slides untuk Java memerlukan JDK 1.8 atau lebih tinggi agar berfungsi dengan benar.
2. Aspose.Slides untuk Java JAR: Unduh versi terbaru Aspose.Slides untuk Java dari [Di Sini](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Gunakan IntelliJ IDEA, Eclipse, atau IDE Java lain pilihan Anda.
4. Pemahaman Dasar tentang Java: Keakraban dengan dasar-dasar bahasa pemrograman Java diperlukan.

## Paket Impor
Untuk mulai menggunakan Aspose.Slides untuk Java, impor paket yang diperlukan:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Ini memastikan bahwa Anda memiliki akses ke semua kelas dan metode yang disediakan oleh Aspose.Slides untuk Java.
## Langkah 1: Siapkan Proyek Anda
Pertama, buat proyek Java baru di IDE Anda dan sertakan file JAR Aspose.Slides for Java di jalur pembuatan proyek Anda.
## Langkah 2: Inisialisasi Objek Presentasi
Membuat contoh sebuah `Presentation` objek dengan memuat file PowerPoint yang ada (.pptx) dari direktori lokal Anda.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Memuat presentasi
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Mengganti `"Your Document Directory"` Dan `"Your Output Directory"` dengan jalur berkas Anda yang sebenarnya.
## Langkah 3: Simpan Presentasi dengan Font Reguler Default
Tentukan font reguler default untuk format output (HTML dan PDF) menggunakan `HtmlOptions` Dan `PdfOptions` masing-masing.
```java
try {
    // Opsi penyimpanan HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Opsi penyimpanan PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Pastikan untuk mengganti `"Arial Black"` Dan `"Lucida Console"` dengan font reguler default yang Anda inginkan.

## Kesimpulan
Dengan mengikuti langkah-langkah ini, Anda telah mempelajari cara memanipulasi presentasi PowerPoint menggunakan Aspose.Slides for Java secara efektif. Kemampuan ini memungkinkan Anda untuk mengotomatiskan tugas, menyesuaikan presentasi, dan menyempurnakan aplikasi Java Anda dengan fungsionalitas penanganan PowerPoint tingkat lanjut.
## Pertanyaan yang Sering Diajukan
### Bisakah Aspose.Slides untuk Java bekerja dengan versi JDK yang lama?
Aspose.Slides untuk Java memerlukan JDK 1.8 atau lebih tinggi untuk kompatibilitas.
### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Slides untuk Java?
Anda dapat memperoleh lisensi sementara dari [Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi yang lebih rinci tentang Aspose.Slides untuk Java?
Jelajahi dokumentasi yang komprehensif [Di Sini](https://reference.aspose.com/slides/java/).
### Apakah ada dukungan komunitas yang tersedia untuk Aspose.Slides untuk Java?
Ya, Anda bisa mendapatkan dukungan komunitas [Di Sini](https://forum.aspose.com/c/slides/11).
### Dapatkah saya mencoba Aspose.Slides untuk Java secara gratis?
Ya, unduh versi uji coba gratis [Di Sini](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}