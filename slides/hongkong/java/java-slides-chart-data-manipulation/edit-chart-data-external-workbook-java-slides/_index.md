---
title: 在 Java 投影片中編輯外部工作簿中的圖表數據
linktitle: 在 Java 投影片中編輯外部工作簿中的圖表數據
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 編輯外部工作簿中的圖表資料。帶有原始程式碼的分步指南。
weight: 17
url: /zh-hant/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## 在 Java 投影片中編輯外部工作簿中的圖表資料簡介

在本指南中，我們將示範如何使用 Aspose.Slides for Java 編輯外部工作簿中的圖表資料。您將學習如何以程式設計方式修改 PowerPoint 簡報中的圖表資料。確保您的專案中安裝並配置了適用於 Java 的 Aspose.Slides 程式庫。

## 先決條件

- 用於 Java 的 Aspose.Slides
- Java開發環境

## 第 1 步：載入簡報

首先，我們需要載入包含要編輯其資料的圖表的 PowerPoint 簡報。代替`"Your Document Directory"`與簡報文件的實際路徑。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 第 2 步：存取圖表

載入簡報後，我們需要存取簡報中的圖表。在此範例中，我們假設圖表位於第一張投影片上，並且是該投影片上的第一個形狀。

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 第三步：修改圖表數據

現在，我們來修改圖表資料。我們將重點放在更改圖表中的特定數據點。在本範例中，我們將第一個系列中的第一個資料點的值設為 100。

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 第 4 步：儲存簡報

對圖表資料進行必要的變更後，將修改後的簡報儲存到新文件中。您可以根據需要指定輸出檔案路徑和格式。

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## 第 5 步：清理

不要忘記處理演示對像以釋放任何資源。

```java
if (pres != null) pres.dispose();
```

現在，您已使用 Aspose.Slides for Java 成功編輯了 PowerPoint 簡報中外部工作簿中的圖表資料。您可以自訂此程式碼以滿足您的特定需求並將其整合到您的 Java 應用程式中。

## 完整的原始碼

```java
        //請注意，外部工作簿的路徑幾乎不會儲存在簡報中
        //因此，請在執行範例之前從 Data/Chart 目錄 D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ 複製檔案 externalWorkbook.xlsx
        //文檔目錄的路徑。
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

在本綜合指南中，我們探討如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中編輯外部工作簿中的圖表資料。透過遵循逐步說明和原始程式碼範例，您已經獲得了以程式設計方式輕鬆修改圖表資料的知識和技能。

## 常見問題解答

### 如何指定不同的圖表或投影片？

若要存取不同的圖表或投影片，請修改對應的索引`getSlides().get_Item()`和`getShapes().get_Item()`方法。請記住，索引從 0 開始。

### 我可以在同一簡報中編輯多個圖表中的資料嗎？

是的，您可以透過對每個圖表重複圖表資料修改步驟來編輯同一簡報中多個圖表中的資料。

### 如果我想編輯具有不同格式的外部工作簿中的資料該怎麼辦？

您可以使用適當的 Aspose.Cells 類別和方法來調整程式碼以處理不同的外部工作簿格式，以讀取和寫入該格式的資料。

### 如何針對多個簡報自動執行此程序？

您可以建立一個循環來處理多個演示文稿，載入每個演示文稿，進行所需的更改，然後逐一儲存修改後的簡報。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
