---
date: '2026-01-09'
description: Temukan cara menggunakan Aspose Slides Maven untuk menambahkan diagram
  ke slide dan menyesuaikan diagram pai dalam presentasi Java. Penyiapan langkah demi
  langkah, kode, dan contoh dunia nyata.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven: Tambahkan Diagram Lingkaran ke Presentasi'
url: /id/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menambahkan Diagram Pai ke Presentasi Menggunakan Aspose.Slides Java

## Pendahuluan
Membuat presentasi yang menarik secara visual sangat penting untuk menyampaikan informasi secara efektif, terutama ketika visualisasi data memainkan peran kunci. Jika Anda ingin mengotomatisasi proses ini dengan **aspose slides maven**, Anda berada di tempat yang tepat. Dalam tutorial ini Anda akan belajar cara **add chart to slide** — khususnya diagram pai — menggunakan Aspose.Slides untuk Java, dan melihat cara menyesuaikannya untuk skenario dunia nyata.

### Apa yang Akan Anda Pelajari
- Cara menginisialisasi objek presentasi di Java.  
- Langkah‑langkah untuk **add a pie chart java** pada slide pertama sebuah presentasi.  
- Mengakses workbook data diagram dan menyebutkan worksheet di dalamnya.  

Mari kita selami bagaimana Anda dapat memanfaatkan Aspose.Slides Java untuk meningkatkan presentasi Anda dengan diagram dinamis!

## Jawaban Cepat
- **What library adds charts via Maven?** aspose slides maven  
- **Which chart type is demonstrated?** Pie chart (add chart to slide)  
- **Minimum Java version required?** JDK 16 or later  
- **Do I need a license for testing?** A free trial works; production needs a license  
- **Where can I find the Maven dependency?** In the setup section below  

## Apa itu Aspose Slides Maven?
Aspose.Slides untuk Java adalah API yang kuat yang memungkinkan pengembang membuat, memodifikasi, dan merender file PowerPoint secara programatis. Paket Maven (`aspose-slides`) menyederhanakan manajemen dependensi, memungkinkan Anda fokus pada pembuatan dan penyesuaian slide—seperti menambahkan diagram pai—tanpa harus menangani penanganan file tingkat rendah.

## Mengapa Menggunakan Aspose.Slides Maven untuk Menambahkan Diagram ke Slide?
- **Otomatisasi:** Menghasilkan laporan dan dasbor secara otomatis.  
- **Presisi:** Kontrol penuh atas tipe diagram, data, dan gaya.  
- **Lintas‑Platform:** Berfungsi pada lingkungan Java apa pun.  

## Prasyarat
- **Aspose.Slides for Java** versi 25.4 atau lebih baru (Maven/Gradle).  
- JDK 16+ terinstal.  
- Sebuah IDE (IntelliJ IDEA, Eclipse, dll.).  
- Pengetahuan dasar Java dan familiaritas dengan Maven atau Gradle.  

