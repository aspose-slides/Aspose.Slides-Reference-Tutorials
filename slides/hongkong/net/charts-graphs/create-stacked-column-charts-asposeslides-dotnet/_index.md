---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 建立視覺上引人注目的基於百分比的堆積長條圖。按照本逐步指南，實現清晰的資料視覺化。"
"title": "如何使用 Aspose.Slides 在 .NET 中建立基於百分比的堆積長條圖"
"url": "/zh-hant/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 建立基於百分比的堆積長條圖

## 介紹

在資料視覺化領域，清晰有效地呈現資訊對於做出有影響力的決策至關重要。為了直觀地顯示複雜的資料集，基於百分比的堆積長條圖是理想的選擇。本指南將引導您使用 Aspose.Slides for .NET（一個專為處理簡報檔案而設計的強大函式庫）來建立這些圖表。

透過學習本教程，您將了解：
- 設定圖表資料並配置數字格式。
- 添加系列並自訂其外觀。
- 格式化標籤以增強可讀性。

準備好了嗎？讓我們從您需要的先決條件開始！

## 先決條件

在建立基於百分比的堆積長條圖之前，請確保您的環境已正確設定。您將需要：

### 所需的函式庫、版本和相依性
- **Aspose.Slides for .NET**：確保此程式庫已安裝。

### 環境設定要求
- 安裝了 .NET SDK 的開發環境。
- Visual Studio 或任何用於執行 C# 程式碼的相容 IDE。

### 知識前提
- 對 C# 程式設計有基本的了解。
- 熟悉.NET專案設定和套件管理。

## 設定 Aspose.Slides for .NET

若要開始使用 Aspose.Slides 建立圖表，請先使用下列方法之一安裝庫：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**套件管理器**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI**
- 搜尋“Aspose.Slides”並安裝最新版本。

### 許可證取得步驟

下載臨時許可證即可開始免費試用 [Aspose的網站](https://purchase.aspose.com/temporary-license/)。為了繼續使用，請考慮購買完整許可證。 

設定完成後，在您的專案中啟動 Aspose.Slides：
```csharp
using Aspose.Slides;
```

## 實施指南

環境準備好後，讓我們將建立基於百分比的堆積長條圖分解為幾個步驟。

### 建立和配置圖表

#### 概述
建立一個實例 `Presentation` 類，這對於使用幻燈片至關重要。然後，在投影片上新增並配置堆積長條圖。

#### 添加堆積長條圖
```csharp
// 建立 Presentation 類別的實例
document = new Presentation();

// 取得第一張投影片的參考
slide = document.Slides[0];

// 在位置 (20, 20) 處新增尺寸為 (500x400) 的 PercentsStackedColumn 圖表
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### 配置數字格式
確保您的數據以百分比顯示：
```csharp
// 配置垂直軸的數字格式
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // 將數字格式設定為百分比
```

#### 新增資料系列和點
清除現有系列資料並新增資料：
```csharp
// 清除所有現有系列數據
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// 存取圖表資料工作簿
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// 新增的數據系列“Reds”
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// 將系列的填滿色彩設為紅色
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// 配置“紅色”系列的標籤格式屬性
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // 設定百分比格式
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// 加上另一個系列“布魯斯”
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// 將系列的填滿色彩設為藍色
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // 設定百分比格式
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### 儲存簡報
將您的簡報儲存到文件中：
```csharp
// 將簡報儲存為 PPTX 格式
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### 故障排除提示
- 確保所有命名空間都已正確匯入。
- 檢查屬性名稱和方法呼叫中的拼字錯誤。
- 驗證儲存檔案的路徑是否存在並且具有正確的權限。

## 實際應用

以下是基於百分比的堆積長條圖可能有用的一些場景：
1. **銷售分析**：以總銷售額的比例來顯示不同地區的產品表現。
2. **預算分配**：顯示各部門如何根據公司整體支出分配預算。
3. **市場研究**：比較一段時間內消費者對不同產品類別的偏好。
4. **教育數據**：顯示學生各科成績分佈。
5. **醫療保健統計**：代表多種健康狀況的患者人口統計。

## 性能考慮

為了獲得最佳性能，請考慮：
- 將資料點的數量限制在必要的範圍內。
- 預載資料以最大限度地減少運行時處理。
- 使用 Aspose.Slides for .NET 的高效能記憶體管理實務。

## 結論

恭喜！您已成功學習如何使用 Aspose.Slides for .NET 建立基於百分比的堆積長條圖。該工具使複雜數據更易於理解和更具視覺吸引力，從而增強了演示效果。

下一步是什麼？探索 Aspose.Slides 中可用的其他圖表類型或將此功能整合到更大的應用程式中。編碼愉快！

## 常見問題部分

**問題1：我可以免費使用 Aspose.Slides 嗎？**
A1：是的，您可以先免費試用，測試 Aspose.Slides 的功能。

**Q2：Aspose.Slides for .NET 支援哪些圖表類型？**
A2：它支援餅圖、長條圖、長條圖、折線圖等各種圖表。

**問題 3：如何開始使用 Aspose.Slides for .NET？**
A3：依照上面所述使用 NuGet 或 .NET CLI 安裝程式庫。按照我們的文件建立您的第一個圖表。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}