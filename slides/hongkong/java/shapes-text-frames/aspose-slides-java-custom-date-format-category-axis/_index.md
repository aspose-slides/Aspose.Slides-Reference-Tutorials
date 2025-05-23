---
"date": "2025-04-17"
"description": "了解如何使用 Aspose.Slides for Java 自訂類別軸的日期格式。透過自訂資料呈現增強您的圖表，非常適合年度報告等。"
"title": "如何在 Aspose.Slides Java 中的類別軸上設定自訂日期格式 |資料視覺化指南"
"url": "/zh-hant/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Aspose.Slides Java 中的類別軸上設定自訂日期格式 |資料視覺化指南

在當今數據驅動的世界中，清晰地呈現資訊對於做出有影響力的決策至關重要。使用 Aspose.Slides for Java 建立圖表時，自訂類別軸上的日期格式可以大大提高理解力和簡報品質。本指南將引導您在 Aspose.Slides 中設定自訂日期格式，以增強投影片的視覺吸引力和資料清晰度。

**您將學到什麼：**
- 設定 Aspose.Slides for Java
- 在分類軸上實現自訂日期格式
- 將 GregorianCalendar 日期轉換為 OLE 自動化日期格式
- 這些功能在現實場景中的實際應用

讓我們深入了解如何輕鬆實現這一目標！

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

### 所需的庫和版本：
- **Aspose.Slides for Java**：您需要 25.4 或更高版本。

### 環境設定要求：
- 能夠運行 Java 程式碼的開發環境（例如 IntelliJ IDEA、Eclipse 或 NetBeans）。
- 在您的專案中設定 Maven 或 Gradle 來管理依賴項。

### 知識前提：
- 對 Java 程式設計有基本的了解。
- 熟悉在簡報中使用圖表組件。

## 設定 Aspose.Slides for Java

若要使用 Aspose.Slides for Java，請將其作為依賴項包含在您的專案中。以下是安裝說明：

**Maven：**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

或者，您可以 [下載最新版本](https://releases.aspose.com/slides/java/) 直接從 Aspose 的官方網站取得。

### 許可證取得：
- **免費試用**：從免費試用開始探索功能。
- **臨時執照**：申請臨時許可證以延長測試時間。
- **購買**：為了長期使用，請考慮購買訂閱。訪問 [Aspose 購買](https://purchase.aspose.com/buy) 了解詳情。

### 基本初始化：

以下是如何在專案中初始化 Aspose.Slides：
```java
import com.aspose.slides.Presentation;
// 實例化代表演示檔案的 Presentation 對象
Presentation pres = new Presentation();
```

現在，讓我們進入本指南的核心！

## 實施指南

### 設定分類軸的日期格式

此功能可讓您自訂日期在圖表類別軸上的顯示方式。以下是詳細指南：

#### 1. 建立新的簡報和圖表
首先建立一個實例 `Presentation` 並新增新的面積圖。
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // 初始化簡報
        Presentation pres = new Presentation();
        
        try {
            // 將面積圖新增至第一張投影片的指定位置和大小
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // 存取圖表數據工作簿以操作圖表數據
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // 清除圖表中的所有現有數據

            // 刪除所有預先存在的類別和系列
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // 使用轉換後的 OLE 自動化日期將日期新增至分類軸
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // 建立新系列並向其中新增資料點
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // 將分類軸類型設定為日期，並配置其數字格式
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // 僅將日期格式化為年份

            // 將簡報儲存到指定目錄
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // OLE 自動化轉換的基準日期
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // 轉換為 OLE 自動化日期
        return String.valueOf(oaDate);
    }
}
```

#### 2. GregorianCalendar 日期到 OLE 自動化日期格式的轉換

Aspose.Slides 需要 OLE 自動化格式的日期，這是一種標準的 Excel 日期格式。以下是如何將 Java `GregorianCalendar` 日期：
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 2021年1月15日
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Excel 的 OLE 自動化基準日期
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### 故障排除提示：
- 確保轉換的基準日期（`30 Dec 1899`) 被正確解析。
- 驗證您的 Java 環境是否支援必要的程式庫和類別。
- 如果出現問題，請檢查 Aspose.Slides 是否有可用的更新或補丁。

### 實際應用

自訂日期格式在以下場景中特別有用：
- **年度報告：** 清晰顯示年度數據趨勢。
- **財務圖表：** 準確呈現財務期間。
- **專案時間表：** 反白顯示特定的時間範圍或里程碑。

透過遵循本指南，您將能夠使用 Aspose.Slides for Java 透過精確且視覺上吸引人的日期格式增強您的簡報。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}