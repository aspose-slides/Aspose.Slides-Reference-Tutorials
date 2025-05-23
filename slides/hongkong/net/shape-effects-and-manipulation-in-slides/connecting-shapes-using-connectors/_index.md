---
"description": "探索 Aspose.Slides for .NET 的強大功能，在簡報中輕鬆連接形狀。使用動態連接器提升您的投影片。"
"linktitle": "在簡報中使用連接器連接形狀"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "Aspose.Slides - 在.NET中無縫連接形狀"
"url": "/zh-hant/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - 在.NET中無縫連接形狀

## 介紹
在動態的簡報世界中，使用連接器連接形狀的能力為您的投影片增添了一層複雜性。 Aspose.Slides for .NET 讓開發人員能夠無縫實現這一目標。本教程將引導您完成整個過程，分解每個步驟以確保您清楚地理解。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
- C# 和 .NET 架構的基本知識。
- 已安裝 Aspose.Slides for .NET。如果沒有，請下載 [這裡](https://releases。aspose.com/slides/net/).
- 已建立開發環境。
## 導入命名空間
在您的 C# 程式碼中，首先匯入必要的命名空間：
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. 設定文檔目錄
首先定義文檔的目錄：
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2.實例化Presentation類
建立 Presentation 類別的實例來表示您的 PPTX 檔案：
```csharp
using (Presentation input = new Presentation())
{
    // 存取選取投影片的形狀集合
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. 在投影片中新增形狀
在投影片中新增必要的形狀，例如橢圓形和矩形：
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. 新增連接器形狀
在投影片的形狀集合中包含連接器形狀：
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. 使用連接器連接形狀
指定要透過連接器連接的形狀：
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. 重新路由連接器
呼叫 reroute 方法設定形狀之間的自動最短路徑：
```csharp
connector.Reroute();
```
## 7.儲存簡報
儲存您的簡報以查看連接的形狀：
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 結論
恭喜！您已使用 Aspose.Slides for .NET 成功透過簡報投影片中的連接器連接形狀。利用此高級功能增強您的簡報效果並吸引觀眾。
## 常見問題解答
### Aspose.Slides for .NET 是否與最新的 .NET 框架相容？
是的，Aspose.Slides for .NET 會定期更新以確保與最新的 .NET 框架版本相容。
### 我可以使用單一連接器連接兩個以上的形狀嗎？
當然，您可以透過擴充程式碼中的連接器邏輯來連接多個形狀。
### 我可以連接的形狀有什麼限制嗎？
Aspose.Slides for .NET 支援連接各種形狀，包括基本形狀、智慧藝術和自訂形狀。
### 如何自訂連接器的外觀？
瀏覽 Aspose.Slides 文檔，以了解自訂連接器外觀（例如線條樣式和顏色）的方法。
### 是否有 Aspose.Slides 支持的社區論壇？
是的，您可以在 [Aspose.Slides論壇](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}