---
"date": "2025-04-15"
"description": "Pelajari cara mengotomatiskan pembuatan diagram lingkaran dalam presentasi .NET dengan Aspose.Slides, meningkatkan visualisasi data dengan mudah."
"title": "Cara Membuat dan Menyesuaikan Diagram Lingkaran dalam Presentasi .NET Menggunakan Aspose.Slides"
"url": "/id/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat dan Menyesuaikan Diagram Lingkaran dalam Presentasi .NET Menggunakan Aspose.Slides

## Perkenalan
Membuat presentasi yang menarik dan informatif sangat penting untuk komunikasi yang efektif, baik saat Anda menyajikan data di tempat kerja atau memamerkan temuan proyek terbaru Anda. Salah satu cara ampuh untuk memvisualisasikan data adalah melalui diagram lingkaran, yang dapat secara ringkas menggambarkan bagian-bagian dari keseluruhan. Namun, membuat diagram ini secara manual dalam perangkat lunak presentasi seperti PowerPoint dapat memakan waktu dan mungkin tidak memiliki fleksibilitas yang diperlukan untuk pembaruan yang dinamis.

Di sinilah Aspose.Slides for .NET berperan. Pustaka komprehensif ini memungkinkan Anda membuat, memodifikasi, dan menata presentasi secara terprogram, menjadikannya alat yang sangat berharga bagi pengembang yang ingin mengotomatiskan alur kerja mereka dan memastikan konsistensi di seluruh presentasi.

Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Slides for .NET untuk membuat dan menyesuaikan diagram pai dalam presentasi Anda. Anda akan mempelajari cara:
- **Buat presentasi dan akses slide**
- **Tambahkan dan konfigurasikan diagram lingkaran**
- **Sesuaikan data dan seri grafik**
- **Gaya sektor diagram pai**
- **Tambahkan label khusus**
- **Konfigurasikan properti tampilan dan simpan presentasi**

Siap untuk mulai membuat diagram lingkaran yang menakjubkan dengan mudah? Mari kita mulai!

## Prasyarat
Sebelum kita memulai, pastikan Anda telah menyiapkan pengaturan berikut:

### Perpustakaan yang Diperlukan
- Aspose.Slides untuk .NET (versi 21.11 atau yang lebih baru direkomendasikan)

### Pengaturan Lingkungan
- Lingkungan pengembangan yang menjalankan .NET Framework atau .NET Core/5+/6+
- Editor kode seperti Visual Studio

### Prasyarat Pengetahuan
- Pemahaman dasar tentang pemrograman C#
- Keakraban dengan konsep berorientasi objek

## Menyiapkan Aspose.Slides untuk .NET
Untuk memulai, Anda perlu memasang pustaka Aspose.Slides. Anda dapat melakukannya dengan salah satu metode berikut:

**.KLIK NET**
```bash
dotnet add package Aspose.Slides
```

**Konsol Pengelola Paket**
```powershell
Install-Package Aspose.Slides
```

**Antarmuka Pengguna Pengelola Paket NuGet**
- Buka proyek Anda di Visual Studio.
- Buka "Alat" > "Manajer Paket NuGet" > "Kelola Paket NuGet untuk Solusi."
- Cari "Aspose.Slides" dan instal versi terbaru.

### Langkah-langkah Memperoleh Lisensi
Untuk menggunakan Aspose.Slides, Anda dapat memulai dengan uji coba gratis dengan mengunduh lisensi sementara. Kunjungi [Situs web Aspose](https://purchase.aspose.com/temporary-license/) untuk mendapatkannya. Untuk penggunaan berkelanjutan, pertimbangkan untuk membeli lisensi penuh.

### Inisialisasi dan Pengaturan Dasar
Setelah terinstal, inisialisasi kelas Presentasi, yang mewakili file PPTX Anda:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Panduan Implementasi
Kami akan membagi proses pembuatan diagram lingkaran menjadi beberapa bagian yang mudah dikelola. Setiap bagian dirancang untuk berfokus pada fitur tertentu, sehingga Anda dapat mengembangkan pengetahuan secara bertahap.

### Membuat Presentasi dan Mengakses Slide
**Ringkasan:** Mulailah dengan membuat presentasi baru dan mengakses slide pertamanya. Ini akan menjadi tahap awal untuk menambahkan diagram dan elemen lainnya.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Membuat instance kelas Presentasi yang mewakili file PPTX
    Presentation presentation = new Presentation();
    
    // Akses slide pertama
    ISlide slides = presentation.Slides[0];
}
```

### Tambahkan dan Konfigurasikan Bagan Pai
**Ringkasan:** Pelajari cara menambahkan diagram lingkaran ke slide Anda dan mengatur judulnya sesuai konteks.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Membuat instance kelas Presentasi yang mewakili file PPTX
    Presentation presentation = new Presentation();
    
    // Akses slide pertama
    ISlide slides = presentation.Slides[0];
    
    // Tambahkan bagan dengan data default ke slide
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Mengatur Judul Bagan
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Sesuaikan Data Bagan dan Seri
**Ringkasan:** Sesuaikan kategori dan seri data agar sesuai dengan kebutuhan spesifik Anda.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Membuat instance kelas Presentasi yang mewakili file PPTX
    Presentation presentation = new Presentation();
    
    // Akses slide pertama
    ISlide slides = presentation.Slides[0];
    
    // Tambahkan bagan dengan data default ke slide
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Tetapkan seri pertama untuk Menampilkan Nilai
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Mengatur indeks lembar data grafik
    int defaultWorksheetIndex = 0;
    
    // Mendapatkan lembar kerja data grafik
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Hapus seri dan kategori yang dihasilkan secara default
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Menambahkan kategori baru
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Menambahkan seri baru
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Sekarang mengisi data seri
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Sesuaikan Gaya Sektor Diagram Lingkaran
**Ringkasan:** Beri gaya pada sektor individual diagram lingkaran Anda untuk meningkatkan daya tarik visual dan menekankan poin data utama.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Membuat instance kelas Presentasi yang mewakili file PPTX
    Presentation presentation = new Presentation();
    
    // Akses slide pertama
    ISlide slides = presentation.Slides[0];
    
    // Tambahkan bagan dengan data default ke slide
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Dapatkan seri dari bagan
    IChartSeries series = chart.ChartData.Series[0];
    
    // Menyesuaikan gaya sektor untuk setiap titik data dalam seri
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Menetapkan batas sektor
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Menetapkan batas sektor
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Menetapkan batas sektor
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Tambahkan Label Kustom ke Bagan Pai
**Ringkasan:** Sempurnakan diagram lingkaran Anda dengan menambahkan label khusus untuk representasi data yang lebih jelas.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Sesuaikan posisi label sesuai kebutuhan
    }
}
```

### Kesimpulan
Anda kini telah mempelajari cara membuat dan menyesuaikan diagram lingkaran dalam presentasi .NET menggunakan Aspose.Slides. Otomatisasi ini dapat meningkatkan upaya visualisasi data Anda secara signifikan, menghemat waktu, dan memastikan konsistensi di seluruh presentasi.

Untuk lebih mengeksplorasi kemampuan Aspose.Slides untuk .NET, pertimbangkan untuk mempelajari fitur tambahan seperti membuat jenis bagan lain atau mengintegrasikan elemen desain yang lebih kompleks ke dalam slide Anda.

Selamat membuat kode!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}