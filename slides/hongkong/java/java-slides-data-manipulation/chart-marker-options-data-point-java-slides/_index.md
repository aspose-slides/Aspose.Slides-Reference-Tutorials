---
title: Java 投影片中資料點的圖表標記選項
linktitle: Java 投影片中資料點的圖表標記選項
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用自訂圖表標記選項優化您的 Java 投影片。學習使用 Aspose.Slides for Java 直覺地增強資料點。探索逐步指南和常見問題。
type: docs
weight: 14
url: /zh-hant/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Java 投影片中資料點上的圖表標記選項簡介

在創建有影響力的簡報時，自訂和操作資料點上的圖表標記的能力可以發揮重要作用。透過 Aspose.Slides for Java，您可以將圖表轉換為動態且具有視覺吸引力的元素。

## 先決條件

在我們深入編碼部分之前，請確保您具備以下先決條件：

- Java開發環境
- Java 函式庫的 Aspose.Slides
- Java 整合開發環境 (IDE)
- 示範文件範例（例如“Test.pptx”）

## 第 1 步：設定環境

首先，請確保您已安裝並準備好必要的工具。在 IDE 中建立一個 Java 專案並匯入 Aspose.Slides for Java 函式庫。

## 第 2 步：載入簡報

首先，載入範例簡報文件。在提供的程式碼中，我們假設文件名稱為「Test.pptx」。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## 第 3 步：建立圖表

現在，讓我們在簡報中建立一個圖表。在此範例中，我們將使用標記的折線圖。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## 第 4 步：使用圖表數據

要操作圖表數據，我們需要存取圖表數據工作簿並準備數據系列。我們將清除預設係列並新增自訂資料。

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## 第 5 步：新增自訂標記

接下來是令人興奮的部分 - 自訂資料點上的標記。在此範例中，我們將使用圖像作為標記。

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//向資料點新增自訂標記
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

//對其他數據點重複此操作
//…

//更改圖表系列標記大小
series.getMarker().setSize(15);
```

## 第 6 步：儲存簡報

自訂圖表標記後，儲存簡報以查看實際變更。

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Java 投影片中資料點上的圖表標記選項的完整原始碼

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//建立預設圖表
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//取得預設圖表資料工作表索引
int defaultWorksheetIndex = 0;
//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//刪除示範系列
chart.getChartData().getSeries().clear();
//新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//設定圖片
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//設定圖片
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//取得第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//在那裡新增點 (1:3)。
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//更改圖表系列標記
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## 結論

透過 Aspose.Slides for Java，您可以透過自訂資料點上的圖表標記來提升您的簡報。這使您可以創建視覺上令人驚嘆且內容豐富的幻燈片來吸引觀眾。

## 常見問題解答

### 如何更改資料點的標記大小？

若要變更資料點的標記大小，請使用`series.getMarker().setSize()`方法並提供所需的大小作為參數。

### 我可以使用圖像作為自訂標記嗎？

是的，您可以使用圖像作為資料點的自訂標記。將填充類型設為`FillType.Picture`並提供您要使用的圖像。

### Aspose.Slides for Java適合建立動態圖表嗎？

絕對地！ Aspose.Slides for Java 提供了在簡報中建立動態和互動式圖表的廣泛功能。

### 我可以使用 Aspose.Slides 自訂圖表的其他方面嗎？

是的，您可以使用 Aspose.Slides for Java 自訂圖表的各個方面，包括標題、軸、資料標籤等。

### 在哪裡可以存取 Aspose.Slides for Java 文件和下載？

您可以在以下位置找到文件：[這裡](https://reference.aspose.com/slides/java/)並下載該庫[這裡](https://releases.aspose.com/slides/java/).