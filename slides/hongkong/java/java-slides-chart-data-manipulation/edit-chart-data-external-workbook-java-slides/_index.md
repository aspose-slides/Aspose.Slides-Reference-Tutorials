---
"description": "了解如何使用 Aspose.Slides for Java 編輯外部工作簿中的圖表資料。帶有原始程式碼的分步指南。"
"linktitle": "在 Java Slides 中的外部工作簿中編輯圖表數據"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中的外部工作簿中編輯圖表數據"
"url": "/zh-hant/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中的外部工作簿中編輯圖表數據


## Java Slides 中編輯外部工作簿中的圖表資料簡介

在本指南中，我們將示範如何使用 Aspose.Slides for Java 編輯外部工作簿中的圖表資料。您將學習如何以程式設計方式修改 PowerPoint 簡報中的圖表資料。確保您已在專案中安裝並配置了 Java 的 Aspose.Slides 程式庫。

## 先決條件

- Aspose.Slides for Java
- Java開發環境

## 步驟 1：載入簡報

首先，我們需要載入包含我們要編輯資料的圖表的 PowerPoint 簡報。代替 `"Your Document Directory"` 使用您的簡報文件的實際路徑。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 第 2 步：存取圖表

簡報載入完成後，我們需要存取簡報中的圖表。在這個例子中，我們假設圖表在第一張投影片上，並且是該投影片上的第一個形狀。

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 步驟3：修改圖表數據

現在，讓我們修改圖表資料。我們將重點放在改變圖表中的特定數據點。在這個例子中，我們將第一個系列中第一個資料點的值設為100。您可以根據需要調整這個值。

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 步驟 4：儲存簡報

對圖表資料進行必要的變更後，將修改後的簡報儲存到新文件中。您可以根據需要指定輸出檔案的路徑和格式。

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## 步驟5：清理

不要忘記處理演示對像以釋放任何資源。

```java
if (pres != null) pres.dispose();
```

現在，您已成功使用 Aspose.Slides for Java 在 PowerPoint 簡報中的外部工作簿中編輯圖表資料。您可以自訂此程式碼以滿足您的特定需求並將其整合到您的 Java 應用程式中。

## 完整的原始碼

```java
        // 請注意，簡報中幾乎不會儲存外部工作簿的路徑
        // 因此，請在執行範例之前從 Data/Chart 目錄 D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ 複製檔案 externalWorkbook.xlsx
        // 文檔目錄的路徑。
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 結論

在本綜合指南中，我們探討如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中的外部工作簿中編輯圖表資料。透過遵循逐步說明和原始程式碼範例，您已經獲得了以程式設計方式輕鬆修改圖表資料的知識和技能。

## 常見問題解答

### 如何指定不同的圖表或投影片？

若要存取不同的圖表或投影片，請修改 `getSlides().get_Item()` 和 `getShapes().get_Item()` 方法。請記住索引從 0 開始。

### 我可以在同一個簡報中編輯多個圖表中的資料嗎？

是的，您可以透過對每個圖表重複圖表資料修改步驟來編輯同一簡報中多個圖表中的資料。

### 如果我想編輯具有不同格式的外部工作簿中的資料怎麼辦？

您可以使用適當的 Aspose.Cells 類別和方法來讀取和寫入該格式的數據，從而調整程式碼以處理不同的外部工作簿格式。

### 我怎麼能自動執行多個簡報的這個過程？

您可以建立一個循環來處理多個演示文稿，載入每個演示文稿，進行所需的更改，然後逐一儲存修改後的簡報。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}