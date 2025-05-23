---
"date": "2025-04-15"
"description": "了解如何透過將外部 Excel 資料與 Aspose.Slides for .NET 連結來增強簡報。本指南將指導您設定、配置和實施動態圖表。"
"title": "如何在 Aspose.Slides .NET 中為圖表設定外部工作簿&#58;逐步指南"
"url": "/zh-hant/net/data-integration/set-external-workbook-chart-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Aspose.Slides .NET 中為圖表設定外部工作簿：逐步指南

## 介紹

將來自外部來源的資料直接合併到您的簡報中可以大大提高其價值。使用 Aspose.Slides for .NET，您可以無縫地為投影片中的圖表設定外部工作簿，以實現動態和更新的視覺化。本教學將引導您完成將基於網路的 Excel 檔案連結到簡報中的圖表的過程。

**您將學到什麼：**
- 配置 Aspose.Slides .NET 環境。
- 從網路位置為圖表設定外部工作簿。
- 在 C# 中實作自訂資源載入處理程序。
- 將外部資料來源與簡報整合的實際應用。

讓我們開始吧！

## 先決條件

在開始編碼之前，請確保滿足以下要求：

- **所需的庫和依賴項**：在您的專案中安裝 Aspose.Slides for .NET。
- **環境設定要求**：設定 C# 開發環境（例如，Visual Studio）。
- **知識前提**：具備C#程式設計基礎知識，熟悉Aspose.Slides。

## 設定 Aspose.Slides for .NET

首先在您的專案中安裝 Aspose.Slides 庫。您可以使用以下任何一種方法：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**套件管理器控制台**
```bash
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI**：搜尋“Aspose.Slides”並安裝最新版本。

### 許可證獲取

若要使用 Aspose.Slides，請先免費試用或申請臨時授權。為了長期使用，請考慮從其官方網站購買完整許可證。

### 基本初始化

以下是如何在應用程式中初始化 Aspose.Slides：
```csharp
using Aspose.Slides;

// 初始化Presentation對象
Presentation pres = new Presentation();
```

## 實施指南

讓我們將實現分解為幾個主要特徵。

### 從網路設定外部工作簿

此功能可讓您將基於網路的 Excel 檔案連結為簡報中圖表的外部工作簿。

#### 步驟 1：指定外部工作簿路徑
指定位於網路磁碟機上的外部工作簿的路徑：
```csharp
string externalWbPath = "http://您的文件目錄/styles/2.xlsx」；
```
代替 `YOUR_DOCUMENT_DIRECTORY` 與託管 Excel 檔案的實際目錄。

#### 步驟 2：配置載入選項
設定載入選項並指定自訂資源載入回調：
```csharp
LoadOptions opts = new LoadOptions();
opts.ResourceLoadingCallback = new WorkbookLoadingHandler();
```

#### 步驟 3：建立簡報並新增圖表
建立一個簡報實例並在第一張投影片中新增一個圖表：
```csharp
using (Presentation pres = new Presentation(opts))
{
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
    IChartData chartData = chart.ChartData;
    
    // 設定圖表資料的外部工作簿路徑
    (chartData as ChartData).SetExternalWorkbook(externalWbPath);
}
```

### 工作簿載入處理程序

此功能涉及建立自訂資源載入處理程序以從指定的網路位置取得 Excel 檔案。

#### 步驟1：實作資源載入回調
創建一個實現的類 `IResourceLoadingCallback`：
```csharp
class WorkbookLoadingHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(IResourceLoadingArgs args)
    {
        string workbookPath = args.OriginalUri;
        
        // 檢查路徑是否為網路位置（而非本機檔案路徑）
        if (workbookPath.IndexOf(':') > 1 && !workbookPath.StartsWith("file:///"))
        {
            try
            {
                WebRequest request = WebRequest.Create(workbookPath);
                request.Credentials = new NetworkCredential("testuser", "testuser");
                
                using (WebResponse response = request.GetResponse())
                using (Stream responseStream = response.GetResponseStream())
                {
                    // 將取得的資料提供給 Aspose.Slides
                    return ResourceLoadingAction.UserProvided;
                }
            }
            catch (Exception ex)
            {
                throw new InvalidOperationException(ex.ToString());
            }
        }
        else
        {
            return ResourceLoadingAction.Default;
        }
    }
}
```

## 實際應用

以下是將外部資料來源與 Aspose.Slides 簡報整合的一些實際用例：
1. **動態報告**：根據最新的網路數據自動更新財務或績效報告中的圖表。
2. **業務儀表板**：建立從公司資料庫或遠端伺服器提取即時資料的互動式儀表板。
3. **教育內容**：利用最新的統計數據開發經濟學或人口統計等學科的教育材料。

## 性能考慮

使用外部工作簿時，請考慮以下效能提示：
- **優化網路請求**：盡量減少網路請求的頻率，以減少延遲和頻寬使用。
- **資源管理**：在不再需要流後及時釋放流，以確保高效使用記憶體。
- **錯誤處理**：針對網路問題實施強大的錯誤處理，以確保應用程式順利運行。

## 結論

現在，您應該對如何使用 Aspose.Slides for .NET 從網路位置設定外部工作簿有充分的了解。此功能可顯著增強簡報的互動性和資料相關性。為了進一步探索，請考慮整合其他 Aspose 程式庫或探索 Aspose.Slides 支援的其他圖表類型。嘗試在您的一個專案中實施此解決方案，以親眼見證其好處！

## 常見問題部分

**1.什麼是 Aspose.Slides for .NET？**
Aspose.Slides for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、操作和轉換 PowerPoint 簡報。

**2. 我可以將 Aspose.Slides 與其他程式語言一起使用嗎？**
是的，Aspose 為 Java、C++、Python 等提供了類似的函式庫。

**3. 載入外部工作簿時如何處理網路錯誤？**
在您的內部實現強大的異常處理 `WorkbookLoadingHandler` 妥善管理潛在的網路問題。

**4. 是否可以使用本地文件代替網路位置？**
是的，你可以修改路徑 `externalWbPath` 如果需要的話指向本地文件。

**5.我可以用新數據自動更新圖表嗎？**
是的，透過定期重新取得和設定外部工作簿，您的圖表將反映對來源資料所做的任何更新。

## 資源
- **文件**： [Aspose.Slides .NET文檔](https://reference.aspose.com/slides/net/)
- **下載**： [Aspose.Slides 發布 .NET 版本](https://releases.aspose.com/slides/net/)
- **購買**： [購買 Aspose.Slides](https://purchase.aspose.com/buy)
- **免費試用**： [Aspose.Slides 免費試用](https://releases.aspose.com/slides/net/)
- **臨時執照**： [取得 Aspose.Slides 的臨時許可證](https://purchase.aspose.com/temporary-license/)
- **支援**： [Aspose 支援論壇](https://forum.aspose.com/c/slides/11)

有了這些資源，您就可以在 .NET 專案中充分發揮 Aspose.Slides 的潛力。編碼愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}