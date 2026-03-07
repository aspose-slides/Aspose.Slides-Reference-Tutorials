---
date: '2026-03-07'
description: 學習如何使用 Aspose.Slides 在 Java 中建立甜甜圈圖表。此一步一步指南涵蓋 Maven Aspose Slides 依賴設定、圖表配置以及儲存簡報。
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: 使用 Aspose.Slides 的 Java 環形圖建立指南
url: /zh-hant/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 的 Java Doughnut Chart 建立指南

## 介紹

以程式方式建立 **doughnut chart** 可以將原始數據轉換成一目了然、吸睛的視覺圖表，立即傳達資訊。於 Java 中，**Aspose.Slides** 讓此流程變得簡單，無需開啟 PowerPoint 即可產生可直接使用的簡報圖表。在本教學中，你將一步步學會如何 **create doughnut chart java**——從設定 Maven Aspose Slides 相依性、客製化系列與類別，最後儲存簡報。

完成本指南後，你將能將動態 doughnut chart 嵌入任何 PPTX 檔案，適用於報告、儀表板或自動化投影片。

### 快速解答
- **使用的函式庫為何？** Aspose.Slides for Java  
- **主要任務？** 在 PPTX 檔案中建立 doughnut chart java  
- **如何加入函式庫？** 使用 Maven Aspose Slides 相依性（或 Gradle）  
- **最低 Java 版本？** JDK 16 或以上  
- **可以自訂顏色與標籤嗎？** 可以，API 提供完整的格式控制  

## Doughnut Chart 是什麼？為何使用它？

Doughnut Chart 是一種帶有空心中心的圓餅圖變形，可在同心環中顯示多個資料系列。這使它非常適合比較多個類別下的整體比例——例如各區域在多個季度的銷售或各部門的預算分配。

## 為何選擇 Aspose.Slides for Java？

- **無需安裝 Office** – 可在任何伺服器上產生 PPTX 檔案。  
- **功能豐富的 API** – 完全掌控圖表類型、資料點與樣式。  
- **高效能** – 為大型簡報進行最佳化。  
- **跨平台** – 支援 Windows、Linux 與 macOS。

## 前置條件

- **必要函式庫：**  
  - Aspose.Slides for Java 版本 25.4 或更新。  

- **環境設定：**  
  - JDK 16 或以上。  
  - 你喜愛的 IDE（IntelliJ IDEA、Eclipse、NetBeans 等）。  

- **知識前提：**  
  - 基本的 Java 程式設計。  
  - 熟悉 Maven 或 Gradle 以管理相依性。

## Maven Aspose Slides 相依性

在 `pom.xml` 中加入以下 Maven 相依性。這是你需要的 **maven aspose slides dependency**，用以將函式庫匯入專案。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

如果你偏好使用 Gradle，請使用下方等效的程式碼片段。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

你也可以直接從官方發行頁面下載 JAR：

[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### 取得授權

若要移除評估水印並解鎖完整功能：

- **免費試用** – 使用臨時授權開始。  
- **臨時授權** – 可於 [Aspose 網站](https://purchase.aspose.com/temporary-license/) 申請。  
- **商業授權** – 購買後於正式環境使用。

在程式碼中套用授權：

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 實作指南

### 初始化簡報並加入 Doughnut Chart

首先，建立或載入簡報，並在第一張投影片加入 Doughnut Chart。

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 設定圖表資料工作簿並清除既有資料

接著，取得支援圖表的工作簿，並清除所有預設的系列或類別。

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### 向圖表加入系列

現在我們將加入最多 15 個系列。每個系列皆可自訂——此處設定了爆炸效果、doughnut‑hole 大小，以及第一切片角度。

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

### 加入類別與資料點

我們會建立 15 個類別，並為每個系列填入資料點。最後一個系列會套用特殊的標籤格式。

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

### 儲存簡報

最後，將更新後的簡報寫入磁碟。

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 常見問題與解決方案

- **找不到授權** – 請確認 `license.lic` 的路徑正確且檔案可讀取。  
- **圖表顯示空白** – 確認在加入新系列前已清除既有的系列/類別。  
- **顏色不正確** – 檢查 `FillType.Solid` 是否已設定於填充與線條格式。  
- **大量系列的效能** – 限制系列/類別數量或重複使用工作簿儲存格。

## 常見問答

**Q: 是否可以在沒有既有 PPTX 檔案的情況下產生 doughnut chart？**  
A: 可以，建立 `new Presentation()` 即可從空白投影片開始。

**Q: Aspose.Slides 是否支援匯出為 PDF？**  
A: 當然支援。建立圖表後，呼叫 `pres.save("output.pdf", SaveFormat.Pdf);` 即可。

**Q: 如何調整 doughnut hole 大小？**  
A: 使用 `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`，其中 value 為 0‑100。

**Q: 能否將資料標籤加到所有系列，而非僅最後一個？**  
A: 可以，將標籤格式化的程式碼塊移出 `if (i == ...)` 條件，並套用於每個 `dataPoint`。

**Q: 支援哪些 Java 版本？**  
A: Aspose.Slides 25.4 支援 JDK 16 及以上。較舊的 JDK 需要使用相對應的 classifier。

**最後更新：** 2026-03-07  
**測試環境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}