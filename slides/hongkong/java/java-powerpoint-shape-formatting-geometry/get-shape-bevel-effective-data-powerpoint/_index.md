---
title: 在 PowerPoint 中取得形狀斜角有效數據
linktitle: 在 PowerPoint 中取得形狀斜角有效數據
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中擷取形狀斜角有效資料。透過令人驚嘆的視覺效果增強您的簡報。
weight: 26
url: /zh-hant/java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
在現代商業簡報中，視覺吸引力在有效傳達訊息方面起著至關重要的作用。斜角效果是增強 PowerPoint 簡報中形狀視覺效果的元素之一。 Aspose.Slides for Java 提供了強大的工具來存取和操作形狀的各種屬性，包括它們的斜角效果。在本教程中，我們將引導您完成使用 Aspose.Slides for Java 檢索形狀斜角有效資料的過程。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. 對 Java 程式語言有基本的了解。
2. 在您的系統上安裝了 Java 開發工具包 (JDK)。
3. 下載並安裝了 Aspose.Slides for Java。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).
## 導入包
首先在 Java 專案中匯入必要的套件：
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## 第 1 步：設定文檔目錄
定義 PowerPoint 簡報所在文件目錄的路徑：
```java
String dataDir = "Your Document Directory";
```
## 第 2 步：載入簡報
使用 Aspose.Slides 庫載入 PowerPoint 簡報：
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## 步驟 3：檢索斜角有效數據
存取形狀的有效斜角資料：
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## 步驟 4：列印斜角屬性
列印出有效形狀的頂面浮雕屬性：
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## 結論
在本教學中，我們示範如何使用 Aspose.Slides for Java 在 PowerPoint 中擷取形狀斜角有效資料。透過執行這些步驟，您可以輕鬆存取和操作形狀的各種屬性，以增強簡報的視覺吸引力。
## 常見問題解答
### 我可以同時對多個形狀套用斜角效果嗎？
是的，您可以迭代幻燈片中的形狀並根據需要套用斜角效果。
### 除了斜角之外，Aspose.Slides 是否支援其他 3D 效果？
是的，Aspose.Slides 提供了多種 3D 效果，您可以將它們套用到 PowerPoint 簡報中的形狀。
### Aspose.Slides 是否與不同版本的 PowerPoint 相容？
Aspose.Slides 確保與各種版本的 PowerPoint 的兼容性，讓您能夠在不同環境中無縫運作。
### 我可以進一步自訂斜角效果屬性嗎？
當然，您可以完全控制斜角效果屬性，並可以根據您的要求進行自訂。
### 在哪裡可以找到有關 Aspose.Slides 的更多資源和支援？
您可以訪問[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11)如有任何問題、支援或其他資源。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
