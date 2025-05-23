---
"description": "Pelajari cara mengelola aturan penggantian font dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java. Tingkatkan kompatibilitas di berbagai perangkat dengan mudah."
"linktitle": "Kumpulan Aturan Fallback dalam PowerPoint Java"
"second_title": "API Pemrosesan PowerPoint Java Aspose.Slides"
"title": "Kumpulan Aturan Fallback dalam PowerPoint Java"
"url": "/id/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Kumpulan Aturan Fallback dalam PowerPoint Java

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola aturan fallback font menggunakan Aspose.Slides untuk Java. Fallback font sangat penting untuk memastikan presentasi Anda ditampilkan dengan benar di berbagai lingkungan, terutama saat font tertentu tidak tersedia. Kami akan memandu Anda mengimpor paket yang diperlukan, menyiapkan lingkungan, dan menerapkan aturan fallback langkah demi langkah.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang pemrograman Java.
- JDK (Java Development Kit) terinstal di sistem Anda.
- Aspose.Slides untuk pustaka Java telah diunduh dan disiapkan. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment) seperti IntelliJ IDEA atau Eclipse terpasang.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## Menyiapkan Objek Presentasi
Pertama, inisialisasi objek Presentasi di mana Anda akan menentukan aturan fallback font Anda.
```java
Presentation presentation = new Presentation();
```
## Membuat Koleksi Aturan Pengganti Font
Berikutnya, buat objek FontFallBackRulesCollection untuk mengelola aturan fallback font kustom Anda.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## Menambahkan Aturan Penggantian Font
Sekarang, tambahkan aturan fallback font tertentu menggunakan rentang Unicode dan nama font fallback.
### Langkah 1: Tentukan Rentang Unicode dan Font
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
Baris ini menetapkan aturan fallback untuk rentang Unicode 0x0B80 hingga 0x0BFF untuk menggunakan font "Vijaya" jika font utama tidak tersedia.
### Langkah 2: Tentukan Rentang Unicode dan Font Lain
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
Di sini, aturan tersebut menetapkan bahwa rentang Unicode 0x3040 hingga 0x309F harus kembali ke font "MS Mincho" atau "MS Gothic".
## Menerapkan Aturan Penggantian Font pada Presentasi
Terapkan koleksi aturan fallback font yang dibuat ke FontsManager presentasi.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## Buang Objek Presentasi
Terakhir, pastikan manajemen sumber daya yang tepat dengan membuang objek Presentasi dalam blok try-finally.
```java
try {
    // Gunakan objek presentasi sesuai kebutuhan
} finally {
    if (presentation != null) presentation.dispose();
}
```
## Kesimpulan
Dalam tutorial ini, kami telah mempelajari cara mengelola aturan fallback font menggunakan Aspose.Slides untuk Java. Memahami dan menerapkan fallback font memastikan rendering font yang konsisten dan andal di berbagai platform dan lingkungan. Dengan mengikuti langkah-langkah ini, Anda dapat menyesuaikan perilaku fallback font untuk memenuhi persyaratan presentasi tertentu dengan lancar.

## Pertanyaan yang Sering Diajukan
### Apa saja aturan fallback font?
Aturan penggantian font menentukan font alternatif yang akan digunakan saat font yang ditentukan tidak tersedia, guna memastikan tampilan teks yang konsisten.
### Bagaimana cara mengunduh Aspose.Slides untuk Java?
Anda dapat mengunduh perpustakaan dari [Di Sini](https://releases.aspose.com/slides/java/).
### Dapatkah saya mencoba Aspose.Slides untuk Java sebelum membeli?
Ya, Anda bisa mendapatkan versi uji coba gratis [Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi untuk Aspose.Slides untuk Java?
Dokumentasi terperinci tersedia [Di Sini](https://reference.aspose.com/slides/java/).
### Bagaimana cara mendapatkan dukungan untuk Aspose.Slides untuk Java?
Untuk dukungan, kunjungi forum Aspose.Slides [Di Sini](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}