---
"description": "使用 Aspose.Slides for Java 為 Java Slides 中的各個圖例自訂字體樣式、大小和顏色，增強 PowerPoint 簡報。"
"linktitle": "Java 投影片中單一圖例的字體屬性"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中單一圖例的字體屬性"
"url": "/zh-hant/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中單一圖例的字體屬性


## Java 投影片中單一圖例的字體屬性介紹

在本教程中，我們將探討如何使用 Aspose.Slides for Java 為 Java Slides 中的單一圖例設定字體屬性。透過自訂字體屬性，您可以使 PowerPoint 簡報中的圖例更具視覺吸引力和資訊量。

## 先決條件

在開始之前，請確保已將 Aspose.Slides for Java 庫整合到您的專案中。您可以從 [Aspose.Slides for Java 文檔](https://reference。aspose.com/slides/java/).

## 步驟 1：初始化簡報並新增圖表

首先，讓我們初始化一個 PowerPoint 簡報並在其中新增一個圖表。在此範例中，我們將使用簇狀長條圖作為說明。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // 其餘代碼在此處
} finally {
    if (pres != null) pres.dispose();
}
```

代替 `"Your Document Directory"` 使用您的 PowerPoint 文件所在的實際目錄。

## 步驟 2：自訂圖例的字體屬性

現在，讓我們自訂圖表中單一圖例條目的字體屬性。在此範例中，我們針對的是第二個圖例條目（索引 1），但您可以根據特定要求調整索引。

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

每行程式碼的作用如下：

- `get_Item(1)` 檢索第二個圖例條目（索引 1）。您可以變更索引以定位不同的圖例條目。
- `setFontBold(NullableBool.True)` 將字體設定為粗體。
- `setFontHeight(20)` 將字體大小設定為 20 點。
- `setFontItalic(NullableBool.True)` 將字體設定為斜體。
- `setFillType(FillType.Solid)` 指定圖例條目文字應具有實心填充。
- `getSolidFillColor().setColor(Color.BLUE)` 將填滿顏色設定為藍色。您可以替換 `Color.BLUE` 用您想要的顏色。

## 步驟 3：儲存修改後的簡報

最後，將修改後的簡報儲存到新檔案以保留您的變更。

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

代替 `"output.pptx"` 使用您喜歡的輸出檔名。

就是這樣！您已成功使用 Aspose.Slides for Java 自訂 Java Slides 簡報中單一圖例條目的字型屬性。

## Java 投影片中單一圖例的字體屬性完整原始碼

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 自訂 Java Slides 中單一圖例的字體屬性。透過調整字體樣式、大小和顏色，您可以增強 PowerPoint 簡報的視覺吸引力和清晰度。

## 常見問題解答

### 我怎麼能更改字體顏色？

若要變更字體顏色，請使用 `tf.getPortionFormat().getFontColor().setColor(yourColor)` 而不是改變填充顏色。代替 `yourColor` 使用所需的字體顏色。

### 如何修改其他圖例屬性？

您可以修改圖例的其他各種屬性，例如位置、大小和格式。有關使用圖例的詳細信息，請參閱 Aspose.Slides for Java 文件。

### 我可以將這些變更套用到多個圖例條目嗎？

是的，您可以循環遍歷圖例條目，並透過調整索引將這些變更套用至多個條目 `get_Item(index)` 並重複自訂程式碼。

釋放資源後，請記得處置演示對象：

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}