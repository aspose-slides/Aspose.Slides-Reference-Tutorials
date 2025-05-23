---
"description": "Pelajari cara mengakses properti bawaan di PowerPoint menggunakan Aspose.Slides untuk Java. Tutorial ini memandu Anda dalam mengambil penulis, tanggal pembuatan, dan banyak lagi."
"linktitle": "Mengakses Properti Bawaan di PowerPoint"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Mengakses Properti Bawaan di PowerPoint"
"url": "/id/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Mengakses Properti Bawaan di PowerPoint

## Perkenalan
Dalam tutorial ini, kita akan menjelajahi cara mengakses properti bawaan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Aspose.Slides adalah pustaka canggih yang memungkinkan pengembang Java bekerja dengan presentasi PowerPoint secara terprogram, memungkinkan tugas-tugas seperti membaca dan memodifikasi properti dengan lancar.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari [Di Sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides untuk Java: Unduh dan instal Aspose.Slides untuk Java dari [tautan ini](https://releases.aspose.com/slides/java/).

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan ke proyek Java Anda. Tambahkan pernyataan impor berikut di awal berkas Java Anda:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Langkah 1: Siapkan Objek Presentasi
Mulailah dengan menyiapkan objek Presentasi untuk mewakili presentasi PowerPoint yang ingin Anda gunakan. Berikut cara melakukannya:
```java
// Jalur ke direktori yang berisi file presentasi
String dataDir = "path_to_your_presentation_directory/";
// Membuat instance kelas Presentasi
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Langkah 2: Akses Properti Dokumen
Setelah menyiapkan objek Presentasi, Anda dapat mengakses properti bawaan presentasi menggunakan antarmuka IDocumentProperties. Berikut ini cara mengambil berbagai properti:
### Kategori
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Status Saat Ini
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Tanggal Pembuatan
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Pengarang
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Keterangan
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Kata Kunci
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Terakhir Diubah Oleh
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Pengawas
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Tanggal Modifikasi
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Format Presentasi
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Tanggal Cetak Terakhir
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Dibagi Antar Produsen
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Subjek
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Judul
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengakses properti bawaan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat dengan mudah mengambil berbagai properti seperti penulis, tanggal pembuatan, dan judul secara terprogram.
## Pertanyaan yang Sering Diajukan
### Bisakah saya memodifikasi properti bawaan ini menggunakan Aspose.Slides untuk Java?
Ya, Anda dapat mengubah properti ini menggunakan Aspose.Slides. Cukup gunakan metode penyetel yang sesuai yang disediakan oleh antarmuka IDocumentProperties.
### Apakah Aspose.Slides kompatibel dengan berbagai versi PowerPoint?
Aspose.Slides mendukung berbagai versi PowerPoint, memastikan kompatibilitas di berbagai platform.
### Bisakah saya mengambil properti khusus juga?
Ya, selain properti bawaan, Anda juga dapat mengambil dan mengubah properti kustom menggunakan Aspose.Slides untuk Java.
### Apakah Aspose.Slides menawarkan dokumentasi dan dukungan?
Ya, Anda dapat menemukan dokumentasi lengkap dan mengakses forum dukungan di [Situs web Aspose](https://reference.aspose.com/slides/java/).
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk Java?
Ya, Anda dapat mengunduh versi uji coba gratis dari [Di Sini](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}