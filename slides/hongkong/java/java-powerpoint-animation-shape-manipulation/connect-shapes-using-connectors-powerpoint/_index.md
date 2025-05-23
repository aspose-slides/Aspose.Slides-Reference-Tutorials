---
"description": "了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中使用連接器連接形狀。為初學者提供逐步教程。"
"linktitle": "使用 PowerPoint 中的連接器連接形狀"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "使用 PowerPoint 中的連接器連接形狀"
"url": "/zh-hant/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 PowerPoint 中的連接器連接形狀

## 介紹
在本教程中，我們將探索如何在 Aspose.Slides for Java 的幫助下使用 PowerPoint 簡報中的連接器連接形狀。按照這些逐步說明，可以有效地連接形狀並創建具有視覺吸引力的幻燈片。
## 先決條件
在開始之前，請確保您符合以下先決條件：
- Java 程式語言的基礎知識。
- 在您的系統上安裝 Java 開發工具包 (JDK)。
- 下載並設定 Java 版 Aspose.Slides。如果你還沒有安裝，你可以從 [這裡](https://releases。aspose.com/slides/java/).
- 程式碼編輯器，例如 Eclipse 或 IntelliJ IDEA。

## 導入包
首先，在您的 Java 專案中匯入使用 Aspose.Slides 所需的套件。
```java
import com.aspose.slides.*;

```
## 步驟 1：實例化表示類
實例化 `Presentation` 類，代表您正在處理的 PPTX 文件。
```java
// 文檔目錄的路徑。                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## 第 2 步：存取形狀集合
存取您想要新增形狀和連接器的選定投影片的形狀集合。
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## 步驟 3：新增形狀
將所需的形狀新增至投影片中。在這個例子中，我們將新增一個橢圓和一個矩形。
```java
// 新增自選形狀橢圓
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// 新增自選形狀矩形
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 步驟 4：新增連接器
將連接器形狀新增至投影片形狀集合。
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 步驟 5：將形狀連接到連接器
將形狀連接到連接器。
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 步驟 6：重新路由連接器
呼叫 reroute 設定形狀之間的自動最短路徑。
```java
connector.reroute();
```
## 步驟 7：儲存簡報
使用連接器連接形狀後儲存簡報。
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
最後，不要忘記處理 Presentation 物件。
```java
if (input != null) input.dispose();
```
現在，您已使用 Aspose.Slides for Java 成功透過 PowerPoint 中的連接器連接形狀。

## 結論
在本教學中，我們學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中使用連接器連接形狀。透過遵循這些簡單的步驟，您可以使用視覺上吸引人的圖表和流程圖來增強您的簡報。
## 常見問題解答
### 我可以自訂 Aspose.Slides for Java 中連接器的外觀嗎？
是的，您可以自訂連接器的各種屬性，例如顏色、線條樣式和粗細，以滿足您的簡報需求。
### Aspose.Slides for Java 是否與所有版本的 PowerPoint 相容？
Aspose.Slides for Java 支援各種 PowerPoint 格式，包括 PPTX、PPT 和 ODP。
### 我可以使用一個連接器連接兩個以上的形狀嗎？
是的，您可以使用 Aspose.Slides for Java 提供的複雜連接器連接多個形狀。
### Aspose.Slides for Java 是否支援為形狀新增文字？
當然，您可以使用 Aspose.Slides for Java 以程式設計方式輕鬆地將文字新增至形狀和連接器。
### 是否有可供 Aspose.Slides for Java 使用者的社群論壇或支援管道？
是的，您可以在 Aspose.Slides 論壇上找到有用的資源、提出問題並與其他使用者交流 [這裡](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}