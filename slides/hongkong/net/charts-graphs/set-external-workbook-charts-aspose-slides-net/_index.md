---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 設定帶有外部 Excel 工作簿的圖表，從而增強您的簡報和資料管理。"
"title": "如何在 Aspose.Slides .NET 中將外部工作簿設定為圖表資料來源"
"url": "/zh-hant/net/charts-graphs/set-external-workbook-charts-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides .NET 將外部工作簿設定為圖表資料來源
## 介紹
在簡報中創建視覺上吸引人的圖表對於有效傳達數據驅動的見解至關重要。將圖表資料與簡報文件分開管理可能會很麻煩。使用 Aspose.Slides for .NET，您可以連結外部工作簿作為圖表的資料來源，從而簡化工作流程並使資料保持井然有序。本教學將指導您使用 Aspose.Slides .NET 實現「從外部工作簿設定圖表資料」功能。

**您將學到什麼：**
- 如何使用 Aspose.Slides for .NET 將外部工作簿設定為圖表的資料來源。
- 使用外部資料在簡報中新增和配置圖表的步驟。
- 將 Aspose.Slides 功能整合到您的 .NET 專案中。

讓我們先設定必要的先決條件。
## 先決條件
在開始之前，請確保您已完成以下設定：
### 所需庫
- **Aspose.Slides for .NET**：此程式庫支援在 .NET 應用程式中建立和操作 PowerPoint 簡報。確保與您的開發環境相容。
### 環境設定要求
- C#開發環境，例如Visual Studio。
- 外部工作簿（例如， `externalWorkbook.xlsx`）包含圖表數據。
### 知識前提
- 對 C# 程式設計和 .NET 框架概念有基本的了解。
- 熟悉以程式設計方式處理 PowerPoint 簡報。
## 設定 Aspose.Slides for .NET
若要將 Aspose.Slides 整合到您的專案中，請使用下列安裝方法之一：
**.NET CLI**
```bash
dotnet add package Aspose.Slides
```
**套件管理器**
```powershell
Install-Package Aspose.Slides
```
**NuGet 套件管理器 UI**
- 在您的 IDE 中開啟 NuGet 套件管理器。
- 搜尋“Aspose.Slides”並安裝最新版本。
### 許可證獲取
為了充分利用 Aspose.Slides，您可能需要獲得許可證。方法如下：
- **免費試用**：從臨時許可證開始，無限制探索所有功能。
- **臨時執照**：在 Aspose 網站上申請評估。
- **購買**：如需長期使用，請購買訂閱。
**基本初始化：**
```csharp
// 初始化 Aspose.Slides 許可證（如果有）
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_your_license.lic");
```
## 實施指南
### 為圖表設定外部工作簿
此功能可讓您將圖表資料連結到外部 Excel 工作簿，確保工作簿中的任何更新都會自動反映在您的簡報中。
#### 步驟 1：初始化簡報並新增圖表
建立一個新的簡報實例並在第一張投影片中新增一個圓餅圖。
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public class Feature_SetExternalWorkbook {
    public static void Run() {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        using (Presentation pres = new Presentation()) {
            // 在第一張投影片的 50,50 位置新增一個圓餅圖，尺寸為 400x600
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
```
#### 步驟 2：存取圖表資料並設定外部工作簿
存取圖表資料集合以指定外部工作簿作為資料來源。
```csharp
            // 存取圖表資料以進行操作。
            IChartData chartData = chart.ChartData;
            
            // 設定包含圖表資料的外部工作簿。
            chartData.SetExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```
#### 步驟 3：從外部工作簿新增系列和資料點
在您的圖表中新增一個新系列，並將其連結到外部工作簿中類別和值的特定儲存格。
```csharp
            // 使用外部工作簿中儲存格 B1 的資料新增系列
            chartData.Series.Add(chartData.ChartDataWorkbook.GetCell(0, "B1"), ChartType.Pie);

            // 從儲存格 B2、B3 和 B4 新增系列的資料點
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B2"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B3"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B4"));

            // 使用儲存格 A2、A3 和 A4 中的資料定義系列的類別
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A2"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A3"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A4"));

            // 使用指定的檔案名稱儲存演示文稿
            pres.Save(dataDir + "Presentation_with_externalWorkbook.pptx");
        }
    }
}
```
### 故障排除提示
- 確保外部工作簿路徑正確且可存取。
- 驗證程式碼中的儲存格參考是否與 Excel 檔案中的儲存格參考相符。
## 實際應用
在以下一些情況下，為圖表設定外部工作簿會非常有用：
1. **財務報告**：隨著電子表格中的財務數據變化，自動更新圖表。
2. **專案管理儀錶板**：將儲存在單獨工作簿中的進度指標連結到簡報投影片。
3. **行銷分析**：使用最新的活動績效數據來維持簡報的更新。
## 性能考慮
使用 Aspose.Slides 時，請考慮以下提示以獲得最佳效能：
- 如果可能的話，透過預先載入必要的資料來盡量減少外部工作簿呼叫。
- 使用 .NET 中的高效能記憶體管理實務來處理大型簡報。
- 定期更新您的 Aspose.Slides 庫以獲得最佳化和錯誤修復。
## 結論
透過學習本教學課程，您已經學會如何使用 Aspose.Slides for .NET 將外部工作簿設定為圖表資料的來源。此功能增強了資料管理並確保您的簡報與任何底層資料變更保持同步。
**後續步驟：**
- 探索 Aspose.Slides 的其他功能以進一步增強您的簡報。
- 嘗試不同的圖表類型和資料配置。
我們鼓勵您嘗試在您的專案中實施這些技術。如需進一步學習，請深入了解 [Aspose.Slides 文檔](https://reference.aspose.com/slides/net/) 或探索他們的論壇以獲得社群支援。
## 常見問題部分
1. **如何連結網頁磁碟機上的外部工作簿？**
   - 確保為您的應用程式環境的存取設定了適當的權限和路徑。
2. **我可以即時更新圖表數據嗎？**
   - 雖然 Aspose.Slides 不直接支援即時更新，但頻繁刷新可以模擬這種效果。
3. **我可以連結的外部工作簿數量有限制嗎？**
   - 不存在固有限制，但效能可能會根據系統的功能和工作簿的複雜性而有所不同。
4. **如果我的圖表無法正確顯示數據，我該如何排除故障？**
   - 檢查程式碼中的儲存格參考是否與 Excel 檔案一致。
5. **外部工作簿支援哪些格式？**
   - Aspose.Slides 主要支持 `.xlsx` 文件，但請確保根據您的特定工作簿設定的相容性。
## 資源
- [Aspose.Slides文檔](https://reference.aspose.com/slides/net/)
- [下載 Aspose.Slides](https://releases.aspose.com/slides/net/)
- [購買 Aspose.Slides 許可證](https://purchase.aspose.com/buy)
- [免費試用評估](https://releases.aspose.com/slides/net/)
- [申請臨時許可證](https://purchase.aspose.com/temporary-license/)
- [Aspose 支援論壇](https://forum.aspose.com/c/slides/14)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}