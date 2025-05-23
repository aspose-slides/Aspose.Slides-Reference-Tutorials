---
"description": "Pelajari kustomisasi bagan tingkat lanjut di Aspose.Slides for .NET. Buat bagan yang menarik secara visual dengan panduan langkah demi langkah."
"linktitle": "Kustomisasi Bagan Lanjutan di Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Kustomisasi Bagan Lanjutan di Aspose.Slides"
"url": "/id/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Kustomisasi Bagan Lanjutan di Aspose.Slides


Membuat bagan yang menarik secara visual dan informatif merupakan bagian penting dari penyajian data dalam banyak aplikasi. Aspose.Slides for .NET menyediakan alat yang tangguh untuk kustomisasi bagan, yang memungkinkan Anda menyempurnakan setiap aspek bagan Anda. Dalam tutorial ini, kita akan menjelajahi teknik kustomisasi bagan tingkat lanjut menggunakan Aspose.Slides for .NET.

## Prasyarat

Sebelum menyelami kustomisasi bagan tingkat lanjut dengan Aspose.Slides untuk .NET, pastikan Anda memiliki prasyarat berikut:

1. Pustaka Aspose.Slides untuk .NET: Anda perlu menginstal dan mengonfigurasi pustaka Aspose.Slides dengan benar di proyek .NET Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/net/).

2. Lingkungan Pengembangan .NET: Anda harus menyiapkan lingkungan pengembangan .NET, termasuk Visual Studio atau IDE lain pilihan Anda.

3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan membantu, karena kita akan menulis kode C# untuk bekerja dengan Aspose.Slides.

Sekarang, mari kita uraikan penyesuaian grafik tingkat lanjut ke dalam beberapa langkah untuk memandu Anda melalui prosesnya.

## Langkah 1: Buat Presentasi

Pertama, buat presentasi baru menggunakan Aspose.Slides.

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

Pada langkah ini, kita memulai presentasi baru yang akan memuat bagan kita.

## Langkah 2: Akses Slide Pertama

Berikutnya, akses slide pertama dalam presentasi di mana Anda ingin menambahkan bagan.

```csharp
// Mengakses slide pertama
ISlide slide = pres.Slides[0];
```

Potongan kode ini memungkinkan Anda bekerja dengan slide pertama dalam presentasi.

## Langkah 3: Menambahkan Bagan Contoh

Sekarang, mari tambahkan contoh diagram ke slide. Dalam contoh ini, kita akan membuat diagram garis dengan penanda.

```csharp
// Menambahkan bagan contoh
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Di sini, kami menentukan jenis bagan (LineWithMarkers) dan posisi serta dimensinya pada slide.

## Langkah 4: Mengatur Judul Bagan

Mari tetapkan judul untuk bagan tersebut untuk memberikan konteks.

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

Kode ini menetapkan judul untuk bagan, menentukan teks, tampilan, dan gaya fontnya.

## Langkah 5: Sesuaikan Garis Grid Utama

Sekarang, mari kita sesuaikan garis kisi utama untuk sumbu nilai.

```csharp
// Mengatur format garis kisi utama untuk sumbu nilai
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Langkah ini mengonfigurasikan tampilan garis kisi utama pada sumbu nilai.

## Langkah 6: Sesuaikan Garis Grid Kecil

Demikian pula, kita dapat menyesuaikan garis kisi minor untuk sumbu nilai.

```csharp
// Mengatur format garis grid minor untuk sumbu nilai
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Kode ini menyesuaikan tampilan garis kisi minor pada sumbu nilai.

## Langkah 7: Tentukan Format Angka Sumbu Nilai

Sesuaikan format angka untuk sumbu nilai.

```csharp
// Mengatur format angka sumbu nilai
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Langkah ini memungkinkan Anda memformat angka yang ditampilkan pada sumbu nilai.

## Langkah 8: Tetapkan Nilai Maksimum dan Minimum Grafik

Tentukan nilai maksimum dan minimum untuk bagan.

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

Di sini, Anda menentukan rentang nilai yang harus ditampilkan sumbu bagan.

## Langkah 9: Sesuaikan Properti Teks Sumbu Nilai

Anda juga dapat menyesuaikan properti teks sumbu nilai.

```csharp
// Mengatur Properti Teks Sumbu Nilai
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Kode ini memungkinkan Anda untuk menyesuaikan gaya font dan tampilan label sumbu nilai.

## Langkah 10: Tambahkan Judul Sumbu Nilai

Jika bagan Anda memerlukan judul untuk sumbu nilai, Anda dapat menambahkannya dengan langkah ini.

```csharp
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

Pada langkah ini, Anda dapat menetapkan judul untuk sumbu nilai.

## Langkah 11: Sesuaikan Garis Grid Utama untuk Sumbu Kategori

