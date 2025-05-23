---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides for Python 建立箱線圖。增強簡報中的資料視覺化。"
"title": "使用 Aspose.Slides 在 Python 中建立箱線圖"
"url": "/zh-hant/python-net/charts-graphs/create-box-whisker-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Python 中建立箱線圖

## 如何使用 Aspose.Slides for Python 建立箱線圖

透過學習如何使用強大的 Aspose.Slides 庫建立箱線圖來增強您的資料視覺化技能。這些圖表非常適合顯示統計分佈，使複雜的數據一目了然。

**您將學到什麼：**
- 使用 Aspose.Slides for Python 設定您的環境
- 建立和自訂箱線圖
- 實際應用和整合機會
- 提升效能的優化技巧

## 先決條件

在開始之前，請確保您已準備好以下內容：
- **Python 版 Aspose.Slides：** 建立和處理 PowerPoint 簡報必不可少的庫。
- **Python環境：** 您需要一個可以運行的 Python 安裝（最好是 Python 3.x）。
- **基本 Python 知識：** 熟悉 Python 程式設計將幫助您更輕鬆地跟進。

## 為 Python 設定 Aspose.Slides

### 安裝訊息

首先，使用 pip 安裝 Aspose.Slides 函式庫：

```bash
pip install aspose.slides
```

### 許可證取得步驟

Aspose 提供不同的授權選項：
- **免費試用：** 下載臨時許可證以探索全部功能，不受評估限制。
- **臨時執照：** 非常適合短期專案或測試目的。
- **購買：** 如果您需要持續訪問，請取得永久許可證。

您可以透過以下方式取得這些許可證 [購買頁面](https://purchase.aspose.com/buy) 或申請免費試用 [臨時執照頁面](https://purchase。aspose.com/temporary-license/).

### 基本初始化和設定

安裝後，初始化 Aspose.Slides for Python 以開始處理簡報。設定環境的方法如下：

```python
import aspose.slides as slides

# 初始化演示實例
def setup_presentation():
    with slides.Presentation() as pres:
        # 在此執行新增圖表等操作
        pass
```

## 實施指南

在本節中，我們將指導您建立箱線圖。

### 在簡報中新增箱線圖

#### 概述

為了在簡報中有效地視覺化數據，請使用 Aspose.Slides for Python 建立箱線圖。這種圖表類型非常適合顯示分佈和識別異常值。

#### 逐步實施

1. **建立新的簡報：**
   
   首先初始化一個新的演示實例：
   
   ```python
   import aspose.slides as slides
   
   def create_box_and_whisker_chart():
       # 建立新的演示實例
       with slides.Presentation() as pres:
           # 在後續步驟中新增圖表
           pass
   ```

2. **將圖表新增到投影片中：**
   
   將箱型圖插入所需位置：
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           # 在第一張投影片上的位置 (50, 50) 處新增一個箱型圖，大小為 (500, 400)
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
   ```

3. **清除現有資料：**
   
   在新增資料之前，請確保圖表是空的：
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           
           # 清除所有現有類別和系列數據
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)  # 清除工作簿以輸入新數據
   ```

4. **在圖表中新增類別：**
   
   用類別填滿圖表：
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           # 定義圖表資料的類別
           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))
   ```

5. **配置系列：**
   
   使用所需的屬性設定您的系列：
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           # 新增系列並配置其屬性
           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           # 定義系列的數據點
           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))
   ```

6. **儲存簡報：**
   
   使用新新增的圖表儲存您的工作：
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))

           # 儲存簡報
           pres.save("YOUR_OUTPUT_DIRECTORY/charts_box_chart_out.pptx", slides.export.SaveFormat.PPTX)

   create_box_and_whisker_chart()
   ```

### 故障排除提示

- **檢查庫安裝：** 確保 `aspose.slides` 已正確安裝。
- **驗證許可證設定：** 如果您遇到限制，請確保您的許可證文件設定正確。
- **語法錯誤：** 仔細檢查程式碼語法中是否有任何拼字錯誤或錯誤。

## 實際應用和整合機會

箱線圖廣泛用於商業分析，以簡潔的方式呈現統計資料。它們有助於識別資料集內的趨勢、異常值和變化，使其成為簡報、報告和儀表板的理想選擇。

將 Aspose.Slides 與 Python 集成，可以以程式設計方式無縫建立豐富的互動式 PowerPoint 簡報，增強您傳達資料驅動見解的方式。

## 提升效能的優化技巧

- **簡化資料輸入：** 在產生圖表之前，請確保您的資料集乾淨且結構良好，以避免在視覺化過程中出現錯誤。
- **優化圖表自訂：** 明智地使用 Aspose.Slides 的自訂選項來增強圖表的可讀性，而不會因過多的元素而使簡報超載。
- **自動執行重複任務：** 利用 Python 腳本自動執行重複性任務（例如資料格式化和圖表生成），從而節省時間並減少錯誤。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}