---
title: 使用 Java 在 PowerPoint 中套用外部陰影
linktitle: 使用 Java 在 PowerPoint 中套用外部陰影
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Java 和 Aspose.Slides 在 PowerPoint 中套用外部陰影效果。增強您的簡報的深度和視覺吸引力。
weight: 13
url: /zh-hant/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 PowerPoint 中套用外部陰影

## 介紹
建立具有視覺吸引力的 PowerPoint 簡報通常需要在形狀和文字中添加各種效果。其中一種效果是外部陰影，它可以使元素脫穎而出並增加幻燈片的深度。在本教學中，您將學習如何使用 Java 和 Aspose.Slides 將外部陰影效果套用至 PowerPoint 中的形狀。
## 先決條件

在開始本教學之前，請確保您具備以下先決條件：

1. Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。您可以從 Oracle 網站下載並安裝最新版本的 JDK。

2.  Aspose.Slides for Java：從下列位置下載並安裝 Aspose.Slides for Java：[下載頁面](https://releases.aspose.com/slides/java/).

3. 整合開發環境 (IDE)：選擇您喜歡的 Java IDE（例如 Eclipse、IntelliJ IDEA 或 NetBeans）來編碼和執行 Java 應用程式。

4. Java 基礎知識：熟悉 Java 程式語言基礎知識和物件導向的概念將有助於理解程式碼範例。

## 導入包

首先，匯入在 Java 專案中使用 Aspose.Slides 和相關功能所需的套件：

```java
import com.aspose.slides.*;
```

現在，讓我們將範例程式碼分解為多個步驟，以使用 Java 和 Aspose.Slides 將外部陰影效果套用到 PowerPoint 中的形狀：

## 第 1 步：設定專案環境

在您的首選 IDE 中建立一個新的 Java 項目，並將 Aspose.Slides for Java 程式庫新增至專案的建置路徑。

## 步驟2：初始化Presentation對象

建立一個實例`Presentation`類，代表 PowerPoint 簡報文件。

```java
Presentation presentation = new Presentation();
```

## 第 3 步：新增投影片和形狀

取得要新增形狀的投影片的引用，然後將自選圖形（例如矩形）新增至投影片。

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## 第四步：自訂形狀

將形狀的填滿類型設為“NoFill”並為形狀新增文字。

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## 第 5 步：自訂文本

存取形狀的文字屬性並自訂字體大小。

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## 步驟6：啟用外陰影效果

為文字部分啟用外部陰影效果。

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## 第7步：設定陰影參數

定義外部陰影效果的參數，例如模糊半徑、方向、距離和陰影顏色。

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## 第 8 步：儲存簡報

儲存修改後的簡報，並將外部陰影效果套用至形狀。

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## 結論

恭喜！您已使用 Java 和 Aspose.Slides 成功地將外部陰影效果套用到 PowerPoint 中的形狀。嘗試不同的參數，以在簡報中實現所需的視覺效果。

## 常見問題解答

### 我可以將外部陰影效果應用到矩形之外的其他形狀嗎？
是的，您可以將外部陰影效果套用到 Aspose.Slides 支援的各種形狀，例如圓形、三角形和自訂形狀。

### 是否可以自訂陰影顏色和強度？
絕對地！您可以完全控制陰影參數，包括顏色、模糊半徑、方向和距離。

### 我可以對同一形狀套用多種效果嗎？
是的，您可以組合多種效果，例如外部陰影、內部陰影、發光和反射，以增強簡報中形狀和文字的視覺吸引力。

### Aspose.Slides 是否支援對文字元素套用效果？
是的，您不僅可以將效果應用於形狀，還可以應用於形狀中的各個文字部分，從而為您設計投影片提供了廣泛的靈活性。

### 在哪裡可以找到有關 Aspose.Slides 的更多資源和支援？
您可以參考[文件](https://reference.aspose.com/slides/java/)取得詳細的 API 參考並探索[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11)以獲得社區支持和討論。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
