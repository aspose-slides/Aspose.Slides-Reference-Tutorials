---
title: Java 投影片中的現有圖表
linktitle: Java 投影片中的現有圖表
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides for Java 增強您的 PowerPoint 簡報。學習以程式方式修改現有圖表。帶有圖表自訂原始程式碼的分步指南。
type: docs
weight: 12
url: /zh-hant/java/chart-elements/existing-chart-java-slides/
---

## 使用 Aspose.Slides for Java 介紹 Java 投影片中的現有圖表

在本教學中，我們將示範如何使用 Aspose.Slides for Java 修改 PowerPoint 簡報中的現有圖表。我們將完成更改圖表資料、類別名稱、系列名稱以及向圖表新增系列的步驟。確保您的專案中設定了 Aspose.Slides for Java。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

1. Aspose.Slides for Java 程式庫包含在您的專案中。
2. 包含要修改的圖表的現有 PowerPoint 簡報。
3. Java開發環境搭建。

## 第 1 步：載入簡報

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";

//實例化表示 PPTX 檔案的簡報類
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## 第 2 步：存取投影片和圖表

```java
//存取第一張投影片
ISlide sld = pres.getSlides().get_Item(0);

//存取投影片上的圖表
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 步驟 3：更改圖表資料和類別名稱

```java
//設定圖表資料表的索引
int defaultWorksheetIndex = 0;

//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//更改圖表類別名稱
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## 第 4 步：更新第一個圖表系列

```java
//取得第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//更新系列名稱
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

//更新系列數據
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## 第 5 步：更新第二個圖表系列

```java
//採取第二個圖表系列
series = chart.getChartData().getSeries().get_Item(1);

//更新系列名稱
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

//更新系列數據
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## 第 6 步：在圖表中新增系列

```java
//新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

//採取第三個圖表系列
series = chart.getChartData().getSeries().get_Item(2);

//填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## 第 7 步：更改圖表類型

```java
//將圖表類型變更為簇狀長條圖
chart.setType(ChartType.ClusteredCylinder);
```

## 步驟 8：儲存修改後的簡報

```java
//使用修改後的圖表儲存演示文稿
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

恭喜！您已使用 Aspose.Slides for Java 成功修改了 PowerPoint 簡報中的現有圖表。現在，您可以使用此程式碼以程式設計方式自訂 PowerPoint 簡報中的圖表。

## Java 投影片中現有圖表的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//實例化表示 PPTX 檔案的簡報類別//實例化表示 PPTX 檔案的簡報類
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
//存取第一張投影片標記
ISlide sld = pres.getSlides().get_Item(0);
//新增帶有預設資料的圖表
IChart chart = (IChart) sld.getShapes().get_Item(0);
//設定圖表資料表索引
int defaultWorksheetIndex = 0;
//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//更改圖表類別名稱
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
//取得第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//現已更新系列數據
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");//修改系列名稱
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
//採取第二個圖表系列
series = chart.getChartData().getSeries().get_Item(1);
//現已更新系列數據
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");//修改系列名稱
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
//現在，新增一個新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
//採取第三個圖表系列
series = chart.getChartData().getSeries().get_Item(2);
//現在正在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
//儲存帶有圖表的簡報
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## 結論

在這個綜合教學中，我們學習如何使用 Aspose.Slides for Java 修改 PowerPoint 簡報中的現有圖表。透過遵循逐步指南並利用原始程式碼範例，您可以輕鬆自訂和更新圖表以滿足您的特定要求。以下是我們所涵蓋內容的回顧：

## 常見問題解答

### 如何更改圖表類型？

您可以使用以下命令更改圖表類型`chart.setType(ChartType.ChartTypeHere)`方法。代替`ChartTypeHere`與所需的圖表類型，例如`ChartType.ClusteredCylinder`在我們的例子中。

### 我可以為系列添加更多數據點嗎？

是的，您可以使用以下命令為系列新增更多資料點`series.getDataPoints().addDataPointForBarSeries(cell)`方法。確保提供適當的單元格資料。

### 如何更新類別名稱？

您可以使用以下方法更新類別名稱`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`設定新的類別名稱。

### 如何修改系列名稱？

若要修改系列名稱，請使用`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)`設定新系列名稱。

### 有沒有辦法從圖表中刪除系列？

是的，您可以使用以下命令從圖表中刪除系列：`chart.getChartData().getSeries().removeAt(index)`方法，其中`index`是您要刪除的系列的索引。