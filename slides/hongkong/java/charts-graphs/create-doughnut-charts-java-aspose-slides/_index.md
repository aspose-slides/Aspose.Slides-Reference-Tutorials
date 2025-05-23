---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides 在 Java 中建立令人驚嘆的甜甜圈圖。本綜合指南涵蓋初始化、資料配置和保存簡報。"
"title": "使用 Aspose.Slides 在 Java 中建立甜甜圈圖綜合指南"
"url": "/zh-hant/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 中建立甜甜圈圖：逐步指南

## 介紹

在當今數據驅動的環境中，有效地視覺化資訊是增強理解和參與的關鍵。雖然以程式設計方式建立專業圖表看起來很有挑戰性，尤其是使用 Java 時，但本指南將引導您使用 Aspose.Slides for Java 輕鬆建立甜甜圈圖表。

透過遵循這些步驟，開發人員將獲得操作簡報幻燈片和無縫整合資料視覺化的實務經驗。

**關鍵要點：**
- 使用 Aspose.Slides Java 初始化示範物件。
- 配置圖表資料並管理現有系列或類別。
- 為您的圖表新增和自訂系列和類別。
- 有效地格式化和顯示資料點。
- 輕鬆地以各種格式儲存您的簡報。

在深入實施之前，請確保您已準備好開始實施所需的一切。

## 先決條件

要遵循本教程，請確保您已具備：

- **所需庫：**
  - Aspose.Slides for Java 版本 25.4 或更高版本。
  
- **環境設定：**
  - 您的系統上安裝了 JDK 16 或更高版本。
  - 像 IntelliJ IDEA、Eclipse 或 NetBeans 這樣的 IDE。

- **知識前提：**
  - 對 Java 程式設計概念有基本的了解。
  - 熟悉管理 Maven 或 Gradle 專案中的依賴項。

## 設定 Aspose.Slides for Java

若要將 Aspose.Slides 整合到您的專案中，請根據您的建置工具執行以下步驟：

**Maven設定：**
將以下相依性新增至您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 設定：**
在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載：**
或者，直接從 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 取得許可證

要使用不受評估限制的 Aspose.Slides：
- **免費試用：** 從臨時許可證開始探索全部功能。
- **臨時執照：** 透過 [Aspose 網站](https://purchase。aspose.com/temporary-license/).
- **購買：** 考慮購買以供持續使用。

使用以下命令在您的 Java 應用程式中應用您的許可證：
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 實施指南

### 初始化演示和圖表

#### 概述
首先初始化一個簡報物件並在第一張投影片中新增一個圓環圖。

**步驟 1：初始化簡報**
載入現有的 PPTX 檔案或建立新的 PPTX 檔案：
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**步驟 2：新增圓環圖**
在第一張投影片上的指定座標處建立圖表：
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 配置圖表資料工作簿並清除現有系列/類別

#### 概述
配置圖表資料工作簿並刪除任何預先存在的系列或類別。

**步驟 1：存取圖表資料工作簿**
檢索與圖表連結的工作簿：
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**第 2 步：清除現有系列和類別**
確保沒有殘留數據點：
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### 在圖表中新增系列

#### 概述
使用多個系列填充您的圖表，每個系列都針對外觀和行為進行客製化。

**步驟 1：迭代新增系列**
循環索引以新增系列：
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // 客製化系列
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 在圖表中新增類別和資料點

#### 概述
配置類別並新增具有特定格式的標籤資料點。

**步驟 1：新增類別**
循環遍歷每個類別的索引：
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**步驟 2：為每個系列新增資料點**
迭代當前類別的每個系列：
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // 數據點格式設定
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // 最後一個系列的標籤格式
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

        // 調整顯示選項
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // 調整標籤位置
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### 儲存簡報

#### 概述
配置完圖表後，將簡報儲存到指定目錄。

**步驟 1：儲存簡報**
使用 `save` 寫入更改的方法：
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 結論

現在您已經了解如何使用 Aspose.Slides 在 Java 中建立和自訂甜甜圈圖。這些步驟為將複雜的資料視覺化整合到您的簡報中奠定了基礎。

**後續步驟：**
- 嘗試 Aspose.Slides 中可用的不同圖表類型。
- 探索其他自訂選項，如顏色、字體和樣式，以滿足您的品牌需求。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}