---
title: Menguasai Efek After-Animasi di PowerPoint dengan Aspose.Slides
linktitle: Kontrol Setelah Animasi Ketik di Slide
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari cara mengontrol efek setelah animasi di slide PowerPoint menggunakan Aspose.Slides untuk .NET. Sempurnakan presentasi Anda dengan elemen visual dinamis.
type: docs
weight: 11
url: /id/net/slide-animation-control/control-after-animation-type/
---
## Perkenalan
Meningkatkan presentasi Anda dengan animasi dinamis adalah aspek penting dalam melibatkan audiens Anda. Aspose.Slides untuk .NET memberikan solusi ampuh untuk mengontrol efek setelah animasi dalam slide. Dalam tutorial ini, kami akan memandu Anda melalui proses penggunaan Aspose.Slides untuk .NET untuk memanipulasi tipe setelah animasi pada slide. Dengan mengikuti panduan langkah demi langkah ini, Anda akan dapat membuat presentasi yang lebih interaktif dan menarik secara visual.
## Prasyarat
Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki yang berikut ini:
- Pengetahuan dasar tentang pemrograman C# dan .NET.
-  Aspose.Slides untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/slides/net/).
- Lingkungan pengembangan terintegrasi (IDE) seperti Visual Studio.
## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Slides. Tambahkan baris berikut ke kode Anda:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
Sekarang, mari kita bagi kode yang diberikan menjadi beberapa langkah untuk pemahaman yang lebih baik:
## Langkah 1: Siapkan Direktori Dokumen
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Pastikan direktori yang ditentukan ada, atau buatlah jika tidak ada.
## Langkah 2: Tentukan Jalur File Output
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
Tentukan jalur file keluaran untuk presentasi yang dimodifikasi.
## Langkah 3: Muat Presentasi
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
Buat instance kelas Presentasi dan muat presentasi yang ada.
## Langkah 4: Ubah Efek Setelah Animasi pada Slide 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
Kloning slide pertama, akses urutan timeline-nya, dan atur efek setelah animasi ke "Sembunyikan pada Klik Mouse Berikutnya".
## Langkah 5: Ubah Efek Setelah Animasi pada Slide 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
Kloning lagi slide pertama, kali ini ubah efek setelah animasi menjadi "Warna" dengan warna hijau.
## Langkah 6: Ubah Efek Setelah Animasi pada Slide 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
Kloning slide pertama sekali lagi, atur efek setelah animasi ke "Sembunyikan Setelah Animasi".
## Langkah 7: Simpan Presentasi yang Dimodifikasi
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
Simpan presentasi yang dimodifikasi dengan jalur file keluaran yang ditentukan.
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengontrol efek setelah animasi pada slide menggunakan Aspose.Slides untuk .NET. Bereksperimenlah dengan berbagai jenis animasi setelahnya untuk membuat presentasi yang lebih dinamis dan menarik.
## FAQ
### Bisakah saya menerapkan efek setelah animasi yang berbeda ke masing-masing elemen dalam slide?
Ya kamu bisa. Ulangi elemen-elemennya dan sesuaikan efek setelah animasinya.
### Apakah Aspose.Slides kompatibel dengan versi terbaru .NET?
Ya, Aspose.Slides diperbarui secara berkala untuk memastikan kompatibilitas dengan versi kerangka .NET terbaru.
### Bagaimana cara menambahkan animasi khusus ke slide menggunakan Aspose.Slides?
 Lihat dokumentasi[Di Sini](https://reference.aspose.com/slides/net/) untuk informasi mendetail tentang menambahkan animasi khusus.
### Format file apa yang didukung Aspose.Slides untuk menyimpan presentasi?
Aspose.Slides mendukung berbagai format, termasuk PPTX, PPT, PDF, dan banyak lagi. Periksa dokumentasi untuk daftar lengkapnya.
### Di mana saya bisa mendapatkan dukungan atau mengajukan pertanyaan terkait Aspose.Slides?
 Mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11) untuk dukungan dan interaksi komunitas.