---
title: Ubah Data Objek OLE di PowerPoint
linktitle: Ubah Data Objek OLE di PowerPoint
second_title: Aspose.Slides API Pemrosesan Java PowerPoint
description: Pelajari cara mengubah data objek OLE di PowerPoint menggunakan Aspose.Slides for Java. Panduan langkah demi langkah untuk pembaruan yang efisien dan mudah.
weight: 14
url: /id/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Mengubah data objek OLE dalam presentasi PowerPoint bisa menjadi tugas penting ketika Anda perlu memperbarui konten yang disematkan tanpa mengedit setiap slide secara manual. Panduan komprehensif ini akan memandu Anda melalui proses menggunakan Aspose.Slides untuk Java, perpustakaan canggih yang dirancang untuk menangani presentasi PowerPoint. Baik Anda seorang pengembang berpengalaman atau baru memulai, tutorial ini akan berguna dan mudah diikuti.
## Prasyarat
Sebelum kita mendalami kodenya, pastikan Anda memiliki semua yang Anda perlukan untuk memulai.
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari[situs Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides untuk Java: Unduh versi terbaru dari[Halaman unduh Aspose.Slide](https://releases.aspose.com/slides/java/).
3. Lingkungan Pengembangan Terintegrasi (IDE): Anda dapat menggunakan IDE Java apa pun seperti IntelliJ IDEA, Eclipse, atau NetBeans.
4.  Aspose.Cells untuk Java: Ini diperlukan untuk mengubah data yang tertanam dalam objek OLE. Unduh dari[Halaman unduh Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  File Presentasi: Siapkan file PowerPoint dengan objek OLE yang tertanam. Untuk tutorial ini, sebut saja`ChangeOLEObjectData.pptx`.
## Paket Impor
Pertama, mari impor paket yang diperlukan ke proyek Java Anda.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dilakukan.
## Langkah 1: Muat Presentasi PowerPoint
Untuk memulai, Anda perlu memuat presentasi PowerPoint yang berisi objek OLE.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Langkah 2: Akses Slide yang Berisi Objek OLE
Berikutnya, dapatkan slide tempat objek OLE tertanam.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Langkah 3: Temukan Objek OLE di Slide
Ulangi bentuk-bentuk di slide untuk menemukan objek OLE.
```java
OleObjectFrame ole = null;
// Melintasi semua bentuk untuk bingkai Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Langkah 4: Ekstrak Data Tersemat dari Objek OLE
Jika objek OLE ditemukan, ekstrak data yang tertanam.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Langkah 5: Ubah Data Tersemat Menggunakan Aspose.Cells
Sekarang, gunakan Aspose.Cells untuk membaca dan memodifikasi data yang disematkan, yang dalam hal ini kemungkinan merupakan buku kerja Excel.
```java
    Workbook wb = new Workbook(msln);
    // Ubah data buku kerja
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Langkah 6: Simpan Data yang Dimodifikasi Kembali ke Objek OLE
Setelah melakukan perubahan yang diperlukan, simpan kembali buku kerja yang dimodifikasi ke objek OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Langkah 7: Simpan Presentasi yang Diperbarui
Terakhir, simpan presentasi PowerPoint yang diperbarui.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Kesimpulan
Memperbarui data objek OLE dalam presentasi PowerPoint menggunakan Aspose.Slides untuk Java adalah proses yang mudah setelah Anda memecahnya menjadi beberapa langkah sederhana. Panduan ini memandu Anda dalam memuat presentasi, mengakses dan memodifikasi data OLE yang tertanam, dan menyimpan presentasi yang diperbarui. Dengan langkah-langkah ini, Anda dapat secara efisien mengelola dan memperbarui konten yang disematkan di slide PowerPoint Anda secara terprogram.
## FAQ
### Apa itu Objek OLE di PowerPoint?
Objek OLE (Penautan dan Penyematan Objek) memungkinkan penyematan konten dari aplikasi lain, seperti spreadsheet Excel, ke dalam slide PowerPoint.
### Bisakah saya menggunakan Aspose.Slides dengan bahasa pemrograman lain?
Ya, Aspose.Slides mendukung beberapa bahasa termasuk .NET, Python, dan C++.
### Apakah saya memerlukan Aspose.Cells untuk memodifikasi objek OLE di PowerPoint?
Ya, jika objek OLE adalah spreadsheet Excel, Anda memerlukan Aspose.Cells untuk memodifikasinya.
### Apakah ada versi uji coba Aspose.Slides?
 Ya, Anda bisa mendapatkan[uji coba gratis](https://releases.aspose.com/) untuk menguji fitur Aspose.Slides.
### Di mana saya dapat menemukan dokumentasi untuk Aspose.Slides?
 Anda dapat menemukan dokumentasi terperinci di[Halaman dokumentasi Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
