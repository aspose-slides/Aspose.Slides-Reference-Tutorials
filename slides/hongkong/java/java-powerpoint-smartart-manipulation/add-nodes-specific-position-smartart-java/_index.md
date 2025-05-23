---
"description": "了解如何使用 Java 和 Aspose.Slides 在 SmartArt 中的特定位置新增節點。輕鬆建立動態簡報。"
"linktitle": "使用 Java 在 SmartArt 中的特定位置新增節點"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "使用 Java 在 SmartArt 中的特定位置新增節點"
"url": "/zh-hant/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 SmartArt 中的特定位置新增節點

## 介紹
在本教程中，我們將指導您使用 Java 和 Aspose.Slides 在 SmartArt 中的特定位置新增節點的過程。 SmartArt 是 PowerPoint 中的一項功能，可讓您建立具有視覺吸引力的圖表。
## 先決條件
在開始之前，請確保您已準備好以下內容：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2. 下載了 Java 函式庫的 Aspose.Slides。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).
3. Java 程式語言的基礎知識。

## 導入包
首先，讓我們在 Java 程式碼中導入必要的套件：
```java
import com.aspose.slides.*;
import java.io.File;
```
## 步驟 1：建立示範實例
首先建立 Presentation 類別的實例：
```java
Presentation pres = new Presentation();
```
## 第 2 步：存取簡報投影片
存取要新增 SmartArt 的幻燈片：
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 步驟 3：新增 SmartArt 形狀
在投影片中新增 SmartArt 造型：
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## 步驟 4：存取 SmartArt 節點
存取所需索引處的 SmartArt 節點：
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## 步驟5：在特定位置新增子節點
在父節點的特定位置新增的子節點：
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## 步驟 6：為節點新增文本
為新新增的節點設定文字：
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## 步驟 7：儲存簡報
儲存修改後的簡報：
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## 結論
在本教程中，您學習如何使用 Java 和 Aspose.Slides 在 SmartArt 中的特定位置新增節點。透過遵循這些步驟，您可以以程式設計方式操作 SmartArt 形狀來建立動態簡報。
## 常見問題解答
### 我可以一次新增多個節點嗎？
是的，您可以透過迭代所需位置以程式設計方式新增多個節點。
### Aspose.Slides 是否與所有版本的 PowerPoint 相容？
Aspose.Slides 支援各種 PowerPoint 格式，確保與大多數版本相容。
### 我可以自訂 SmartArt 節點的外觀嗎？
是的，您可以自訂節點的外觀，包括其大小、顏色和樣式。
### Aspose.Slides 是否支援其他程式語言？
是的，Aspose.Slides 為多種程式語言提供了函式庫，包括 .NET 和 Python。
### Aspose.Slides 有試用版嗎？
是的，您可以從下載免費試用版 [這裡](https://releases。aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}