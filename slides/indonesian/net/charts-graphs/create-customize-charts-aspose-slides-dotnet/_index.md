---
"date": "2025-04-15"
"description": "Pelajari cara membuat dan menyesuaikan diagram menggunakan Aspose.Slides for .NET, termasuk menampilkan persentase sebagai label data. Ikuti panduan langkah demi langkah ini."
"title": "Cara Membuat & Menyesuaikan Grafik dengan Aspose.Slides .NET&#58; Menampilkan Persentase sebagai Label"
"url": "/id/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat & Menyesuaikan Bagan dengan Aspose.Slides .NET: Menampilkan Persentase sebagai Label

## Perkenalan

Menyajikan data secara efektif sangat penting dalam banyak bidang, dan bagan memainkan peran penting dengan mengubah informasi yang rumit menjadi visual yang jelas. Membuat bagan yang sempurna melibatkan tugas penyesuaian seperti menampilkan persentase pada label—tugas yang dipermudah dengan Aspose.Slides for .NET. Pustaka ini menyederhanakan proses pembuatan dan modifikasi bagan dalam presentasi PowerPoint.

Dalam tutorial ini, Anda akan mempelajari cara menggunakan Aspose.Slides for .NET untuk membuat bagan kolom bertumpuk dari awal dan menyesuaikannya dengan menampilkan nilai persentase sebagai label data. Dengan mengikuti langkah-langkah ini, Anda akan menyempurnakan slide Anda dengan representasi data yang tepat dan menarik secara visual.

**Apa yang Akan Anda Pelajari:**
- Menginisialisasi Aspose.Slides untuk .NET
- Membuat bagan kolom bertumpuk
- Menghitung dan menampilkan persentase pada label data
- Praktik terbaik mengoptimalkan kinerja grafik

Sebelum kita mulai implementasi, mari pastikan Anda telah menyiapkan segalanya untuk memulai.

## Prasyarat

Untuk mengikuti tutorial ini secara efektif, pastikan Anda memiliki:
- **SDK Inti .NET** terinstal di komputer Anda.
- Pemahaman dasar tentang pengembangan aplikasi C# dan .NET.
- Visual Studio atau IDE serupa untuk menulis dan menjalankan kode C#.

Anda memerlukan Aspose.Slides for .NET untuk membuat bagan, jadi pastikan pengaturannya seperti yang dijelaskan di bawah ini.

## Menyiapkan Aspose.Slides untuk .NET

Aspose.Slides untuk .NET adalah pustaka canggih yang memungkinkan Anda bekerja dengan presentasi PowerPoint secara terprogram. Berikut cara menambahkannya ke proyek Anda:

### Instalasi

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Konsol Manajer Paket:**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet:** 
- Buka NuGet Package Manager dan cari "Aspose.Slides". Instal versi terbaru.

### Akuisisi Lisensi

