---
"description": "透過本詳細教學了解如何使用 Aspose.Slides for Java 為 PowerPoint 中的形狀新增動畫。非常適合創建引人入勝的簡報。"
"linktitle": "在 PowerPoint 中為形狀新增動畫"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 PowerPoint 中為形狀新增動畫"
"url": "/zh-hant/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 PowerPoint 中為形狀新增動畫

## 介紹
創建引人入勝的簡報通常需要在形狀和文字中添加動畫。動畫可以讓您的投影片更加生動、更吸引人，確保您的觀眾保持興趣。在本教學中，我們將指導您使用 Aspose.Slides for Java 為 PowerPoint 簡報中的形狀新增動畫的過程。閱讀本文後，您將能夠毫不費力地創建專業動畫。
## 先決條件
在深入學習本教學之前，請確保您已準備好所需的一切：
1. Aspose.Slides for Java 函式庫：您需要安裝 Aspose.Slides for Java 函式庫。你可以 [點此下載](https://releases。aspose.com/slides/java/).
2. Java 開發工具包 (JDK)：確保您的機器上安裝了 JDK。
3. 整合開發環境 (IDE)：使用任何 Java IDE，如 IntelliJ IDEA、Eclipse 或 NetBeans。
4. Java 基礎：本教學假設您對 Java 程式設計有基本的了解。
## 導入包
首先，您需要匯入 Aspose.Slides 和其他所需的 Java 類別所需的套件。
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## 步驟 1：設定項目目錄
首先，為您的專案文件建立一個目錄。
```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## 步驟2：初始化演示對象
接下來，實例化 `Presentation` 類別來代表您的 PowerPoint 文件。
```java
// 實例化代表 PPTX 的 Presentation 類
Presentation pres = new Presentation();
```
## 步驟 3：存取第一張投影片
現在，訪問簡報中的第一張投影片，您將在其中新增動畫。
```java
// 存取第一張投影片
ISlide sld = pres.getSlides().get_Item(0);
```
## 步驟 4：為投影片新增形狀
在幻燈片中添加一個矩形並在其中插入一些文字。
```java
// 在投影片中新增矩形
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## 步驟5：套用動畫效果
將「PathFootball」動畫效果應用於形狀。
```java
// 新增 PathFootBall 動畫效果
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## 步驟 6：建立互動式觸發器
建立一個按鈕形狀，點擊時將觸發動畫。
```java
// 建立一個「按鈕」形狀來觸發動畫
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## 步驟 7：定義互動序列
定義按鈕的一系列效果。
```java
// 為按鈕建立一系列效果
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## 步驟 8：新增自訂使用者路徑
在形狀中新增自訂使用者路徑動畫。
```java
// 新增自訂使用者路徑動畫效果
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// 創造運動效果
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// 定義路徑點
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## 步驟 9：儲存簡報
最後，將簡報儲存到您想要的位置。
```java
// 將簡報儲存為 PPTX 文件
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// 處置演示對象
if (pres != null) pres.dispose();
```
## 結論
就是這樣！您已成功使用 Aspose.Slides for Java 為 PowerPoint 簡報中的形狀新增動畫。這個強大的庫可以輕鬆地透過動態效果增強您的演示文稿，確保您的觀眾保持參與。請記住，熟能生巧，因此請不斷嘗試不同的效果和觸發器，以找到最適合您需求的方法。
## 常見問題解答
### 什麼是 Aspose.Slides for Java？
Aspose.Slides for Java 是一個強大的 API，可以以程式設計方式建立、修改和操作 PowerPoint 簡報。
### 我可以免費使用 Aspose.Slides 嗎？
您可以免費試用 Aspose.Slides [臨時執照](https://purchase.aspose.com/temporary-license/)。要繼續使用，需要付費許可證。
### 哪些 Java 版本與 Aspose.Slides 相容？
Aspose.Slides 支援 Java SE 6 以上版本。
### 如何為多個形狀添加不同的動畫？
您可以透過對每個形狀重複這些步驟並根據需要指定不同的效果來為多個形狀添加不同的動畫。
### 在哪裡可以找到更多範例和文件？
查看 [文件](https://reference.aspose.com/slides/java/) 和 [支援論壇](https://forum.aspose.com/c/slides/11) 取得更多範例和協助。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}