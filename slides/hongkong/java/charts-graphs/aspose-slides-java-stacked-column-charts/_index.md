---
"date": "2025-04-17"
"description": "學習使用 Aspose.Slides for Java 建立專業簡報。本指南涵蓋如何設定您的環境、如何添加堆積長條圖以及如何自訂它們以提高清晰度。"
"title": "使用 Aspose.Slides™ 掌握 Java 中的堆積長條圖綜合指南"
"url": "/zh-hant/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 掌握 Java 中的堆疊長條圖：綜合指南

## 介紹

透過將富有洞察力的資料視覺化與 Aspose.Slides for Java 的強大功能結合起來，提升您的簡報。無論您準備的是業務報告還是展示專案統計數據，使用堆積長條圖建立具有專業外觀的投影片都非常簡單。

在本教程中，我們將探討如何使用 Aspose.Slides for Java 建立動態簡報並添加視覺上吸引人的堆積長條圖。閱讀本指南後，您將掌握以下所需技能：
- 設定您的環境以使用 Aspose.Slides
- 從頭開始建立簡報
- 添加和自訂百分比堆積長條圖
- 格式化圖表軸和資料標籤以提高清晰度

讓我們深入研究如何創建吸引觀眾的簡報。

## 先決條件
在開始之前，請確保您具備以下條件：
- **Java 開發工具包 (JDK)：** 版本 8 或更高版本。
- **整合開發環境（IDE）：** 任何整合開發環境，如 IntelliJ IDEA 或 Eclipse。
- **Maven/Gradle：** 用於管理依賴項（可選但建議）。
- **Java基礎知識：** 熟悉 Java 程式設計概念。

## 設定 Aspose.Slides for Java
首先，您需要在專案中包含 Aspose.Slides 庫。方法如下：

**Maven：**
將此依賴項新增至您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**
將其包含在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下載：**
或者，從下載最新的 JAR [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 許可證獲取
您可以從免費試用開始探索 Aspose.Slides 的功能。若要消除評估限制，請考慮取得臨時或購買許可證。
- **免費試用：** 無需立即付費即可存取有限的功能。
- **臨時執照：** 請求方式 [Aspose 的網站](https://purchase。aspose.com/temporary-license/).
- **購買：** 請造訪購買頁面以獲得完全存取權。

### 基本初始化
以下是在 Java 應用程式中初始化 Aspose.Slides 的方法：
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // 建立 Presentation 類別的實例
        Presentation presentation = new Presentation();
        
        // 對展示對象執行操作
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## 實施指南

### 建立簡報並新增幻燈片
**概述：**
首先建立一個帶有初始投影片的簡單簡報。這是您進一步增強的基礎。

#### 步驟1：初始化演示對象
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // 建立新的演示實例
        Presentation presentation = new Presentation();
        
        // 參考第一張投影片（自動建立）
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 步驟 2： 儲存簡報
```java
// 將簡報儲存到文件
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### 將百分比堆積長條圖加入投影片
**概述：**
透過添加百分比堆積長條圖來增強您的投影片，以便於輕鬆比較數據。

#### 步驟 1：初始化並存取投影片
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // 下一步繼續新增圖表
    }
}
```

#### 步驟 2：將圖表新增至投影片
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### 自訂圖表軸數字格式
**概述：**
自訂圖表垂直軸的數字格式以增強可讀性。

#### 步驟 1：新增並存取圖表
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### 步驟 2：設定自訂數字格式
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### 在圖表中新增系列和數據點
**概述：**
用數據系列填充您的圖表，使其資訊豐富且具有視覺吸引力。

#### 步驟 1：初始化簡報和圖表
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 步驟 2：新增資料系列
```java
// 清除現有系列並新增系列
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// 根據需要添加更多數據點
```

### 格式化系列填滿色彩
**概述：**
透過格式化每個系列的填滿顏色來增強圖表的美感。

#### 步驟 1：初始化並存取圖表
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### 步驟 2：設定填滿顏色
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// 對其他系列使用不同顏色重複此操作
```

### 格式化資料標籤
**概述：**
透過自訂格式使資料標籤更具可讀性。

#### 步驟 1：存取圖表系列和資料點
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 第 2 步：自訂資料標籤
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## 結論
透過遵循本指南，您已經學習如何設定 Aspose.Slides for Java 並使用百分比堆積長條圖建立動態簡報。透過調整顏色和標籤來進一步客製化您的圖表以滿足您的需求。

編碼愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}