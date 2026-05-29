---
date: '2026-05-29'
description: Pelajari cara membuat pie chart Aspose menggunakan Aspose.Slides Maven,
  menambahkan pie chart Java ke slide, dan menyesuaikan data chart. Panduan langkah
  demi langkah dengan penyiapan Maven dan contoh dunia nyata.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Buat Pie Chart Aspose – Tambahkan Chart ke Presentasi dengan Maven
url: /id/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menambahkan Diagram Pai ke Presentasi Menggunakan Aspose.Slides Java

## Pendahuluan
Dalam panduan ini Anda akan **create pie chart aspose** dengan Aspose.Slides Maven dan melihat cara menyematkannya ke dalam slide PowerPoint. Membuat presentasi yang menarik secara visual sangat penting untuk menyampaikan informasi secara efektif, terutama ketika visualisasi data memainkan peran utama. Jika Anda ingin mengotomatisasi proses ini dengan **aspose slides maven**, Anda berada di tempat yang tepat. Kami akan memandu penambahan diagram ke slide — khususnya diagram pai — dan menyesuaikannya untuk skenario dunia nyata.

### Apa yang Akan Anda Pelajari
- Cara menginisialisasi objek presentasi dalam Java.  
- Langkah‑langkah untuk **add a pie chart java** pada slide pertama sebuah presentasi.  
- Mengakses workbook data diagram dan menampilkan daftar worksheet di dalamnya.  

Mari kita selami bagaimana Anda dapat memanfaatkan Aspose.Slides Java untuk meningkatkan presentasi Anda dengan diagram dinamis!

## Jawaban Cepat
- **Library apa yang menambahkan diagram melalui Maven?** aspose slides maven  
- **Jenis diagram apa yang ditunjukkan?** Pie chart (add chart to slide)  
- **Versi Java minimum yang diperlukan?** JDK 16 atau lebih baru  
- **Apakah saya memerlukan lisensi untuk pengujian?** A free trial works; production needs a license  
- **Di mana saya dapat menemukan dependensi Maven?** In the setup section below  

## Apa itu Aspose Slides Maven?
Aspose.Slides for Java adalah API yang kuat yang memungkinkan pengembang membuat, memodifikasi, dan merender file PowerPoint secara programatis. Paket Maven (`aspose-slides`) menyederhanakan manajemen dependensi, memungkinkan Anda fokus pada pembuatan dan penyesuaian slide—seperti menambahkan diagram pai—tanpa harus menangani penanganan file tingkat rendah.

## Mengapa Menggunakan Aspose.Slides Maven untuk Menambahkan Diagram ke Slide?
Menggunakan Aspose.Slides Maven memungkinkan Anda menghasilkan diagram langsung dari kode Java tanpa penyuntingan PowerPoint manual. Ini memberikan kontrol programatis penuh atas jenis diagram, sumber data, dan gaya, memastikan konsistensi merek dan akurasi. Artefak Maven juga menangani semua dependensi yang diperlukan, menyederhanakan proses build dan memungkinkan integrasi mulus ke dalam pipeline CI/CD.

## Prasyarat
- **Aspose.Slides for Java** versi 25.4 atau lebih baru (Maven/Gradle).  
- JDK 16+ terpasang.  
- IDE (IntelliJ IDEA, Eclipse, dll.).  
- Pengetahuan dasar Java dan familiaritas dengan Maven atau Gradle.

