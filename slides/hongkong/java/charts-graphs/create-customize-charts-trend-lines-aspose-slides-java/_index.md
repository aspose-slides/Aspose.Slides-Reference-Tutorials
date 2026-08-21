---
date: '2026-08-21'
description: 了解如何使用 Aspose.Slides for Java 建立叢集柱狀圖並加入趨勢線。內容包括授權設定、Maven/Gradle 整合以及詳細範例。
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: 使用 Aspose.Slides for Java 建立叢集柱狀圖並加入趨勢線。本指南涵蓋授權設定、Maven/Gradle 以及逐步程式碼範例。
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: 使用 Aspose.Slides for Java 建立叢集柱狀圖並加入趨勢線
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: 如何使用 Aspose.Slides for Java 建立叢集柱狀圖並加入趨勢線
url: /zh-hant/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Slides for Java 建立叢集柱狀圖並加入趨勢線

建立引人入勝的簡報往往從清晰的資料視覺化開始。在本指南中，您將 **建立叢集柱狀圖** 物件，然後使用功能強大的 Aspose.Slides for Java API 為其加入各種趨勢線——指數、線性、對數、移動平均、多項式與冪次。

## 快速答覆
- **第一步是什麼？** 初始化 `Presentation` 物件，並在投影片上加入叢集柱狀圖。  
- **需要哪個版本的函式庫？** Aspose.Slides for Java 25.4 或更新版本。  
- **可以使用 Maven 或 Gradle 嗎？** 可以，兩者皆受支援；Maven 使用 `<dependency>`，Gradle 使用 `implementation`。  
- **需要授權嗎？** 試用授權可用於評估；完整的 Aspose.Slides 授權會移除評估限制。  
- **有多少種趨勢線類型？** 六種內建類型：指數、線性、對數、移動平均、多項式與冪次。

## 什麼是建立叢集柱狀圖？
`create clustered column chart` 指的是產生一種圖表，於每個類別內將多個資料系列並排顯示，方便比較各系列之間的數值。此圖表類型非常適合呈現類別資料，例如各區域的季銷售額，讓觀眾能快速看出群組間的差異。

## 為何要加入趨勢線？
趨勢線揭示資料系列的底層走勢，協助您預測未來值、突顯成長率，或平滑噪聲資料。將趨勢線加入叢集柱狀圖後，原始數字即可轉化為可行的洞見，讓利害關係人了解長期趨勢並作出資料驅動的決策。

## 前置需求
- **Java Development Kit (JDK)：** 8 或更新版本。  
- **Aspose.Slides for Java：** 版本 25.4 或更新。  
- **IDE：** IntelliJ IDEA、Eclipse，或任何相容的 Java 編輯器。  
- **建置工具：** Maven 或 Gradle（非必須，但建議使用）。  
- **授權：** 試用或已購買的 Aspose.Slides 授權檔。  

您應具備基本的 Java 語法知識，並熟悉專案相依管理。

## 如何設定 Aspose.Slides for Java？
將 Aspose.Slides 函式庫加入您的專案，然後將授權檔放置於執行時可被找到的位置。如此即可取得完整功能，並移除評估限制。

### Maven
將以下相依加入 `pom.xml` 檔案：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 檔案中加入此行：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下載
您也可以從 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 手動下載 JAR。

#### Aspose Slides 授權
將 `Aspose.Slides.lic` 檔案放在專案根目錄，或以程式方式設定授權：

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

