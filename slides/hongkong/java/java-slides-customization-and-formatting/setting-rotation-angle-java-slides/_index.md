---
"description": "使用 Aspose.Slides for Java 優化您的 Java 投影片。學習設定文字元素的旋轉角度。帶有原始程式碼的分步指南。"
"linktitle": "在 Java Slides 中設定旋轉角度"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中設定旋轉角度"
"url": "/zh-hant/java/customization-and-formatting/setting-rotation-angle-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中設定旋轉角度


## Java Slides 中設定旋轉角度的介紹

在本教學中，我們將探討如何使用 Aspose.Slides for Java 函式庫設定圖表軸標題中文字的旋轉角度。透過調整旋轉角度，您可以自訂圖表軸標題的外觀，以更好地滿足您的簡報需求。

## 先決條件

在開始之前，請確保您已經在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 Aspose 網站下載該程式庫並按照其文件中提供的安裝說明進行操作。

## 步驟 1：建立簡報

首先，您需要建立一個新的簡報或載入一個現有的簡報。在此範例中，我們將建立一個新的簡報：

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 步驟 2：為投影片新增圖表

接下來，我們將向投影片新增圖表。在此範例中，我們新增了一個聚集長條圖：

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## 步驟3：設定軸標題的旋轉角度

要設定軸標題的旋轉角度，您需要存取圖表的垂直軸標題並調整其旋轉角度。您可以按照以下步驟操作：

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

在此程式碼片段中，我們將旋轉角度設為 90 度，這將垂直旋轉文字。您可以將角度調整到所需的值。

## 步驟 4：儲存簡報

最後，將簡報儲存為 PowerPoint 檔案：

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Java Slides 中設定旋轉角度的完整原始碼

```java
// 文檔目錄的路徑。
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

在本教學中，您學習如何使用 Aspose.Slides for Java 設定圖表軸標題中文字的旋轉角度。此功能可讓您自訂圖表的外觀以建立具有視覺吸引力的簡報。嘗試不同的旋轉角度來實現圖表所需的外觀。

## 常見問題解答

### 如何更改投影片中其他文字元素的旋轉角度？

您可以使用類似的方法來變更其他文字元素（例如形狀或文字方塊）的旋轉角度。存取元素的文字格式並根據需要設定旋轉角度。

### 我也可以旋轉水平軸標題中的文字嗎？

是的，您可以透過調整旋轉角度來旋轉橫軸標題中的文字。只需將旋轉角度設定為所需的值，例如垂直文字為 90 度，水平文字為 0 度。

### 圖表標題還有哪些其他格式選項可用？

Aspose.Slides for Java 為圖表標題提供了各種格式選項，包括字體樣式、顏色和對齊方式。您可以瀏覽文件以取得有關自訂圖表標題的更多詳細資訊。

### 是否可以為圖表軸標題中的文字旋轉製作動畫？

是的，您可以使用 Aspose.Slides for Java 為文字元素（包括圖表軸標題）新增動畫效果。有關向簡報新增動畫的信息，請參閱文件。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}