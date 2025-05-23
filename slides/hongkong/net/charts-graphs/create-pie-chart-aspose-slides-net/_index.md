---
"date": "2025-04-15"
"description": "了解如何使用 Aspose.Slides for .NET 以程式設計方式將圓餅圖新增至您的簡報中，輕鬆增強資料視覺化。"
"title": "使用 Aspose.Slides for .NET 在 PowerPoint 中建立圓餅圖"
"url": "/zh-hant/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 建立圓餅圖並將其新增至簡報中
## 介紹
創建引人注目的簡報通常不僅僅涉及文字；圖表等視覺元素可以顯著增強資料敘述的影響力。如果您希望以程式設計方式將動態圓餅圖新增至 PowerPoint 簡報中， **Aspose.Slides for .NET** 是一個強大的工具，可以使這項任務無縫且有效率。本教學將引導您為簡報投影片新增圓餅圖並使用外部資料來源對其進行設定。

### 您將學到什麼
- 如何使用 Aspose.Slides for .NET 建立新的簡報
- 在第一張投影片中加入圓餅圖
- 將外部工作簿 URL 設定為圖表的資料來源
- 將簡報儲存為 PPTX 格式
讓我們從先決條件開始，深入了解如何輕鬆實現這一點。
## 先決條件
在開始之前，請確保您已準備好以下內容：
- **Aspose.Slides for .NET** 已安裝庫。您需要一個與 .NET Framework 或 .NET Core/.NET 5+ 相容的版本。
- 具備 C# 程式設計基礎並熟悉 Visual Studio IDE。
- 在您的機器上設定的開發環境（Windows、macOS 或 Linux）。
## 設定 Aspose.Slides for .NET
### 安裝說明
可以使用多種方法將 Aspose.Slides for .NET 新增到您的專案中：
**.NET CLI**
```shell
dotnet add package Aspose.Slides
```
**套件管理器控制台**
```powershell
Install-Package Aspose.Slides
```
**NuGet 套件管理器 UI**
1. 在 Visual Studio 中開啟 NuGet 套件管理器。
2. 搜尋“Aspose.Slides”。
3. 安裝最新版本。
### 許可證獲取
要使用 Aspose.Slides，您可以先免費試用許可證，無限制地探索其功能。對於生產環境，請考慮購買商業許可證或取得臨時許可證以進行擴展測試。訪問 [Aspose的購買頁面](https://purchase.aspose.com/buy) 了解更多詳情。
### 基本初始化
要在您的專案中使用 Aspose.Slides，您需要使用您的授權（如果可用）對其進行初始化：
```csharp
// 初始化函式庫
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## 實施指南
現在您已完成設置，讓我們逐步介紹每個功能。
### 建立圖表並將其新增至簡報
#### 概述
我們將首先建立一個演示文稿，然後在第一張幻燈片中新增一個圓餅圖。
#### 步驟：
1. **初始化簡報**
   首先創建一個 `Presentation` 類，代表您的 PowerPoint 文件。
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // 我們將在這裡添加圖表。
   }
   ```
2. **新增圓餅圖**
   使用 `Shapes.AddChart` 方法在投影片上的特定座標處插入圓餅圖。
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### 為圖表資料設定外部工作簿
#### 概述
現在讓我們配置餅圖以使用來自外部工作簿的資料。
#### 步驟：
1. **存取圖表數據**
   檢索圖表資料接口，您將在其中指定外部資料來源 URL。
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **設定外部工作簿 URL**
   使用以下方式設定資料來源的 URL `SetExternalWorkbook`。此範例使用佔位符 URL，應將其替換為實際資料來源路徑。
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://路徑/不存在”，false）；
   ```
### 將簡報儲存到文件
#### 概述
最後，將簡報以 PPTX 格式儲存到您想要的位置。
#### 步驟：
1. **儲存簡報**
   使用 `Save` 方法 `Presentation` 類別將檔案寫入磁碟。
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## 實際應用
- **商業報告**：自動產生季度績效評估圖表。
- **數據儀表板**：與資料來源集成，即時更新可視化報告。
- **教育內容**：建立動態演示文稿，從外部研究或研究論文中提取最新數據。
透過整合 Aspose.Slides，您可以自動化和增強跨各個領域的簡報建立過程。
## 性能考慮
處理大型資料集或大量圖表時：
- 透過在 .NET 中有效管理記憶體來優化資源使用情況。
- 處置 `Presentation` 對象正確釋放資源。
- 盡可能使用非同步操作來提高應用程式的回應能力。
## 結論
透過學習本教學課程，您將學習如何使用 Aspose.Slides for .NET 以程式設計方式建立帶有圓餅圖的簡報。您現在擁有了自動建立圖表和有效管理外部資料來源的工具。
### 後續步驟
透過自訂圖表樣式、新增更多圖表類型或整合其他 Aspose 元件（如 Aspose.Cells）來進一步探索增強的資料處理功能。
## 常見問題部分
1. **什麼是 Aspose.Slides？**  
   一個用於在 .NET 中以程式設計方式操作 PowerPoint 簡報的強大程式庫。
2. **我可以在沒有許可證的情況下使用 Aspose.Slides 嗎？**  
   是的，但有限制。考慮取得免費試用版或購買完整功能許可證。
3. **如何動態更新圖表資料？**  
   利用外部工作簿並在 `SetExternalWorkbook` 方法。
4. **Aspose.Slides 可以在多個平台上使用嗎？**  
   是的，它支援 Windows、macOS 和 Linux 上的 .NET Framework 和 .NET Core/.NET 5+。
5. **還支援哪些其他圖表類型？**  
   除了圓餅圖，您還可以使用 Aspose.Slides 建立長條圖、折線圖等。
## 資源
- [Aspose.Slides文檔](https://reference.aspose.com/slides/net/)
- [下載最新版本](https://releases.aspose.com/slides/net/)
- [購買許可證](https://purchase.aspose.com/buy)
- [免費試用](https://releases.aspose.com/slides/net/)
- [臨時執照](https://purchase.aspose.com/temporary-license/)
- [支援論壇](https://forum.aspose.com/c/slides/11)
立即開始將 Aspose.Slides 整合到您的專案中，以增強和自動化您的 PowerPoint 簡報！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}