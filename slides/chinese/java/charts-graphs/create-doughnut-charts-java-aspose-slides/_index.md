---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides 在 Java 中创建精美的圆环图。本指南内容全面，涵盖初始化、数据配置和保存演示文稿。"
"title": "使用 Aspose.Slides 在 Java 中创建甜甜圈图——综合指南"
"url": "/zh/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 中创建甜甜圈图：分步指南

## 介绍

在当今数据驱动的环境中，有效地可视化信息是增强理解和参与度的关键。虽然以编程方式创建专业图表似乎颇具挑战性，尤其是在使用 Java 的情况下，但本指南将指导您使用 Aspose.Slides for Java 轻松创建甜甜圈图。

通过遵循这些步骤，开发人员将获得操作演示幻灯片和无缝集成数据可视化的实践经验。

**关键要点：**
- 使用 Aspose.Slides Java 初始化演示对象。
- 配置图表数据并管理现有系列或类别。
- 为您的图表添加和自定义系列和类别。
- 有效地格式化和显示数据点。
- 轻松地以各种格式保存您的演示文稿。

在深入实施之前，请确保您已准备好开始实施所需的一切。

## 先决条件

要遵循本教程，请确保您已具备：

- **所需库：**
  - Aspose.Slides for Java 版本 25.4 或更高版本。
  
- **环境设置：**
  - 您的系统上安装了 JDK 16 或更高版本。
  - 像 IntelliJ IDEA、Eclipse 或 NetBeans 这样的 IDE。

- **知识前提：**
  - 对 Java 编程概念有基本的了解。
  - 熟悉管理 Maven 或 Gradle 项目中的依赖项。

## 设置 Aspose.Slides for Java

要将 Aspose.Slides 集成到您的项目中，请根据您的构建工具执行以下步骤：

**Maven设置：**
将以下依赖项添加到您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 设置：**
在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载：**
或者，直接从 [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).

### 获取许可证

要使用不受评估限制的 Aspose.Slides：
- **免费试用：** 从临时许可证开始探索全部功能。
- **临时执照：** 通过 [Aspose 网站](https://purchase。aspose.com/temporary-license/).
- **购买：** 考虑购买以供持续使用。

使用以下命令在您的 Java 应用程序中应用您的许可证：
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 实施指南

### 初始化演示和图表

#### 概述
首先初始化一个演示对象并在第一张幻灯片中添加一个圆环图。

**步骤 1：初始化演示文稿**
加载现有的 PPTX 文件或创建新文件：
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**步骤 2：添加圆环图**
在第一张幻灯片上的指定坐标处创建图表：
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 配置图表数据工作簿并清除现有系列/类别

#### 概述
配置图表数据工作簿并删除任何预先存在的系列或类别。

**步骤 1：访问图表数据工作簿**
检索与图表链接的工作簿：
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**第 2 步：清除现有系列和类别**
确保没有残留数据点：
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### 向图表添加系列

#### 概述
使用多个系列填充您的图表，每个系列都针对外观和行为进行定制。

**步骤 1：迭代添加系列**
循环索引以添加系列：
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // 定制系列
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 向图表添加类别和数据点

#### 概述
配置类别并添加具有特定格式的标签数据点。

**步骤 1：添加类别**
循环遍历每个类别的索引：
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**步骤 2：向每个系列添加数据点**
迭代当前类别的每个系列：
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // 数据点格式设置
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // 最后一个系列的标签格式
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

        // 调整显示选项
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // 调整标签位置
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### 保存演示文稿

#### 概述
配置完图表后，将演示文稿保存到指定目录。

**步骤 1：保存演示文稿**
使用 `save` 写入更改的方法：
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 结论

现在您已经学习了如何使用 Aspose.Slides 在 Java 中创建和自定义甜甜圈图。这些步骤为将复杂的数据可视化集成到您的演示文稿中奠定了基础。

**后续步骤：**
- 尝试 Aspose.Slides 中可用的不同图表类型。
- 探索其他自定义选项，如颜色、字体和样式，以满足您的品牌需求。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}