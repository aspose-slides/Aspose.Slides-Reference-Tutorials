---
title: 在 Java 投影片中設定圖例自訂選項
linktitle: 在 Java 投影片中設定圖例自訂選項
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java Slides 中設定自訂圖例選項。自訂 PowerPoint 圖表中的圖例位置和大小。
weight: 14
url: /zh-hant/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## 在 Java 投影片中設定圖例自訂選項簡介

在本教學中，我們將示範如何使用 Aspose.Slides for Java 自訂 PowerPoint 簡報中圖表的圖例屬性。您可以修改圖例的位置、大小和其他屬性以滿足您的簡報需求。

## 先決條件

在開始之前，請確保您具備以下條件：

- 安裝了 Java API 的 Aspose.Slides。
- Java開發環境搭建。

## 步驟1：導入必要的類別：

```java
//為 Java 類別導入 Aspose.Slides
import com.aspose.slides.*;
```

## 步驟 2：指定文檔目錄的路徑：

```java
String dataDir = "Your Document Directory";
```

## 第三步：建立一個實例`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## 步驟 4：將投影片新增至簡報：

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## 步驟 5：在投影片中加入聚集長條圖：

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## 步驟 6. 設定圖例屬性：

- 設定圖例的 X 位置（相對於圖表寬度）：

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- 設定圖例的 Y 位置（相對於圖表高度）：

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- 設定圖例的寬度（相對於圖表寬度）：

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- 設定圖例的高度（相對於圖表高度）：

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## 步驟 7：將簡報儲存到磁碟：

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

就是這樣！您已使用 Aspose.Slides for Java 成功自訂了 PowerPoint 簡報中圖表的圖例屬性。

## 在 Java 幻燈片中設定圖例自訂選項的完整原始程式碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
try
{
	//取得投影片參考
	ISlide slide = presentation.getSlides().get_Item(0);
	//在投影片上加入聚集長條圖
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	//設定圖例屬性
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	//將簡報寫入磁碟
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## 結論

在本教學中，我們學習如何使用 Aspose.Slides for Java 自訂 PowerPoint 簡報中圖表的圖例屬性。您可以修改圖例的位置、大小和其他屬性，以建立具有視覺吸引力且資訊豐富的簡報。

## 常見問題解答

## 如何更改圖例的位置？

若要變更圖例的位置，請使用`setX`和`setY`圖例物件的方法。這些值是相對於圖表的寬度和高度指定的。

## 如何調整圖例的大小？

您可以使用以下命令調整圖例的大小`setWidth`和`setHeight`圖例物件的方法。這些值也與圖表的寬度和高度相關。

## 我可以自訂其他圖例屬性嗎？

是的，您可以自訂圖例的各種屬性，例如字體樣式、邊框、背景顏色等。瀏覽 Aspose.Slides 文件以取得進一步自訂圖例的詳細資訊。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
