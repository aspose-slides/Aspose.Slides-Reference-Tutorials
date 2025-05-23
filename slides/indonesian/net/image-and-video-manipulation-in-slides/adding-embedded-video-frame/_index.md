---
"description": "Sempurnakan presentasi Anda dengan video tertanam menggunakan Aspose.Slides for .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar."
"linktitle": "Aspose.Slides - Menambahkan Video Tertanam dalam Presentasi .NET"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides - Menambahkan Video Tertanam dalam Presentasi .NET"
"url": "/id/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Menambahkan Video Tertanam dalam Presentasi .NET

## Perkenalan
Dalam dunia presentasi yang dinamis, mengintegrasikan elemen multimedia dapat meningkatkan keterlibatan secara signifikan. Aspose.Slides untuk .NET menyediakan solusi yang hebat untuk menggabungkan bingkai video yang disematkan ke dalam slide presentasi Anda. Tutorial ini akan memandu Anda melalui prosesnya, menguraikan setiap langkah untuk memastikan pengalaman yang lancar.
## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda memiliki hal berikut:
- Aspose.Slides untuk Pustaka .NET: Unduh dan instal pustaka dari [halaman rilis](https://releases.aspose.com/slides/net/).
- Konten Media: Miliki berkas video (misalnya, "Wildlife.mp4") yang ingin Anda sematkan dalam presentasi Anda.
## Mengimpor Ruang Nama
Mulailah dengan mengimpor namespace yang diperlukan dalam proyek .NET Anda:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Langkah 1: Siapkan Direktori
Pastikan proyek Anda memiliki direktori yang diperlukan untuk file dokumen dan media:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Buat direktori jika belum ada.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Langkah 2: Buat Kelas Presentasi
Buat contoh kelas Presentasi untuk merepresentasikan file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Dapatkan slide pertama
    ISlide sld = pres.Slides[0];
```
## Langkah 3: Sisipkan Video ke Dalam Presentasi
Gunakan kode berikut untuk menyematkan video di dalam presentasi:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Langkah 4: Tambahkan Bingkai Video
Sekarang, tambahkan bingkai video ke slide:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Langkah 5: Mengatur Properti Video
Atur video ke bingkai video dan konfigurasikan mode pemutaran dan volume:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Langkah 6: Simpan Presentasi
Terakhir, simpan file PPTX ke disk:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Ulangi langkah-langkah ini untuk setiap video yang ingin Anda sematkan dalam presentasi Anda.
## Kesimpulan
Selamat! Anda telah berhasil menambahkan bingkai video tertanam ke presentasi Anda menggunakan Aspose.Slides for .NET. Fitur dinamis ini dapat meningkatkan presentasi Anda ke tingkat yang lebih tinggi, memikat audiens Anda dengan elemen multimedia yang terintegrasi dengan mulus ke dalam slide Anda.
## Tanya Jawab Umum
### Bisakah saya menyematkan video di slide presentasi mana pun?
Ya, Anda dapat memilih slide mana pun dengan mengubah indeks di `pres.Slides[index]`.
### Format video apa yang didukung?
Aspose.Slides mendukung berbagai format video, termasuk MP4, AVI, dan WMV.
### Bisakah saya menyesuaikan ukuran dan posisi bingkai video?
Tentu saja! Sesuaikan parameter di `AddVideoFrame(x, y, width, height, video)` sesuai kebutuhan.
### Apakah ada batasan jumlah video yang dapat saya sematkan?
Jumlah video yang tertanam biasanya dibatasi oleh kapasitas perangkat lunak presentasi Anda.
### Bagaimana saya bisa mencari bantuan lebih lanjut atau berbagi pengalaman saya?
Kunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk dukungan dan diskusi komunitas.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}