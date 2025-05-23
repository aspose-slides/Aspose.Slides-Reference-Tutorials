---
"description": "了解如何使用 Aspose.Slides for Java 取得 Java Slides 中圖表資料標籤的實際位置。帶有原始程式碼的分步指南。"
"linktitle": "取得 Java 投影片中圖表資料標籤的實際位置"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "取得 Java 投影片中圖表資料標籤的實際位置"
"url": "/zh-hant/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 取得 Java 投影片中圖表資料標籤的實際位置


## Java Slides 中取得圖表資料標籤實際位置的介紹

在本教學中，您將學習如何使用 Aspose.Slides for Java 擷取圖表資料標籤的實際位置。我們將建立一個 Java 程序，產生帶有圖表的 PowerPoint 演示文稿，自訂資料標籤，然後新增表示這些資料標籤位置的形狀。

## 先決條件

在開始之前，請確保您的 Java 專案中已設定了 Aspose.Slides for Java 程式庫。

## 步驟 1：建立 PowerPoint 簡報

首先，讓我們建立一個新的 PowerPoint 簡報並在其中新增圖表。我們將在本教學的後面自訂圖表的資料標籤。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## 第 2 步：自訂資料標籤
現在，讓我們自訂圖表系列的資料標籤。我們將設定它們的位置並顯示其值。

```java
try {
    // ……（上一個代碼）
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ……（剩餘代碼）
} finally {
    if (pres != null) pres.dispose();
}
```

## 步驟3：取得資料標籤的實際位置
在此步驟中，我們將遍歷圖表系列的資料點並檢索值大於 4 的資料標籤的實際位置。然後我們將添加省略號來表示這些位置。

```java
try {
    // ……（上一個代碼）
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ……（剩餘代碼）
} finally {
    if (pres != null) pres.dispose();
}
```

## 步驟 4：儲存簡報
最後，將產生的簡報儲存到文件中。

```java
try {
    // ……（上一個代碼）
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 取得 Java 投影片中圖表資料標籤實際位置的完整原始程式碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//待辦事項
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 檢索 Java Slides 中圖表資料標籤的實際位置。現在，您可以利用這些知識，透過自訂資料標籤及其位置的視覺化表示來增強您的 PowerPoint 簡報。

## 常見問題解答

### 如何自訂圖表中的資料標籤？

若要自訂圖表中的資料標籤，您可以使用 `setDefaultDataLabelFormat` 圖表系列上的方法並設定位置和可見性等屬性。例如：
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### 如何新增形狀來表示資料標籤位置？

您可以遍歷圖表系列的數據點並使用 `getActualX`， `getActualY`， `getActualWidth`， 和 `getActualHeight` 資料標籤的方法來取得其位置。然後，您可以使用 `addAutoShape` 方法。以下是一個例子：
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### 如何保存產生的簡報？

您可以使用 `save` 方法。提供所需的文件路徑和 `SaveFormat` 作為參數。例如：
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}