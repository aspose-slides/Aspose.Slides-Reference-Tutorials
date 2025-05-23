---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides 在 Java 演示文稿中创建、自定义和保存带有百分比标签的图表。立即提升您的演讲技巧！"
"title": "使用 Aspose.Slides 在 Java 演示文稿中创建和自定义图表"
"url": "/zh/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 演示文稿中创建和自定义图表

## 介绍
创建引人入胜的演示文稿通常不仅仅涉及文本；它需要能够有效传达信息的动态图表。如果您希望使用 Aspose.Slides 为基于 Java 的演示文稿添加复杂的图表功能，那么本教程非常适合您。我们将指导您创建演示文稿、添加和配置图表、计算总计、显示百分比标签以及保存您的工作——所有这些只需几个简单的步骤即可完成。

**您将学到什么：**
- 如何使用 Aspose.Slides for Java 创建和自定义带有图表的演示文稿
- 计算图表中的类别总数
- 在图表上以百分比标签的形式显示数据
- 使用增强的图表功能保存演示文稿

让我们深入了解开始之前所需的先决条件。

## 先决条件
要遵循本教程，请确保您具备以下条件：

- **Java 开发工具包 (JDK)**：版本 8 或更高版本。
- **集成开发环境**：例如 IntelliJ IDEA、Eclipse 或任何支持 Java 的 IDE。
- **Aspose.Slides for Java 库**：这对于处理演示功能至关重要。

### 所需的库和版本
您需要 Aspose.Slides for Java。以下是如何将其添加到您的项目中：

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

或者，您可以直接从 [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).

### 环境设置
确保您的开发环境配置为使用 JDK 8 或更高版本，并且您的 IDE 已设置为使用 Maven 或 Gradle 管理依赖项。

**许可证获取：**
- **免费试用**：访问基本功能以进行测试。
- **临时执照**：测试高级功能，不受评估限制。
- **购买**：对于长期商业使用，请考虑购买许可证。

## 设置 Aspose.Slides for Java
首先在您的 Java 项目中设置 Aspose.Slides 库。初始化和配置方法如下：

1. 如上所示，通过 Maven 或 Gradle 添加依赖项。
2. 导入必要的 Aspose.Slides 包：
   ```java
   import com.aspose.slides.*;
   ```

3. 初始化一个新的 `Presentation` 实例：
   ```java
   Presentation presentation = new Presentation();
   ```

此设置将允许您开始以编程方式构建演示文稿。

## 实施指南

### 在演示文稿中创建和自定义图表

#### 概述
创建图表包括初始化演示文稿、访问幻灯片以及添加具有特定属性（如类型、位置和大小）的图表。

**步骤：**
1. **创建演示实例**：首先创建一个 `Presentation` 班级。
2. **访问幻灯片**：使用以下方法检索第一张幻灯片 `get_Item(0)`。
3. **添加图表**： 使用 `addChart()` 在指定坐标处添加具有定义尺寸的堆积柱形图。

```java
// 功能：创建带图表的演示文稿
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

### 计算类别总计

#### 概述
计算类别总数涉及遍历图表中的每个系列以汇总每个类别的值。

**步骤：**
1. **初始化数组**：创建一个数组来保存总值。
2. **迭代类别和系列**：使用嵌套循环来累计所有系列中每个类别的总数。

```java
// 功能：计算图表中类别的总计
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

### 在图表上以百分比标签显示数据

#### 概述
此功能专注于配置数据标签以百分比显示值，从而提供清晰的可视化效果。

**步骤：**
1. **配置系列标签**：设置标签属性，例如字体大小和图例键的可见性。
2. **计算百分比**：根据总类别值计算每个数据点的百分比。
3. **设置标签文本**：格式化标签以显示带有两位小数的百分比。

```java
// 功能：在图表上以百分比标签显示数据
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

### 保存带有图表的演示文稿

#### 概述
最后，将演示文稿以PPTX格式保存到指定路径。

**步骤：**
1. **保存方法**：使用 `save()` 方法 `Presentation` 实例。
2. **处置资源**：确保保存后释放资源。

```java
// 功能：保存带有图表的演示文稿
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## 实际应用

1. **财务报告**：使用图表显示各部门的收入增长百分比。
2. **销售数据分析**：使用百分比标签按地区可视化销售数据，以获得更清晰的洞察。
3. **教育演示**：利用可视化统计数据增强学术演示。
4. **营销活动**：将广告系列效果指标以引人入胜的视觉效果显示。
5. **商业战略会议**：在战略规划讨论中使用图表传达复杂数据。

## 性能考虑
- **内存管理**：处理 `Presentation` 对象以释放资源。
- **优化图表加载**：如果可能，仅将必要的图表元素加载到内存中。
- **批处理**：处理多个演示文稿时，请考虑分批处理以有效管理资源消耗。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}