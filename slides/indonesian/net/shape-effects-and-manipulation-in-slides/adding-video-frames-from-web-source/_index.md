---
title: Tutorial Menyematkan Bingkai Video dengan Aspose.Slides untuk .NET
linktitle: Menambahkan Bingkai Video dari Sumber Web di Slide Presentasi dengan Aspose.Slides
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara menyematkan bingkai video dengan mulus ke dalam slide PowerPoint menggunakan Aspose.Slides untuk .NET. Sempurnakan presentasi dengan multimedia dengan mudah.
weight: 20
url: /id/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Perkenalan
Dalam dunia presentasi yang dinamis, menggabungkan elemen multimedia dapat meningkatkan keterlibatan secara signifikan dan menyampaikan pesan yang berdampak. Salah satu cara ampuh untuk mencapai hal ini adalah dengan menyematkan bingkai video ke dalam slide presentasi. Dalam tutorial ini, kita akan mempelajari cara melakukannya dengan lancar menggunakan Aspose.Slides untuk .NET. Aspose.Slides adalah perpustakaan tangguh yang memungkinkan pengembang memanipulasi presentasi PowerPoint secara terprogram, memberikan kemampuan ekstensif untuk membuat, mengedit, dan menyempurnakan slide.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki hal berikut:
1.  Aspose.Slides untuk .NET Library: Unduh dan instal perpustakaan dari[Aspose.Slide untuk Dokumentasi .NET](https://reference.aspose.com/slides/net/).
2. Contoh File Video: Siapkan file video yang ingin Anda sematkan dalam presentasi Anda. Anda dapat menggunakan contoh yang diberikan dengan video bernama "Wildlife.mp4."
## Impor Namespace
Dalam proyek .NET Anda, sertakan namespace yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Mari kita uraikan proses penyematan bingkai video ke dalam slide presentasi menggunakan Aspose.Slides untuk .NET menjadi langkah-langkah yang dapat dikelola:
## Langkah 1: Siapkan Direktori
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// Buat direktori jika belum ada.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Pastikan untuk mengganti "Direktori Dokumen Anda" dan "Direktori Media Anda" dengan jalur yang sesuai di proyek Anda.
## Langkah 2: Buat Objek Presentasi
```csharp
using (Presentation pres = new Presentation())
{
    // Dapatkan slide pertama
    ISlide sld = pres.Slides[0];
```
Inisialisasi presentasi baru dan akses slide pertama untuk menyematkan bingkai video.
## Langkah 3: Sematkan Video dalam Presentasi
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 Memanfaatkan`AddVideo` metode untuk menyematkan video ke dalam presentasi, menentukan jalur file dan perilaku pemuatan.
## Langkah 4: Tambahkan Bingkai Video
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
Buat bingkai video pada slide, tentukan posisi dan dimensinya.
## Langkah 5: Konfigurasikan Pengaturan Video
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Kaitkan bingkai video dengan video yang disematkan, atur mode putar, dan sesuaikan volume sesuai preferensi Anda.
## Langkah 6: Simpan Presentasi
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Simpan presentasi yang dimodifikasi dengan bingkai video tertanam.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menyematkan bingkai video ke dalam slide presentasi menggunakan Aspose.Slides untuk .NET. Fitur ini membuka kemungkinan menarik untuk menciptakan presentasi dinamis dan menarik yang memikat audiens Anda.
## FAQ
### Bisakah saya menyematkan video dengan format berbeda menggunakan Aspose.Slides?
Ya, Aspose.Slides mendukung berbagai format video, memastikan fleksibilitas dalam presentasi Anda.
### Bagaimana cara mengontrol pengaturan pemutaran video yang disematkan?
 Sesuaikan`PlayMode` Dan`Volume` properti bingkai video untuk menyesuaikan perilaku pemutaran.
### Apakah Aspose.Slides kompatibel dengan versi terbaru .NET?
Aspose.Slides diperbarui secara berkala untuk menjaga kompatibilitas dengan kerangka .NET terbaru.
### Bisakah saya menyematkan banyak video dalam satu slide menggunakan Aspose.Slides?
Ya, Anda dapat menyematkan banyak video dengan menambahkan bingkai video tambahan ke slide.
### Di mana saya dapat menemukan dukungan untuk pertanyaan terkait Aspose.Slides?
 Mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk dukungan dan diskusi komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
