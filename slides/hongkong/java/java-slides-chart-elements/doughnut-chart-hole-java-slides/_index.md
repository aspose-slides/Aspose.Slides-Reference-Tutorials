---
title: Java 投影片中的圓環圖孔
linktitle: Java 投影片中的圓環圖孔
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides for Java 在 Java 投影片中建立具有自訂孔尺寸的圓環圖。帶有圖表自訂原始程式碼的分步指南。
weight: 11
url: /zh-hant/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的圓環圖孔


## Java 投影片中帶洞的圓環圖簡介

在本教程中，我們將指導您使用 Aspose.Slides for Java 建立帶孔的圓環圖。本逐步指南將透過原始程式碼範例引導您完成整個過程。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。您可以從[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/).

## 第 1 步：導入所需的庫

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 第 2 步：初始化簡報

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";

//建立Presentation類別的實例
Presentation presentation = new Presentation();
```

## 第 3 步：建立圓環圖

```java
try {
    //在第一張投影片上建立圓環圖
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    //設定圓環圖中孔的大小（以百分比表示）
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    //將簡報儲存到磁碟
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    //處理演示對象
    if (presentation != null) presentation.dispose();
}
```

## 第 4 步：運行程式碼

在 IDE 或文字編輯器中執行 Java 程式碼以建立具有指定孔大小的圓環圖。確保更換`"Your Document Directory"`與您要儲存簡報的實際路徑。

## Java 投影片中圓環圖孔的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	//將簡報寫入磁碟
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 建立有孔的圓環圖。您可以透過調整來自訂孔的大小`setDoughnutHoleSize`方法參數。

## 常見問題解答

### 如何更改圖表部分的顏色？

若要變更圖表部分的顏色，您可以使用`setDataPointsInLegend`方法上的`IChart`物件並為每個數據點設定所需的顏色。

### 我可以為圓環圖分段加上標籤嗎？

是的，您可以使用以下指令為圓環圖段新增標籤`setDataPointsLabelValue`方法上的`IChart`目的。

### 是否可以為圖表添加標題？

當然！您可以使用以下命令向圖表新增標題`setTitle`方法上的`IChart`物件並提供所需的標題文字。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
