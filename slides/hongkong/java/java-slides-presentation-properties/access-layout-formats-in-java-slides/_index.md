---
"description": "了解如何使用 Aspose.Slides for Java 存取和操作 Java Slides 中的佈局格式。在 PowerPoint 簡報中輕鬆自訂形狀和線條樣式。"
"linktitle": "存取 Java Slides 中的佈局格式"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "存取 Java Slides 中的佈局格式"
"url": "/zh-hant/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 存取 Java Slides 中的佈局格式


## Java Slides 中的 Access 版面配置格式簡介

在本教程中，我們將探討如何使用 Aspose.Slides for Java API 存取和使用 Java Slides 中的版面格式。佈局格式可讓您控制簡報佈局投影片中形狀和線條的外觀。我們將介紹如何擷取版面投影片上形狀的填滿格式和線條格式。

## 先決條件

1. Aspose.Slides for Java 函式庫。
2. 帶有佈局幻燈片的 PowerPoint 簡報（PPTX 格式）。

## 步驟 1：載入簡報

首先，我們需要載入包含版面配置投影片的 PowerPoint 簡報。代替 `"Your Document Directory"` 使用您的文件目錄的實際路徑。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## 第 2 步：存取佈局格式

現在，讓我們循環瀏覽簡報中的佈局投影片，並存取每個佈局投影片上形狀的填滿格式和線條格式。

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // 存取形狀的填充格式
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // 訪問形狀的線條格式
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

在上面的程式碼中：

- 我們使用 `for` 環形。
- 對於每個佈局投影片，我們建立陣列來儲存該投影片上形狀的填滿格式和線條格式。
- 我們使用嵌套 `for` 循環遍歷佈局幻燈片上的形狀並檢索它們的填充和線條格式。

## 步驟 3：使用佈局格式

現在我們已經存取了佈局投影片上形狀的填滿格式和線條格式，您可以根據需要對它們執行各種操作。例如，您可以變更形狀的填滿顏色、線條樣式或其他屬性。

## Java 投影片中存取佈局格式的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教程中，我們探討如何使用 Aspose.Slides for Java API 存取和操作 Java Slides 中的版面格式。佈局格式對於控制 PowerPoint 簡報中佈局投影片內形狀和線條的外觀至關重要。

## 常見問題解答

### 如何更改形狀的填滿顏色？

若要變更形狀的填滿顏色，可以使用 `IFillFormat` 對象的方法。以下是一個例子：

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // 將填滿類型設為純色
fillFormat.getSolidFillColor().setColor(Color.RED); // 將填滿色彩設為紅色
```

### 如何更改形狀的線條樣式？

若要變更形狀的線條樣式，可以使用 `ILineFormat` 對象的方法。以下是一個例子：

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // 將線型設定為單線
lineFormat.setWidth(2.0); // 將線寬設定為 2.0 磅
lineFormat.getSolidFillColor().setColor(Color.BLUE); // 將線條顏色設定為藍色
```

### 如何將這些變更套用到版面配置投影片上的形狀？

若要將這些變更套用至版面配置投影片上的特定形狀，您可以使用版面配置投影片的形狀集合中的索引來存取該形狀。例如：

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // 存取佈局投影片上的第一個形狀
```

然後您可以使用 `IFillFormat` 和 `ILineFormat` 使用前面答案中所示的方法來修改形狀的填滿和線條格式。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}