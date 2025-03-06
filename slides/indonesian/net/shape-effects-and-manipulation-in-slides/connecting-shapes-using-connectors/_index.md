---
title: Aspose.Slides - Hubungkan Bentuk dengan Mulus di .NET
linktitle: Menghubungkan Bentuk menggunakan Konektor dalam Presentasi
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Jelajahi kekuatan Aspose.Slides untuk .NET, menghubungkan bentuk dengan mudah dalam presentasi Anda. Tinggikan slide Anda dengan konektor dinamis.
weight: 29
url: /id/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam dunia presentasi yang dinamis, kemampuan untuk menghubungkan bentuk menggunakan konektor menambah lapisan kecanggihan pada slide Anda. Aspose.Slides untuk .NET memberdayakan pengembang untuk mencapai hal ini dengan lancar. Tutorial ini akan memandu Anda melalui prosesnya, menguraikan setiap langkah untuk memastikan pemahaman yang jelas.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang kerangka C# dan .NET.
-  Aspose.Slides untuk .NET diinstal. Jika tidak, unduh[Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan pengembangan telah disiapkan.
## Impor Namespace
Dalam kode C# Anda, mulailah dengan mengimpor namespace yang diperlukan:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Siapkan Direktori Dokumen
Mulailah dengan menentukan direktori untuk dokumen Anda:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Membuat Instansiasi Kelas Presentasi
Buat instance kelas Presentasi untuk mewakili file PPTX Anda:
```csharp
using (Presentation input = new Presentation())
{
    // Mengakses koleksi bentuk untuk slide yang dipilih
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Tambahkan Bentuk ke Slide
Tambahkan bentuk yang diperlukan ke slide Anda, seperti Ellipse dan Rectangle:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Tambahkan Bentuk Konektor
Sertakan bentuk konektor dalam koleksi bentuk slide:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Hubungkan Bentuk dengan Konektor
Tentukan bentuk yang akan dihubungkan dengan konektor:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Rutekan Ulang Konektor
Panggil metode perutean ulang untuk mengatur jalur terpendek otomatis antar bentuk:
```csharp
connector.Reroute();
```
## 7. Simpan Presentasi
Simpan presentasi Anda untuk melihat bentuk yang terhubung:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Kesimpulan
Selamat! Anda telah berhasil menyambungkan bentuk menggunakan konektor di slide presentasi menggunakan Aspose.Slides untuk .NET. Sempurnakan presentasi Anda dengan fitur canggih ini dan pikat audiens Anda.
## FAQ
### Apakah Aspose.Slides for .NET kompatibel dengan kerangka .NET terbaru?
Ya, Aspose.Slides untuk .NET diperbarui secara berkala untuk memastikan kompatibilitas dengan versi kerangka .NET terbaru.
### Bisakah saya menghubungkan lebih dari dua bentuk menggunakan satu konektor?
Tentu saja, Anda dapat menghubungkan beberapa bentuk dengan memperluas logika konektor dalam kode Anda.
### Apakah ada batasan pada bentuk yang dapat saya sambungkan?
Aspose.Slides untuk .NET mendukung penyambungan berbagai bentuk, termasuk bentuk dasar, seni cerdas, dan bentuk khusus.
### Bagaimana cara menyesuaikan tampilan konektor?
Jelajahi dokumentasi Aspose.Slides untuk mengetahui metode menyesuaikan tampilan konektor, seperti gaya garis dan warna.
### Apakah ada forum komunitas untuk dukungan Aspose.Slides?
 Ya, Anda dapat menemukan bantuan dan berbagi pengalaman Anda di[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
