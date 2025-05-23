---
"date": "2025-04-18"
"description": "Pelajari cara menyempurnakan presentasi Anda dengan menyesuaikan poin-poin SmartArt dengan gambar menggunakan Aspose.Slides untuk Java. Ikuti panduan langkah demi langkah ini untuk mendapatkan tampilan yang profesional."
"title": "Cara Menyesuaikan Bullet SmartArt dengan Gambar Menggunakan Aspose.Slides untuk Java | Panduan Langkah demi Langkah"
"url": "/id/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Menyesuaikan Poin SmartArt dengan Gambar Menggunakan Aspose.Slides untuk Java

## Perkenalan

Membuat presentasi yang menarik secara visual sangat penting untuk menarik perhatian audiens dan mengomunikasikan pesan Anda secara efektif. Salah satu tantangan umum dalam mendesain slide adalah menyempurnakan poin-poin penting dalam grafik SmartArt menggunakan gambar khusus. Tutorial ini akan memandu Anda dalam menetapkan gambar sebagai format isian poin dalam node SmartArt dengan Aspose.Slides untuk Java, yang memungkinkan Anda untuk meningkatkan presentasi Anda secara profesional.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan dan menggunakan Aspose.Slides untuk Java
- Menyesuaikan poin-poin penting dengan gambar dalam grafik SmartArt
- Aplikasi praktis dari kustomisasi ini
- Memecahkan masalah umum

Sebelum kita mulai penerapannya, pastikan Anda telah menyiapkan semuanya.

## Prasyarat

Untuk mengikuti tutorial ini, pastikan Anda memenuhi prasyarat berikut:

1. **Perpustakaan dan Ketergantungan**Anda memerlukan Aspose.Slides untuk pustaka Java versi 25.4 atau yang lebih baru.
2. **Pengaturan Lingkungan**:
   - IDE yang kompatibel seperti IntelliJ IDEA atau Eclipse
   - JDK 16 terinstal di mesin Anda
3. **Prasyarat Pengetahuan**: Keakraban dengan pemrograman Java dan struktur presentasi PowerPoint dasar.

## Menyiapkan Aspose.Slides untuk Java

Untuk memulai, sertakan pustaka Aspose.Slides dalam proyek Anda menggunakan salah satu metode berikut:

### Pakar

Tambahkan ketergantungan ini ke `pom.xml` mengajukan:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Bahasa Inggris Gradle

Sertakan ini di dalam `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Unduh Langsung

Atau, unduh perpustakaan langsung dari [Aspose.Slides untuk rilis Java](https://releases.aspose.com/slides/java/).

**Langkah-langkah Memperoleh Lisensi**: Aspose menawarkan lisensi uji coba gratis yang sempurna untuk menguji fitur-fiturnya. Anda dapat meminta lisensi sementara atau membeli lisensi untuk menghapus batasan evaluasi.

Untuk menginisialisasi dan mengatur lingkungan Anda, buatlah sebuah instance dari `Presentation` kelas seperti yang ditunjukkan:

```java
Presentation presentation = new Presentation();
```

## Panduan Implementasi

Bagian ini akan menguraikan proses menjadi beberapa langkah yang dapat dikelola, menjelaskan cara mencapai fungsionalitas yang diinginkan.

### Menambahkan SmartArt dengan Isian Bullet Kustom

#### Ringkasan

Kita akan mulai dengan menambahkan bentuk SmartArt ke slide Anda dan menyesuaikan poin-poinnya menggunakan isian gambar.

#### Petunjuk Langkah demi Langkah

**1. Inisialisasi Objek Presentasi**

```java
Presentation presentation = new Presentation();
```

*Tujuan*: Menginisialisasi contoh presentasi baru tempat Anda akan menambahkan grafik SmartArt.

**2. Tambahkan Bentuk SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Penjelasan*: Baris ini menambahkan bentuk SmartArt baru ke slide pertama pada posisi (x=10, y=10) dengan dimensi 500x400 piksel. `VerticalPictureList` tata letak digunakan untuk perataan vertikal.

**3. Akses dan Kustomisasi Isian Poin**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Tujuan*: Memeriksa apakah node memiliki `BulletFillFormat` properti. Jika demikian, gambar akan dimuat dan ditetapkan sebagai isian untuk poin-poin.
*Parameter*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: Jalur ke berkas gambar Anda.
  - `PictureFillMode.Stretch`: Memastikan gambar mengisi area poin sepenuhnya.

**4. Simpan Presentasi Anda**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}