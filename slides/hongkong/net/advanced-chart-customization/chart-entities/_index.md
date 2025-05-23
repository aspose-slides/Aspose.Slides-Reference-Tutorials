---
"description": "了解如何使用 Aspose.Slides for .NET 建立令人驚嘆的圖表。透過我們的逐步指南提升您的數據視覺化遊戲。"
"linktitle": "圖表實體和格式"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "使用 Aspose.Slides for .NET 建立漂亮的圖表"
"url": "/zh-hant/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Slides for .NET 建立漂亮的圖表


在當今數據驅動的世界中，有效的數據視覺化是向受眾傳達訊息的關鍵。 Aspose.Slides for .NET 是一個功能強大的程式庫，可讓您建立令人驚嘆的簡報和投影片，包括引人注目的圖表。在本教程中，我們將引導您完成使用 Aspose.Slides for .NET 建立精美圖表的過程。我們將把每個範例分解為多個步驟，以幫助您理解和實現圖表實體和格式。那麼，就讓我們開始吧！

## 先決條件

在我們深入使用 Aspose.Slides for .NET 建立漂亮的圖表之前，您需要確保滿足以下先決條件：

1. Aspose.Slides for .NET：確保您已安裝 Aspose.Slides for .NET 程式庫。您可以從 [網站](https://releases。aspose.com/slides/net/).

2. 開發環境：您應該有一個具有 Visual Studio 或任何其他支援 .NET 開發的 IDE 的工作開發環境。

3. 基本 C# 知識：熟悉 C# 程式設計對於本教學至關重要。

現在我們已經滿足了先決條件，讓我們繼續使用 Aspose.Slides for .NET 建立漂亮的圖表。

## 導入命名空間

首先，您需要匯入必要的命名空間才能使用 Aspose.Slides for .NET：

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## 步驟 1：建立簡報

我們首先建立一個新的簡報。該簡報將作為我們圖表的畫布。

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

## 第 2 步：存取第一張投影片

讓我們進入簡報中的第一張投影片，我們將在其中放置圖表。

```csharp
// 存取第一張投影片
ISlide slide = pres.Slides[0];
```

## 步驟 3：新增範例圖表

現在，我們將在幻燈片中新增一個範例圖表。在此範例中，我們將建立帶有標記的折線圖。

```csharp
// 新增範例圖表
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 步驟4：設定圖表標題

我們將為圖表添加標題，使其更具資訊量和視覺吸引力。

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

## 步驟5：自訂垂直軸網格線

在此步驟中，我們將自訂垂直軸網格線，以使我們的圖表更具視覺吸引力。

```csharp
// 設定數值軸的主要網格線格式
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// 設定數值軸的次要網格線格式
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// 設定值軸編號格式
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## 步驟 6：定義垂直軸範圍

在此步驟中，我們將設定垂直軸的最大值、最小值和單位值。

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

## 步驟 7：自訂垂直軸文本

我們現在將自訂垂直軸上文字的外觀。

```csharp
// 設定數值軸文字屬性
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

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

## 步驟 8：自訂橫軸網格線

現在，讓我們自訂水平軸的網格線。

```csharp
// 設定分類軸的主要網格線格式
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// 設定分類軸的次要網格線格式
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// 設定分類軸文字屬性
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## 步驟9：自訂水平軸標籤

在此步驟中，我們將調整水平軸標籤的位置和旋轉。

```csharp
// 設定分類軸標籤位置
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// 設定分類軸標籤旋轉角度
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## 步驟 10：自訂圖例

讓我們增強圖表中的圖例以提高可讀性。

```csharp
// 設定圖例文字屬性
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// 設定顯示不重疊圖表的圖表圖例
chart.Legend.Overlay = true;
```

## 步驟11：自訂圖表背景

我們將定製圖表、後牆和地板的背景顏色。

```csharp
// 設定圖表背景牆顏色
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// 設定繪圖區域顏色
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## 步驟 12：儲存簡報

最後，讓我們將帶有格式化的圖表儲存到簡報中。

```csharp
// 儲存簡報
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## 結論

現在，使用 Aspose.Slides for .NET 在簡報中建立美觀且資訊豐富的圖表比以往更簡單。在本教程中，我們介紹了自訂圖表各個方面的基本步驟，使其具有視覺吸引力和資訊量。利用這些技術，您可以創建令人驚嘆的圖表，有效地將數據傳達給您的受眾。

開始嘗試使用 Aspose.Slides for .NET 並將您的資料視覺化提升到一個新的水平！

## 常見問題

### 1.什麼是 Aspose.Slides for .NET？

Aspose.Slides for .NET 是一個功能強大的程式庫，可讓 .NET 開發人員建立、操作和轉換 Microsoft PowerPoint 簡報。它提供了用於處理投影片、形狀、圖表等的多種功能。

### 2. 哪裡可以下載 Aspose.Slides for .NET？

您可以從網站下載 Aspose.Slides for .NET [這裡](https://releases。aspose.com/slides/net/).

### 3. Aspose.Slides for .NET 有免費試用版嗎？

是的，您可以從以下位置免費試用 Aspose.Slides for .NET [這裡](https://releases。aspose.com/).

### 4. 如何取得 Aspose.Slides for .NET 的臨時授權？

如果您需要臨時駕照，可以從 [此連結](https://purchase。aspose.com/temporary-license/).

### 5. Aspose.Slides for .NET 有社群或支援論壇嗎？

是的，您可以找到 Aspose.Slides 社群和支援論壇 [這裡](https://forum。aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}