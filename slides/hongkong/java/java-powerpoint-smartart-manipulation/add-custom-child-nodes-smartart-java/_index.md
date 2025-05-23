---
"description": "了解如何使用 Java 和 Aspose.Slides 為 PowerPoint 簡報中的 SmartArt 新增自訂子節點。輕鬆使用專業圖形增強您的投影片。"
"linktitle": "使用 Java 在 SmartArt 中新增自訂子節點"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "使用 Java 在 SmartArt 中新增自訂子節點"
"url": "/zh-hant/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 SmartArt 中新增自訂子節點

## 介紹
SmartArt 是 PowerPoint 中的一項強大功能，可讓使用者快速輕鬆地建立具有專業外觀的圖形。在本教程中，我們將學習如何使用 Java 和 Aspose.Slides 為 SmartArt 新增自訂子節點。
## 先決條件
在開始之前，請確保您具備以下條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。
2. Aspose.Slides for Java：從下列位置下載並安裝 Aspose.Slides for Java [這裡](https://releases。aspose.com/slides/java/).

## 導入包
首先，在 Java 專案中匯入必要的套件：
```java
import com.aspose.slides.*;
```
## 步驟 1：載入簡報
載入要為 SmartArt 新增自訂子節點的 PowerPoint 簡報：
```java
String dataDir = "Your Document Directory";
// 載入所需的簡報
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## 步驟 2：將 SmartArt 新增至投影片
現在，讓我們將 SmartArt 新增至投影片中：
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## 步驟 3：移動 SmartArt 形狀
將 SmartArt 造型移至新位置：
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## 步驟 4：變更形狀寬度
更改 SmartArt 形狀的寬度：
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## 步驟5：改變形狀高度
更改 SmartArt 造型的高度：
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## 步驟 6：旋轉形狀
旋轉 SmartArt 造型：
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## 步驟 7：儲存簡報
最後，儲存修改後的簡報：
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## 結論
在本教程中，我們學習如何使用 Java 和 Aspose.Slides 為 SmartArt 新增自訂子節點。透過遵循這些步驟，您可以使用自訂圖形來增強您的簡報，使其更具吸引力和專業性。
## 常見問題解答
### 我可以使用 Aspose.Slides for Java 新增不同類型的 SmartArt 佈局嗎？
是的，Aspose.Slides for Java 支援各種 SmartArt 佈局，讓您可以選擇最適合您簡報需求的佈局。
### Aspose.Slides for Java 是否與不同版本的 PowerPoint 相容？
Aspose.Slides for Java 旨在與不同版本的 PowerPoint 無縫協作，確保跨平台的兼容性和一致性。
### 我可以透過程式自訂 SmartArt 造型的外觀嗎？
絕對地！使用 Aspose.Slides for Java，您可以透過程式設計自訂 SmartArt 形狀的外觀、大小、顏色和佈局，以滿足您的設計偏好。
### Aspose.Slides for Java 是否提供文件和支援？
是的，您可以在 Aspose 網站上找到全面的文件並造訪社群支援論壇。
### Aspose.Slides for Java 有試用版嗎？
是的，您可以從網站下載 Aspose.Slides for Java 的免費試用版，以便在購買之前了解其功能和功能 [這裡](https://releases。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}