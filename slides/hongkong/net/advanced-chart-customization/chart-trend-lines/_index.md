---
title: 探索 Aspose.Slides for .NET 中的圖表趨勢線
linktitle: 圖表趨勢線
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 在此逐步指南中了解如何使用 Aspose.Slides for .NET 將各種趨勢線新增至圖表。輕鬆增強您的數據視覺化技能！
weight: 12
url: /zh-hant/net/advanced-chart-customization/chart-trend-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


在資料視覺化和演示領域，合併圖表可以是有效傳達訊息的強大方式。 Aspose.Slides for .NET 提供了一組功能豐富的工具來處理圖表，包括在圖表中新增趨勢線的功能。在本教程中，我們將深入研究使用 Aspose.Slides for .NET 逐步在圖表中新增趨勢線的過程。 

## 先決條件

在我們開始使用 Aspose.Slides for .NET 之前，您需要確保滿足以下先決條件：

1. Aspose.Slides for .NET：要存取該程式庫並使用它，您必須安裝 Aspose.Slides for .NET。您可以從以下位置取得該庫[下載頁面](https://releases.aspose.com/slides/net/).

2. 開發環境：您應該設定一個開發環境，最好使用 Visual Studio 等 .NET 整合開發環境。

3. C# 基礎知識：對 C# 程式設計的基本了解是有益的，因為我們將使用 C# 與 Aspose.Slides for .NET 一起工作。

現在我們已經介紹了先決條件，讓我們逐步分解向圖表添加趨勢線的過程。

## 導入命名空間

首先，確保將必要的命名空間匯入到 C# 專案中。這些命名空間對於使用 Aspose.Slides for .NET 至關重要。

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## 第 1 步：建立簡報

在此步驟中，我們建立一個空白簡報以供使用。

```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";

//如果目錄尚不存在，則建立該目錄。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

//建立空白簡報
Presentation pres = new Presentation();
```

## 第 2 步：將圖表新增至投影片

接下來，我們將聚集長條圖加入投影片中。

```csharp
//建立簇狀長條圖
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## 第 3 步：在圖表中新增趨勢線

現在，我們為圖表系列添加各種類型的趨勢線。

### 新增指數趨勢線

```csharp
//為圖表系列 1 新增指數趨勢線
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### 新增線性趨勢線

```csharp
//為圖表系列 1 新增線性趨勢線
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### 增加對數趨勢線

```csharp
//為圖表系列 2 新增對數趨勢線
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### 增加移動平均趨勢線

```csharp
//為圖表系列 2 新增移動平均趨勢線
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### 增加多項式趨勢線

```csharp
//為圖表系列 3 新增多項式趨勢線
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### 增加功率趨勢線

```csharp
//為圖表系列 3 增加功率趨勢線
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## 第 4 步：儲存簡報

將趨勢線新增至圖表後，儲存簡報。

```csharp
//儲存簡報
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已使用 Aspose.Slides for .NET 成功將各種趨勢線新增至圖表。

## 結論

Aspose.Slides for .NET 是一個多功能函式庫，可讓您輕鬆建立和操作圖表。透過遵循此逐步指南，您可以為圖表添加不同類型的趨勢線，從而增強資料的視覺化表示。

### 常見問題解答

### 在哪裡可以找到 Aspose.Slides for .NET 的文檔？
您可以存取文檔[這裡](https://reference.aspose.com/slides/net/).

### 如何下載 .NET 版 Aspose.Slides？
您可以從下載頁面下載 Aspose.Slides for .NET[這裡](https://releases.aspose.com/slides/net/).

### Aspose.Slides for .NET 有沒有免費試用版？
是的，您可以透過造訪免費試用 Aspose.Slides for .NET[這個連結](https://releases.aspose.com/).

### 在哪裡可以購買 Aspose.Slides for .NET？
要購買 Aspose.Slides for .NET，請造訪購買頁面[這裡](https://purchase.aspose.com/buy).

### 我需要 Aspose.Slides for .NET 的臨時授權嗎？
您可以從以下位置取得 Aspose.Slides for .NET 的臨時授權：[這個連結](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
