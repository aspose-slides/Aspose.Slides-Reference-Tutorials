---
"description": "了解如何使用 Aspose.Slides for Java 設定外部工作簿並更新 Java Slides 中的圖表資料。增強您的 PowerPoint 自動化技能。"
"linktitle": "在 Java Slides 中設定外部工作簿並更新圖表數據"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中設定外部工作簿並更新圖表數據"
"url": "/zh-hant/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中設定外部工作簿並更新圖表數據


## Java 投影片中設定外部工作簿並更新圖表資料的介紹

在本綜合指南中，我們將引導您完成使用 Aspose.Slides for Java API 在 Java Slides 中設定包含更新圖表資料的外部工作簿的過程。這個強大的程式庫可讓您以程式設計方式操作 PowerPoint 簡報，從而輕鬆自動執行從外部來源更新圖表資料等任務。在本教程結束時，您將透過逐步說明和附帶的 Java 程式碼清楚地了解如何完成此任務。

## 先決條件

在深入實施之前，請確保您已滿足以下先決條件：

1. Aspose.Slides for Java：您應該安裝 Aspose.Slides for Java 函式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).

2. Java 開發環境：確保您的系統上已設定 Java 開發環境。

## 步驟 1：建立新簡報

首先，讓我們使用 Aspose.Slides for Java 建立一個新的 PowerPoint 簡報。以下是實現該目的的 Java 程式碼：

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：新增圖表

現在，讓我們在簡報中新增一個圖表。我們將在此範例中建立一個圓餅圖：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## 步驟 3：設定外部工作簿

在這裡我們將外部工作簿設定為圖表的資料來源。您需要提供外部工作簿的 URL，即使它現在不存在：

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://路徑/不存在”，false）；
```

## 步驟 4：儲存簡報

最後，儲存包含更新後的圖表資料的簡報：

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Java 投影片中設定外部工作簿並更新圖表資料的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://路徑/不存在”，false）；
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

恭喜！您已經了解如何使用 Aspose.Slides for Java 在 Java Slides 中設定包含更新圖表資料的外部工作簿。這對於從外部資料來源動態更新 PowerPoint 簡報中的圖表非常有用。

## 常見問題解答

### 如何更新圖表的外部工作簿資料？

若要更新圖表的外部工作簿數據，您只需修改指定 URL 處的外部工作簿中的資料。下次開啟簡報時，Aspose.Slides for Java 將從外部工作簿中取得更新的資料並相應地更新圖表。

### 我可以使用本地文件作為外部工作簿嗎？

是的，您可以透過提供文件路徑而不是 URL 將本機文件用作外部工作簿。只需確保檔案路徑正確並且可以從 Java 應用程式存取即可。

### 使用 Aspose.Slides for Java 的外部工作簿有什麼限制嗎？

雖然使用外部工作簿是一項強大的功能，但請記住，外部工作簿資料的可用性取決於其在提供的 URL 或檔案路徑上的可存取性。確保在開啟簡報時外部資料來源可用，以避免資料擷取問題。

### 設定外部工作簿後可以自訂圖表外觀嗎？

是的，即使在設定外部工作簿之後，您也可以自訂圖表的外觀，包括其標題、標籤、顏色等。 Aspose.Slides for Java 提供了廣泛的圖表格式化選項來滿足您的需求。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多文件和資源？

有關詳細文檔和其他資源，請造訪 Aspose.Slides for Java 文檔 [這裡](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}