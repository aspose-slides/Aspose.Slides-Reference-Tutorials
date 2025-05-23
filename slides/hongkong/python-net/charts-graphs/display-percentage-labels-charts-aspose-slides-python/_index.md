---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides for Python 輕鬆在 PowerPoint 簡報中的圖表上顯示百分比標籤。非常適合增強數據可視化。"
"title": "如何使用 Aspose.Slides for Python 在圖表上顯示百分比標籤&#58;綜合指南"
"url": "/zh-hant/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在圖表上顯示百分比標籤

## 介紹

在演示和報告中，有效地視覺化數據至關重要，尤其是當您想要清晰地突出比例或分佈時。但是如果您需要將這些百分比直接顯示在圖表上該怎麼辦？本綜合指南將指導您使用 **Aspose.Slides for Python** 輕鬆地將百分比值顯示為圖表上的標籤。

### 您將學到什麼：
- 如何使用 Aspose.Slides for Python 在 PowerPoint 簡報中建立和嵌入圖表。
- 在圖表上將資料點顯示為百分比標籤。
- 有效地儲存和管理 PowerPoint 簡報。

準備好開始為您的數據添加富有洞察力的視覺效果了嗎？在深入研究程式碼之前，讓我們先看看您需要什麼！

## 先決條件

在開始之前，請確保您具備以下條件：
- **Aspose.Slides for Python**：此程式庫對於以程式設計方式建立和操作 PowerPoint 簡報至關重要。
- **Python 環境**：對 Python 程式設計和環境設定有基本的了解。
- **PIP 套件管理器**：用於安裝Aspose.Slides。

## 為 Python 設定 Aspose.Slides

要開始使用 Aspose.Slides，您首先需要安裝它：

```bash
pip install aspose.slides
```

### 許可證取得步驟：
您可以開始免費試用或取得臨時授權來探索 Aspose.Slides 的全部功能。如需延長使用時間，請考慮購買訂閱。

#### 基本初始化和設定

安裝完成後，您將像這樣初始化您的演示環境：

```python
import aspose.slides as slides

# 初始化 Presentation 對象
def create_presentation():
    with slides.Presentation() as presentation:
        # 您的程式碼在這裡
```

## 實施指南

現在我們已經設定好了，讓我們深入研究在圖表上顯示百分比。

### 建立圖表並新增數據

#### 概述
我們將創建一個堆積長條圖，每個數據點都有百分比標籤，讓查看者一眼就能看到準確的比例。

##### 步驟 1：為投影片新增圖表

```python
# 存取簡報中的第一張投影片
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # 添加堆積長條圖
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

此程式碼片段為第一張投影片新增了一個基本圖表。這 `add_chart` 方法指定圖表的類型及其位置和大小。

##### 第 2 步：計算類別的總值

```python
def calculate_totals(chart):
    total_for_category = []
    # 對每個類別的所有系列的值進行求和
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

此循環計算整個系列中所有資料點的總和，這對於百分比計算至關重要。

#### 設定百分比標籤

##### 步驟 3：配置系列數據點

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # 設定預設標籤選項以隱藏非必要訊息
        series.labels.default_data_label_format.show_legend_key = False
        
        # 計算並設定百分比標籤
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # 建立帶有百分比值的文字部分
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # 清除現有標籤並新增新的百分比標籤
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # 隱藏其他資料標籤元素
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

此部分處理每個資料點以計算其佔總數的百分比並將其指派為標籤。

### 儲存您的簡報

```python
def save_presentation(presentation, output_directory):
    # 儲存您的簡報並進行修改
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}