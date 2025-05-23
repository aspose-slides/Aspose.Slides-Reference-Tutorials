---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂圓餅圖。利用數據驅動的洞察力增強您的簡報。"
"title": "使用 Aspose.Slides for Python 建立引人入勝的 PowerPoint 圓餅圖 |圖表和圖形教學"
"url": "/zh-hant/python-net/charts-graphs/aspose-slides-python-powerpoint-pie-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Python 建立 PowerPoint 圓餅圖

**類別：** 圖表和圖形

創建引人入勝且資訊豐富的簡報是有效傳達數據驅動見解的關鍵。如果您希望透過添加視覺上吸引人的圓餅圖來增強 PowerPoint 投影片的效果， **Aspose.Slides for Python** 庫是一個簡化此過程的優秀工具。在本教學中，我們將引導您使用 Aspose.Slides for Python 在 PowerPoint 中建立圓餅圖。

## 您將學到什麼：
- 安裝並設定 Aspose.Slides for Python
- 在 PowerPoint 投影片中建立基本圓餅圖
- 使用數據點、顏色、邊框、標籤、引線和旋轉自訂餅圖
- 優化使用圖表時的效能

讓我們深入了解開始所需的步驟。

## 先決條件

在實施程式碼之前，請確保您已具備以下條件：
- 系統上安裝了 Python（建議使用 3.6 或更高版本）
- `pip` 用於安裝庫的套件管理器
- 對 Python 程式設計和 PowerPoint 簡報有基本的了解

## 為 Python 設定 Aspose.Slides

要開始使用 Aspose.Slides for Python，您需要使用 pip 安裝程式庫：

```bash
pip install aspose.slides
```

**許可證取得：**
您可以從下載免費試用許可證開始 [Aspose的下載頁面](https://releases.aspose.com/slides/python-net/)。為了更廣泛的使用，請考慮購買完整許可證或取得臨時許可證以用於評估目的。

### 基本初始化和設定

安裝 Aspose.Slides 後，在 Python 腳本中導入必要的模組：

```python
import aspose.slides as slides
import aspose.pydrawing as drawing
```

## 實施指南

在本節中，我們將餅圖的建立分解為詳細步驟。

### 建立和自訂餅圖

#### 概述
建立圓餅圖涉及初始化簡報物件、新增投影片，然後插入帶有自訂資料點和視覺元素的圖表。

#### 建立圓餅圖的步驟

1. **實例化表示類**
   首先建立一個演示實例。這將作為您的投影片和圖表的容器。

   ```python
   with slides.Presentation() as presentation:
       # 存取第一張投影片
       slide = presentation.slides[0]
   ```

2. **在投影片中加入圓餅圖**
   使用 `add_chart` 方法在投影片上的指定座標處插入圓餅圖。

   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

3. **設定圖表標題**
   使用適當的標題自訂圖表並將其格式化以使文字居中。

   ```python
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

4. **存取圖表資料工作簿**
   使用 `chart_data_workbook` 管理和自訂您的資料類別和系列。

   ```python
   fact = chart.chart_data.chart_data_workbook
   default_worksheet_index = 0

   # 清除所有現有系列或類別
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()

   # 新增類別（季度）
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   # 新增系列
   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   ```

5. **用數據點填滿系列**
   將資料點插入您的系列中以表示圓餅圖的不同部分。

   ```python
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 3, 1, 30))
   ```

6. **將多種顏色應用於圖表**
   使用不同的顏色自訂每個餅圖切片。

   ```python
   chart.chart_data.series_groups[0].is_color_varied = True

   # 定義一個函數來自定義點的外觀
   def customize_point(point, fill_color, line_color):
       point.format.fill.fill_type = slides.FillType.SOLID
       point.format.fill.solid_fill_color.color = drawing.Color(fill_color)
       
       point.format.line.fill_format.fill_type = slides.FillType.SOLID
       point.format.line.fill_format.solid_fill_color.color = drawing.Color(line_color)
       point.format.line.width = 3.0
       point.format.line.style = slides.LineStyle.THIN_THICK
       point.format.line.dash_style = slides.LineDashStyle.DASH_DOT
   
   # 自訂第一個數據點的外觀
   customize_point(series.data_points[0], "Cyan", "Gray")
   ```

7. **自訂資料點標籤**
   調整標籤設定以顯示數值、百分比或系列名稱。

   ```python
   def customize_label(point, show_value=True, show_legend_key=False,
                       show_percentage=False, show_series_name=False):
       lbl = point.label
       lbl.data_label_format.show_value = show_value
       lbl.data_label_format.show_legend_key = show_legend_key
       lbl.data_label_format.show_percentage = show_percentage
       lbl.data_label_format.show_series_name = show_series_name
   
   # 設定第一個資料點的標籤屬性
   customize_label(series.data_points[0], True)
   ```

8. **啟用引線並旋轉圓餅圖**
   為了增強可讀性，請根據需要啟用引線並旋轉切片。

   ```python
   series.labels.default_data_label_format.show_leader_lines = True

   # 將第一個圓餅圖旋轉 180 度
   chart.chart_data.series_groups[0].first_slice_angle = 180
   ```

9. **儲存簡報**
   最後，儲存應用了所有自訂設定的簡報。

   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 故障排除提示
- 確保 Aspose.Slides 已正確安裝和匯入。
- 檢查方法名稱或參數中是否有任何拼字錯誤，因為這些可能會導致錯誤。
- 驗證儲存輸出檔案的目錄路徑是否存在。

## 實際應用

餅圖用途廣泛，可用於多個領域：
1. **商業分析**：可視化不同產品或服務之間的收入分配。
2. **行銷報告**：顯示特定產業中競爭對手的市場佔有率。
3. **教育演示**：展示與學生表現或人口統計相關的統計資料。

## 性能考慮
- 透過優化圖表元素和減少不必要的複雜性來最大限度地減少資源使用。
- 處理圖表的大型資料集時使用高效的資料結構。
- 透過在使用後及時釋放資源來有效地管理記憶體。

## 結論

透過遵循本指南，您已經學習如何使用 Aspose.Slides for Python 在 PowerPoint 中建立圓餅圖。現在您可以將這些技術應用到您的簡報中並探索進一步的自訂選項。考慮整合其他圖表類型或利用其他 Aspose.Slides 功能來增強您的資料視覺化技能。

### 後續步驟
- 嘗試不同的圖表自訂
- 探索動態報告中圖表的集成
- 深入了解 Aspose.Slides 文檔，以了解更多高級功能

## 常見問題部分

1. **什麼是 Aspose.Slides？**
   - 一個強大的庫，允許以程式設計方式建立和操作 PowerPoint 簡報。
2. **我可以免費使用 Aspose.Slides 嗎？**
   - 是的，您可以從試用許可證開始，或在購買之前評估其功能。
3. **我還可以建立哪些其他圖表類型？**
   - 除了圓餅圖，您還可以使用 Aspose.Slides 建立長條圖、折線圖、散佈圖等。

## 關鍵字推薦
- “Aspose.Slides for Python”
- “PowerPoint 圓餅圖”
- 《Python PowerPoint 圖表》

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}