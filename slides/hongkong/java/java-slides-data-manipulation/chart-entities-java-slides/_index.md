---
title: Java 投影片中的圖表實體
linktitle: Java 投影片中的圖表實體
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 學習使用 Aspose.Slides 建立和自訂 Java Slides 圖表。使用強大的圖表實體增強您的簡報。
weight: 13
url: /zh-hant/java/data-manipulation/chart-entities-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 投影片中的圖表實體簡介

圖表是在簡報中可視化資料的強大工具。無論您是在建立業務報告、學術簡報或任何其他形式的內容，圖表都有助於有效地傳達訊息。 Aspose.Slides for Java 提供了處理圖表的強大功能，使其成為 Java 開發人員的首選。

## 先決條件

在我們深入了解圖表實體的世界之前，請確保您具備以下先決條件：

- 安裝了 Java 開發工具包 (JDK)
- Aspose.Slides for Java 程式庫下載並新增到您的專案中
- Java程式設計基礎知識

現在，讓我們開始使用 Aspose.Slides for Java 建立和自訂圖表。

## 第 1 步：建立簡報

第一步是建立一個新演示文稿，您將在其中添加圖表。以下是建立簡報的程式碼片段：

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：新增圖表

準備好簡報後，就可以新增圖表了。在此範例中，我們將新增一個帶有標記的簡單折線圖。您可以這樣做：

```java
//存取第一張投影片
ISlide slide = pres.getSlides().get_Item(0);

//新增範例圖表
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 第 3 步：自訂圖表標題

定義明確的圖表應該有一個標題。讓我們為圖表設定一個標題：

```java
//設定圖表標題
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## 第四步：設定網格線格式

您可以設定圖表的主要和次要網格線的格式。讓我們為垂直軸網格線設定一些格式：

```java
//設定數值軸的主要網格線格式
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

//設定數值軸的次網格線格式
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 第5步：自訂值軸

您可以控制數值軸的數字格式、最大值和最小值。自訂方法如下：

```java
//設定值軸號格式
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

//設定圖表最大值、最小值
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## 第 6 步：新增值軸標題

為了使圖表包含更多信息，您可以向值軸添加標題：

```java
//設定值軸標題
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## 第7步：格式化類別軸

類別軸通常表示資料類別，也可以自訂：

```java
//設定類別軸的主要網格線格式
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//設定類別軸的次網格線格式
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 第 8 步：新增圖例

圖例有助於解釋圖表中的資料系列。讓我們自訂圖例：

```java
//設定圖例文字屬性
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

//設定顯示圖表圖例而不重疊圖表
chart.getLegend().setOverlay(true);
```

## 第 9 步：儲存簡報

最後，用圖表儲存您的簡報：

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Java 投影片中圖表實體的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
//實例化演示 // 實例化演示
Presentation pres = new Presentation();
try
{
	//存取第一張投影片
	ISlide slide = pres.getSlides().get_Item(0);
	//新增範例圖表
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	//設定圖表標題
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	//設定數值軸的主要網格線格式
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	//設定數值軸的次網格線格式
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//設定值軸號格式
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	//設定圖表最大值、最小值
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	//設定值軸文字屬性
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	//設定值軸標題
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	//設定值軸線格式：現已廢棄
	//Chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	//設定類別軸的主要網格線格式
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//設定類別軸的次網格線格式
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	//設定類別軸文字屬性
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	//設定類別標題
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	//設定類別軸標籤位置
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	//設定類別軸標籤旋轉角度
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	//設定圖例文字屬性
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	//設定顯示圖表圖例而不重疊圖表
	chart.getLegend().setOverlay(true);
	//在輔助值軸上繪製第一個系列
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	//設定圖表後牆顏色
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//設定繪圖區域顏色
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	//儲存簡報
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本文中，我們使用 Aspose.Slides for Java 探索了 Java Slides 中圖表實體的世界。您已經學習如何建立、自訂和操作圖表來增強您的簡報。圖表不僅使您的數據具有視覺吸引力，還可以幫助您的受眾更輕鬆地理解複雜的資訊。

## 常見問題解答

### 如何更改圖表類型？

若要變更圖表類型，請使用`chart.setType()`方法並指定所需的圖表類型。

### 我可以將多個數據系列添加到圖表中嗎？

是的，您可以使用以下命令將多個資料系列新增至圖表中`chart.getChartData().getSeries().addSeries()`方法。

### 如何自訂圖表顏色？

您可以透過設定各種圖表元素（例如網格線、標題和圖例）的填滿格式來自訂圖表顏色。

### 我可以建立 3D 圖表嗎？

是的，Aspose.Slides for Java 支援建立 3D 圖表。您可以設定`ChartType`到 3D 圖表類型來建立一個。

### Aspose.Slides for Java 與最新的 Java 版本相容嗎？

是的，Aspose.Slides for Java 會定期更新以支援最新的 Java 版本，並提供跨各種 Java 環境的兼容性。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
