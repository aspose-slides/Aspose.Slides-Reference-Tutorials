---
date: '2026-08-16'
description: 了解如何在 Java 中使用 Aspose.Slides 添加環形圖。本分步指南涵蓋 Maven 依賴設定、圖表配置、顏色、標籤以及 PPTX
  的儲存。
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: 如何在 Java 中使用 Aspose.Slides 添加環形圖。請依照本指南設定 Maven、客製化顏色、標籤並產生 PPTX 檔案。
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: 如何在 Java 中使用 Aspose.Slides 添加環形圖
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: 如何在 Java 中使用 Aspose.Slides 添加環形圖
url: /zh-hant/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Java 中使用 Aspose.Slides 添加環形圖

## 介紹

以程式方式建立 **環形圖** 可以將原始數字轉換為引人注目的視覺效果，立即傳遞故事。於 Java 中，**Aspose.Slides** 讓此過程變得簡單，讓您在不開啟 PowerPoint 的情況下產生可直接使用的簡報圖表。在本教學中，您將一步步學習 **如何在 PPTX 檔案中加入環形圖**——從設定 Maven Aspose Slides 相依性、客製化系列、類別、顏色與標籤，最後儲存簡報。

完成本指南後，您將能將動態環形圖嵌入任何 PPTX 檔案，適用於報告、儀表板或自動化簡報。

### 快速解答
- **使用的函式庫？** Aspose.Slides for Java  
- **主要任務？** 在 PPTX 檔案中加入環形圖  
- **如何加入函式庫？** 使用 Maven Aspose Slides 相依性（或 Gradle）  
- **最低 Java 版本？** JDK 16 或以上  
- **可以自訂顏色與標籤嗎？** 可以，API 提供完整的格式控制  

## 什麼是環形圖以及為何使用它？

環形圖是帶有空心中心的餅圖變體，允許以同心環方式顯示多個資料系列。**它能在多個類別間視覺化整體與部分的關係，同時保留中心空間供額外資訊使用。** 這使其非常適合比較不同區域在多個季度的銷售、部門間的預算分配，或任何需要呈現階層比例資料的情境。

## 為何使用 Aspose.Slides for Java？

您可以在未安裝 Microsoft Office 的情況下加入環形圖，且此函式庫支援 **超過 50 種以上的輸入與輸出格式**，同時處理超過 500 張投影片的簡報。Aspose.Slides 提供 **最高 3 倍的渲染速度**，相較於在相同硬體上使用原生 Office 自動化，且可在 Windows、Linux 與 macOS 上執行。這些具體的效益意味著您能在無頭伺服器上產生大型簡報，且效能可預測。

## 前置條件

- **必要函式庫**  
  - Aspose.Slides for Java 25.4 或更新版本（提供加入環形圖的功能）。

- **環境**  
  - 已在機器上安裝 JDK 16 或以上。  
  - 如 IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE。

- **知識**  
  - 基本的 Java 語法與物件導向概念。  
  - 熟悉 Maven 或 Gradle 以管理相依性。

## Maven Aspose Slides 相依性

在 `pom.xml` 中加入以下 Maven 相依性。這是您需要的 **Maven Aspose Slides 相依性**，可將函式庫匯入專案。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

如果您偏好 Gradle，請使用下方等效的程式碼片段。

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

您也可以直接從官方發行頁面下載 JAR：  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### 取得授權

要移除評估浮水印並解鎖完整功能集：

- **免費試用** – 使用臨時授權開始。  
- **臨時授權** – 從 [Aspose 網站](https://purchase.aspose.com/temporary-license/) 申請。  
- **商業授權** – 購買以供正式使用。

在程式碼中套用授權：

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## 實作指南

### 初始化簡報並加入環形圖

Presentation 是 Aspose.Slides 中代表 PowerPoint 簡報的類別。  
載入現有的 PPTX 或建立新的 `Presentation` 物件，然後在第一張投影片加入環形圖。

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### 設定圖表資料工作簿並清除現有資料

工作簿是內部的試算表，用於儲存圖表資料。  
取得支援圖表的工作簿，然後清除任何預設的系列或類別，以便從乾淨的狀態開始。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 向圖表加入系列

系列代表在圖表上繪製的一組資料點。  
您最多可加入 15 個系列。每個系列皆可自訂——此處我們設定了爆炸效果、環形孔大小與第一片角度。

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### 加入類別與資料點

類別是圖表軸上每個資料點的標籤。  
建立 15 個類別，並為每個系列填入資料點。最後一個系列會套用特殊的標籤格式。

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### 自訂顏色與資料標籤

`FillType.Solid` 指定圖表元素的實心填色。  
為每個系列設定實心填色並啟用資料標籤。對於最後一個系列，我們亦會變更標籤字體顏色。

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### 儲存簡報

`save` 將簡報寫入指定格式的檔案。  
將更新後的簡報寫入磁碟為 PPTX 格式，或視需求匯出為 PDF。

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## 常見問題與解決方案

- **找不到授權** – 確認 `license.lic` 的路徑正確且檔案可讀取。  
- **圖表顯示空白** – 確認在加入新系列/類別前已清除既有的系列/類別。  
- **顏色不正確** – 確認填色與線條格式皆設定為 `FillType.Solid`。  
- **大量系列的效能** – 限制系列/類別數量或重複使用工作簿儲存格，以控制記憶體使用。

## 常見問答

**Q: 我可以在沒有預先存在的 PPTX 檔案的情況下產生環形圖嗎？**  
A: 可以，建立 `new Presentation()` 以從空白簡報開始，然後依上述方式加入圖表。

**Q: Aspose.Slides 是否支援匯出為 PDF？**  
A: 當然支援。建立圖表後，呼叫 `pres.save("output.pdf", SaveFormat.Pdf);` 即可取得投影片的 PDF 版本。

**Q: 如何變更環形孔的大小？**  
A: 使用 `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`，其中 `value` 的範圍為 0 到 100。

**Q: 能否將資料標籤加到所有系列，而不僅是最後一個？**  
A: 可以，將標籤格式化的程式碼塊移出 `if (i == ...)` 條件，並套用至每個 `dataPoint`。

**Q: 支援哪些 Java 版本？**  
A: Aspose.Slides 25.4 支援 JDK 16 及以上。較早的 JDK 需要在 Maven 相依性中使用相應的 classifier。

---

**最後更新：** 2026-08-16  
**測試環境：** Aspose.Slides for Java 25.4（jdk16 classifier）  
**作者：** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 相關教學

- [如何使用 Aspose.Slides for Java 在 PowerPoint 中加入圖表：一步一步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [如何在 Java 中使用 Aspose.Slides 自訂圓餅圖顏色 – 完整指南](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [使用 Aspose.Slides for Java 為 PowerPoint 圖表類別添加動畫 | 步驟指南](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}