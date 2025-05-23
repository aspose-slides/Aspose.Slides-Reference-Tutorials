---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 在 PowerPoint 簡報中輕鬆建立和自訂圓環圖。透過本綜合指南增強您的視覺資料呈現。"
"title": "如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立甜甜圈圖&#58;逐步指南"
"url": "/zh-hant/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立甜甜圈圖：逐步指南

## 介紹

使用視覺上吸引人的圓環圖來增強您的 PowerPoint 簡報可以顯著改善您呈現資料的方式。 Aspose.Slides for .NET 提供了一種建立和自訂這些圖表的有效方法。本教學將引導您完成使用 Aspose.Slides for .NET 為 PowerPoint 投影片新增可自訂的圓環圖（包括調整孔大小）的步驟。

**您將學到什麼：**
- 設定 Aspose.Slides for .NET
- 將圓環圖加入投影片的步驟
- 配置圓環圖孔徑的技巧
- 實際應用和性能考慮

在深入研究之前，讓我們先了解一下您需要什麼！

## 先決條件

在開始之前，請確保您符合以下要求：

### 所需的庫和版本
- Aspose.Slides for .NET（最新版本）
- Visual Studio 或任何支援 .NET 開發的相容 IDE

### 環境設定要求
- 安裝了 .NET Framework 的 Windows 環境
- C# 程式設計基礎知識

## 設定 Aspose.Slides for .NET

首先，您需要安裝 Aspose.Slides 函式庫。您可以使用以下不同的方法來實現此目的：

**使用 .NET CLI：**
```bash
dotnet add package Aspose.Slides
```

**使用套件管理器控制台：**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI：**
搜尋「Aspose.Slides」並直接透過 IDE 的 NuGet 介面安裝最新版本。

### 許可證取得步驟
1. **免費試用：** 首先下載免費試用版來評估功能。
2. **臨時執照：** 如果您需要更多時間，請向 Aspose 申請臨時許可證。
3. **購買：** 為了長期使用，請考慮購買完整版。

安裝完成後，使用以下基本設定初始化您的專案：
```csharp
using Aspose.Slides;

// 初始化新的 Presentation 對象
Presentation presentation = new Presentation();
```

## 實施指南

讓我們將使用 Aspose.Slides for .NET 建立圓環圖的過程分解為易於管理的步驟。

### 建立圓環圖

#### 概述
我們首先在 PowerPoint 投影片中新增一個圓環圖，並設定其位置和大小。

**新增圖表：**
```csharp
using Aspose.Slides.Charts;

// 存取簡報中的第一張投影片（預設會建立一張）
ISlide slide = presentation.Slides[0];

// 在投影片的 (50, 50) 位置增加一個圓環圖，寬度和高度均為 400 個單位
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **參數：** `ChartType.Doughnut`，x 位置：50，y 位置：50，寬度：400，高度：400。

### 設定孔尺寸

#### 概述
接下來，我們將配置圓環圖的孔徑，使其更具視覺吸引力。

**配置孔尺寸：**
```csharp
// 將圓環圖的孔徑設定為 90%
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **關鍵配置：** `DoughnutHoleSize` 決定中心被「切掉」的程度。 0 至 100 之間的數值代表百分比。

### 儲存您的簡報

最後，將變更儲存到新的 PowerPoint 檔案：
```csharp
// 定義簡報的儲存路徑
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// 將修改後的簡報儲存為 PPTX 格式
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **筆記：** 代替 `YOUR_OUTPUT_DIRECTORY` 使用您想要的文件位置。

### 故障排除提示

- 確保 Aspose.Slides 已正確安裝和匯入。
- 在儲存簡報之前，請先驗證輸出目錄路徑是否存在。

## 實際應用

使用 Aspose.Slides for .NET 建立的甜甜圈圖可用於各種場景：

1. **商業報告：** 說明預算分配或銷售分配等財務數據。
2. **行銷分析：** 顯示不同品牌的市佔率百分比。
3. **教育材料：** 用於以視覺上引人入勝的方式解釋統計概念。

將 Aspose.Slides 與其他系統集成，以便在企業環境中自動產生和分發報告。

## 性能考慮

處理大型簡報或大量圖表時，請考慮以下提示：

- 在將資料新增至投影片之前優化資料處理。
- 盡可能重複使用演示物件以節省記憶體。
- 定期更新您的 Aspose.Slides 庫以獲得效能改進。

## 結論

您已經學習如何使用 Aspose.Slides for .NET 建立和自訂圓環圖。這個多功能工具可以增強簡報的視覺吸引力，讓數據更容易一目了然地理解。

**後續步驟：**
探索 Aspose.Slides 中可用的其他圖表類型或深入研究動畫等高級功能。

準備好嘗試了嗎？前往下面的資源部分並開始實驗！

## 常見問題部分

1. **Aspose.Slides for .NET 用於什麼？**  
   它是一個用於以程式設計方式建立、修改和轉換 PowerPoint 簡報的庫。

2. **我怎麼能改變甜甜圈部分的顏色？**  
   使用 `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` 調整填充屬性。

3. **我可以在一次簡報中建立多個圖表嗎？**  
   是的，透過在不同的投影片或位置上重複圖表建立步驟，可以根據需要添加任意數量的圖表。

4. **如何取得 Aspose.Slides for .NET 的商業使用許可？**  
   透過 Aspose 官方網站購買許可證以進行商業使用。

5. **如果我的簡報無法正確保存，我該怎麼辦？**  
   檢查檔案路徑權限並確保您的專案引用是最新的。

## 資源

- [Aspose.Slides文檔](https://reference.aspose.com/slides/net/)
- [下載 Aspose.Slides for .NET](https://releases.aspose.com/slides/net/)
- [購買許可證](https://purchase.aspose.com/buy)
- [免費試用版](https://releases.aspose.com/slides/net/)
- [臨時許可證申請](https://purchase.aspose.com/temporary-license/)
- [支援論壇](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}