---
title: 在 PowerPoint 中對形狀套用斜角效果
linktitle: 在 PowerPoint 中對形狀套用斜角效果
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 透過我們的逐步指南，了解如何使用 Aspose.Slides for Java 將斜角效果套用到 PowerPoint 中的形狀。增強您的簡報。
weight: 13
url: /zh-hant/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
創建具有視覺吸引力的演示對於吸引和保持觀眾的注意力至關重要。在形狀中添加斜角效果可以增強投影片的整體美感，讓您的簡報脫穎而出。在本教學中，我們將引導您完成使用 Aspose.Slides for Java 將斜角效果套用至 PowerPoint 中的形狀的過程。無論您是希望自動建立簡報的開發人員，還是只是喜歡修改設計的人，本指南都能滿足您的需求。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- Java 開發工具包 (JDK)：確保已安裝 JDK。您可以從[甲骨文網站](https://www.oracle.com/java/technologies/javase-downloads.html).
- 用於 Java 的 Aspose.Slides Library：從以下位置下載該程式庫[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
- IDE（整合開發環境）：使用您選擇的任何 IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。
-  Aspose 許可證：若要無限制地使用 Aspose.Slides，請從以下位置取得許可證[提出購買](https://purchase.aspose.com/buy)或得到一個[臨時執照](https://purchase.aspose.com/temporary-license/)進行評估。
## 導入包
首先，您需要匯入在 Java 專案中使用 Aspose.Slides 所需的套件。您可以這樣做：
```java
import com.aspose.slides.*;

import java.awt.*;
```
## 第 1 步：設定您的項目
在開始編碼之前，請確保您的項目設定正確。將 Aspose.Slides 庫包含在專案的建置路徑中。如果您使用 Maven，請將以下依賴項新增至您的`pom.xml`文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## 第 2 步：建立簡報
要開始使用 Aspose.Slides，您需要建立一個實例`Presentation`班級。此類別代表一個 PowerPoint 文件。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation pres = new Presentation();
```
## 第 3 步：存取第一張投影片
建立簡報後，造訪第一張投影片，您將在其中新增和操作形狀。
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 第 4 步：為投影片新增形狀
現在，在投影片中新增一個形狀。在此範例中，我們將新增一個橢圓。
```java
//在投影片上新增形狀
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## 第 5 步：對形狀套用斜角效果
接下來，對形狀應用斜角效果以賦予其三維外觀。
```java
//設定形狀的 ThreeDFormat 屬性
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## 第 6 步：儲存簡報
最後，將簡報作為 PPTX 檔案儲存到指定目錄。
```java
//將簡報寫入 PPTX 文件
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## 第 7 步：處理演示對象
為了釋放資源，請務必確保`Presentation`對像已妥善處置。
```java
if (pres != null) pres.dispose();
```
## 結論
使用 Aspose.Slides for Java 將斜角效果應用於 PowerPoint 簡報中的形狀是一個簡單的過程，可以顯著增強投影片的視覺吸引力。透過遵循本指南中概述的步驟，您可以輕鬆建立專業且引人入勝的簡報。記得探索[Aspose.Slides 文檔](https://reference.aspose.com/slides/java/)了解更多詳細資訊和進階功能。
## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個功能強大的 API，可讓開發人員以程式設計方式建立、修改和管理 PowerPoint 簡報。
### 我可以免費使用 Aspose.Slides for Java 嗎？
 Aspose.Slides 提供免費試用版，您可以從以下位置下載[這裡](https://releases.aspose.com/)。要獲得完整功能，您需要購買許可證。
### 我可以在投影片中新增哪些類型的形狀？
您可以使用 Aspose.Slides for Java 新增各種形狀，例如矩形、橢圓形、直線和自訂形狀。
### 除了斜角之外，是否可以套用其他 3D 效果？
是的，Aspose.Slides for Java 可讓您套用各種 3D 效果，包括深度、光線和相機效果。
### 在哪裡可以獲得 Aspose.Slides for Java 的支援？
您可以從 Aspose 社群和支援團隊獲得支持[支援論壇](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
