---
title: Java 投影片中的圖表趨勢線
linktitle: Java 投影片中的圖表趨勢線
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 將各種趨勢線新增至 Java Slides。包含有效資料視覺化程式碼範例的逐步指南。
weight: 15
url: /zh-hant/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的圖表趨勢線


## Java 投影片中的圖表趨勢線簡介：逐步指南

在本綜合指南中，我們將探討如何使用 Aspose.Slides for Java 在 Java Slides 中建立圖表趨勢線。圖表趨勢線可以為您的簡報提供有價值的補充，有助於有效地視覺化和分析數據趨勢。我們將透過清晰的解釋和程式碼範例引導您完成整個過程。

## 先決條件

在我們深入建立圖表趨勢線之前，請確保您具備以下先決條件：

- Java開發環境
- Java 函式庫的 Aspose.Slides
- 您選擇的程式碼編輯器

## 第 1 步：開始

讓我們先設定必要的環境並建立一個新的簡報：

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
//建立空白簡報
Presentation pres = new Presentation();
```

我們已經初始化了演示文稿，現在準備添加聚集長條圖：

```java
//建立簇狀長條圖
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## 步驟 2：新增指數趨勢線

讓我們先為我們的圖表系列添加指數趨勢線：

```java
//為圖表系列 1 新增指數趨勢線
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## 第三步：新增線性趨勢線

接下來，我們將向圖表系列添加線性趨勢線：

```java
//為圖表系列 1 新增線性趨勢線
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## 第四步：新增對數趨勢線

現在，讓我們為不同的圖表系列添加對數趨勢線：

```java
//為圖表系列 2 新增對數趨勢線
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## 第五步：新增移動平均趨勢線

我們還可以加入一條移動平均趨勢線：

```java
//為圖表系列 2 新增移動平均趨勢線
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## 步驟 6：新增多項式趨勢線

增加多項式趨勢線：

```java
//為圖表系列 3 新增多項式趨勢線
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## 第7步：新增功率趨勢線

最後，我們加入一條功率趨勢線：

```java
//為圖表系列 3 增加功率趨勢線
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## 步驟 8：儲存簡報

現在我們已經在圖表中添加了各種趨勢線，讓我們保存簡報：

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

恭喜！您已使用 Aspose.Slides for Java 在 Java Slides 中成功建立了具有不同類型趨勢線的簡報。

## Java 投影片中圖表趨勢線的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
//建立空白簡報
Presentation pres = new Presentation();
//建立簇狀長條圖
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
//為圖表系列 1 新增潛在趨勢線
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
//為圖表系列 1 新增線性趨勢線
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
//為圖表系列 2 新增對數趨勢線
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
//為圖表系列 2 新增移動平均線趨勢線
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
//為圖表系列 3 新增多項式趨勢線
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
//為圖表系列 3 增加功率趨勢線
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
//儲存簡報
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 函式庫為 Java Slides 中的圖表新增不同類型的趨勢線。無論您是進行數據分析還是創建資訊豐富的演示文稿，可視化趨勢的能力都是一個強大的工具。

## 常見問題解答

### 如何更改 Aspose.Slides for Java 中趨勢線的顏色？

若要變更趨勢線的顏色，您可以使用`getSolidFillColor().setColor(Color)`方法，如添加線性趨勢線的範例所示。

### 我可以將多條趨勢線添加到單一圖表系列中嗎？

是的，您可以將多條趨勢線新增到單一圖表系列中。只需撥打`getTrendLines().add()`您要新增的每條趨勢線的方法。

### 如何從 Aspose.Slides for Java 的圖表中刪除趨勢線？

若要從圖表中刪除趨勢線，您可以使用`removeAt(int index)`方法，指定要刪除的趨勢線的索引。

### 是否可以自訂趨勢線方程式顯示？

是的，您可以使用以下命令自訂趨勢線方程式顯示`setDisplayEquation(boolean)`方法，如範例所示。

### 如何存取 Aspose.Slides for Java 的更多資源和範例？

您可以在以下位置存取 Aspose.Slides for Java 的其他資源、文件和範例：[阿斯普斯網站](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
