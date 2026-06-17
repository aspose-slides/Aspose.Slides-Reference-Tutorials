---
date: '2026-06-03'
description: 学习如何使用 Aspose.Slides for Java 将图表导出到 Excel 并创建 Java 图表。掌握数据可视化、业务报告幻灯片和工作簿生成。
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: 将图表导出到 Excel 并使用 Aspose.Slides 创建图表
url: /zh/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 将图表导出到 Excel 并使用 Aspose.Slides 创建图表

**使用 Aspose.Slides for Java 掌握数据可视化技术**

在当今数据驱动的环境中，*将图表导出到 Excel* 的编程技能可以将原始数字转化为引人入胜的可视化故事。无论您是构建业务报告幻灯片还是交互式分析仪表板，Aspose.Slides for Java 都能让您直接在代码中生成、定制和导出图表。在本教程中，您将学习如何创建图表对象、将图表数据导出到 Excel，以及将图表链接到外部工作簿，实现无缝的数据管理。

## 快速答案
- **需要的库是什么？** Aspose.Slides for Java (v25.4+)。  
- **我可以将图表数据导出到 Excel 吗？** 是 – 使用 `readWorkbookStream()` 并将字节写入 *.xlsx* 文件。  
- **需要哪个 Java 版本？** JDK 16 或更高。  
- **我需要许可证吗？** 免费试用可用于评估；生产环境需要永久许可证。  
- **演示的图表类型是什么？** 饼图，但相同方法适用于柱形图、折线图等其他图表类型。

## Aspose.Slides for Java 是什么？
Aspose.Slides for Java 是一个纯 Java API，允许开发者在没有 Microsoft Office 的情况下创建、编辑和转换 PowerPoint 演示文稿。它提供了完整的类集合，用于幻灯片操作、图表生成和格式转换，从而实现自动化报告解决方案。它支持 **50+ 图表类型**、完整的数据绑定以及直接的 Excel 导出，使其成为 **data visualization java** 项目的理想选择。

## 为什么使用 Aspose.Slides 创建图表并导出图表到 Excel？
快速可靠地将图表导出到 Excel。Aspose.Slides 消除了对 Office 安装的需求，提供 **超过 50 种内置图表样式**，并且在标准服务器硬件上能够在 **30 秒内处理高达 300 MB 的演示文稿**。您还可以生成原生的 Excel 工作簿，使下游分析师能够直接使用原始数据，无需手动复制粘贴。

## 前置条件
在开始之前，请确保您具备以下条件：

### 必需的库和版本
- **Aspose.Slides for Java** 版本 25.4 或更高（支持 JDK 16+）

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

或者，您可以直接[下载最新版本](https://releases.aspose.com/slides/java/)。

### 许可证获取步骤
Aspose.Slides 提供免费试用许可证，以探索其全部功能。您也可以申请临时许可证或购买长期许可证。请按照以下步骤操作：

1. 访问 [Aspose 购买页面](https://purchase.aspose.com/buy) 获取许可证。  
2. 免费试用，请从 [Releases](https://releases.aspose.com/slides/java/) 下载。  
3. 在[此处](https://purchase.aspose.com/temporary-license/)申请临时许可证。

获取许可证文件后，在 Java 应用程序中初始化它：

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 步骤指南

### 如何创建图表 – 加载演示文稿
在添加或修改图表之前，需要加载现有的 PowerPoint 文件。  
`Presentation` 类表示内存中的 PowerPoint 文件，提供对幻灯片、形状和图表对象的访问。  
使用 `new Presentation("input.pptx")` 加载文件，然后通过 `presentation.getSlides().get_Item(0)` 操作第一张幻灯片。务必在 `finally` 块中调用 `presentation.dispose()` 以释放本机资源。

### 如何创建图表 – 向幻灯片添加饼图
插入饼图，非常适合展示比例数据。  
`IChart` 接口是图表操作的主要入口；`addChart` 在目标幻灯片上创建新图表。提供图表类型 (`ChartType.Pie`)、X/Y 坐标以及宽度/高度。创建后，您可以通过 `ChartData` 对象自定义标题、图例和数据系列。

### 如何导出图表到 Excel – 导出图表数据
导出图表数据使分析师能够在 Excel 中处理数字，从而获得更深入的洞察。  
`readWorkbookStream()` 将图表底层的 Excel 工作簿以字节数组形式返回。调用 `chart.getChartData().readWorkbookStream()` 获取工作簿，并使用标准 Java I/O 将该数组写入名为 `externalWorkbook1.xlsx` 的文件。生成的 Excel 文件包含图表使用的精确数据，便于进一步分析。

### 如何创建图表 – 设置外部工作簿以实现动态数据
将图表链接到外部工作簿，可在无需重新生成幻灯片的情况下实现实时数据更新。  
`setExternalWorkbook()` 将图表绑定到外部 Excel 文件，以实现动态数据更新。使用 `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` 将图表绑定到外部文件。当 Excel 工作簿被编辑后，图表将在下次打开演示文稿时自动反映更改，支持动态报告场景。

## 实际应用
Aspose.Slides 为各种实际场景提供了多功能解决方案：

1. **业务报告幻灯片：** 自动从数据管道生成季度业绩图表。  
2. **学术演示：** 将研究数据转化为清晰的可视化，无需手动绘图。  
3. **财务分析：** 将图表数据导出到 Excel，供审计员核对数字，减少人工错误。  
4. **营销分析：** 可视化活动指标，并与利益相关者共享可编辑工作簿，以实现协作决策。  
5. **自动化仪表板生成：** 将图表创建 API 与计划任务结合，每天早晨生成最新的幻灯片套件。

## 常见问题与故障排除
- **`FileNotFoundException`** – 确认 `dataDir` 指向有效文件夹且输出路径可写。  
- **内存泄漏** – 始终在 `finally` 块中调用 `presentation.dispose()` 以释放本机资源。  
- **图表未显示** – 确保幻灯片索引 (`get_Item(0)`) 对应已有幻灯片，并且图表尺寸在幻灯片范围内。  
- **Excel 导出生成空文件** – 在调用 `readWorkbookStream()` 前确认图表确实包含数据系列。

## 常见问答

**Q: 我可以使用不同的图表类型（例如柱形图、折线图）并使用相同的代码吗？**  
A: 是的。将 `ChartType.Pie` 替换为其他 `ChartType` 枚举值，例如 `ChartType.Bar` 或 `ChartType.Line`。

**Q: 在创建图表后可以更新外部工作簿吗？**  
A: 当然可以。直接修改 Excel 文件；链接的图表将在下次打开演示文稿时反映更改。

**Q: Excel 导出功能需要单独的许可证吗？**  
A: 不需要。Excel 导出功能已包含在标准的 Aspose.Slides for Java 许可证中。

**Q: 支持哪些 Java 版本？**  
A: Aspose.Slides for Java 支持 JDK 16 及更高版本；早期版本可能可用，但未正式测试。

**Q: 如何将生成的 Excel 工作簿嵌入到 PPTX 文件中？**  
A: 使用 `chart.getChartData().setExternalWorkbook(null)` 将工作簿嵌入，或保留外部链接以实现动态更新。

---

**最后更新：** 2026-06-03  
**测试环境：** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**作者：** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [在 Java 中使用 Aspose.Slides 创建图表 – 添加和验证图表](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [使用 Aspose.Slides Java 从 PowerPoint 图表恢复工作簿数据](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [如何使用 Aspose.Slides for Java 更新 PowerPoint 图表数据范围](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}