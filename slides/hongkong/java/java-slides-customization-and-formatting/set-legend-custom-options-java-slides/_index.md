---
"description": "了解如何使用 Aspose.Slides for Java 在 Java Slides 中設定自訂圖例選項。自訂 PowerPoint 圖表中的圖例位置和大小。"
"linktitle": "在 Java Slides 中設定圖例自訂選項"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中設定圖例自訂選項"
"url": "/zh-hant/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中設定圖例自訂選項


## Java Slides 中設定圖例自訂選項的介紹

在本教學中，我們將示範如何使用 Aspose.Slides for Java 自訂 PowerPoint 簡報中圖表的圖例屬性。您可以修改圖例的位置、大小和其他屬性以滿足您的簡報需求。

## 先決條件

在開始之前，請確保您已具備以下條件：

- 已安裝 Aspose.Slides for Java API。
- Java開發環境搭建。

## 步驟1：導入必要的類別：

```java
// 導入 Aspose.Slides 用於 Java 類
import com.aspose.slides.*;
```

## 第 2 步：指定文檔目錄的路徑：

```java
String dataDir = "Your Document Directory";
```

## 步驟 3：創建 `Presentation` 班級：

```java
Presentation presentation = new Presentation();
```

## 步驟 4：為簡報新增投影片：

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## 步驟 5：在投影片中新增簇狀長條圖：

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## 步驟6.設定圖例屬性：

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

就是這樣！您已成功使用 Aspose.Slides for Java 自訂 PowerPoint 簡報中圖表的圖例屬性。

## Java 投影片中設定圖例自訂選項的完整原始程式碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立 Presentation 類別的實例
Presentation presentation = new Presentation();
try
{
	// 取得投影片的參考
	ISlide slide = presentation.getSlides().get_Item(0);
	// 在投影片上新增簇狀長條圖
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// 設定圖例屬性
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// 將簡報寫入磁碟
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

## 我要如何改變圖例的位置？

若要變更圖例的位置，請使用 `setX` 和 `setY` 圖例物件的方法。這些值是相對於圖表的寬度和高度指定的。

## 我要如何調整圖例的大小？

您可以使用 `setWidth` 和 `setHeight` 圖例物件的方法。這些值也與圖表的寬度和高度有關。

## 我可以自訂其他圖例屬性嗎？

是的，您可以自訂圖例的各種屬性，例如字體樣式、邊框、背景顏色等。探索 Aspose.Slides 文件以取得進一步自訂圖例的詳細資訊。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}