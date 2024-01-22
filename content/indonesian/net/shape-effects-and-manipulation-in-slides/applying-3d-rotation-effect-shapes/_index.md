---
title: Menguasai Rotasi 3D dalam Presentasi dengan Aspose.Slides for .NET
linktitle: Menerapkan Efek Rotasi 3D pada Bentuk di Slide Presentasi
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Sempurnakan presentasi Anda dengan Aspose.Slides untuk .NET! Pelajari cara menerapkan efek rotasi 3D pada bentuk dalam tutorial ini. Buat presentasi yang dinamis dan menakjubkan secara visual.
type: docs
weight: 23
url: /id/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---
## Perkenalan
Membuat slide presentasi yang menarik dan dinamis adalah aspek kunci dari komunikasi yang efektif. Aspose.Slides for .NET menyediakan seperangkat alat canggih untuk menyempurnakan presentasi Anda, termasuk kemampuan untuk menerapkan efek rotasi 3D pada bentuk. Dalam tutorial ini, kita akan memandu proses penerapan efek rotasi 3D pada bentuk di slide presentasi menggunakan Aspose.Slides untuk .NET.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
-  Aspose.Slides untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/slides/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET, seperti Visual Studio, untuk menulis dan menjalankan kode Anda.
## Impor Namespace
Dalam proyek .NET Anda, impor namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Slides. Sertakan namespace berikut di awal kode Anda:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Langkah 1: Siapkan Proyek Anda
Buat proyek baru di lingkungan pengembangan .NET pilihan Anda. Pastikan Anda telah menambahkan referensi Aspose.Slides ke proyek Anda.
## Langkah 2: Inisialisasi Presentasi
Buat instance kelas Presentasi untuk mulai bekerja dengan slide:
```csharp
Presentation pres = new Presentation();
```
## Langkah 3: Tambahkan BentukOtomatis
Tambahkan BentukOtomatis ke slide, tentukan tipe, posisi, dan dimensinya:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Langkah 4: Atur Efek Rotasi 3D
Konfigurasikan efek rotasi 3D untuk BentukOtomatis:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Langkah 5: Simpan Presentasi
Simpan presentasi yang dimodifikasi dengan efek rotasi 3D yang diterapkan:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Langkah 6: Ulangi untuk Bentuk Lainnya
Jika Anda memiliki bentuk tambahan, ulangi Langkah 3 hingga 5 untuk setiap bentuk.
## Kesimpulan
Menambahkan efek rotasi 3D ke bentuk di slide presentasi Anda dapat meningkatkan daya tarik visualnya secara signifikan. Dengan Aspose.Slides untuk .NET, proses ini menjadi mudah, memungkinkan Anda membuat presentasi yang menawan.
## FAQ
### Bisakah saya menerapkan rotasi 3D ke kotak teks di Aspose.Slides untuk .NET?
Ya, Anda dapat menerapkan efek rotasi 3D ke berbagai bentuk, termasuk kotak teks, menggunakan Aspose.Slides.
### Apakah ada versi uji coba Aspose.Slides untuk .NET yang tersedia?
 Ya, Anda dapat mengakses versi uji coba[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides untuk .NET?
 Mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk dukungan dan diskusi komunitas.
### Bisakah saya membeli lisensi sementara untuk Aspose.Slides untuk .NET?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Slides untuk .NET?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/slides/net/).