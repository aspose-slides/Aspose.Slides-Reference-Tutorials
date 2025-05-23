---
"date": "2025-04-22"
"description": "了解如何使用 Python 和 Aspose.Slides 建立圓環圖。本逐步指南涵蓋了設定、自訂以及增強簡報的最佳實踐。"
"title": "如何使用 Aspose.Slides 在 Python 中建立甜甜圈圖逐步指南"
"url": "/zh-hant/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides 在 Python 中建立甜甜圈圖：逐步指南

在資料視覺化領域，有效地呈現資訊可以顯著影響理解和決策。無論您是在製作商業簡報還是分析複雜的資料集，圖表都是不可或缺的工具。在各種圖表類型中，環形圖提供了一種具有直覺中心孔的吸引人的方式來表示比例資料。本逐步指南將引導您使用 Aspose.Slides（一個功能強大的簡報處理庫）在 Python 中建立圓環圖。

## 您將學到什麼
- 如何設定和使用 Aspose.Slides for Python
- 在簡報投影片中新增圓環圖的過程
- 自訂圖表中的系列和類別
- 調整標籤、顏色和爆炸效果等視覺元素
- 使用 Aspose.Slides 優化效能的最佳實踐

## 先決條件
在開始之前，請確保您已：
- **Python 環境**：您的機器上安裝了 Python 3.x。
- **Aspose.Slides for Python**：使用 pip 安裝此程式庫。
- **對 Python 程式設計的基本了解**：熟悉循環和物件導向程式設計將會有所幫助。

## 為 Python 設定 Aspose.Slides
首先，透過 pip 安裝 Aspose.Slides 函式庫：

```bash
pip install aspose.slides
```

### 許可證獲取
Aspose 提供免費試用，可在有限時間內無限制地測試功能。為了實現這一點：
1. 訪問 [免費試用](https://releases.aspose.com/slides/python-net/) 頁。
2. 按照說明下載並套用您的臨時許可證。

為了繼續使用，請考慮從 [購買頁面](https://purchase。aspose.com/buy).

### 基本初始化
設定Aspose.Slides後，按如下方式初始化它：

```python
import aspose.slides as slides

# 建立 Presentation 類別的實例。
with slides.Presentation() as pres:
    # 用於操作簡報的程式碼放在這裡。

# 進行更改後儲存簡報。
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## 實施指南
設定 Aspose.Slides 後，請依照下列步驟將環形圖逐張新增至簡報中。

### 建立新簡報並新增投影片
首先創建一個 `Presentation` 班級：

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # 在此上下文中存取或建立幻燈片。
```

### 在第一張投影片中加入圓環圖
存取第一張投影片並使用 `add_chart` 方法。將圖表類型指定為 `DOUGHNUT`，以及位置和大小：

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### 配置圖表數據
清除現有資料並配置隱藏圖例等設定：

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### 新增系列和類別
為圓環圖新增多個系列和類別。以下介紹如何建立具有特定屬性的 15 個系列：

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

類似地新增類別：

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # 為每個系列新增資料點。
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # 自訂每個數據點的外觀。
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # 配置最後一個系列的標籤設定。
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### 儲存簡報
最後，將您的簡報儲存到指定目錄：

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## 實際應用
圓環圖用途廣泛，可用於各種場景，例如：
1. **預算分配**：顯示不同部門如何使用其分配的資金。
2. **市佔率分析**：比較競爭產品或公司的市佔率。
3. **調查結果**：可視化有關偏好或滿意度水準的調查問題的答案。

## 性能考慮
為確保使用 Aspose.Slides 時獲得最佳效能：
- 透過在使用後正確處理物件來最大限度地減少記憶體使用。
- 僅在必要時將簡報載入到記憶體中，並儘快關閉它們。
- 如果您要處理大量圖表，請考慮批次處理投影片。

## 結論
透過遵循本指南，您已經學習如何使用 Aspose.Slides for Python 建立動態甜甜圈圖。這些視覺化可以使數據更易於理解和吸引人，從而增強您的簡報效果。繼續探索庫的功能以進一步自訂和優化您的圖表。

## 常見問題部分
1. **我可以在不購買許可證的情況下使用 Aspose.Slides 嗎？**
   - 是的，您可以從免費試用許可證開始進行評估。
2. **如何在 Aspose.Slides 中更改圖表顏色？**
   - 使用 `fill_format` 屬性來設定圖表元素所需的顏色。
3. **可以將圖表匯出為圖像嗎？**
   - 是的，您可以使用庫的渲染功能將包含圖表的幻燈片渲染為圖像格式。
4. **新增圖表時有哪些常見問題？**
   - 在嘗試儲存或顯示圖表之前，請確保所有資料點和類別都已正確新增。
5. **我可以將 Aspose.Slides 與其他 Python 函式庫整合嗎？**
   - 絕對地！您可以將它與 Pandas 等庫一起使用以增強資料處理功能。

## 資源
- [Aspose.Slides文檔](https://reference.aspose.com/slides/python-net/)
- [下載 Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [購買許可證](https://purchase.aspose.com/buy)
- [免費試用和臨時許可證](https://releases.aspose.com/slides/python-net/)
- [Aspose 社群論壇](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}