---
title: 在 Java 投影片中設定旋轉角度
linktitle: 在 Java 投影片中設定旋轉角度
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides for Java 優化您的 Java 投影片。學習設定文字元素的旋轉角度。帶有原始程式碼的分步指南。
weight: 17
url: /zh-hant/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中設定旋轉角度


## Java 投影片設定旋轉角度簡介

在本教程中，我們將探索如何使用 Aspose.Slides for Java 庫設定圖表軸標題中文字的旋轉角度。透過調整旋轉角度，您可以自訂圖表軸標題的外觀，以更好地滿足您的簡報需求。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 Aspose 網站下載該程式庫並按照其文件中提供的安裝說明進行操作。

## 第 1 步：建立簡報

首先，您需要建立一個新的簡報或載入現有的簡報。在此範例中，我們將建立一個新簡報：

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：將圖表新增至投影片

接下來，我們將向投影片新增圖表。在此範例中，我們新增一個聚集長條圖：

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## 步驟 3：設定軸標題的旋轉角度

要設定軸標題的旋轉角度，您需要存取圖表的垂直軸標題並調整其旋轉角度。您可以這樣做：

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

在此程式碼片段中，我們將旋轉角度設為 90 度，這將垂直旋轉文字。您可以將角度調整為您想要的值。

## 第 4 步：儲存簡報

最後，將簡報儲存到 PowerPoint 檔案：

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## 在Java幻燈片中設定旋轉角度的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 設定圖表軸標題中文字的旋轉角度。此功能可讓您自訂圖表的外觀，以建立具有視覺吸引力的簡報。嘗試不同的旋轉角度以獲得所需的圖表外觀。

## 常見問題解答

### 如何更改投影片中其他文字元素的旋轉角度？

您可以使用類似的方法來變更其他文字元素（例如形狀或文字方塊）的旋轉角度。存取元素的文字格式並根據需要設定旋轉角度。

### 我也可以旋轉橫軸標題中的文字嗎？

是的，您可以透過調整旋轉角度來旋轉橫軸標題中的文字。只需將旋轉角度設定為所需的值，例如垂直文字為 90 度，水平文字為 0 度。

### 還有哪些其他格式選項可用於圖表標題？

Aspose.Slides for Java 為圖表標題提供了各種格式選項，包括字體樣式、顏色和對齊方式。您可以瀏覽文件以取得有關自訂圖表標題的更多詳細資訊。

### 是否可以為圖表軸標題中的文字旋轉設定動畫？

是的，您可以使用 Aspose.Slides for Java 將動畫效果新增至文字元素，包括圖表軸標題。有關向簡報新增動畫的信息，請參閱文件。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
