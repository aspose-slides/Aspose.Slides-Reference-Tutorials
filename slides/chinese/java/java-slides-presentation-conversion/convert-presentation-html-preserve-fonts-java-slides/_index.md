---
"description": "使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 HTML，同时保留原始字体。"
"linktitle": "将演示文稿转换为 HTML 并在 Java 幻灯片中保留原始字体"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "将演示文稿转换为 HTML 并在 Java 幻灯片中保留原始字体"
"url": "/zh/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 将演示文稿转换为 HTML 并在 Java 幻灯片中保留原始字体


## Java 幻灯片中如何将演示文稿转换为 HTML 并保留原始字体

在本教程中，我们将探索如何使用 Aspose.Slides for Java 将 PowerPoint 演示文稿 (PPTX) 转换为 HTML，同时保留原始字体。这将确保生成的 HTML 与原始演示文稿的外观非常相似。

## 步骤 1：设置项目
在深入研究代码之前，让我们确保您已完成必要的设置：

1. 下载 Aspose.Slides for Java：如果您还没有下载，请下载并将 Aspose.Slides for Java 库包含在您的项目中。

2. 创建 Java 项目：在您最喜欢的 IDE 中设置一个 Java 项目，并确保您有一个可以放置 Aspose.Slides JAR 文件的“lib”文件夹。

3. 导入所需的类：在 Java 文件的开头导入必要的类：

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 步骤 2：将演示文稿转换为包含原始字体的 HTML

现在，让我们将 PowerPoint 演示文稿转换为 HTML，同时保留原始字体：

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";

// 加载演示文稿
Presentation pres = new Presentation("input.pptx");

try {
    // 排除 Calibri 和 Arial 等默认演示字体
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // 创建 HTML 选项并设置自定义 HTML 格式化程序
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // 将演示文稿保存为 HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // 处置演示对象
    if (pres != null) pres.dispose();
}
```

在此代码片段中：

- 我们使用以下方式加载输入 PowerPoint 演示文稿 `Presentation`。

- 我们定义一个字体列表（`fontNameExcludeList`)，我们想要将其排除在 HTML 嵌入之外。这对于排除 Calibri 和 Arial 等常见字体以减小文件大小很有用。

- 我们创建一个实例 `EmbedAllFontsHtmlController` 并将字体排除列表传递给它。

- 我们创造 `HtmlOptions` 并使用设置自定义 HTML 格式化程序 `HtmlFormatter。createCustomFormatter(embedFontsController)`.

- 最后，我们使用指定的选项将演示文稿保存为 HTML。

## 将演示文稿转换为 HTML 并在 Java 幻灯片中保留原始字体的完整源代码

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// 排除默认演示字体
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java 将 PowerPoint 演示文稿转换为 HTML 格式，同时保留原始字体。当您希望在 Web 上共享演示文稿时保持其视觉保真度时，此功能非常有用。

## 常见问题解答

### 如何下载适用于 Java 的 Aspose.Slides？

您可以从 Aspose 网站下载 Aspose.Slides for Java。访问 [这里](https://downloads.aspose.com/slides/java/) 获取最新版本。

### 我可以自定义排除字体的列表吗？

是的，您可以自定义 `fontNameExcludeList` 数组根据您的要求包含或排除特定字体。

### 此方法适用于 PPT 等较旧的 PowerPoint 格式吗？

此代码示例适用于 PPTX 文件。如果您需要转换较旧的 PPT 文件，则可能需要对代码进行一些调整。

### 我如何进一步自定义 HTML 输出？

您可以探索 `HtmlOptions` 类来定制 HTML 输出的各个方面，例如幻灯片大小、图像质量等等。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}