---
"description": "了解 Aspose.Slides for .NET 中的進階圖表自訂。透過逐步指導創建具有視覺吸引力的圖表。"
"linktitle": "Aspose.Slides 中的進階圖表自訂"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "Aspose.Slides 中的進階圖表自訂"
"url": "/zh-hant/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides 中的進階圖表自訂


創建具有視覺吸引力且資訊豐富的圖表是許多應用程式中資料呈現的重要組成部分。 Aspose.Slides for .NET 提供了強大的圖表自訂工具，讓您可以微調圖表的各個方面。在本教程中，我們將探索使用 Aspose.Slides for .NET 的高級圖表自訂技術。

## 先決條件

在使用 Aspose.Slides for .NET 進行進階圖表自訂之前，請確保您已滿足以下先決條件：

1. Aspose.Slides for .NET 函式庫：您需要在 .NET 專案中安裝並正確設定 Aspose.Slides 函式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/net/).

2. .NET 開發環境：您應該設定一個 .NET 開發環境，包括 Visual Studio 或您選擇的任何其他 IDE。

3. C# 基礎知識：熟悉 C# 程式語言將會很有幫助，因為我們將編寫 C# 程式碼來與 Aspose.Slides 一起使用。

現在，讓我們將進階圖表客製化分解為多個步驟，以引導您完成整個過程。

## 步驟 1：建立簡報

首先，使用 Aspose.Slides 建立一個新的簡報。

```csharp
// 文檔目錄的路徑。
string dataDir = "Your Document Directory";

// 如果目錄尚不存在，則建立該目錄。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// 實例化演示
Presentation pres = new Presentation();
```

在此步驟中，我們啟動一個用於保存圖表的新簡報。

## 第 2 步：存取第一張投影片

接下來，存取簡報中要新增圖表的第一張投影片。

```csharp
// 存取第一張投影片
ISlide slide = pres.Slides[0];
```

此程式碼片段可讓您處理簡報中的第一張投影片。

## 步驟3：新增範例圖表

現在，讓我們為投影片新增一個範例圖表。在此範例中，我們將建立帶有標記的折線圖。

```csharp
// 新增範例圖表
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

在這裡，我們指定圖表的類型（LineWithMarkers）及其在幻燈片上的位置和尺寸。

## 步驟4：設定圖表標題

讓我們為圖表設定一個標題來提供背景資訊。

```csharp
// 設定圖表標題
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

此程式碼設定圖表的標題，指定其文字、外觀和字體樣式。

## 步驟 5：自訂主要網格線

現在，讓我們自訂數值軸的主要網格線。

```csharp
// 設定數值軸的主要網格線格式
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

此步驟配置數值軸上主要網格線的外觀。

## 步驟 6：自訂次要網格線

類似地，我們可以自訂數值軸的次要網格線。

```csharp
// 設定數值軸的次要網格線格式
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

此代碼調整數值軸上次要網格線的外觀。

## 步驟 7：定義值軸數字格式

自訂數值軸的數字格式。

```csharp
// 設定值軸編號格式
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

此步驟可讓您格式化數值軸上顯示的數字。

## 步驟 8：設定圖表最大值和最小值

定義圖表的最大值和最小值。

```csharp
// 設定圖表最大值、最小值
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

在這裡，您可以指定圖表軸應顯示的值的範圍。

## 步驟 9：自訂數值軸文字屬性

您也可以自訂值軸的文字屬性。

```csharp
// 設定數值軸文字屬性
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

此程式碼可讓您調整值軸標籤的字體樣式和外觀。

## 步驟 10：新增值軸標題

如果您的圖表需要數值軸的標題，您可以透過此步驟新增。

```csharp
// 設定數值軸標題
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

在此步驟中，您可以為值軸設定標題。

## 步驟 11：自訂分類軸的主要網格線

現在，讓我們專注於類別軸的主要網格線。

```csharp
// 設定分類軸的主要網格線格式
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

此代碼配置類別軸上主要網格線的外觀。

## 步驟 12：自訂分類軸的次網格線

與數值軸類似，您可以自訂分類軸的次要網格線。

```csharp
// 設定分類軸的次要網格線格式
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

在這裡，您可以調整類別軸上次要網格線的外觀。

## 步驟 13：自訂分類軸文字屬性

自訂類別軸標籤的文字屬性。

```csharp
// 設定分類軸文字屬性
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

此程式碼可讓您調整類別軸標籤的字體樣式和外觀。

## 步驟 14：新增分類軸標題

如果需要，您也可以為類別軸新增標題。

```csharp
// 設定類別標題
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

在此步驟中，您可以為分類軸設定標題。

## 步驟15：其他自訂

您可以探索進一步的自訂，例如圖例、圖表背景牆、地板和繪圖區域顏色。這些自訂功能可讓您增強圖表的視覺吸引力。

```csharp
// 額外客製化（可選）

// 設定圖例文字屬性
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// 設定顯示不重疊圖表的圖表圖例
chart.Legend.Overlay = true;

// 在次要數值軸上繪製第一個系列（如果需要）
// 圖表.ChartData.Series[0].PlotOnSecondAxis = true;

// 設定圖表背景牆顏色
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// 設定圖表底部顏色
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// 設定繪圖區域顏色
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// 儲存簡報
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

這些額外的客製化是可選的，可以根據您的特定圖表設計要求進行應用。

## 結論

在本逐步指南中，我們探索了使用 Aspose.Slides for .NET 進行進階圖表自訂。您已經學習如何建立簡報、新增圖表以及微調其外觀，包括網格線、軸標籤和其他視覺元素。透過 Aspose.Slides 提供的強大自訂選項，您可以建立有效傳達數據並吸引受眾的圖表。

如果您在使用 Aspose.Slides for .NET 時有任何問題或遇到任何挑戰，請隨時瀏覽文檔 [這裡](https://reference.aspose.com/slides/net/) 或在 Aspose.Slides 中尋求幫助 [論壇](https://forum。aspose.com/).

## 常見問題解答

### Aspose.Slides for .NET 支援哪些版本的 .NET？
Aspose.Slides for .NET 支援各種 .NET 版本，包括 .NET Framework 和 .NET Core。您可以參考文件以取得受支援版本的完整清單。

### 我可以使用 Aspose.Slides for .NET 從 Excel 檔案等資料來源建立圖表嗎？
是的，Aspose.Slides for .NET 允許您從外部資料來源（如 Excel 電子表格）建立圖表。您可以瀏覽文件以取得詳細範例。

### 如何為我的圖表系列新增自訂資料標籤？
要向圖表系列添加自訂資料標籤，您可以訪問 `DataLabels` 系列的屬性並根據需要自訂標籤。請參閱文件以取得程式碼範例和範例。

### 是否可以將圖表匯出為不同的文件格式，例如 PDF 或圖像格式？
是的，Aspose.Slides for .NET 提供了將帶有圖表的簡報匯出為各種格式的選項，包括 PDF 和圖像格式。您可以使用該庫以所需的輸出格式儲存您的工作。

### 在哪裡可以找到更多有關 Aspose.Slides for .NET 的教學和範例？
您可以在 Aspose.Slides 上找到豐富的教學課程、程式碼範例和文檔 [網站](https://reference。aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}