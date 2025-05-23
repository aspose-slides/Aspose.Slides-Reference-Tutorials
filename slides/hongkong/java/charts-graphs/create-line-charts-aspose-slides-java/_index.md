---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides 在 Java 中建立標記的折線圖。本教程涵蓋圖表創建、系列添加以及有效保存簡報。"
"title": "使用 Aspose.Slides for Java 建立具有預設標記的折線圖"
"url": "/zh-hant/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Java 建立具有預設標記的折線圖
## 介紹
創建具有視覺吸引力且資訊豐富的圖表對於簡報、報告和儀表板至關重要。在軟體開發中自動化此過程可以節省時間並確保文件之間的一致性。本教學課程示範如何使用 Aspose.Slides for Java 建立標記的折線圖。
**Aspose.Slides for Java** 是一個功能強大的庫，使開發人員能夠以程式設計方式操作 PowerPoint 簡報，而無需安裝 Microsoft Office。它簡化了創建、編輯和匯出幻燈片等任務，使其成為自動文件生成的重要工具。
**您將學到什麼：**
- 如何初始化 Aspose.Slides for Java
- 建立標記的折線圖的步驟
- 在圖表中新增系列和類別
- 配置圖表圖例
- 儲存簡報
準備好了嗎？首先，請確保您已設定好一切！
## 先決條件
在開始之前，請確保您的開發環境已準備就緒：
1. **庫和依賴項：**
   - Aspose.Slides for Java 函式庫（建議 25.4 版本）
   - Java 開發工具包 (JDK) 16 或更高版本
2. **環境設定：**
   - 您的 IDE 應該支援 Maven 或 Gradle 建置工具。
   - 如果需要，請確保您擁有有效的許可證文件。
3. **知識前提：**
   - 對 Java 程式設計有基本的了解
   - 熟悉使用 Maven 或 Gradle 建置項目
有了這些，讓我們為您的專案設定 Aspose.Slides！
## 設定 Aspose.Slides for Java
要使用 Aspose.Slides for Java，您需要將其作為依賴項包含在您的專案中。根據您使用的是 Maven 還是 Gradle，設定會略有不同。
### Maven
將以下相依性新增至您的 `pom.xml` 文件：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
將其包含在您的 `build.gradle` 文件：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 直接下載
或者，您可以從 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).
**許可證取得步驟：**
- 如需免費試用，請訪問 [免費試用頁面](https://releases。aspose.com/slides/java/).
- 若要取得臨時許可證，請導航至 [臨時執照頁面](https://purchase。aspose.com/temporary-license/).
- 透過他們的購買完整許可證 [購買門戶](https://purchase。aspose.com/buy).
**基本初始化：**
以下是如何在 Java 應用程式中初始化 Aspose.Slides：
```java
import com.aspose.slides.Presentation;
// 初始化新的展示對象
Presentation pres = new Presentation();
```
現在，讓我們開始建立圖表！
## 實施指南
### 功能 1：使用預設標記建立圖表
本節示範如何建立附有標示的折線圖。此功能對於有效地視覺化資料趨勢至關重要。
#### 新增折線圖
若要新增標記的折線圖：
```java
import com.aspose.slides.*;
// 存取第一張投影片
ISlide slide = pres.getSlides().get_Item(0);
// 在投影片中位置 (10, 10) 處新增標示的折線圖，大小為 (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### 清算系列和類別
重新開始：
```java
// 清除現有系列和類別，確保一切順利
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// 取得圖表的資料工作簿以進行進一步操作
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### 功能2：新增系列和類別
添加系列和類別對於用有意義的數據填充圖表至關重要。
#### 建立新系列
若要新增名為「系列 1」的新系列：
```java
// 在圖表中新增系列
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// 存取第一個系列的資料填充
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### 填充類別和數據點
若要新增類別和相應的資料點：
```java
// 新增類別名稱及其各自的資料點
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// 優雅地處理空數據點
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### 功能 3：新增第二個系列並填入資料點
添加額外的系列可以為您的圖表提供更多的深度。
#### 建立並填滿第二個系列
若要新增“系列 2”：
```java
// 新增另一個名為「系列 2」的系列
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// 存取第二個系列的資料填充
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// 為「系列 2」新增資料點
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### 功能四：配置圖表圖例
配置圖例可增強圖表的可讀性。
#### 調整圖例設定
配置方法：
```java
// 啟用圖例並將其設定為不覆蓋在資料點上
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### 功能 5：儲存簡報
圖表準備好後，將簡報儲存到文件中。
```java
try {
    // 將修改後的簡報儲存到指定目錄
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## 實際應用
1. **業務報告：**
   - 使用財務報告中的圖表來描述一段時間內的趨勢。
2. **數據分析：**
   - 在分析階段可視化資料模式和相關性。
3. **教育材料：**
   - 為學術講座或簡報建立資訊幻燈片。
4. **專案管理：**
   - 使用視覺化圖表元素增強專案時間表。
5. **行銷簡報：**
   - 使用圖表有效地顯示銷售趨勢和活動結果。
## 結論
您已經學習如何使用 Aspose.Slides 在 Java 中建立標記的折線圖、新增系列和類別、設定圖例以及儲存簡報。這些技能對於在各種專業應用程式中創建動態視覺內容非常有價值。
要了解有關 Aspose.Slides 功能的更多資訊或尋求社區支持，請訪問他們的 [官方文檔](https://docs.aspose.com/slides/java/) 或加入 Stack Overflow 等論壇。
編碼愉快！

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}