## Menyiapkan Aspose.Slides untuk Java
Pertama, sertakan Aspose.Slides dalam proyek Anda melalui Maven atau Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sebagai alternatif, Anda dapat [mengunduh rilis terbaru](https://releases.aspose.com/slides/java/) langsung dari situs web Aspose.

### Akuisisi Lisensi
Aspose.Slides for Java menawarkan percobaan gratis dengan lisensi sementara untuk pengujian. Untuk penggunaan produksi tanpa batas, beli lisensi melalui [halaman pembelian](https://purchase.aspose.com/buy).

## Panduan Implementasi
Di bawah ini kami membagi solusi menjadi dua fitur: menambahkan diagram pai dan mengakses workbook data diagramnya.

### Fitur 1: Membuat Presentasi dan Menambahkan Diagram
#### Gambaran Umum
Bagian ini menunjukkan cara membuat presentasi baru dan **add a pie chart** ke slide pertama.

#### Bagaimana cara membuat pie chart aspose?
Muat kelas `Presentation`, tambahkan diagram tipe `ChartType.Pie`, dan simpan file. Seluruh operasi hanya memerlukan tiga panggilan API dan selesai dalam kurang dari satu detik untuk dek 10‑slide tipikal, menjadikannya ideal untuk pembuatan laporan otomatis.

#### Langkah‑per‑Langkah

**Langkah 1: Inisialisasi Objek Presentasi Baru**  
Kelas `Presentation` adalah objek tingkat‑atas Aspose.Slides yang mewakili file PowerPoint dalam memori.  
```java
Presentation pres = new Presentation();
```
*Membuat instance `Presentation` yang akan menampung semua slide.*

**Langkah 2: Tambahkan Diagram Pai**  
`ChartType.Pie` memberi tahu Aspose untuk merender diagram pai.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Menempatkan diagram pai pada koordinat (50, 50) dengan lebar 400 dan tinggi 500.*

**Langkah 3: Buang Sumber Daya**  
Memanggil `dispose()` melepaskan sumber daya native dan mencegah kebocoran memori.  
```java
if (pres != null) pres.dispose();
```
*Melepaskan sumber daya native; selalu panggil `dispose()` setelah selesai.*

### Fitur 2: Mengakses Workbook Data Diagram dan Worksheet
#### Gambaran Umum
Pelajari cara mengakses workbook dasar yang menyimpan data diagram dan mengiterasi worksheet-nya.

#### Bagaimana cara mengakses workbook data diagram?
Ambil `IChartDataWorkbook` dari diagram, lalu iterasi koleksi `Worksheets`‑nya. Workbook ini meniru file Excel, memungkinkan Anda membaca, memodifikasi, atau menambahkan seri data secara programatis, yang akan langsung tercermin pada diagram saat disegarkan selama runtime tanpa harus memulai ulang.

#### Langkah‑per‑Langkah

**Langkah 1: (Gunakan Kembali) Inisialisasi Objek Presentasi Baru**  
*Sama seperti Fitur 1, Langkah 1.*

**Langkah 2: (Gunakan Kembali) Tambahkan Diagram Pai**  
*Sama seperti Fitur 1, Langkah 2.*

**Langkah 3: Dapatkan Workbook Data Diagram**  
`IChartDataWorkbook` adalah antarmuka yang menyediakan akses baca/tulis ke workbook internal diagram yang mirip Excel.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Mengambil `IChartDataWorkbook` yang terhubung ke diagram.*

**Langkah 4: Iterasi Melalui Worksheet**  
Objek `Worksheet` mewakili lembar individual di dalam workbook.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Mencetak nama setiap worksheet, memungkinkan Anda memverifikasi struktur data.*

**Langkah 5: Buang Sumber Daya**  
*Sama seperti Fitur 1, Langkah 3.*

## Aplikasi Praktis
- **Pelaporan Data:** Membuat deck slide secara otomatis dengan metrik terkini untuk intelijen bisnis.  
- **Presentasi Akademik:** Memvisualisasikan hasil penelitian tanpa pembuatan diagram manual.  
- **Materi Pemasaran:** Menampilkan kinerja produk atau hasil survei secara instan.

## Pertimbangan Kinerja
- Aspose.Slides dapat menangani **lebih dari 50 format input dan output** serta memproses presentasi ratusan halaman tanpa memuat seluruh file ke memori.  
- Jaga jumlah slide dan diagram tetap wajar; setiap diagram mengonsumsi memori native.  
- Selalu panggil `dispose()` untuk membebaskan sumber daya dengan cepat.  
- Optimalkan penanganan data workbook—hindari memuat dataset besar ke dalam satu diagram.

## Kesimpulan
Kami telah membahas bagaimana **aspose slides maven** memungkinkan Anda **add chart to slide** secara programatis dan cara bekerja dengan workbook data diagram. Dengan blok‑bangunan ini Anda dapat mengotomatisasi alur kerja pelaporan apa pun yang memerlukan output PowerPoint yang halus.

### Langkah Selanjutnya
- Jelajahi opsi penataan diagram (warna, legenda, label data).  
- Hubungkan ke sumber data eksternal (CSV, basis data) untuk mengisi diagram secara dinamis.  
- Gabungkan beberapa jenis diagram dalam satu presentasi untuk cerita yang lebih kaya.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara menginstal Aspose.Slides untuk Java?**  
A: Gunakan dependensi Maven atau Gradle yang ditunjukkan di atas, atau unduh pustaka dari halaman rilis.

**Q: Apa saja persyaratan sistem untuk Aspose.Slides?**  
A: JDK 16 atau lebih baru; pustaka ini berjalan di platform apa pun yang mendukung Java.

**Q: Bisakah saya menambahkan jenis diagram lain selain diagram pai?**  
A: Ya, Aspose.Slides mendukung bar, line, scatter, radar, dan lebih dari 20 jenis diagram.

**Q: Bagaimana cara menangani presentasi besar secara efisien?**  
A: Buang objek dengan cepat, batasi gambar beresolusi tinggi, dan gunakan kembali templat diagram untuk menjaga penggunaan memori tetap rendah.

**Q: Di mana saya dapat menemukan detail lebih lanjut tentang fitur Aspose.Slides?**  
A: Kunjungi [Aspose documentation](https://reference.aspose.com/slides/java/) untuk referensi API lengkap.

**Q: Apakah lisensi diperlukan untuk penggunaan komersial?**  
A: Lisensi yang valid diperlukan untuk produksi; percobaan gratis tersedia untuk evaluasi.

**Q: Apakah paket Maven mencakup semua kemampuan diagram?**  
A: Ya, artefak Maven `aspose-slides` berisi mesin diagram lengkap.

## Sumber Daya
- Dokumentasi: [Referensi API Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- Unduh: [Rilis Terbaru](https://releases.aspose.com/slides/java/)
- Pembelian dan Percobaan: [Halaman Pembelian](https://purchase.aspose.com/buy)
- Percobaan Gratis: [Unduhan Percobaan](https://releases.aspose.com/slides/java/)
- Lisensi Sementara: [Minta Lisensi Sementara](https://purchase.aspose.com/temporary-license/)
- Forum Dukungan: [Forum Komunitas Aspose](https://forum.aspose.com/c/slides/11)

---  

**Terakhir Diperbarui:** 2026-05-29  
**Diuji Dengan:** Aspose.Slides 25.4 untuk Java (jdk16)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menyesuaikan Warna Diagram Pai di Java dengan Aspose.Slides – Panduan Lengkap](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Buat Diagram Pai dalam Pai di Java dengan Aspose.Slides: Panduan Komprehensif](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animasi Diagram PowerPoint Menggunakan Aspose.Slides untuk Java – Panduan Langkah‑per‑Langkah](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}