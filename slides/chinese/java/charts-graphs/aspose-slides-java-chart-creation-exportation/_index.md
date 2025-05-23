---
"date": "2025-04-17"
"description": "学习使用 Java 中的 Aspose.Slides 创建和导出图表。通过分步指南和代码示例掌握数据可视化技术。"
"title": "Aspose.Slides Java&#58; 创建和导出数据可视化图表"
"url": "/zh/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides Java 创建和导出图表

**使用 Aspose.Slides for Java 掌握数据可视化技术**

在当今数据驱动的时代，有效的数据可视化对于做出明智的决策至关重要。将图表功能集成到您的 Java 应用程序中，可以将原始数据转化为引人入胜的视觉故事。本教程将指导您使用 Aspose.Slides for Java 创建和导出图表，确保您的演示文稿既信息丰富又具有视觉吸引力。

**您将学到什么：**
- 轻松加载和操作演示文件
- 在幻灯片中添加各种类型的图表
- 将图表数据无缝导出到外部工作簿
- 设置外部工作簿路径以实现高效的数据管理

让我们开始吧！

## 先决条件
在开始之前，请确保您已准备好以下设置：

### 所需的库和版本
- **Aspose.Slides for Java** 版本 25.4 或更高版本

### 环境设置要求
- Java 开发工具包 (JDK) 16 或更高版本
- 代码编辑器或 IDE，例如 IntelliJ IDEA 或 Eclipse

### 知识前提
- 对 Java 编程有基本的了解
- 熟悉 Maven 或 Gradle 构建系统

## 设置 Aspose.Slides for Java
要开始使用 Aspose.Slides，您需要将其添加到您的项目中。具体操作如下：

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

或者，您可以 [直接下载最新版本](https://releases。aspose.com/slides/java/).

### 许可证获取步骤
Aspose.Slides 提供免费试用许可证，方便您探索其全部功能。您也可以申请临时许可证或购买许可证以延长使用期限。请按以下步骤操作：
1. 访问 [Aspose 购买页面](https://purchase.aspose.com/buy) 获得你的执照。
2. 如需免费试用，请从以下位置下载 [发布](https://releases。aspose.com/slides/java/).
3. 申请临时执照 [这里](https://purchase。aspose.com/temporary-license/).

获得许可证文件后，请在 Java 应用程序中对其进行初始化：
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 实施指南
### 功能 1：负载演示
加载演示文稿是任何操作任务的第一步。

#### 概述
此功能演示如何使用 Aspose.Slides for Java 加载现有的 PowerPoint 文件。

#### 逐步实施
**将图表添加到幻灯片**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // 设置文档目录的路径
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // 加载现有演示文稿
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // 清理资源
        if (pres != null) pres.dispose();
    }
}
```
**解释：**
- `Presentation` 使用你的路径初始化 `.pptx` 文件。
- 始终丢弃 `Presentation` 反对免费资源。

### 功能 2：将图表添加到幻灯片
添加图表可以显著增强数据呈现。

#### 概述
此功能显示如何将饼图添加到演示文稿的第一张幻灯片。

#### 逐步实施
**将图表添加到幻灯片**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // 设置文档目录的路径
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 在位置 (50, 50) 添加一个饼图，宽度为 400，高度为 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**解释：**
- `addChart` 方法用于插入饼图。
- 参数包括图表的类型及其在幻灯片上的位置/大小。

### 功能 3：将图表数据导出到外部工作簿
导出数据允许在 PowerPoint 之外进行进一步分析。

#### 概述
此功能演示了如何将演示文稿中的图表数据导出到外部 Excel 工作簿。

#### 逐步实施
**导出数据**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // 设置文档目录和输出目录的路径
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 访问第一张幻灯片的图表
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // 定义外部工作簿的路径
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // 将图表数据导出到 Excel 流
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
**解释：**
- `readWorkbookStream` 提取图表数据。
- 使用以下方式将数据写入 Excel 文件 `FileOutputStream`。

### 功能4：为图表数据设置外部工作簿
将图表链接到外部工作簿可以简化数据管理。

#### 概述
此功能演示了如何设置外部工作簿路径来存储图表数据。

#### 逐步实施
**设置外部工作簿路径**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // 设置文档目录的路径
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 访问第一张幻灯片的图表
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // 定义并设置外部工作簿的路径
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**解释：**
- `setExternalWorkbook` 将图表链接到 Excel 文件，允许动态数据更新。

## 实际应用
Aspose.Slides 为各种场景提供了多种解决方案：

1. **商业报告：** 直接从 Java 应用程序创建带有图表的详细报告。
2. **学术报告：** 利用交互式图表增强教育内容。
3. **财务分析：** 将财务数据导出到 Excel 进行深入分析。
4. **营销分析：** 使用动态图表来直观地展示活动效果。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}