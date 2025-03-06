---
title: Atur Penggantian Font di Java PowerPoint
linktitle: Atur Penggantian Font di Java PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengatur fallback font di Java PowerPoint menggunakan Aspose.Slides for Java untuk memastikan tampilan teks yang konsisten.
type: docs
weight: 16
url: /id/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari seluk-beluk pengaturan fallback font dalam presentasi Java PowerPoint menggunakan Aspose.Slides untuk Java. Penggantian font sangat penting untuk memastikan bahwa teks dalam presentasi Anda ditampilkan dengan benar di berbagai perangkat dan sistem operasi, bahkan ketika font yang diperlukan tidak tersedia.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Slide untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/java/).
- Pemahaman dasar bahasa pemrograman Java.
- Lingkungan Pengembangan Terintegrasi (IDE) seperti IntelliJ IDEA atau Eclipse.

## Paket Impor
Pertama, sertakan paket Aspose.Slides for Java yang diperlukan di kelas Java Anda:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Langkah 1: Inisialisasi Aturan Penggantian Font
Untuk mengatur penggantian font, Anda perlu menentukan aturan yang menentukan rentang Unicode dan font cadangan yang sesuai. Inilah cara Anda menginisialisasi aturan ini:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Langkah 2: Terapkan Aturan Penggantian Font
Selanjutnya, Anda menerapkan aturan ini pada presentasi atau slide di mana penggantian font perlu diatur. Di bawah ini adalah contoh penerapan aturan-aturan ini pada slide dalam presentasi PowerPoint:
```java
// Dengan asumsi slide adalah objek Slide Anda
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Kesimpulan
Mengatur fallback font dalam presentasi Java PowerPoint menggunakan Aspose.Slides untuk Java sangat penting untuk memastikan tampilan teks yang konsisten di berbagai lingkungan. Dengan menentukan aturan fallback seperti yang ditunjukkan dalam tutorial ini, Anda dapat menangani situasi ketika font tertentu tidak tersedia, sehingga menjaga integritas presentasi Anda.

## FAQ
### Apa itu penggantian font dalam presentasi PowerPoint?
Penggantian font memastikan teks ditampilkan dengan benar dengan mengganti font yang tersedia dengan font yang tidak diinstal.
### Bagaimana cara mengunduh Aspose.Slides untuk Java?
 Anda dapat mengunduh Aspose.Slides untuk Java dari[Di Sini](https://releases.aspose.com/slides/java/).
### Apakah Aspose.Slides untuk Java kompatibel dengan semua IDE Java?
Ya, Aspose.Slides untuk Java kompatibel dengan IDE Java populer seperti IntelliJ IDEA dan Eclipse.
### Bisakah saya mendapatkan lisensi sementara untuk produk Aspose?
Ya, lisensi sementara untuk produk Aspose dapat diperoleh dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Slides untuk Java?
 Untuk dukungan terkait Aspose.Slides untuk Java, kunjungi[Asumsikan forum](https://forum.aspose.com/c/slides/11).