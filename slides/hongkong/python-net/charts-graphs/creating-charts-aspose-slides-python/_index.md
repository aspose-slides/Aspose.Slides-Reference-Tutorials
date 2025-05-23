---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 建立和配置令人驚嘆的圖表。按照本逐步指南，在簡報中實現有效的資料視覺化。"
"title": "使用 Aspose.Slides 在 Python 中建立圖表綜合指南"
"url": "/zh-hant/python-net/charts-graphs/creating-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Python 中建立圖表：綜合指南

## 介紹
在簡報中創建視覺上吸引人的圖表可以使數據更易於理解，讓您毫不費力地傳達複雜的訊息。本教學將指導您使用 Aspose.Slides for Python 建立和配置圖表 - 這是一個強大的庫，透過提供強大的圖表操作功能來改變您設計簡報的方式。

**您將學到什麼：**
- 如何在簡報中建立堆積長條圖
- 使用自訂標籤新增和格式化資料系列
- 儲存已配置的簡報

在本教學結束時，您將獲得使用 Aspose.Slides Python 來增強簡報的實作經驗。在我們開始創建一些令人驚嘆的圖表之前，讓我們先深入了解如何設定您的環境！

## 先決條件
在開始之前，請確保您符合以下先決條件：

1. **Python環境：** 您的系統上應該安裝了 Python（建議使用 3.x 版本）。
2. **Python 版 Aspose.Slides：** 可以透過 pip 安裝。
3. **許可證取得：** 雖然可以免費試用，但請考慮取得臨時或完整許可證以解鎖所有功能。

## 為 Python 設定 Aspose.Slides
要開始在您的專案中使用 Aspose.Slides，您需要安裝該程式庫並了解如何設定您的環境：

**安裝：**
```bash
pip install aspose.slides
```

安裝後，您可以透過將其匯入到腳本中來初始化和使用 Aspose.Slides。要充分利用其功能，請取得許可證。可以免費試用，或者如果需要更長的使用時間，請考慮購買或申請臨時許可證。

## 實施指南

### 功能 1：建立並配置帶有圖表的簡報
**概述：** 本節將引導您使用 Aspose.Slides Python 設定簡報投影片並向其中新增圖表。

#### 步驟 1：初始化簡報
首先建立一個新的演示物件。使用 `with` 自動資源管理語句：
```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # 存取簡報中的第一張投影片
    slide = presentation.slides[0]
```

#### 步驟 2：為投影片新增圖表
在這裡，我們在指定位置添加具有定義尺寸的堆積長條圖：
```python
# 在幻燈片中添加堆積長條圖
chart = slide.shapes.add_chart(slides.charts.ChartType.PERCENTS_STACKED_COLUMN, 20, 20, 500, 400)
```

#### 步驟 3：配置圖表軸
設定垂直軸數字格式以更好地表示資料：
```python
# 配置垂直軸數字格式
chart.axes.vertical_axis.is_number_format_linked_to_source = False
chart.axes.vertical_axis.number_format = "0.00%"
```

### 功能 2：向圖表新增和格式化資料系列
**概述：** 本節重點介紹如何新增資料系列、為其填充值以及自訂其外觀。

#### 步驟 1：定義資料工作簿
初始化圖表的資料工作簿：
```python
default_worksheet_index = 0
workbook = chart.chart_data.chart_data_workbook
```

#### 步驟 2：新增並填入資料系列
在圖表中新增一個名為「Reds」的新系列，然後用資料點填滿它：
```python
# 新增系列並填充數據點
series = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 1, "Reds"), chart.type)

for i in range(1, 5):
    series.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 1, [0.30, 0.50, 0.80, 0.65][i-1])
    )
```

#### 步驟 3：設定係列外觀格式
自訂填滿顏色和資料標籤格式：
```python
# 將系列填滿設定為紅色
series.format.fill.fill_type = slides.FillType.SOLID
series.format.fill.solid_fill_color.color = drawing.Color.red

# 配置百分比顯示的資料標籤
series.labels.default_data_label_format.show_value = True
series.labels.default_data_label_format.number_format = "0.0%"
```

### 功能 3：向圖表新增並格式化第二個資料系列
**概述：** 本節擴展了新增具有其自身樣式的第二個資料系列。

#### 步驟 1：新增第二個系列
新增另一個名為「Blues」的系列：
```python
# 新增第二個系列，名為“Blues”
series2 = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 2, "Blues"), chart.type)
```

#### 步驟 2：填滿並格式化系列
用數據點填滿它並套用格式：
```python
# 填充第二個系列
for i in range(1, 5):
    series2.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 2, [0.70, 0.50, 0.20, 0.35][i-1])
    )

# 將填滿設為藍色並配置標籤
series2.format.fill.fill_type = slides.FillType.SOLID
series2.format.fill.solid_fill_color.color = drawing.Color.blue

series2.labels.default_data_label_format.show_value = True
```

### 功能 4：將演示文稿儲存到磁碟
**概述：** 圖表配置完成後，儲存簡報。

#### 步驟 1：儲存您的工作
使用 `save` 儲存檔案的方法：
```python
# 將簡報儲存到磁碟
directory = "YOUR_OUTPUT_DIRECTORY"
presentation.save(f"{directory}/charts_set_data_labels_percentage_sign_out.pptx", slides.export.SaveFormat.PPTX)
```

## 實際應用
使用 Aspose.Slides for Python，您可以增強各個領域的簡報：
1. **商業報告：** 建立帶有動態圖表的詳細季度報告。
2. **教育內容：** 設計具有視覺數據表現形式的引人入勝的教育材料。
3. **銷售示範：** 有效地說明銷售趨勢和預測。

這些範例示範如何將 Aspose.Slides 整合到現有工作流程中以提供精美的簡報。

## 性能考慮
為確保最佳性能：
- 有效地管理內存，特別是在處理圖表中的大型資料集時。
- 利用 Aspose.Slides 進行 Python 資源管理的最佳實務。
- 定期更新您的庫以獲得效能增強。

透過遵循這些提示，您可以在處理複雜的簡報時保持順暢而有效率的操作。

## 結論
在本教學中，我們探討如何使用 Aspose.Slides for Python 在簡報中建立和設定圖表。現在，您已經掌握了將視覺上引人注目的資料視覺化整合到您的專案中的知識。為了進一步提高您的技能，請探索庫的其他功能或嘗試不同的圖表類型。

**後續步驟：** 嘗試在實際專案中實現這些概念以鞏固您的理解。

## 常見問題部分
1. **如何安裝 Aspose.Slides for Python？**
   - 使用 `pip install aspose.slides` 輕鬆下載並安裝。
2. **我可以在不購買許可證的情況下使用 Aspose.Slides 嗎？**
   - 是的，您可以先免費試用，或申請臨時許可證。
3. **是否可以進一步自訂圖表資料標籤？**
   - 絕對地！您可以探索庫的 API 提供的更多格式化選項。
4. **建立圖表時有哪些常見問題？**
   - 確保所有數據點的格式正確並連結到適當的系列。
5. **如何將 Aspose.Slides 與其他系統整合？**
   - 使用其全面的 API 無縫整合到您現有的 Python 專案中。

## 資源
- [文件](https://reference.aspose.com/slides/python-net/)
- [下載](https://releases.aspose.com/slides/python-net/)
- [購買](https://purchase.aspose.com/buy)
- [免費試用](https://releases.aspose.com/slides/python-net/)
- [臨時執照](https://purchase.aspose.com/temporary-license/)
- [支援論壇](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}