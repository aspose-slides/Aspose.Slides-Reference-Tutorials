---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 簡報中新增和自訂圓餅圖。透過本逐步指南節省時間並確保一致性。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中新增和自訂圓餅圖"
"url": "/zh-hant/python-net/charts-graphs/add-customize-pie-charts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中新增和自訂圓餅圖

## 介紹
創建視覺上吸引人的簡報至關重要，尤其是當您需要簡潔地傳達複雜數據時。無論是財務報告或績效指標，圓餅圖都可以成為一目了然地說明比例的有效工具。但是，手動將這些圖表添加到幻燈片中可能非常耗時，而且容易出現不一致。

使用 Aspose.Slides Python 函式庫，流程的自動化變得無縫。本教學將引導您使用 Aspose.Slides for Python 輕鬆在 PowerPoint 簡報中新增和自訂圓餅圖。透過遵循，您不僅可以節省時間，還可以確保投影片的一致性。

**您將學到什麼：**
- 如何在投影片中加入圓餅圖
- 設定餅圖的標題和居中文本
- 配置資料系列和類別以獲得詳細見解
- 為不同的切片啟用自動顏色變化

讓我們深入了解如何有效地實現這些功能。開始之前，請確保您的環境已正確設定。

## 先決條件
要遵循本教程，您需要：
- 您的機器上安裝了 Python（建議使用 3.x 版本）
- Python 的 Aspose.Slides 函式庫
- 對 Python 程式設計和 PowerPoint 簡報有基本的了解

確保您具有執行 Python 腳本所需的必要設定。如果沒有，請考慮從以下位置安裝 Python [python.org](https://www。python.org/downloads/).

## 為 Python 設定 Aspose.Slides
要開始在專案中使用 Aspose.Slides，請透過 pip 安裝它：

```bash
pip install aspose.slides
```

### 許可證取得步驟
Aspose 提供其庫的免費試用。您可以下載臨時許可證以不受限制地探索全部功能。開始：
- 訪問 [Aspose 的購買頁面](https://purchase.aspose.com/buy) 購買選項。
- 透過以下方式獲得臨時許可證 [臨時許可證頁面](https://purchase。aspose.com/temporary-license/).

### 基本初始化
以下是如何在 Python 腳本中初始化 Aspose.Slides：

```python
import aspose.slides as slides

# 初始化 Presentation 類別來建立或開啟簡報文件
with slides.Presentation() as presentation:
    # 您的程式碼在此處
    pass
```

透過此設置，您就可以開始在簡報中新增圓餅圖。

## 實施指南

### 為投影片新增圓餅圖
#### 概述
新增基本餅圖需要建立新的形狀類型 `Chart` 在你的幻燈片上。本節將引導您完成新增預設餅圖的步驟。

#### 步驟
1. **存取第一張投影片**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **新增圓餅圖形狀**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

   - 參數： `ChartType.PIE` 指定圖表類型。
   - 座標和尺寸定義餅圖的位置和大小。

3. **儲存簡報**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_add_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 設定餅圖標題和中心文本
#### 概述
使用標題自訂餅圖可以增強其可讀性並為檢視者提供背景資訊。

#### 步驟
1. **存取第一張投影片**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **新增圖表並設定標題**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   # 設定標題
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

3. **儲存簡報**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_pie_chart_title_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 配置圓餅圖資料系列和類別
#### 概述
為了使餅圖更具資訊量，您需要在其中輸入實際資料。

#### 步驟
1. **存取第一張投影片**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **配置數據**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   fact = chart.chart_data.chart_data_workbook
   
   # 清除現有數據
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()
   
   # 新增帶有資料點的類別和系列
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   
   # 新增數據點
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 3, 1, 30))
   ```

3. **儲存簡報**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_configure_pie_chart_data_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 啟用自動餅圖切片顏色
#### 概述
透過自動改變切片顏色來增強視覺吸引力可以使您的圖表更具吸引力。

#### 步驟
1. **存取第一張投影片**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **啟用顏色變化**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   series = chart.chart_data.series[0]
   series.parent_series_group.is_color_varied = True
   ```

3. **儲存簡報**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_enable_automatic_pie_slice_colors_out.pptx", slides.export.SaveFormat.PPTX)
   ```

## 實際應用
1. **商業報告**：使用圓餅圖顯示競爭對手之間的市佔率分佈。
2. **教育材料**：說明課程涵蓋的不同主題的百分比。
3. **財務分析**：顯示費用類別佔總預算的比例。
4. **行銷洞察**：依人口統計或偏好對客戶進行視覺化細分。

與 Pandas 等數據分析工具的整合可以進一步自動化該過程，從而可以在簡報中進行即時更新。

## 性能考慮
使用 Aspose.Slides 和 Python 時：
- 優化程式碼以有效管理內存，尤其是在處理大型資料集時。
- 避免對展示對象進行冗餘操作。
- 使用 `with` 用於上下文管理的語句，以確保資源在使用後得到適當釋放。

## 結論
現在您已經全面了解如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂圓餅圖。透過自動執行這些任務，您可以顯著提高生產力，同時確保簡報的一致性。 

為了進一步實現這一點，探索整合動態資料來源或自動產生整個幻燈片。

## 關鍵字推薦
- “Aspose.Slides for Python”
- “PowerPoint 圓餅圖”
- “使用 Python 自動化 PowerPoint 圖表”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}