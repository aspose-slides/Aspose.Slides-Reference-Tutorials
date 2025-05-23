---
"description": "了解如何使用 Aspose.Slides for .NET 增強您的 PowerPoint 圖表。使用影像自訂資料點標記。創建引人入勝的簡報。"
"linktitle": "數據點上的圖表標記選項"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "在 Aspose.Slides .NET 中使用資料點上的圖表標記選項"
"url": "/zh-hant/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Slides .NET 中使用資料點上的圖表標記選項


在處理簡報和資料視覺化時，Aspose.Slides for .NET 提供了多種強大的功能來建立、自訂和操作圖表。在本教學中，我們將探討如何使用資料點上的圖表標記選項來增強圖表示範。本逐步指南將引導您完成整個過程，從先決條件和匯入命名空間開始，到將每個範例分解為多個步驟。

## 先決條件

在深入研究使用資料點上的圖表標記選項之前，請確保您已滿足以下先決條件：

- Aspose.Slides for .NET：請確定您已安裝 Aspose.Slides for .NET。您可以從 [網站](https://releases。aspose.com/slides/net/).

- 範例簡報：在本教學中，我們將使用名為「Test.pptx」的範例簡報。您的文件目錄中應該有此簡報。

現在，讓我們開始導入必要的命名空間。

## 導入命名空間

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

我們已經導入了所需的命名空間並初始化了我們的簡報。現在，讓我們繼續在數據點上使用圖表標記選項。

## 步驟1：建立預設圖表

```csharp

// 文檔目錄的路徑。
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// 建立預設圖表
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

我們在投影片上的指定位置和大小建立類型為「LineWithMarkers」的預設圖表。

## 步驟2：取得預設圖表資料工作表索引

```csharp
// 取得預設圖表資料工作表索引
int defaultWorksheetIndex = 0;
```

這裡我們取得了預設圖表資料工作表的索引。

## 步驟3：取得圖表資料工作表

```csharp
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

我們取得圖表資料工作簿來處理圖表資料。

## 步驟4：修改圖表系列

```csharp
// 刪除示範系列
chart.ChartData.Series.Clear();

// 新增系列
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

在此步驟中，我們刪除任何現有的示範系列，並為圖表新增一個名為「系列 1」的新系列。

## 步驟5：設定數據點的圖片填充

```csharp
// 設定標記的圖片
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// 以第一個圖表系列為例
IChartSeries series = chart.ChartData.Series[0];

// 使用圖片填充添加新數據點
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

我們為資料點設定了圖片標記，讓您自訂每個資料點在圖表上的顯示方式。

## 步驟6：更改圖表系列標記大小

```csharp
// 更改圖表系列標記大小
series.Marker.Size = 15;
```

在這裡，我們調整圖表系列標記的大小，使其更具視覺吸引力。

## 步驟 7：儲存簡報

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

最後，我們使用新的圖表設定來儲存簡報。

## 結論

Aspose.Slides for .NET 讓您能夠透過各種自訂選項建立令人驚嘆的圖表簡報。在本教程中，我們將重點放在如何使用資料點上的圖表標記選項來增強資料的視覺表現。使用 Aspose.Slides for .NET，您可以將簡報提升到一個新的水平，使其更具吸引力和資訊量。

如果您對 Aspose.Slides for .NET 有任何疑問或需要協助，請隨時訪問 [Aspose.Slides 文檔](https://reference.aspose.com/slides/net/) 或聯繫 [Aspose 社區](https://forum.aspose.com/) 以獲得支持。

## 常見問題 (FAQ)

### 我可以在 Aspose.Slides for .NET 中使用自訂圖像作為資料點的標記嗎？
是的，您可以使用自訂圖像作為 Aspose.Slides for .NET 中資料點的標記，如本教學所示。

### 如何更改 Aspose.Slides for .NET 中的圖表類型？
您可以透過指定不同的圖表類型來變更圖表類型 `ChartType` 建立圖表時，例如「長條圖」、「圓餅圖」或「面積圖」。

### Aspose.Slides for .NET 是否與最新版本的 PowerPoint 相容？
Aspose.Slides for .NET 旨在與各種 PowerPoint 格式相容，並定期更新以保持與最新 PowerPoint 版本的兼容性。

### 在哪裡可以找到更多關於 Aspose.Slides for .NET 的教學和資源？
您可以在 [Aspose.Slides 文檔](https://reference。aspose.com/slides/net/).

### 是否有 Aspose.Slides for .NET 的試用版？
是的，您可以下載免費試用版來試用 Aspose.Slides for .NET [這裡](https://releases。aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}