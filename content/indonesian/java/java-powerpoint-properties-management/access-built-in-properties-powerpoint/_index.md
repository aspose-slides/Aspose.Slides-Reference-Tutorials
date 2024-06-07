---
title: Akses Properti Bawaan di PowerPoint
linktitle: Akses Properti Bawaan di PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengakses properti bawaan di PowerPoint menggunakan Aspose.Slides untuk Java. Tutorial ini memandu Anda dalam mengambil penulis, tanggal pembuatan, dan banyak lagi.
type: docs
weight: 10
url: /id/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---
## Perkenalan
Dalam tutorial ini, kita akan menjelajahi cara mengakses properti bawaan dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Aspose.Slides adalah perpustakaan canggih yang memungkinkan pengembang Java bekerja dengan presentasi PowerPoint secara terprogram, memungkinkan tugas-tugas seperti membaca dan memodifikasi properti dengan lancar.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari[Di Sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Unduh dan instal Aspose.Slides for Java dari[Link ini](https://releases.aspose.com/slides/java/).

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan ke proyek Java Anda. Tambahkan pernyataan import berikut di awal file Java Anda:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
```
## Langkah 1: Siapkan Objek Presentasi
Mulailah dengan menyiapkan objek Presentasi untuk mewakili presentasi PowerPoint yang ingin Anda kerjakan. Inilah cara Anda melakukannya:
```java
// Jalur ke direktori yang berisi file presentasi
String dataDir = "path_to_your_presentation_directory/";
// Buat instance kelas Presentasi
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Langkah 2: Akses Properti Dokumen
Setelah menyiapkan objek Presentasi, Anda dapat mengakses properti bawaan presentasi menggunakan antarmuka IDocumentProperties. Inilah cara Anda dapat mengambil berbagai properti:
### Kategori
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Status terkini
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
### Kata kunci
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Terakhir Dimodifikasi Oleh
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Pengawas
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Tanggal yang diubah
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
### Dibagi Antar Produser
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
## FAQ
### Bisakah saya memodifikasi properti bawaan ini menggunakan Aspose.Slides untuk Java?
Ya, Anda dapat mengubah properti ini menggunakan Aspose.Slides. Cukup gunakan metode penyetel yang sesuai yang disediakan oleh antarmuka IDocumentProperties.
### Apakah Aspose.Slides kompatibel dengan versi PowerPoint yang berbeda?
Aspose.Slides mendukung berbagai versi PowerPoint, memastikan kompatibilitas di berbagai platform.
### Bisakah saya mengambil properti khusus juga?
Ya, selain properti bawaan, Anda juga dapat mengambil dan memodifikasi properti khusus menggunakan Aspose.Slides untuk Java.
### Apakah Aspose.Slides menawarkan dokumentasi dan dukungan?
 Ya, Anda dapat menemukan dokumentasi komprehensif dan mengakses forum dukungan di[Asumsikan situs web](https://reference.aspose.com/slides/java/).
### Apakah ada versi uji coba yang tersedia untuk Aspose.Slides untuk Java?
 Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).