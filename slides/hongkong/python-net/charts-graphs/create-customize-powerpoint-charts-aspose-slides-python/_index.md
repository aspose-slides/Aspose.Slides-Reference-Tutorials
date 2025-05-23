---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂圖表。輕鬆使用專業的視覺效果增強您的簡報。"
"title": "使用 Aspose.Slides for Python 掌握 PowerPoint 圖表&#58;輕鬆建立和自訂"
"url": "/zh-hant/python-net/charts-graphs/create-customize-powerpoint-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Python 掌握 PowerPoint 中的圖表建立和自訂

## 介紹
無論您是在董事會會議室進行簡報還是與客戶分享數據見解，創建具有視覺吸引力的簡報對於有效溝通至關重要。挑戰通常在於在 PowerPoint 投影片中整合能夠準確表示資料的引人注目的圖表。和 **Aspose.Slides for Python**，這項任務變得無縫且有效率。

在本綜合教學中，我們將探討如何使用 Aspose.Slides Python 輕鬆建立和自訂 PowerPoint 圖表。這個強大的庫提供了強大的功能，可以透過專業品質的視覺效果增強您的簡報。

**您將學到什麼：**
- 如何設定 Aspose.Slides for Python
- 在投影片中建立折線圖
- 修改現有圖表數據
- 使用影像設定自訂標記
- 這些技術的實際應用

準備好提升您的 PowerPoint 圖表了嗎？讓我們深入了解先決條件並開始吧！

## 先決條件
在我們開始之前，請確保您擁有必要的工具和知識：

1. **Python 安裝**：請確保您的系統上安裝了 Python（建議使用 3.6 或更高版本）。
2. **Aspose.Slides for Python**：透過 pip 安裝：
   ```bash
   pip install aspose.slides
   ```
3. **開發環境**：使用 VSCode 或 PyCharm 等 IDE 進行更好的程式碼管理。
4. **Python 基礎知識**：熟悉 Python 語法和程式設計概念至關重要。

## 為 Python 設定 Aspose.Slides
首先，您需要在開發環境中設定 Aspose.Slides for Python：

### 安裝
使用 pip 安裝庫：
```bash
pip install aspose.slides
```

### 許可證獲取
Aspose.Slides 提供不同的授權選項：
- **免費試用**：測試功能有限的功能。
- **臨時執照**：取得免費臨時許可證，以便在測試期間存取全部功能。
- **購買**：為了持續使用，請考慮購買訂閱。

**基本初始化和設定：**
```python
import aspose.slides as slides

# 初始化Presentation對象
with slides.Presentation() as presentation:
    # 在此處新增程式碼來操作簡報
    pass
```

## 實施指南
讓我們將實現分解為三個主要特徵：

### 建立並添加圖表
#### 概述
此功能示範如何在 PowerPoint 投影片中新增標記的折線圖。

**步驟：**
1. **開啟簡報**：先開啟一個新的或現有的簡報。
2. **選擇幻燈片**：選擇要新增圖表的投影片。
3. **新增折線圖**： 使用 `add_chart` 方法插入圖表。
4. **儲存簡報**：使用更新的幻燈片儲存您的變更。

**程式碼實作：**
```python
import aspose.slides as slides

def add_chart_to_slide():
    # 開啟新的簡報
    with slides.Presentation() as presentation:
        # 選擇第一張投影片
        slide = presentation.slides[0]
        
        # 在選定的幻燈片上，以 (0, 0) 為位置，以 (400, 400) 為大小添加帶有標記的折線圖
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # 將新增圖表的簡報儲存到磁碟
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### 修改圖表數據
#### 概述
了解如何清除現有資料並為圖表新增新的點系列。

**步驟：**
1. **訪問圖表**：從投影片中檢索圖表。
2. **清除現有系列**：刪除任何預先存在的資料系列。
3. **新增數據點**：將新資料插入系列中。
4. **儲存變更**：保留對演示文件的變更。

**程式碼實作：**
```python
import aspose.slides as slides

def modify_chart_data():
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        chart = slide.shapes.add_chart(slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400)
        
        # 存取圖表資料的預設工作表索引
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # 清除圖表中所有現有系列
        chart.chart_data.series.clear()
        
        # 在圖表中新增具有指定名稱和類型的新系列
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # 存取圖表資料中的第一個（也是唯一一個）系列
        series = chart.chart_data.series[0]
        
        # 在系列中新增資料點並設定其值
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.value = 4.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.value = 2.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 3, 1, 3.5))
        point.value = 3.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 4, 1, 4.5))
        point.value = 4.5
        
        # 將更新後的簡報儲存到磁碟
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### 使用圖像設定圖表標記
#### 概述
透過為資料點設定自訂影像標記來增強您的圖表。

**步驟：**
1. **新增折線圖**：在投影片中插入折線圖。
2. **載入圖片**：從文件目錄新增用作標記的影像。
3. **設定圖像標記**：將這些影像應用於系列上的特定資料點。
4. **調整標記大小**：自訂圖像標記的大小以獲得更好的可見性。

**程式碼實作：**
```python
import aspose.slides as slides

def set_chart_markers_with_images():
    # 開啟新的簡報
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        
        # 在選定的幻燈片上，以 (0, 0) 為位置，以 (400, 400) 為大小添加帶有標記的折線圖
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # 存取圖表資料的預設工作表索引
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # 清除圖表中所有現有系列並新增系列
        chart.chart_data.series.clear()
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # 存取圖表資料中的第一個（也是唯一一個）系列
        series = chart.chart_data.series[0]
        
        # 載入圖像並將其添加到簡報的圖像集合中
        image1 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image1.jpg")
        imgx1 = presentation.images.add_image(image1)
        
        image2 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image2.jpg")
        imgx2 = presentation.images.add_image(image2)
        
        # 新增數據點並設定其標記圖像
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx1
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx2
        
        # 將帶有自訂標記的簡報儲存到磁碟
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_with_image_markers_out.pptx", slides.export.SaveFormat.PPTX)
```

## 結論
透過學習本教程，您現在已經掌握了使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂圖表的堅實基礎。無論是新增新的資料系列還是使用影像標記增強視覺化效果，這些技術都將幫助您創建更具影響力的簡報。

## 關鍵字推薦
- “Aspose.Slides for Python”
- “PowerPoint 圖表自訂”
- “使用 Python 在 PowerPoint 中建立圖表”
- “Python 演示增強”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}