Sekarang, mari fokus pada garis kisi utama untuk sumbu kategori.

```csharp
// Mengatur format garis kisi utama untuk sumbu Kategori
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Kode ini mengonfigurasikan tampilan garis kisi utama pada sumbu kategori.

## Langkah 12: Sesuaikan Garis Kisi Minor untuk Sumbu Kategori

Mirip dengan sumbu nilai, Anda dapat menyesuaikan garis kisi minor untuk sumbu kategori.

```csharp
// Mengatur format garis grid Minor untuk sumbu Kategori
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Di sini, Anda menyesuaikan tampilan garis kisi kecil pada sumbu kategori.

## Langkah 13: Sesuaikan Properti Teks Sumbu Kategori

Sesuaikan properti teks untuk label sumbu kategori.

```csharp
// Mengatur Properti Teks Sumbu Kategori
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Kode ini memungkinkan Anda untuk menyesuaikan gaya font dan tampilan label sumbu kategori.

## Langkah 14: Tambahkan Judul Sumbu Kategori

Anda juga dapat menambahkan judul ke sumbu kategori jika diperlukan.

```csharp
// Pengaturan Kategori Judul
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

Pada langkah ini, Anda dapat menetapkan judul untuk sumbu kategori.

## Langkah 15: Kustomisasi Tambahan

Anda dapat menjelajahi kustomisasi lebih lanjut, seperti legenda, dinding belakang bagan, lantai, dan warna area plot. Kustomisasi ini memungkinkan Anda untuk meningkatkan daya tarik visual bagan Anda.

```csharp
// Kustomisasi Tambahan (Opsional)

// Mengatur Properti Teks Legenda
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Mengatur legenda grafik pertunjukan tanpa grafik yang tumpang tindih
chart.Legend.Overlay = true;

// Merencanakan seri pertama pada sumbu nilai sekunder (jika diperlukan)
// Chart.ChartData.Series[0].PlotOnSecondAxis = benar;

// Mengatur warna dinding belakang grafik
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Mengatur warna lantai grafik
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Mengatur warna area plot
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Simpan presentasi
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Kustomisasi tambahan ini bersifat opsional dan dapat diterapkan berdasarkan persyaratan desain bagan spesifik Anda.

## Kesimpulan

Dalam panduan langkah demi langkah ini, kami telah menjelajahi kustomisasi bagan tingkat lanjut menggunakan Aspose.Slides untuk .NET. Anda telah mempelajari cara membuat presentasi, menambahkan bagan, dan menyempurnakan tampilannya, termasuk garis kisi, label sumbu, dan elemen visual lainnya. Dengan opsi kustomisasi canggih yang disediakan oleh Aspose.Slides, Anda dapat membuat bagan yang secara efektif menyampaikan data Anda dan menarik perhatian audiens Anda.

Jika Anda memiliki pertanyaan atau menghadapi tantangan saat bekerja dengan Aspose.Slides untuk .NET, jangan ragu untuk menjelajahi dokumentasinya [Di Sini](https://reference.aspose.com/slides/net/) atau mencari bantuan di Aspose.Slides [forum](https://forum.aspose.com/).

## Tanya Jawab Umum

### Versi .NET apa yang didukung oleh Aspose.Slides untuk .NET?
Aspose.Slides untuk .NET mendukung berbagai versi .NET, termasuk .NET Framework dan .NET Core. Anda dapat merujuk ke dokumentasi untuk daftar lengkap versi yang didukung.

### Dapatkah saya membuat bagan dari sumber data seperti file Excel menggunakan Aspose.Slides for .NET?
Ya, Aspose.Slides untuk .NET memungkinkan Anda membuat bagan dari sumber data eksternal seperti lembar kerja Excel. Anda dapat menjelajahi dokumentasi untuk contoh terperinci.

### Bagaimana cara menambahkan label data khusus ke rangkaian bagan saya?
Untuk menambahkan label data khusus ke seri bagan Anda, Anda dapat mengakses `DataLabels` properti seri dan sesuaikan label sesuai kebutuhan. Lihat dokumentasi untuk contoh dan contoh kode.

### Apakah mungkin untuk mengekspor bagan ke format file lain, seperti format PDF atau gambar?
Ya, Aspose.Slides untuk .NET menyediakan opsi untuk mengekspor presentasi Anda dengan diagram ke berbagai format, termasuk format PDF dan gambar. Anda dapat menggunakan pustaka untuk menyimpan pekerjaan Anda dalam format keluaran yang diinginkan.

### Di mana saya dapat menemukan lebih banyak tutorial dan contoh untuk Aspose.Slides for .NET?
Anda dapat menemukan banyak tutorial, contoh kode, dan dokumentasi di Aspose.Slides [situs web](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}