## Menyiapkan Aspose.Slides untuk Java
Pertama, sertakan Aspose.Slides dalam proyek Anda melalui Maven atau Gradle.

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sebagai alternatif, Anda dapat [mengunduh rilis terbaru](https://releases.aspose.com/slides/java/) langsung dari situs web Aspose.

### Akuisisi Lisensi
Aspose.Slides untuk Java menawarkan percobaan gratis dengan lisensi sementara untuk pengujian. Untuk penggunaan produksi tanpa batas, beli lisensi melalui [halaman pembelian](https://purchase.aspose.com/buy).

## Panduan Implementasi
Di bawah ini kami membagi solusi menjadi dua fitur: menambahkan diagram pai dan mengakses workbook datanya.

### Fitur 1: Membuat Presentasi dan Menambahkan Diagram
#### Gambaran Umum
Bagian ini menunjukkan cara membuat presentasi baru dan **add a pie chart** ke slide pertama.

#### Langkah‑per‑Langkah

**Step 1: Initialize a New Presentation Object**  
```java
Presentation pres = new Presentation();
```
*Membuat instance `Presentation` yang akan menampung semua slide.*

**Step 2: Add a Pie Chart**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Menempatkan diagram pai pada koordinat (50, 50) dengan lebar 400 dan tinggi 500. Enum `ChartType.Pie` memberi tahu Aspose untuk merender diagram pai.*

**Step 3: Dispose of Resources**  
```java
if (pres != null) pres.dispose();
```
*Melepaskan sumber daya native; selalu panggil `dispose()` setelah selesai.*

### Fitur 2: Mengakses Workbook Data Diagram dan Worksheet
#### Gambaran Umum
Pelajari cara mengakses workbook dasar yang menyimpan data diagram dan mengiterasi worksheet‑nya.

#### Langkah‑per‑Langkah

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Sama seperti Fitur 1, Langkah 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*Sama seperti Fitur 1, Langkah 2.*

**Step 3: Get the Chart Data Workbook**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Mengambil `IChartDataWorkbook` yang terhubung ke diagram.*

**Step 4: Iterate Through Worksheets**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Mencetak nama setiap worksheet, memungkinkan Anda memverifikasi struktur data.*

**Step 5: Dispose of Resources**  
*Sama seperti Fitur 1, Langkah 3.*

## Aplikasi Praktis
- **Pelaporan Data:** Membuat deck slide secara otomatis dengan metrik terkini untuk intelijen bisnis.  
- **Presentasi Akademik:** Memvisualisasikan hasil riset tanpa pembuatan diagram manual.  
- **Materi Pemasaran:** Menampilkan kinerja produk atau hasil survei secara instan.  

## Pertimbangan Kinerja
- Jaga jumlah slide dan diagram tetap wajar; masing‑masing mengonsumsi memori.  
- Selalu panggil `dispose()` untuk membebaskan sumber daya native.  
- Optimalkan penanganan data workbook—hindari memuat dataset besar ke dalam satu diagram.  

## Kesimpulan
Kami telah membahas bagaimana **aspose slides maven** memungkinkan Anda **add chart to slide** secara programatis dan cara bekerja dengan workbook data diagram. Dengan blok‑bangunan ini Anda dapat mengotomatisasi alur kerja pelaporan apa pun yang memerlukan output PowerPoint yang rapi.

### Langkah Selanjutnya
- Jelajahi opsi styling diagram (warna, legenda, label data).  
- Hubungkan ke sumber data eksternal (CSV, basis data) untuk mengisi diagram secara dinamis.  
- Gabungkan beberapa tipe diagram dalam satu presentasi untuk storytelling yang lebih kaya.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara menginstal Aspose.Slides untuk Java?**  
A: Gunakan dependensi Maven atau Gradle yang ditunjukkan di atas, atau unduh library dari halaman rilis.

**Q: Apa persyaratan sistem untuk Aspose.Slides?**  
A: JDK 16 atau lebih baru; library ini independen platform.

**Q: Bisakah saya menambahkan tipe diagram lain selain diagram pai?**  
A: Ya, Aspose.Slides mendukung diagram batang, garis, sebar, dan banyak tipe diagram lainnya.

**Q: Bagaimana cara menangani presentasi besar secara efisien?**  
A: Segera dispose objek, batasi jumlah gambar beresolusi tinggi, dan gunakan kembali templat diagram bila memungkinkan.

**Q: Di mana saya dapat menemukan detail lebih lanjut tentang fitur Aspose.Slides?**  
A: Kunjungi [dokumentasi Aspose](https://reference.aspose.com/slides/java/) untuk referensi API lengkap.

**Q: Apakah lisensi diperlukan untuk penggunaan komersial?**  
A: Lisensi yang valid diperlukan untuk produksi; percobaan gratis tersedia untuk evaluasi.

**Q: Apakah paket Maven mencakup semua kemampuan diagram?**  
A: Ya, artefak Maven `aspose-slides` berisi mesin diagram lengkap.

---  

**Terakhir Diperbarui:** 2026-01-09  
**Diuji Dengan:** Aspose.Slides 25.4 for Java (jdk16)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## Sumber Daya
- Dokumentasi: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Unduhan: [Latest Releases](https://releases.aspose.com/slides/java/)
- Pembelian dan Percobaan: [Purchase Page](https://purchase.aspose.com/buy)
- Percobaan Gratis: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Lisensi Sementara: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Forum Dukungan: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)