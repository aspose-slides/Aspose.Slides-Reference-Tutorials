---
"date": "2025-04-16"
"description": "了解如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立動態 SmartArt 圖形。使用此綜合指南增強您的簡報效果。"
"title": "使用 Aspose.Slides for .NET 在 PowerPoint 中建立 SmartArt 形狀&#58;逐步指南"
"url": "/zh-hant/net/smart-art-diagrams/create-smartart-shapes-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for .NET 在 PowerPoint 中建立 SmartArt 形狀：逐步指南

## 介紹

透過使用 C# 整合動態 SmartArt 圖形來增強您的 PowerPoint 簡報。使用 Aspose.Slides for .NET，您可以在投影片中無縫建立和管理 SmartArt 形狀。本指南將引導您完成使用 Aspose.Slides for .NET 設定和實作 SmartArt 的過程。

**您將學到什麼：**
- 使用 Aspose.Slides for .NET 設定您的環境
- 在 PowerPoint 投影片中建立 SmartArt 形狀
- 在程式碼中有效地管理目錄

## 先決條件（H2）

為了成功實施此解決方案，請確保您已：
- **所需庫**：Aspose.Slides for .NET（建議使用 21.11 或更高版本）
- **開發環境**：.NET Core 或 .NET Framework
- **基礎知識**：熟悉C#與檔案系統操作

## 設定 Aspose.Slides for .NET（H2）

### 安裝

首先使用以下方法之一安裝 Aspose.Slides：

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Visual Studio 中的套件管理器控制台**
```powershell
Install-Package Aspose.Slides
```

**NuGet 套件管理器 UI**
1. 開啟 NuGet 套件管理器。
2. 搜尋“Aspose.Slides”並安裝最新版本。

### 許可證獲取
- **免費試用**：從下載臨時許可證 [這裡](https://purchase.aspose.com/temporary-license/) 評估 Aspose.Slides 的全部功能。
- **購買**：如需繼續使用，請透過以下方式購買許可證 [此連結](https://purchase。aspose.com/buy).

取得許可證檔案後，請在應用程式中進行初始化，如下所示：
```csharp
License license = new License();
license.SetLicense("Aspose.Slides.lic");
```

## 實施指南（H2）

### 功能：建立 SmartArt 形狀 (H2)

此功能可讓您以程式設計方式為 PowerPoint 投影片新增視覺上吸引人的 SmartArt 圖形。

#### 流程概述（H3）
我們將先設定一個目錄，建立一個示範對象，然後再加入一個 SmartArt 形狀。

#### 代碼演練（H3）
1. **目錄管理**
   確保您的文件目錄存在或在必要時建立它：
   ```csharp
   string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // 定義目標文檔目錄路徑
   bool isExists = Directory.Exists(dataDir); // 檢查目錄是否存在
   if (!isExists) 
       Directory.CreateDirectory(dataDir); // 如果目錄不存在，則建立該目錄
   ```

2. **建立新的簡報**
   初始化一個新的簡報並存取其第一張投影片：
   ```csharp
   using (Presentation pres = new Presentation())
   {
       ISlide slide = pres.Slides[0]; // 存取第一張投影片
   ```
   
3. **將 SmartArt 新增至幻燈片**
   在指定座標處新增具有所需尺寸和佈局類型的 SmartArt 形狀：
   ```csharp
   // 使用 BasicBlockList 佈局新增 SmartArt 形狀
   ISmartArt smart = slide.Shapes.AddSmartArt(0, 0, 400, 400, SmartArtLayoutType.BasicBlockList);
   ```

4. **儲存簡報**
   最後，將您的簡報儲存到所需的目錄：
   ```csharp
   pres.Save(dataDir + "SimpleSmartArt_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}