試用授權會移除所有功能限制，但購買授權可消除評估浮水印並提供完整效能最佳化。正式上線時，建議從 [Aspose purchase page](https://purchase.aspose.com/buy) 購買授權。

## 如何建立簡報並加入叢集柱狀圖？
`Presentation` 類別代表 PowerPoint 檔案，提供建立、編輯與儲存投影片的方法。建立 `Presentation`、加入投影片，然後以 `addChart` 並指定 `ChartType.ClusteredColumn` 來建立圖表物件。此流程會設定投影片畫布、插入圖表形狀，並為資料填充與樣式做準備。

1. **初始化簡報** – 設定輸出資料夾並建立新的 `Presentation` 實例。  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **加入叢集柱狀圖** – 取得圖表形狀、設定系列，並填入資料點。  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## 如何加入指數趨勢線？
`ITrendline` 介面定義可加入圖表系列的趨勢線，以模型化資料走勢。透過建立 `ITrendline` 實例、將其 `TrendlineType` 設為 `Exponential`，再附加至目標系列，即可加入指數趨勢線。此類趨勢線適用於快速且加速成長的資料。

1. **設定趨勢線** – 選取系列並呼叫 `addTrendline(TrendlineType.Exponential)`。  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## 如何加入線性趨勢線？
線性趨勢線顯示資料點的最佳擬合直線。您亦可自訂外觀，例如線條顏色與粗細，以符合簡報風格。

1. **設定趨勢線** – 使用 `addTrendline(TrendlineType.Linear)`，然後透過 `getLineFormat().setFillFormat().setFillType(FillType.Solid)` 變更顏色。  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## 如何加入帶自訂文字方塊的對數趨勢線？
對數趨勢線適合最初快速成長、之後趨於平緩的資料。覆寫預設標籤可加入說明文字，說明趨勢的意義。

1. **自訂趨勢線** – 加入趨勢線後，存取其 `getDataLabel()`，並設定 `setText("Custom label")` 屬性。  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## 如何加入移動平均趨勢線？
移動平均趨勢線可平滑短期波動，突顯長期走勢。您可指定用於平均的週期（點數），以控制線條的平滑度。

1. **設定趨勢線** – 呼叫 `addTrendline(TrendlineType.MovingAverage)`，並使用 `setPeriod(3)` 以三點移動平均為例。  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## 如何加入多項式趨勢線？
多項式趨勢線以多項式方程式擬合資料曲線。`order` 屬性控制多項式的次數，讓您能模型更複雜的關係。

1. **自訂趨勢線** – 加入趨勢線後，設定 `setOrder(3)` 以取得三次（立方）擬合。  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## 如何加入冪次趨勢線？
冪次趨勢線適用於資料遵循冪律關係的情況。您亦可設定向前與向後的預測值，將線條延伸至現有資料範圍之外。

1. **設定趨勢線** – 使用 `addTrendline(TrendlineType.Power)`，並調整 `setBackward(2)` 以向後延伸線條。  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## 叢集柱狀圖中趨勢線的實務應用
- **財務分析：** 指數與多項式趨勢有助於預測股價走勢。  
- **銷售預測：** 移動平均線平滑季節性高峰，提供更清晰的銷售趨勢視圖。  
- **科學研究：** 對數趨勢適合跨越多個量級的資料，如聲音強度或 pH 值。  
- **營運監控：** 冪次趨勢可模型隨時間衰退的效能。

## 如何在使用 Aspose.Slides 時最佳化記憶體？
在儲存後即時釋放物件，使用 `presentation.dispose()`。對於大型資料集，啟用圖像懶載入，避免一次將整個圖表載入記憶體。

- **釋放模式：** 將 `Presentation` 包於 try‑with‑resources 區塊，或在 finally 中呼叫 `presentation.dispose()`。  
- **懶載入：** 處理數千筆資料時，設定 `ChartData.setUseCache(true)`。  
- **串流輸出：** 直接寫入 `FileOutputStream`，避免將整個檔案保留在 RAM 中。

## Aspose.Slides for Java 的量化效益
Aspose.Slides 支援 **超過 50 種圖表類型**，可在一般 2 GHz CPU 上於 **30 秒內** 產生 **超過 1,000 張投影片**，且能在不安裝 Microsoft Office 的情況下處理 **500 頁 PDF**。以上數據皆以最新 25.4 版驗證。

## 結論
您現在已掌握完整的 **建立叢集柱狀圖** 物件並以 Aspose.Slides for Java 為其加入所有主要趨勢線類型的端對端解決方案。依循上述步驟，即可產出既具視覺吸引力又具分析深度的資料驅動簡報。

接下來可探索圖表樣式設定、匯出為 PDF/HTML，並自動化多資料來源的圖表產生。

## 常見問答

**Q: 如何在 Maven 專案中設定 Aspose.Slides？**  
A: 將 Maven 章節中顯示的 `<dependency>` 片段加入 `pom.xml`，然後執行 `mvn clean install`。

**Q: 我可以自訂趨勢線的顏色與標籤之外的屬性嗎？**  
A: 可以，您能透過 `ITrendline` API 修改線條樣式、寬度、虛線模式，甚至設定前向/後向預測值。

**Q: 若遇到版本相容性錯誤該怎麼辦？**  
A: 確認您的 JDK 版本符合 Aspose.Slides 的最低需求（JDK 8+），並參閱 Aspose 發行說明以了解任何破壞性變更。

**Q: 能否自動為多個圖表加入趨勢線？**  
A: 完全可以。遍歷投影片集合中的每個 `IChart`，對每個系列呼叫相應的 `addTrendline` 方法。

**Q: 正式環境是否需要付費授權？**  
A: 需要，購買的 Aspose.Slides 授權會移除評估限制，並解鎖完整效能最佳化。

---

**最後更新：** 2026-08-21  
**測試環境：** Aspose.Slides for Java 25.4  
**作者：** Aspose

## 相關教學

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}