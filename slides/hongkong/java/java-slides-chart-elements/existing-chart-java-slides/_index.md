---
"description": "使用 Aspose.Slides for Java 增強您的 PowerPoint 簡報。學習以程式方式修改現有圖表。帶有圖表自訂原始程式碼的分步指南。"
"linktitle": "Java Slides 中的現有圖表"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java Slides 中的現有圖表"
"url": "/zh-hant/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides 中的現有圖表


## 使用 Aspose.Slides for Java 介紹 Java Slides 中的現有圖表

在本教學中，我們將示範如何使用 Aspose.Slides for Java 修改 PowerPoint 簡報中的現有圖表。我們將介紹更改圖表資料、類別名稱、系列名稱以及在圖表中新增系列的步驟。確保您的專案中已設定了 Aspose.Slides for Java。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

1. 您的專案中包含 Java 程式庫的 Aspose.Slides。
2. 現有的 PowerPoint 簡報中包含要修改的圖表。
3. Java開發環境搭建。

## 步驟 1：載入簡報

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 實例化代表 PPTX 檔案的 Presentation 類
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## 第 2 步：存取投影片和圖表

```java
// 存取第一張投影片
ISlide sld = pres.getSlides().get_Item(0);

// 存取投影片上的圖表
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 步驟3：更改圖表資料和類別名稱

```java
// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;

// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 更改圖表類別名稱
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## 步驟4：更新第一個圖表系列

```java
// 以第一個圖表系列為例
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 更新系列名稱
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// 更新系列數據
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## 步驟5：更新第二個圖表系列

```java
// 取第二個圖表系列
series = chart.getChartData().getSeries().get_Item(1);

// 更新系列名稱
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// 更新系列數據
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## 步驟 6：在圖表中新增系列

```java
// 新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// 以第三組圖表為例
series = chart.getChartData().getSeries().get_Item(2);

// 填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## 步驟 7：更改圖表類型

```java
// 將圖表類型變更為簇狀圓柱圖
chart.setType(ChartType.ClusteredCylinder);
```

## 步驟 8：儲存修改後的簡報

```java
// 儲存包含修改後的圖表的簡報
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

恭喜！您已成功使用 Aspose.Slides for Java 修改了 PowerPoint 簡報中的現有圖表。現在您可以使用此程式碼以程式設計方式自訂 PowerPoint 簡報中的圖表。

## Java 投影片中現有圖表的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 實例化代表 PPTX 檔案的 Presentation 類別// 實例化代表 PPTX 檔案的 Presentation 類別
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// 訪問第一個 slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// 新增帶有預設資料的圖表
IChart chart = (IChart) sld.getShapes().get_Item(0);
// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 更改圖表類別名稱
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// 採取第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 正在更新系列數據
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// 修改系列名稱
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Take Second 圖表系列
series = chart.getChartData().getSeries().get_Item(1);
// 正在更新系列數據
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// 修改系列名稱
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// 現在，新增一個新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// 拿下第三張圖表系列
series = chart.getChartData().getSeries().get_Item(2);
// 現在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// 將簡報與圖表一起保存
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## 結論

在本綜合教學中，我們學習如何使用 Aspose.Slides for Java 修改 PowerPoint 簡報中的現有圖表。透過遵循逐步指南並利用原始程式碼範例，您可以輕鬆自訂和更新圖表以滿足您的特定要求。以下是我們所討論內容的回顧：

## 常見問題解答

### 我該如何更改圖表類型？

您可以使用 `chart.setType(ChartType.ChartTypeHere)` 方法。代替 `ChartTypeHere` 使用所需的圖表類型，例如 `ChartType.ClusteredCylinder` 在我們的例子中。

### 我可以為系列中添加更多數據點嗎？

是的，您可以使用 `series.getDataPoints().addDataPointForBarSeries(cell)` 方法。確保提供適當的單元格資料。

### 如何更新類別名稱？

您可以使用以下方式更新類別名稱 `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` 設定新的類別名稱。

### 如何修改系列名稱？

若要修改系列名稱，請使用 `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` 設定新的系列名稱。

### 有沒有辦法從圖表中刪除某個系列？

是的，你可以使用 `chart.getChartData().getSeries().removeAt(index)` 方法，其中 `index` 是您要刪除的系列的索引。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}