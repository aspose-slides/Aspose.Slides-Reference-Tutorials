---
title: 在 PowerPoint 中使用連接器連接形狀
linktitle: 在 PowerPoint 中使用連接器連接形狀
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 的 PowerPoint 簡報中的連接器連接形狀。適合初學者的逐步教程。
weight: 18
url: /zh-hant/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
在本教學中，我們將探索如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中使用連接器連接形狀。請按照這些逐步說明有效連接形狀並創建具有視覺吸引力的幻燈片。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Java 程式語言的基礎知識。
- 在您的系統上安裝了 Java 開發工具包 (JDK)。
- 下載並設定 Aspose.Slides for Java。如果您還沒有安裝，可以從以下位置下載[這裡](https://releases.aspose.com/slides/java/).
- 程式碼編輯器，例如 Eclipse 或 IntelliJ IDEA。

## 導入包
首先，匯入在 Java 專案中使用 Aspose.Slides 所需的套件。
```java
import com.aspose.slides.*;

```
## 第 1 步：實例化演示類
實例化`Presentation`類，它代表您正在處理的 PPTX 文件。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## 第 2 步：存取形狀集合
存取要在其中新增形狀和連接器的選定投影片的形狀集合。
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## 第 3 步：新增形狀
將所需的形狀新增至投影片中。在此範例中，我們將新增一個橢圓形和一個矩形。
```java
//新增自動形狀橢圓
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
//新增自動形狀矩形
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 第 4 步：新增連接器
將連接器形狀新增至投影片形狀集合。
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 第 5 步：將形狀連接到連接器
將形狀連接到連接器。
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 第 6 步：重新路由連接器
呼叫重新路由以設定形狀之間的自動最短路徑。
```java
connector.reroute();
```
## 第 7 步：儲存簡報
使用連接器連接形狀後儲存簡報。
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
最後，不要忘記處理Presentation 物件。
```java
if (input != null) input.dispose();
```
現在，您已經使用 Aspose.Slides for Java 在 PowerPoint 中使用連接器成功連接了形狀。

## 結論
在本教學中，我們學習如何使用 PowerPoint 簡報中的連接器和 Aspose.Slides for Java 連線形狀。透過遵循這些簡單的步驟，您可以使用具有視覺吸引力的圖表和流程圖來增強您的簡報。
## 常見問題解答
### 我可以自訂 Aspose.Slides for Java 中連接器的外觀嗎？
是的，您可以自訂連接器的各種屬性，例如顏色、線條樣式和粗細，以滿足您的簡報需求。
### Aspose.Slides for Java 是否與所有版本的 PowerPoint 相容？
Aspose.Slides for Java 支援各種 PowerPoint 格式，包括 PPTX、PPT 和 ODP。
### 我可以使用一個連接器連接兩個以上的形狀嗎？
是的，您可以使用 Aspose.Slides for Java 提供的複雜連接器連接多個形狀。
### Aspose.Slides for Java 是否支援為形狀新增文字？
當然，您可以使用 Aspose.Slides for Java 以程式設計方式輕鬆地將文字新增至形狀和連接器。
### 是否有 Java 使用者的 Aspose.Slides 的社群論壇或支援管道？
是的，您可以在 Aspose.Slides 論壇上找到有用的資源、提出問題並與其他使用者互動[這裡](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
