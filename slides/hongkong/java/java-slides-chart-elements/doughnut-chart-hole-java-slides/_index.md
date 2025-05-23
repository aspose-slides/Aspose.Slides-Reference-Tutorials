---
"description": "使用 Aspose.Slides for Java 在 Java Slides 中建立具有自訂孔大小的甜甜圈圖。帶有圖表自訂原始程式碼的分步指南。"
"linktitle": "Java 投影片中的甜甜圈圖漏洞"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的甜甜圈圖漏洞"
"url": "/zh-hant/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的甜甜圈圖漏洞


## Java 投影片中的孔甜甜圈圖介紹

在本教程中，我們將指導您使用 Aspose.Slides for Java 建立有孔的甜甜圈圖。本逐步指南將透過原始程式碼範例引導您完成整個過程。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從 [Aspose.Slides for Java 文檔](https://reference。aspose.com/slides/java/).

## 步驟 1：導入所需的庫

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 步驟 2：初始化簡報

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 建立 Presentation 類別的實例
Presentation presentation = new Presentation();
```

## 步驟 3：建立圓環圖

```java
try {
    // 在第一張投影片上建立圓環圖
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // 設定圓環圖中孔的大小（百分比）
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // 將簡報儲存到磁碟
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // 處置演示對象
    if (presentation != null) presentation.dispose();
}
```

## 步驟 4：運行程式碼

在 IDE 或文字編輯器中執行 Java 程式碼以建立具有指定孔徑的圓環圖。確保更換 `"Your Document Directory"` 與您想要儲存簡報的實際路徑。

## Java 投影片中甜甜圈圖洞的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立 Presentation 類別的實例
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// 將簡報寫入磁碟
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 建立有孔的甜甜圈圖。您可以透過調整 `setDoughnutHoleSize` 方法參數。

## 常見問題解答

### 如何更改圖表部分的顏色？

若要變更圖表段的顏色，您可以使用 `setDataPointsInLegend` 方法 `IChart` 物件並為每個數據點設定所需的顏色。

### 我可以為環形圖的各個部分加上標籤嗎？

是的，您可以使用 `setDataPointsLabelValue` 方法 `IChart` 目的。

### 可以為圖表添加標題嗎？

當然！您可以使用 `setTitle` 方法 `IChart` 物件並提供所需的標題文字。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}