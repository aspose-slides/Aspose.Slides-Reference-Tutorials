---
title: Kumpulan Aturan Fallback di Java PowerPoint
linktitle: Kumpulan Aturan Fallback di Java PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengelola aturan penggantian font dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Tingkatkan kompatibilitas antar perangkat dengan mudah.
type: docs
weight: 11
url: /id/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola aturan fallback font menggunakan Aspose.Slides untuk Java. Penggantian font sangat penting dalam memastikan presentasi Anda ditampilkan dengan benar di berbagai lingkungan, terutama ketika font tertentu tidak tersedia. Kami akan memandu Anda dalam mengimpor paket yang diperlukan, menyiapkan lingkungan, dan menerapkan aturan fallback langkah demi langkah.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang pemrograman Java.
- JDK (Java Development Kit) diinstal pada sistem Anda.
-  Aspose.Slides untuk perpustakaan Java diunduh dan disiapkan. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment) seperti IntelliJ IDEA atau Eclipse diinstal.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## Menyiapkan Objek Presentasi
Pertama, inisialisasi objek Presentasi tempat Anda akan menentukan aturan penggantian font.
```java
Presentation presentation = new Presentation();
```
## Membuat Kumpulan Aturan Penggantian Font
Selanjutnya, buat objek FontFallBackRulesCollection untuk mengelola aturan penggantian font kustom Anda.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## Menambahkan Aturan Penggantian Font
Sekarang, tambahkan aturan penggantian font tertentu menggunakan rentang Unicode dan nama font cadangan.
### Langkah 1: Tentukan Rentang Unicode dan Font
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
Baris ini menetapkan aturan cadangan untuk rentang Unicode 0x0B80 hingga 0x0BFF untuk menggunakan font "Vijaya" jika font utama tidak tersedia.
### Langkah 2: Tentukan Rentang Unicode dan Font Lainnya
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
Di sini, aturan menetapkan bahwa rentang Unicode 0x3040 hingga 0x309F harus diganti ke font "MS Mincho" atau "MS Gothic".
## Menerapkan Aturan Penggantian Font pada Presentasi
Terapkan kumpulan aturan fallback font yang dibuat ke FontsManager presentasi.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## Buang Objek Presentasi
Terakhir, pastikan manajemen sumber daya yang tepat dengan membuang objek Presentation dalam blok try-finally.
```java
try {
    // Gunakan objek presentasi sesuai kebutuhan
} finally {
    if (presentation != null) presentation.dispose();
}
```
## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara mengelola aturan fallback font menggunakan Aspose.Slides untuk Java. Memahami dan menerapkan penggantian font memastikan rendering font yang konsisten dan andal di berbagai platform dan lingkungan. Dengan mengikuti langkah-langkah ini, Anda dapat menyesuaikan perilaku penggantian font untuk memenuhi persyaratan presentasi tertentu dengan lancar.

## FAQ
### Apa aturan penggantian font?
Aturan penggantian font menentukan font alternatif untuk digunakan ketika font yang ditentukan tidak tersedia, sehingga memastikan tampilan teks konsisten.
### Bagaimana cara mengunduh Aspose.Slides untuk Java?
 Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/slides/java/).
### Bisakah saya mencoba Aspose.Slides untuk Java sebelum membeli?
 Ya, Anda bisa mendapatkan versi uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi Aspose.Slides untuk Java?
 Dokumentasi terperinci tersedia[Di Sini](https://reference.aspose.com/slides/java/).
### Bagaimana cara mendapatkan dukungan untuk Aspose.Slides untuk Java?
Untuk dukungan, kunjungi forum Aspose.Slides[Di Sini](https://forum.aspose.com/c/slides/11).