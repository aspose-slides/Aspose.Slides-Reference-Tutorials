---
"description": "了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立令人驚嘆的圓餅圖。為 Java 開發人員提供帶有原始程式碼的分步指南。"
"linktitle": "Java 投影片中的圓餅圖"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的圓餅圖"
"url": "/zh-hant/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的圓餅圖


## 使用 Aspose.Slides 在 Java Slides 中建立圓餅圖的簡介

在本教學中，我們將示範如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立圓餅圖。我們將為您提供逐步說明和 Java 原始程式碼來幫助您入門。本指南假設您已經使用 Aspose.Slides for Java 設定了開發環境。

## 先決條件

在開始之前，請確保您已在專案中安裝並配置了 Aspose.Slides for Java 程式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).

## 步驟 1：導入所需庫

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

確保從 Aspose.Slides 庫導入必要的類別。

## 步驟 2：初始化簡報

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 實例化代表 PPTX 檔案的 Presentation 類
Presentation presentation = new Presentation();
```

建立一個新的 Presentation 物件來代表您的 PowerPoint 檔案。代替 `"Your Document Directory"` 與您想要儲存簡報的實際路徑。

## 步驟 3：新增投影片

```java
// 存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
```

取得要新增圓餅圖的簡報的第一張投影片。

## 步驟 4：新增圓餅圖

```java
// 新增具有預設資料的圓餅圖
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

將圓餅圖新增至投影片的指定位置和大小。

## 步驟5：設定圖表標題

```java
// 設定圖表標題
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

為圓餅圖設定標題。您可以根據需要自訂標題。

## 步驟6：自訂圖表數據

```java
// 設定第一個系列以顯示值
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;

// 取得圖表資料工作表
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// 刪除預設產生的系列和類別
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 新增類別
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// 新增系列
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// 填充系列數據
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

透過新增類別和系列並設定它們的值來自訂圖表資料。在這個例子中，我們有三個類別和一個系列以及相應的數據點。

## 步驟 7：自訂餅圖磁區

```java
// 設定扇區顏色
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// 自訂每個區域的外觀
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// 自訂扇區邊界
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// 以類似方式客製其他部門
```

自訂餅圖中每個磁區的外觀。您可以變更顏色、邊框樣式和其他視覺屬性。

## 步驟 8：自訂資料標籤

```java
// 自訂資料標籤
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// 以類似的方式自訂其他資料點的資料標籤
```

為圓餅圖中的每個資料點自訂資料標籤。您可以控制圖表上顯示哪些值。

## 步驟 9：顯示指引線

```java
// 顯示圖表的引線
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

啟用引線將資料標籤與其對應的磁區連接起來。

## 步驟10：設定餅圖旋轉角度

```java
// 設定圓餅圖扇區的旋轉角度
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

設定餅圖扇區的旋轉角度。在這個例子中，我們將其設定為 180 度。

## 步驟 11：儲存簡報

```java
// 使用圓餅圖儲存簡報
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

將圓餅圖簡報儲存到指定目錄。

## Java 投影片中餅圖的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 實例化代表 PPTX 檔案的 Presentation 類
Presentation presentation = new Presentation();
// 存取第一張投影片
ISlide slides = presentation.getSlides().get_Item(0);
// 新增帶有預設資料的圖表
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// 設定圖表標題
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// 將第一個系列設定為顯示值
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 刪除預設產生的系列和類別
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// 新增類別
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// 新增系列
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// 現在填充系列數據
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// 在新版本中不起作用
// 新增點並設定扇區顏色
// 系列.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// 設定扇區邊界
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// 設定扇區邊界
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// 設定扇區邊界
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// 為新系列的每個類別建立自訂標籤
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.設定顯示類別名稱(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// 顯示圖表的引線
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// 設定圓餅圖扇區的旋轉角度
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// 將簡報與圖表一起保存
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## 結論

您已成功使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立圓餅圖。您可以根據您的特定要求自訂圖表的外觀和資料標籤。本教學提供了一個基本的範例，您可以根據需要進一步增強和自訂您的圖表。

## 常見問題解答

### 如何改變圓餅圖中各個磁區的顏色？

若要變更圓餅圖中各個磁區的顏色，您可以自訂每個資料點的填滿顏色。在提供的程式碼範例中，我們示範如何使用 `getSolidFillColor().setColor()` 方法。您可以修改顏色值以獲得所需的外觀。

### 我可以為餅圖添加更多類別和資料系列嗎？

是的，您可以為圓餅圖新增其他類別和資料系列。為此，您可以使用 `getChartData().getCategories().add()` 和 `getChartData().getSeries().add()` 方法，如範例所示。只需為新類別和系列提供適當的數據和標籤即可擴展您的圖表。

### 如何自訂資料標籤的外觀？

您可以使用 `getDataLabelFormat()` 每個數據點的標籤上的方法。在範例中，我們示範如何使用 `getDataLabelFormat().setShowValue(true)`。您可以透過控制顯示的值、顯示圖例鍵以及調整其他格式選項來進一步自訂資料標籤。

### 我可以更改餅圖的標題嗎？

是的，您可以更改餅圖的標題。在提供的程式碼中，我們使用設定圖表標題 `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`。您可以替換 `"Sample Title"` 使用您想要的標題文字。

### 如何儲存產生的圓餅圖簡報？

若要儲存圓餅圖演示文稿，請使用 `presentation.save()` 方法。提供所需的文件路徑和名稱以及您想要儲存簡報的格式。例如：
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

確保指定正確的檔案路徑和格式。

### 我可以使用 Aspose.Slides for Java 建立其他類型的圖表嗎？

是的，Aspose.Slides for Java 支援各種圖表類型，包括長條圖、折線圖等。您可以透過更改 `ChartType` 新增圖表時。有關建立不同類型圖表的更多詳細信息，請參閱 Aspose.Slides 文件。

### 如何找到有關使用 Aspose.Slides for Java 的更多資訊和範例？

欲了解更多資訊、詳細文件和其他範例，您可以訪問 [Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/)。它提供全面的資源來幫助您有效地使用圖書館。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}