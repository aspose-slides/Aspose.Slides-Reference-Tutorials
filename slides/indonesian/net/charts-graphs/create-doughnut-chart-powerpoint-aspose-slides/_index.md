---
"date": "2025-04-15"
"description": "Pelajari cara membuat bagan donat yang dinamis dan menarik secara visual dalam presentasi PowerPoint menggunakan pustaka Aspose.Slides for .NET yang canggih."
"title": "Cara Membuat Bagan Donat di PowerPoint Menggunakan Aspose.Slides untuk .NET"
"url": "/id/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara Membuat Bagan Donat di PowerPoint Menggunakan Aspose.Slides untuk .NET
Membuat bagan yang menarik secara visual sangat penting untuk penyajian data yang efektif. Bagan donat sangat cocok untuk mengilustrasikan bagian-bagian dari keseluruhan, sehingga cocok untuk visualisasi data berbasis persentase. Tutorial ini akan memandu Anda membuat bagan donat yang dinamis di PowerPoint menggunakan pustaka Aspose.Slides for .NET yang canggih.

## Perkenalan
Presentasi sering kali memerlukan representasi visual dari kumpulan data yang kompleks, sedangkan diagram batang atau garis tradisional mungkin tidak memadai. Diagram donat muncul sebagai alat serbaguna untuk mengomunikasikan data berbasis persentase secara efektif dengan gaya dan kejelasan. Dalam tutorial ini, kita akan membahas bagaimana Aspose.Slides for .NET menyederhanakan proses pembuatan diagram ini secara langsung dalam PowerPoint.

**Apa yang Akan Anda Pelajari:**
- Menyiapkan Aspose.Slides untuk .NET
- Petunjuk langkah demi langkah untuk membuat diagram donat
- Menambahkan seri dan kategori ke bagan Anda
- Mengonfigurasi label data untuk meningkatkan kejelasan
- Menyimpan presentasi akhir

Mari selami bagaimana Anda dapat memanfaatkan Aspose.Slides for .NET untuk menyempurnakan presentasi Anda dengan bagan donat khusus.

## Prasyarat
Sebelum kita memulai, pastikan Anda telah menyiapkan hal-hal berikut:
- **Aspose.Slides untuk pustaka .NET**: Tersedia melalui NuGet atau unduh langsung.
- **Lingkungan Pengembangan**:Visual Studio direkomendasikan untuk proyek .NET.
- Pengetahuan dasar tentang C# dan keakraban dengan struktur PowerPoint.

## Menyiapkan Aspose.Slides untuk .NET
Untuk mulai membuat bagan, pertama-tama Anda perlu menyiapkan pustaka Aspose.Slides di proyek Anda. Berikut ini beberapa cara untuk menginstalnya:

**Menggunakan .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Menggunakan Konsol Manajer Paket:**

```powershell
Install-Package Aspose.Slides
```

**Melalui UI Pengelola Paket NuGet:**
Cari "Aspose.Slides" dan instal versi terbaru.

Setelah terinstal, Anda dapat mulai menyiapkan proyek Anda. Jika Anda baru mengenal Aspose.Slides, pertimbangkan untuk mendapatkan lisensi sementara atau uji coba gratis untuk menjelajahi semua kemampuannya tanpa batasan.

### Inisialisasi Proyek Anda
Berikut ini cara menginisialisasi Aspose.Slides di aplikasi Anda:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Buat instance kelas Presentasi
        Presentation presentation = new Presentation();
        
        // Kode Anda untuk memanipulasi presentasi ada di sini
        
        // Simpan presentasi
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Panduan Implementasi
### Membuat Bagan Donat
#### Ringkasan
Pertama, kita akan membuat diagram donat kosong di slide PowerPoint. Diagram ini berfungsi sebagai dasar untuk menambahkan data dan menyesuaikan tampilannya.

**Langkah 1: Tambahkan Bagan Donat**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Tambahkan diagram donat ke slide pertama pada posisi (10, 10) dengan ukuran (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Hapus seri dan kategori yang ada
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Nonaktifkan legenda untuk tampilan yang lebih bersih
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Penjelasan:**
- **tambahkanBagan**: Menyisipkan bagan donat baru pada slide.
- **dapatkanBukuPekerjaanDataBagan**: Menyediakan akses ke sel data dalam bagan untuk manipulasi.

### Menambahkan Seri dan Kategori
#### Ringkasan
Berikutnya, kami akan mengisi bagan Anda dengan data yang bermakna dengan menambahkan seri dan kategori.

**Langkah 2: Tambahkan Seri Data**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Tambahkan seri
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Menyesuaikan lubang donat dan sudut awal
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Tambahkan kategori
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Memformat isian dan garis titik data
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Penjelasan:**
- **menambahkan**: Menyisipkan seri dan kategori baru ke dalam bagan.
- **setelUkuranLubangDonat**Mengonfigurasi ukuran lubang donat, meningkatkan daya tarik visualnya.

### Mengonfigurasi Label Data
#### Ringkasan
Label data memberikan konteks pada data bagan Anda. Mari tingkatkan keterbacaan dengan menyesuaikannya.

**Langkah 3: Kustomisasi Label Data**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Menyesuaikan label data
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Penjelasan:**
- **Label Data I**: Menyesuaikan label data untuk kejelasan dan presentasi.
- **setTeksPusat**Bahasa Indonesia: **tampilkanPersentase**: Tingkatkan keterbacaan label dengan memusatkan teks dan menampilkan persentase.

## Kesimpulan
Dengan mengikuti panduan ini, Anda telah mempelajari cara membuat bagan donat dinamis di PowerPoint menggunakan Aspose.Slides for .NET. Pustaka canggih ini memungkinkan kustomisasi yang luas, sehingga Anda dapat menyesuaikan bagan secara tepat dengan kebutuhan presentasi Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}