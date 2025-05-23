---
"date": "2025-04-15"
"description": "Pelajari cara membuat diagram donat dinamis menggunakan Aspose.Slides for .NET. Ikuti panduan ini untuk petunjuk langkah demi langkah, termasuk pengaturan dan fitur lanjutan."
"title": "Panduan Langkah demi Langkah &#58; Membuat Bagan Donat dengan Aspose.Slides .NET | Bagan & Grafik"
"url": "/id/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Panduan Langkah demi Langkah: Membuat Bagan Donat dengan Aspose.Slides .NET

## Perkenalan

Bayangkan Anda ditugaskan untuk menyajikan hasil analisis data kepada tim atau klien Anda, dan Anda memerlukan cara yang menarik untuk memvisualisasikan informasi tersebut. Gunakan bagan donat—alat serbaguna yang dapat mengubah angka mentah menjadi wawasan yang mudah dipahami. Dengan Aspose.Slides untuk .NET, membuat bagan donat khusus di slide presentasi Anda menjadi mudah dan efisien. Panduan ini akan memandu Anda menggunakan Aspose.Slides untuk membuat bagan donat yang menarik secara visual, lengkap dengan konfigurasi seri yang disesuaikan.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan lingkungan pengembangan Anda dengan Aspose.Slides untuk .NET
- Membuat dan menyesuaikan diagram donat dalam presentasi
- Menerapkan fitur-fitur lanjutan seperti nama kategori dan garis pemimpin
- Mengoptimalkan kinerja untuk set data besar

Mari kita bahas prasyarat yang Anda perlukan untuk memulai.

## Prasyarat

Sebelum menerapkan fitur ini, pastikan lingkungan pengembangan Anda telah disiapkan dengan benar. Tutorial ini mengasumsikan pengetahuan dasar tentang pemrograman .NET dan keakraban dengan Visual Studio atau IDE serupa.

### Pustaka dan Versi yang Diperlukan
- **Aspose.Slides untuk .NET**: Pastikan kompatibilitas dengan versi terbaru dengan memeriksa [dokumentasi resmi](https://reference.aspose.com/slides/net/).

### Persyaratan Pengaturan Lingkungan
- Lingkungan .NET yang berfungsi.
- Akses ke editor kode, seperti Visual Studio.

### Prasyarat Pengetahuan
- Pemahaman dasar tentang C# dan kerangka kerja .NET.
- Kemampuan memahami konsep perangkat lunak presentasi (opsional tetapi bermanfaat).

## Menyiapkan Aspose.Slides untuk .NET

Untuk mulai menggunakan Aspose.Slides di proyek Anda, Anda perlu menginstalnya melalui NuGet. Berikut adalah metode yang tersedia:

**Menggunakan .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Menggunakan Manajer Paket:**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet:**
Cari "Aspose.Slides" dan instal versi terbaru.

### Langkah-langkah Memperoleh Lisensi

1. **Uji Coba Gratis**:Mulailah dengan [uji coba gratis](https://releases.aspose.com/slides/net/) untuk menjelajahi fungsi dasar.
2. **Lisensi Sementara**: Dapatkan lisensi sementara jika Anda memerlukan akses ke fitur lengkap untuk tujuan evaluasi dengan mengunjungi [Di Sini](https://purchase.aspose.com/temporary-license/).
3. **Pembelian**:Untuk penggunaan komersial, beli lisensi dari [Situs web Aspose](https://purchase.aspose.com/buy).

Setelah terinstal dan dilisensikan, inisialisasi Aspose.Slides di proyek Anda:
```csharp
using Aspose.Slides;

// Inisialisasi Aspose.Slides untuk .NET
var presentation = new Presentation();
```

## Panduan Implementasi

### Membuat Presentasi Baru dan Menambahkan Bagan Donat

#### Ringkasan
Kita akan mulai dengan membuat presentasi baru dan menambahkan diagram donat ke slide pertama. Bagian ini membahas cara memuat presentasi yang sudah ada, mengakses slide, dan menyisipkan diagram.

**Langkah 1: Memuat atau Membuat Presentasi**
Pertama, tentukan direktori dokumen Anda dan muat presentasi yang ada:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Jika Anda belum memiliki file, buat file baru dengan `new Presentation()`.

**Langkah 2: Akses Slide Pertama**
Dapatkan akses ke slide pertama tempat kita akan menambahkan bagan kita:
```csharp
ISlide slide = pres.Slides[0];
```

**Langkah 3: Tambahkan Bagan Donat**
Tambahkan bagan donat pada koordinat dan dimensi yang ditentukan:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Mengonfigurasi Buku Kerja Data

#### Ringkasan
Bagian ini menjelaskan cara mengonfigurasi buku kerja data yang terkait dengan bagan donat Anda.

**Langkah 4: Akses dan Hapus Data yang Ada**
Akses buku kerja data bagan. Lalu hapus seri atau kategori yang ada:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Langkah 5: Nonaktifkan Legenda dan Tambahkan Seri**
Nonaktifkan legenda untuk menjaga grafik tetap bersih, lalu tambahkan hingga 15 seri dengan konfigurasi khusus:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Menambahkan Kategori dan Titik Data

#### Ringkasan
Sekarang, mari isi bagan dengan kategori dan titik data untuk setiap seri.

**Langkah 6: Tambahkan Kategori**
Ulangi untuk menambahkan 15 kategori:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Langkah 7: Mengisi Titik Data**
Tambahkan titik data untuk setiap seri dalam kategori saat ini:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Sesuaikan penampilan
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Konfigurasikan format label untuk seri terakhir
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Konfigurasikan tampilan label
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Menyimpan Presentasi

**Langkah 8: Simpan File**
Terakhir, simpan presentasi Anda ke direktori yang ditentukan:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}