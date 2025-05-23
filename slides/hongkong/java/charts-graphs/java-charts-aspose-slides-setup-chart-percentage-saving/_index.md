---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides 在 Java 簡報中建立、自訂和儲存帶有百分比標籤的圖表。今天就提升您的演講技巧！"
"title": "使用 Aspose.Slides 在 Java 簡報中建立和自訂圖表"
"url": "/zh-hant/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 簡報中建立和自訂圖表

## 介紹
創建引人注目的簡報通常不僅僅涉及文字；它需要能夠有效傳達訊息的動態圖表。如果您希望使用 Aspose.Slides 透過複雜的圖表功能增強基於 Java 的演示文稿，那麼本教學適合您。我們將指導您建立簡報、新增和配置圖表、計算總數、顯示百分比標籤以及儲存您的工作—只需幾個簡單的步驟即可完成。

**您將學到什麼：**
- 如何使用 Aspose.Slides for Java 建立和自訂帶有圖表的簡報
- 計算圖表中的類別總數
- 在圖表上以百分比標籤的形式顯示數據
- 使用增強的圖表功能儲存演示文稿

讓我們深入了解開始之前所需的先決條件。

## 先決條件
要遵循本教程，請確保您具備以下條件：

- **Java 開發工具包 (JDK)**：版本 8 或更高版本。
- **整合開發環境**：例如 IntelliJ IDEA、Eclipse 或任何支援 Java 的 IDE。
- **Aspose.Slides for Java 函式庫**：這對於處理演示功能至關重要。

### 所需的庫和版本
您需要適用於 Java 的 Aspose.Slides。將其包含在您的項目中的方法如下：

**Maven：**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，您可以直接從 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

### 環境設定
確保您的開發環境已配置為使用 JDK 8 或更高版本，並且您的 IDE 已設定為使用 Maven 或 Gradle 管理相依性。

**許可證取得：**
- **免費試用**：存取基本功能以進行測試。
- **臨時執照**：測試進階功能，不受評估限制。
- **購買**：對於長期商業使用，請考慮購買許可證。

## 設定 Aspose.Slides for Java
首先在您的 Java 專案中設定 Aspose.Slides 庫。初始化和配置方法如下：

1. 如上所示，透過 Maven 或 Gradle 新增依賴項。
2. 導入必要的 Aspose.Slides 套件：
   ```java
   import com.aspose.slides.*;
   ```

3. 初始化一個新的 `Presentation` 實例：
   ```java
   Presentation presentation = new Presentation();
   ```

此設定將允許您開始以程式設計方式建立簡報。

## 實施指南

### 在簡報中建立和自訂圖表

#### 概述
建立圖表包括初始化簡報、存取投影片以及新增具有特定屬性（如類型、位置和大小）的圖表。

**步驟：**
1. **建立演示實例**：先創建一個 `Presentation` 班級。
2. **存取幻燈片**：使用以下方法檢索第一張投影片 `get_Item(0)`。
3. **新增圖表**： 使用 `addChart()` 在指定座標處新增具有定義尺寸的堆積長條圖。

```java
// 功能：建立帶有圖表的簡報
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### 計算類別總計

#### 概述
計算類別總數涉及遍歷圖表中的每個系列以匯總每個類別的值。

**步驟：**
1. **初始化數組**：建立一個陣列來保存總值。
2. **迭代類別和系列**：使用巢狀循環來累積所有系列中每個類別的總數。

```java
// 功能：計算圖表中類別的總計
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### 在圖表上以百分比標籤顯示數據

#### 概述
此功能專注於配置資料標籤以百分比顯示值，從而提供清晰的視覺化效果。

**步驟：**
1. **配置系列標籤**：設定標籤屬性，例如字體大小和圖例鍵的可見性。
2. **計算百分比**：根據總類別值計算每個資料點的百分比。
3. **設定標籤文字**：格式化標籤以顯示帶有兩位小數的百分比。

```java
// 功能：在圖表上以百分比標籤顯示數據
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### 儲存帶有圖表的簡報

#### 概述
最後，將簡報以PPTX格式儲存到指定路徑。

**步驟：**
1. **保存方法**：使用 `save()` 方法 `Presentation` 實例。
2. **處置資源**：確保保存後釋放資源。

```java
// 功能：儲存帶有圖表的簡報
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## 實際應用

1. **財務報告**：使用圖表顯示各部門的收入成長百分比。
2. **銷售數據分析**：使用百分比標籤按地區可視化銷售數據，以獲得更清晰的見解。
3. **教育演示**：利用可視化統計數據增強學術演示。
4. **行銷活動**：將廣告活動效果指標以引人入勝的視覺效果顯示。
5. **商業策略會議**：在策略規劃討論中使用圖表傳達複雜數據。

## 性能考慮
- **記憶體管理**：處理 `Presentation` 對像以釋放資源。
- **優化圖表加載**：如果可能，僅將必要的圖表元素載入記憶體。
- **批次處理**：處理多個簡報時，請考慮分批處理以有效管理資源消耗。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}