Untuk memanfaatkan Aspose.Slides secara penuh, mulailah dengan uji coba gratis. Untuk penggunaan lebih lama, pertimbangkan untuk memperoleh lisensi sementara atau membelinya dari [Asumsikan](https://purchase.aspose.com/buy)Ikuti panduan mereka untuk menyiapkan lisensi di lingkungan proyek Anda.

### Inisialisasi Dasar

Setelah terinstal, inisialisasi `Presentation` kelas untuk mulai membuat slide:
```csharp
using Aspose.Slides;

// Inisialisasi instance kelas Presentasi
tPresentation presentation = new Presentation();
```

Sekarang, mari kita lanjutkan ke penerapan fitur pembuatan dan penyesuaian bagan menggunakan Aspose.Slides untuk .NET.

## Panduan Implementasi

### Membuat Bagan Kolom Bertumpuk

Sasaran kami adalah membuat bagan kolom bertumpuk dan menyesuaikannya dengan menampilkan persentase sebagai label data. Berikut caranya:

#### Inisialisasi Presentasi

Mulailah dengan membuat contoh `Presentation`:
```csharp
using Aspose.Slides;

// Inisialisasi instance kelas Presentasi
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Tambahkan Bagan ke Slide

Tambahkan bagan kolom bertumpuk ke slide pertama Anda pada koordinat dan dimensi yang ditentukan:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Baris ini menciptakan `StackedColumn` grafik pada posisi (20, 20) dengan lebar dan tinggi 400.

#### Hitung Nilai Total untuk Perhitungan Persentase

Untuk menampilkan persentase, hitung nilai total untuk setiap kategori di semua seri:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Jumlahkan nilai semua seri untuk setiap kategori
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Sesuaikan Label Data untuk Menampilkan Nilai Persentase

Selanjutnya, ulangi setiap seri dan sesuaikan label data:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Hitung persentase
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Hapus teks untuk menghindari tumpang tindih
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Konfigurasikan format label untuk menyembunyikan label data default
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Bagian ini menghitung persentase untuk setiap titik data dan menetapkannya sebagai label khusus, memastikan tidak ada tumpang tindih dengan label default.

#### Simpan Presentasi

Terakhir, simpan presentasi Anda untuk melihat hasilnya:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Aplikasi Praktis

Menampilkan persentase dalam grafik dapat sangat berguna dalam skenario seperti:
1. **Pelaporan Keuangan:** Menampilkan distribusi portofolio atau hasil investasi sebagai persentase.
2. **Analisis Penjualan:** Mewakili data pangsa pasar berdasarkan persentase untuk menyoroti kinerja di seluruh wilayah.
3. **Hasil Survei:** Tampilkan respons survei sebagai persentase untuk perbandingan visual yang lebih baik.
4. **Manajemen Proyek:** Gunakan diagram lingkaran dengan persentase untuk menggambarkan alokasi sumber daya.
5. **Pendidikan:** Jelaskan konsep statistik menggunakan visual berbasis persentase yang jelas.

Mengintegrasikan bagan yang disesuaikan ini ke dalam sistem seperti CRM atau ERP dapat meningkatkan dasbor dan laporan, membantu proses pengambilan keputusan.

## Pertimbangan Kinerja

Saat bekerja dengan Aspose.Slides untuk .NET, terutama dengan kumpulan data besar:
- **Manajemen Memori:** Buang objek presentasi dengan benar untuk mengosongkan memori. Gunakan `using` pernyataan jika berlaku.
- **Penanganan Data yang Efisien:** Lakukan perhitungan di luar loop jika memungkinkan untuk mengurangi overhead komputasi.
- **Penyeimbangan Beban:** Untuk aplikasi web, pastikan sumber daya server disediakan secara memadai untuk permintaan pembuatan bagan secara bersamaan.

## Kesimpulan

Tutorial ini membahas pembuatan dan penyesuaian diagram menggunakan Aspose.Slides for .NET dengan menampilkan nilai persentase sebagai label. Menguasai teknik ini memungkinkan Anda untuk menyempurnakan presentasi Anda dengan representasi data yang terperinci dan menarik secara visual.

Sebagai langkah berikutnya, jelajahi jenis bagan dan opsi penyesuaian lain yang tersedia di Aspose.Slides. Bereksperimenlah dengan kumpulan data yang berbeda untuk mengubahnya menjadi visual yang hebat yang mengomunikasikan wawasan dengan jelas.

## Bagian FAQ

**Q1: Bagaimana cara menangani kumpulan data besar saat membuat bagan dengan Aspose.Slides untuk .NET?**
A1: Untuk kumpulan data besar, optimalkan perhitungan dan gunakan teknik manajemen memori yang efisien. Uraikan tugas pemrosesan untuk menghindari kelebihan memori.

**Q2: Dapatkah saya menggunakan Aspose.Slides untuk .NET dalam aplikasi web?**
A2: Ya, dapat diintegrasikan ke dalam aplikasi ASP.NET. Pastikan alokasi sumber daya server yang tepat untuk kinerja yang optimal.

**Q3: Apakah mungkin untuk mengekspor bagan yang dibuat dengan Aspose.Slides ke format lain?**
A3: Tentu saja! Anda dapat mengekspor presentasi yang berisi grafik yang telah Anda sesuaikan ke berbagai format seperti PDF dan file gambar menggunakan kemampuan pustaka.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}