---
title: 在 Java 投影片中新增自訂行
linktitle: 在 Java 投影片中新增自訂行
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用自訂行增強您的 Java 投影片。使用 Aspose.Slides for Java 的逐步指南。了解在簡報中添加和自訂線條以獲得有影響力的視覺效果。
weight: 10
url: /zh-hant/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中新增自訂行


## 在 Java 投影片中新增自訂行簡介

在本教程中，您將學習如何使用 Aspose.Slides for Java 將自訂行新增至 Java 投影片中。自訂線條可用於增強投影片的視覺表現並突出顯示特定內容。我們將為您提供逐步說明以及原始程式碼來實現這一目標。讓我們開始吧！

## 先決條件

開始之前，請確保您的 Java 專案中已設定 用於 Java 的 Aspose.Slides 程式庫。您可以從以下網站下載該資料庫：[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## 第 1 步：初始化簡報

首先，您需要建立一個新的簡報。在此範例中，我們將建立一個空白簡報。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：新增圖表

接下來，我們將向投影片新增圖表。在此範例中，我們新增一個聚集長條圖。您可以選擇適合您需求的圖表類型。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## 第 3 步：新增自訂行

現在，讓我們為圖表新增一條自訂線。我們將創建一個`IAutoShape`類型的`ShapeType.Line`並將其放置在圖表中。

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## 第 4 步：客製化線路

您可以透過設定線條的屬性來自訂線條的外觀。在此範例中，我們將線條顏色設為紅色。

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## 第 5 步：儲存簡報

最後，將簡報儲存到您想要的位置。

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## 在 Java 投影片中新增自訂行的完整原始程式碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

恭喜！您已使用 Aspose.Slides for Java 成功將自訂行新增至 Java 投影片中。您可以進一步自訂線條的屬性以實現您想要的視覺效果。

## 常見問題解答

### 如何更改線條顏色？

若要變更線條顏色，請使用以下程式碼：
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

代替`YOUR_COLOR`與所需的顏色。

### 我可以將自訂線條新增到其他形狀嗎？

是的，您可以將自訂線條新增至各種形狀，而不僅僅是圖表。只需創建一個`IAutoShape`並根據您的需求進行客製化。

### 如何更改線條粗細？

您可以透過設定更改線條粗細`Width`行格式的屬性。例如：
```java
shape.getLineFormat().setWidth(2); //將線條粗細設定為 2 點
```

### 是否可以在幻燈片中添加多行？

是的，您可以透過重複本教學中提到的步驟為投影片新增多行。每條線都可以獨立自訂。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
