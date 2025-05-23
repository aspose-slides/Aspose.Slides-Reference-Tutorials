---
"description": "Pelajari cara membuat grafik yang memukau dengan Aspose.Slides untuk .NET. Tingkatkan kemampuan visualisasi data Anda dengan panduan langkah demi langkah kami."
"linktitle": "Entitas dan Pemformatan Bagan"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Membuat Bagan Menarik dengan Aspose.Slides untuk .NET"
"url": "/id/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Membuat Bagan Menarik dengan Aspose.Slides untuk .NET


Dalam dunia yang digerakkan oleh data saat ini, visualisasi data yang efektif adalah kunci untuk menyampaikan informasi kepada audiens Anda. Aspose.Slides for .NET adalah pustaka canggih yang memungkinkan Anda membuat presentasi dan slide yang memukau, termasuk bagan yang menarik. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan bagan yang indah menggunakan Aspose.Slides for .NET. Kami akan menguraikan setiap contoh menjadi beberapa langkah untuk membantu Anda memahami dan menerapkan entitas dan pemformatan bagan. Jadi, mari kita mulai!

## Prasyarat

Sebelum kita mulai membuat bagan yang indah dengan Aspose.Slides untuk .NET, Anda harus memastikan bahwa Anda memiliki prasyarat berikut:

1. Aspose.Slides untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari [situs web](https://releases.aspose.com/slides/net/).

2. Lingkungan Pengembangan: Anda harus memiliki lingkungan pengembangan yang berfungsi dengan Visual Studio atau IDE lain yang mendukung pengembangan .NET.

3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# sangat penting untuk tutorial ini.

Sekarang setelah prasyarat kita terpenuhi, mari kita lanjutkan membuat bagan yang indah dengan Aspose.Slides untuk .NET.

## Mengimpor Ruang Nama

Pertama, Anda perlu mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Slides untuk .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Langkah 1: Buat Presentasi

Kita mulai dengan membuat presentasi baru untuk digunakan. Presentasi ini akan berfungsi sebagai kanvas untuk bagan kita.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "Your Document Directory";

// Buat direktori jika belum ada.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Membuat presentasi secara instan
Presentation pres = new Presentation();
```

## Langkah 2: Akses Slide Pertama

Mari mengakses slide pertama dalam presentasi di mana kita akan menempatkan bagan kita.

```csharp
// Mengakses slide pertama
ISlide slide = pres.Slides[0];
```

## Langkah 3: Tambahkan Bagan Contoh

Sekarang, kita akan menambahkan contoh diagram ke slide kita. Dalam contoh ini, kita akan membuat diagram garis dengan penanda.

```csharp
// Menambahkan bagan contoh
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Langkah 4: Tetapkan Judul Bagan

Kami akan memberi judul pada bagan kami, membuatnya lebih informatif dan menarik secara visual.

```csharp
// Menetapkan Judul Bagan
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Langkah 5: Sesuaikan Garis Grid Sumbu Vertikal

Pada langkah ini, kita akan menyesuaikan garis kisi sumbu vertikal untuk membuat bagan kita lebih menarik secara visual.

```csharp
// Mengatur format garis kisi utama untuk sumbu nilai
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Mengatur format garis grid minor untuk sumbu nilai
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Mengatur format angka sumbu nilai
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Langkah 6: Tentukan Rentang Sumbu Vertikal

Pada langkah ini, kita akan menetapkan nilai maksimum, minimum, dan satuan untuk sumbu vertikal.

```csharp
// Mengatur nilai maksimum dan minimum grafik
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Langkah 7: Kustomisasi Teks Sumbu Vertikal

Sekarang kita akan menyesuaikan tampilan teks pada sumbu vertikal.

```csharp
// Mengatur Properti Teks Sumbu Nilai
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Mengatur judul sumbu nilai
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Langkah 8: Sesuaikan Garis Grid Sumbu Horizontal

Sekarang, mari kita sesuaikan garis kisi untuk sumbu horizontal.

```csharp
// Mengatur format garis kisi utama untuk sumbu Kategori
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Mengatur format garis grid Minor untuk sumbu Kategori
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Mengatur Properti Teks Sumbu Kategori
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Langkah 9: Kustomisasi Label Sumbu Horizontal

Pada langkah ini, kita akan menyesuaikan posisi dan rotasi label sumbu horizontal.

```csharp
// Mengatur posisi label sumbu kategori
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Mengatur sudut rotasi label sumbu kategori
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Langkah 10: Sesuaikan Legenda

Mari tingkatkan legenda pada bagan kita supaya lebih mudah dibaca.

```csharp
// Mengatur Properti Teks Legenda
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Mengatur legenda grafik pertunjukan tanpa grafik yang tumpang tindih
chart.Legend.Overlay = true;
```

## Langkah 11: Sesuaikan Latar Belakang Bagan

Kami akan menyesuaikan warna latar belakang bagan, dinding belakang, dan lantai.

```csharp
// Mengatur warna dinding belakang grafik
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Mengatur warna area plot
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Langkah 12: Simpan Presentasi

Terakhir, mari simpan presentasi kita dengan bagan yang diformat.

```csharp
// Simpan Presentasi
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Kesimpulan

Membuat bagan yang cantik dan informatif dalam presentasi Anda kini lebih mudah dari sebelumnya dengan Aspose.Slides for .NET. Dalam tutorial ini, kami telah membahas langkah-langkah penting untuk menyesuaikan berbagai aspek bagan, menjadikannya menarik secara visual dan informatif. Dengan teknik-teknik ini, Anda dapat membuat bagan yang memukau yang secara efektif menyampaikan data Anda kepada audiens.

Mulailah bereksperimen dengan Aspose.Slides untuk .NET dan tingkatkan visualisasi data Anda ke tingkat berikutnya!

## Pertanyaan yang Sering Diajukan

### 1. Apa itu Aspose.Slides untuk .NET?

Aspose.Slides untuk .NET adalah pustaka canggih yang memungkinkan pengembang .NET untuk membuat, memanipulasi, dan mengonversi presentasi Microsoft PowerPoint. Pustaka ini menyediakan berbagai fitur untuk bekerja dengan slide, bentuk, bagan, dan banyak lagi.

### 2. Di mana saya dapat mengunduh Aspose.Slides untuk .NET?

Anda dapat mengunduh Aspose.Slides untuk .NET dari situs web [Di Sini](https://releases.aspose.com/slides/net/).

### 3. Apakah ada uji coba gratis yang tersedia untuk Aspose.Slides untuk .NET?

Ya, Anda bisa mendapatkan uji coba gratis Aspose.Slides untuk .NET dari [Di Sini](https://releases.aspose.com/).

### 4. Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Slides for .NET?

Jika Anda memerlukan lisensi sementara, Anda dapat memperolehnya dari [tautan ini](https://purchase.aspose.com/temporary-license/).

### 5. Apakah ada komunitas atau forum dukungan untuk Aspose.Slides for .NET?

Ya, Anda dapat menemukan komunitas dan forum dukungan Aspose.Slides [Di Sini](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}