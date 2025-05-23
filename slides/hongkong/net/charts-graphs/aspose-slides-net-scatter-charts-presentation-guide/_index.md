---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 透過散佈圖增強您的簡報。按照本綜合指南可以有效地建立和自訂圖表。"
"title": "使用 Aspose.Slides .NET™ 將散佈圖新增至簡報中逐步指南"
"url": "/zh-hant/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides .NET 在簡報中新增散佈圖：逐步指南

## 介紹
您是否希望透過輕鬆整合散點圖來增強您的簡報效果？透過 Aspose.Slides for .NET 的強大功能，建立和自訂圖表變得輕而易舉。本教學將指導您使用 Aspose.Slides for .NET 將散佈圖新增至投影片中。透過掌握這些技術，您將更有效地呈現數據並創建具有視覺吸引力的簡報。

**您將學到什麼：**
- 在您的專案中設定 Aspose.Slides for .NET
- 建立新的簡報並存取其第一張投影片
- 在幻燈片中加入帶有平滑線條的散佈圖
- 清除現有系列並在圖表中新增系列
- 修改資料點和標記樣式以增強視覺化
- 將簡報儲存到指定目錄

讓我們先回顧一下先決條件。

## 先決條件
在實作 Aspose.Slides for .NET 之前，請確保您具備以下條件：
- **Aspose.Slides for .NET 函式庫**：版本 23.7 或更高版本。
- **開發環境**：Visual Studio 2019 或更新版本，帶有 .NET Framework 4.6.1+ 或 .NET Core/5+。
- **基本 C# 知識**：熟悉C#物件導向程式設計。

## 設定 Aspose.Slides for .NET
要開始使用 Aspose.Slides，您需要在專案中安裝該程式庫。方法如下：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**使用套件管理器控制台：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI：**
- 搜尋“Aspose.Slides”並安裝最新版本。

### 許可證獲取
您可以從免費試用開始，或申請臨時許可證來探索所有功能。要購買，請按照以下步驟操作：
1. 訪問 [購買 Aspose.Slides](https://purchase.aspose.com/buy) 購買完整許可證。
2. 如需臨時許可證，請訪問 [臨時許可證頁面](https://purchase。aspose.com/temporary-license/).

取得許可證文件後，請使用以下命令將其新增至您的專案：
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## 實施指南
我們將根據特性將實作分解為邏輯部分。

### 建立簡報並新增幻燈片
本節簡報如何建立簡報並存取其第一張投影片。

#### 概述
首先創建一個 `Presentation` 類，代表您的 PowerPoint 文件。使用此物件模型可以輕鬆存取投影片。

#### 實施步驟
**步驟 1：初始化簡報**
```csharp
using Aspose.Slides;

// 建立新簡報
t Presentation pres = new Presentation();
```
此程式碼初始化一個新的演示文件。

**第 2 步：存取第一張投影片**
```csharp
// 存取簡報中的第一張投影片
ISlide slide = pres.Slides[0];
```
這裡， `pres.Slides[0]` 存取第一張投影片。 

### 將散點圖加入投影片
現在讓我們為您的簡報新增一個散佈圖。

#### 概述
新增圖表可以幫助您在簡報中直觀地呈現資料。 Aspose.Slides 可以輕鬆合併各種類型的圖表，包括散點圖。

#### 實施步驟
**步驟 1：建立並新增散佈圖**
```csharp
using Aspose.Slides.Charts;

// 建立並新增帶有平滑線的預設散點圖
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
此程式碼片段在指定的位置和大小添加散佈圖。

### 清除圖表資料並新增系列
#### 概述
您可能需要透過清除現有系列並添加新系列來自訂您的圖表。本節介紹此功能。

#### 實施步驟
**步驟 1：存取圖表資料工作簿**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// 清除所有預先存在的系列
chart.ChartData.Series.Clear();
```
此程式碼清除現有資料以重新開始新系列。

**第 2 步：新增系列**
```csharp
// 新增名為「系列 1」的新系列
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// 新增另一個名為「Series 2」的系列
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
這些步驟為圖表添加了兩個新系列。

### 修改第一個系列資料點和標記樣式
#### 概述
自訂資料點和標記樣式，以便更好地視覺化散佈圖。

#### 實施步驟
**步驟 1：存取並新增資料點**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// 新增資料點 (1, 3) 和 (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**步驟 2：修改標記樣式**
```csharp
// 變更系列類型並修改標記樣式
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### 修改第二個系列資料點和標記樣式
#### 概述
同樣，客製化第二個系列以滿足您的簡報需求。

#### 實施步驟
**步驟 1：存取並新增多個數據點**
```csharp
// 訪問第二個圖表系列
series = chart.ChartData.Series[1];

// 新增多個數據點
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**步驟 2：修改標記樣式**
```csharp
// 更改第二個系列的標記大小和符號
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### 儲存簡報
最後，將您的簡報儲存到指定目錄。

#### 實施步驟
**步驟 1：定義目錄**
確保輸出目錄存在。如果沒有，請創建它：
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// 儲存簡報
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
此程式碼將您的簡報檔案儲存到指定位置。

## 結論
現在，您已成功使用 Aspose.Slides for .NET 將散佈圖新增至您的簡報。繼續探索庫中可用的其他功能和自訂功能，以增強您的資料視覺化技能。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}