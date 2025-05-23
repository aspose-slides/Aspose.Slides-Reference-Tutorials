---
"description": "透過本全面的逐步教學，了解如何使用 Aspose.Slides for Java 在 PowerPoint 中對形狀套用 3D 旋轉效果。"
"linktitle": "在 PowerPoint 中對形狀套用 3D 旋轉效果"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 PowerPoint 中對形狀套用 3D 旋轉效果"
"url": "/zh-hant/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 PowerPoint 中對形狀套用 3D 旋轉效果

## 介紹
您準備好將您的 PowerPoint 簡報提升到一個新的水平嗎？添加 3D 旋轉效果可以使您的投影片更具活力和吸引力。無論您是經驗豐富的開發人員還是剛入門，本逐步教學都會向您展示如何使用 Aspose.Slides for Java 將 3D 旋轉效果套用至 PowerPoint 中的形狀。讓我們開始吧！
## 先決條件
在開始之前，請確保您已準備好以下事項：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從 [Oracle 網站](https://www。oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java：從 [下載連結](https://releases。aspose.com/slides/java/).
3. 整合開發環境 (IDE)：使用 IntelliJ IDEA 或 Eclipse 等 IDE 進行編碼。
4. 有效的駕照：如果你沒有駕照，你可以獲得 [臨時執照](https://purchase.aspose.com/temporary-license/) 試用這些功能。
## 導入包
首先，讓我們在您的 Java 專案中匯入必要的套件。這些匯入將幫助您使用 Aspose.Slides 處理簡報和形狀。
```java
import com.aspose.slides.*;

```
## 步驟 1：設定您的項目
在深入研究程式碼之前，請先設定您的專案環境。確保已將 Aspose.Slides for Java 新增至專案的依賴項。
將 Aspose.Slides 加入您的專案：
1. 從 [下載頁面](https://releases。aspose.com/slides/java/).
2. 將這些 JAR 檔案新增至專案的建置路徑。
## 步驟 2：建立新的 PowerPoint 簡報
在此步驟中，我們將建立一個新的 PowerPoint 簡報。
```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立 Presentation 類別的實例
Presentation pres = new Presentation();
```
此程式碼片段初始化了一個新的演示對象，我們將在其中添加形狀。
## 步驟 3：新增矩形
接下來，讓我們在第一張投影片中新增一個矩形。
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
此程式碼在第一張投影片上的指定位置和大小新增一個矩形。
## 步驟 4：對矩形套用 3D 旋轉
現在，讓我們對矩形形狀套用 3D 旋轉效果。
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
在這裡，我們設定深度、相機旋轉角度、相機類型和照明類型，使我們的矩形具有 3D 外觀。
## 步驟 5：新增線條形狀
讓我們在幻燈片中添加另一個形狀，這次是一條線。
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
此程式碼在投影片上放置一個線條形狀。
## 步驟 6：對線條套用 3D 旋轉
最後，我們將對線條形狀套用 3D 旋轉效果。
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
與矩形類似，我們為線形設定 3D 屬性。
## 步驟 7：儲存簡報
新增和配置形狀後，儲存簡報。
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
此程式碼以所需的格式使用指定的檔案名稱儲存您的簡報。
## 結論
恭喜！您已成功使用 Aspose.Slides for Java 將 3D 旋轉效果套用至 PowerPoint 簡報中的形狀。透過遵循這些步驟，您可以建立具有視覺吸引力和動態的簡報。如需進一步客製化和更多高級功能，請參閱 [Aspose.Slides 文檔](https://reference。aspose.com/slides/java/).
## 常見問題解答
### 什麼是 Aspose.Slides for Java？
Aspose.Slides for Java 是一個強大的 API，可以以程式設計方式建立、修改和操作 PowerPoint 簡報。
### 我可以免費試用 Aspose.Slides for Java 嗎？
是的，你可以得到 [免費試用](https://releases.aspose.com/) 或 [臨時執照](https://purchase.aspose.com/temporary-license/) 測試功能。
### 我可以在 Aspose.Slides 中為哪些類型的形狀添加 3D 效果？
您可以為各種形狀（如矩形、線條、橢圓和自訂形狀）添加 3D 效果。
### 如何獲得 Aspose.Slides for Java 的支援？
您可以訪問 [支援論壇](https://forum.aspose.com/c/slides/11) 尋求協助並討論任何問題。
### 我可以在商業專案中使用 Aspose.Slides for Java 嗎？
是的，但是您需要購買許可證。您可以從 [購買頁面](https://purchase。aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}