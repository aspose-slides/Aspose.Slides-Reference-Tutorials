---
title: 在 PowerPoint 中對形狀套用 3D 旋轉效果
linktitle: 在 PowerPoint 中對形狀套用 3D 旋轉效果
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 透過這個全面的逐步教學，了解如何使用 Aspose.Slides for Java 在 PowerPoint 中的形狀上套用 3D 旋轉效果。
weight: 12
url: /zh-hant/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
您準備好將 PowerPoint 簡報提升到新的水平了嗎？添加 3D 旋轉效果可以使您的投影片更具活力和吸引力。無論您是經驗豐富的開發人員還是剛入門，本逐步教學都會向您展示如何使用 Aspose.Slides for Java 將 3D 旋轉效果套用至 PowerPoint 中的形狀。讓我們開始吧！
## 先決條件
在我們開始之前，請確保您已準備好以下內容：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從[甲骨文網站](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java：從下列位置下載最新版本的 Aspose.Slides for Java：[下載連結](https://releases.aspose.com/slides/java/).
3. 整合開發環境 (IDE)：使用 IntelliJ IDEA 或 Eclipse 等 IDE 進行編碼。
4. 有效許可證：如果您沒有許可證，您可以獲得[臨時執照](https://purchase.aspose.com/temporary-license/)嘗試這些功能。
## 導入包
首先，讓我們在 Java 專案中導入必要的套件。這些匯入將幫助您使用 Aspose.Slides 處理簡報和形狀。
```java
import com.aspose.slides.*;

```
## 第 1 步：設定您的項目
在深入研究程式碼之前，請設定您的專案環境。確保您已將 Aspose.Slides for Java 新增至專案的依賴項。
將 Aspose.Slides 加入您的專案：
1. 從以下位置下載 Aspose.Slides JAR 文件[下載頁面](https://releases.aspose.com/slides/java/).
2. 將這些 JAR 檔案新增至專案的建置路徑。
## 步驟 2：建立新的 PowerPoint 簡報
在此步驟中，我們將建立一個新的 PowerPoint 簡報。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation pres = new Presentation();
```
此程式碼片段初始化一個新的演示對象，我們將在其中添加形狀。
## 第三步：新增一個矩形
接下來，我們在第一張投影片中新增一個矩形。
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
此程式碼在第一張投影片上的指定位置和大小處新增一個矩形形狀。
## 步驟 4：對矩形套用 3D 旋轉
現在，讓我們對矩形套用 3D 旋轉效果。
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
在這裡，我們設定深度、相機旋轉角度、相機類型和照明類型，以使矩形具有 3D 外觀。
## 步驟5：新增線條形狀
讓我們為投影片添加另一個形狀，這次是一條線。
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
此程式碼在投影片上放置一條線條形狀。
## 第 6 步：對直線應用 3D 旋轉
最後，我們將對線條形狀套用 3D 旋轉效果。
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
與矩形類似，我們設定線形狀的 3D 屬性。
## 第 7 步：儲存簡報
新增並配置形狀後，儲存簡報。
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
此程式碼使用指定的檔案名稱以所需的格式儲存簡報。
## 結論
恭喜！您已使用 Aspose.Slides for Java 成功地將 3D 旋轉效果套用到 PowerPoint 簡報中的形狀。透過執行以下步驟，您可以建立具有視覺吸引力的動態簡報。如需進一步客製化和更高級的功能，請參閱[Aspose.Slides 文檔](https://reference.aspose.com/slides/java/).
## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個功能強大的 API，用於以程式設計方式建立、修改和操作 PowerPoint 簡報。
### 我可以免費試用 Aspose.Slides for Java 嗎？
是的，您可以獲得[免費試用](https://releases.aspose.com/)或一個[臨時執照](https://purchase.aspose.com/temporary-license/)來測試功能。
### 我可以在 Aspose.Slides 中向哪些類型的形狀添加 3D 效果？
您可以將 3D 效果新增至各種形狀，例如矩形、直線、橢圓形和自訂形狀。
### 如何獲得 Aspose.Slides for Java 支援？
您可以訪問[支援論壇](https://forum.aspose.com/c/slides/11)尋求協助並討論任何問題。
### 我可以在商業專案中使用 Aspose.Slides for Java 嗎？
是的，但您需要購買許可證。您可以從[購買頁面](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
