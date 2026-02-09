---
date: '2026-02-09'
description: 学习如何使用 Aspose.Slides for Java 创建图表并将图表导出到 Excel。掌握数据可视化、业务报告幻灯片和工作簿生成。
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: 如何使用 Aspose.Slides Java 创建图表
url: /zh/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Java 创建图表

**使用 Aspose.Slides for Java 掌握数据可视化技术**

在当今数据驱动的环境中，*如何以编程方式创建图表* 是一种能够将原始数字转化为引人入胜的可视化故事的技能。无论您是构建业务报告幻灯片还是交互式分析仪表板，Aspose.Slides for Java 都能让您直接在代码中生成、定制和导出图表。在本教程中，您将学习如何创建图表对象、将图表数据导出到 Excel，以及将图表链接到外部工作簿以实现无缝的数据管理。

## 快速回答
- **需要的库是什么？** Aspose.Slides for Java (v25.4+)。  
- **我可以将图表数据导出到 Excel 吗？** 可以 – 使用 `readWorkbookStream()` 并将字节写入 *.xlsx* 文件。  
- **需要哪个 Java 版本？** JDK 16 或更高。  
- **我需要许可证吗？** 免费试用可用于评估；生产环境需要正式许可证。  
- **演示的图表类型是什么？** 饼图，但相同的方法同样适用于柱形图、折线图和其他图表类型。

## Aspose.Slides for Java 是什么？
Aspose.Slides for Java 是一个纯 Java API，允许开发者在没有 Microsoft Office 的情况下创建、编辑和转换 PowerPoint 演示文稿。它支持完整的图表类型、数据绑定和导出功能，是 **data visualization java** 项目的理想选择。

## 为什么使用 Aspose.Slides 创建图表并导出图表到 Excel？
- **无需 Office 安装** – 可在任何服务器或云环境中运行。  
- **丰富的图表库** – 数十种图表类型和完整的样式控制。  
- **直接导出到 Excel** – 生成外部工作簿以供后续分析。  
- **面向性能** – 低内存占用，快速处理大型演示文稿。

## 前置条件
在开始之前，请确保您具备以下条件：

### 必需的库和版本
- **Aspose.Slides for Java** 版本 25.4 或更高

### 环境设置要求
- Java Development Kit (JDK) 16 或更高  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE（或您喜欢的任何文本编辑器）

### 知识前提
- 基本的 Java 编程技能  
- 熟悉 Maven 或 Gradle 构建工具

## 设置 Aspose.Slides for Java
使用您喜欢的构建系统将库添加到项目中。

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，您可以[直接下载最新版本](https://releases.aspose.com/slides/java/)。

### 许可证获取步骤
Aspose.Slides 提供免费试用许可证，以探索其全部功能。您也可以申请临时许可证或购买永久许可证以供长期使用。请按照以下步骤操作：

1. 访问 [Aspose 购买页面](https://purchase.aspose.com/buy) 获取许可证。  
2. 免费试用请从 [Releases](https://releases.aspose.com/slides/java/) 下载。  
3. 在[此处](https://purchase.aspose.com/temporary-license/)申请临时许可证。

获取许可证文件后，在 Java 应用程序中进行初始化：

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 步骤指南

### 如何创建图表 – 加载演示文稿
在添加或修改图表之前，首先需要加载现有的 PowerPoint 文件。

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**说明：**  
- `Presentation` 表示 PowerPoint 文件。  
- 始终调用 `dispose()` 以释放本机资源。

### 如何创建图表 – 向幻灯片添加饼图
现在我们将插入一个饼图，它非常适合展示比例数据。

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**说明：**  
- `addChart` 将图表插入到第一张幻灯片上。  
- 参数定义了图表类型、X/Y 位置和大小。

### 如何导出图表到 Excel – 导出图表数据
导出图表数据使分析人员能够在 Excel 中处理这些数字，从而获得更深入的洞察。

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**说明：**  
- `readWorkbookStream()` 将图表底层的 Excel 工作簿提取为字节数组。  
- 将字节数组写入 `externalWorkbook1.xlsx`，即可得到可直接使用的 Excel 文件。

### 如何创建图表 – 设置外部工作簿以实现动态数据
将图表链接到外部工作簿后，只需编辑 Excel 文件即可更新图表。

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**说明：**  
- `setExternalWorkbook` 将图表绑定到指定的 Excel 文件，实现无需重新生成幻灯片的实时数据更新。

## 实际应用
Aspose.Slides 为各种真实场景提供了多样化的解决方案：

1. **业务报告幻灯片：** 自动从数据管道生成季度业绩图表。  
2. **学术演示：** 将研究数据转化为清晰的可视化，无需手动绘图。  
3. **财务分析：** 将图表数据导出到 Excel，供审计员核对数字。  
4. **营销分析：** 可视化活动指标，并与利益相关者共享可编辑的工作簿。

## 常见问题与故障排除
- **`FileNotFoundException`** – 确认 `dataDir` 指向有效文件夹且输出路径可写。  
- **内存泄漏** – 始终在 `finally` 块中调用 `pres.dispose()` 以释放本机资源。  
- **图表未显示** – 确保幻灯片索引 (`get_Item(0)`) 对应实际存在的幻灯片。

## 常见问答

**Q: 我可以使用不同的图表类型（例如柱形图、折线图）并使用相同的代码吗？**  
A: 可以。将 `ChartType.Pie` 替换为其他 `ChartType` 枚举值，如 `ChartType.Bar` 或 `ChartType.Line`。

**Q: 在创建图表后可以更新外部工作簿吗？**  
A: 当然可以。直接修改 Excel 文件；下次打开演示文稿时，链接的图表会反映出更改。

**Q: 导出到 Excel 的功能需要单独的许可证吗？**  
A: 不需要。Excel 导出功能已包含在标准的 Aspose.Slides for Java 许可证中。

**Q: 支持哪些 Java 版本？**  
A: Aspose.Slides for Java 支持 JDK 16 及以上；早期版本可能可用，但未正式测试。

**Q: 如何将生成的 Excel 工作簿嵌入到 PPTX 文件中？**  
A: 使用 `chart.getChartData().setExternalWorkbook(null)` 将工作簿嵌入，或保留外部链接以实现动态更新。

---

**最后更新：** 2026-02-09  
**测试环境：** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}