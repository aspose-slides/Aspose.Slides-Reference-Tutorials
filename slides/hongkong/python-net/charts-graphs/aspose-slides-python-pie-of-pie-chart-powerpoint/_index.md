---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 簡報中建立和自訂圓餅圖，從而增強您的資料視覺化技能。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中建立餅狀圖"
"url": "/zh-hant/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中建立餅狀圖

建立具有視覺吸引力的圖表（例如圓餅圖）可以使複雜資訊更易於理解，從而顯著增強您的 PowerPoint 簡報。本教學將指導您使用 Aspose.Slides for Python 建立圓餅圖。

## 您將學到什麼

- 為 Python 設定 Aspose.Slides
- 使用圓餅圖建立 PowerPoint 簡報的步驟
- 配置資料標籤和系列組選項以提高可讀性
- 餅圖中餅圖在簡報中的實際應用

讓我們深入了解如何設定您的環境並實現這些功能。

### 先決條件

在開始之前，請確保您已準備好以下內容：

- **Python安裝**：建議使用 Python 3.6 或更高版本。
- **Aspose.Slides for Python**：使用 pip 安裝：
  ```bash
  pip install aspose.slides
  ```
- **執照**：從 Aspose 取得免費試用許可證，以無限制地探索全部功能。

#### 知識前提

熟悉 Python 程式設計的基本知識並了解 PowerPoint 簡報將會很有幫助。如果您對這些內容還不熟悉，請考慮先探索一下入門資源。

### 為 Python 設定 Aspose.Slides

若要開始使用 Aspose.Slides for Python，請依照以下簡單步驟操作：

1. **安裝**：使用 pip 安裝庫：
   ```bash
   pip install aspose.slides
   ```

2. **許可證獲取**： 
   - 訪問 [Aspose 的購買頁面](https://purchase.aspose.com/buy) 購買許可證或獲得臨時免費試用。
   - 使用以下程式碼片段在您的專案中應用您的許可證：
     ```python
     import aspose.slides as slides

     # 載入許可證文件
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **基本初始化**：
   首先匯入 Aspose.Slides 並啟動示範物件。

### 實施指南

#### 功能一：使用圖表建立簡報

此功能將示範如何建立 PowerPoint 簡報並在第一張投影片中新增圓餅圖。

##### 新增圖表

首先建立一個新的簡報，並在第一張投影片上的位置 (50, 50) 新增一個圓餅圖：

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # 添加具有指定尺寸的“圓餅圖”
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### 配置資料標籤

為了增強可讀性，配置資料標籤以顯示值：

```python
# 啟用資料標籤中的值顯示以提高清晰度
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### 設定圓餅圖選項

配置圓餅圖中的圓餅圖的特定屬性，例如第二個圓餅圖的大小和分割位置：

```python
# 設定第二個圓餅圖的大小和分割屬性
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### 儲存簡報

最後，將您的簡報儲存到所需的目錄：

```python
# 將簡報與圖表一起保存
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### 實際應用

圓餅圖用途廣泛，可用於各種場景：

1. **商業報告**：可視化不同部門或產品之間的資料分佈。
2. **學術項目**：目前調查結果顯示主要主題以及不太重要的發現。
3. **財務分析**：在預算報告中比較主要費用和次要成本。

### 性能考慮

為了在使用 Aspose.Slides 時獲得最佳性能：

- 如果可能的話，盡量減少投影片和圖表的數量，以減少記憶體使用量。
- 定期清理程式碼中未使用的資源或參考。
- 使用 Python 的內建垃圾收集器（`gc` 使用“記憶體管理模組”來有效地管理記憶體。

### 結論

您已經學習如何使用 Aspose.Slides for Python 建立具有圓餅圖的 PowerPoint 簡報。這項技能可以大大增強簡報的視覺吸引力和效能。考慮探索 Aspose.Slides 中的更多功能，例如添加動畫或整合多媒體元素。

### 後續步驟

- 嘗試 Aspose.Slides 中可用的不同圖表類型。
- 將此功能整合到更大的演示自動化工作流程中。

### 常見問題部分

**Q：我可以自訂餅圖的顏色嗎？**
答：是的，您可以使用 `fill_format` 每個段的屬性。

**Q：如何使用 Aspose.Slides 處理大型資料集？**
答：優化您的資料輸入並考慮將其分成更小的區塊以保持效能。

**Q：有沒有辦法可以一次自動新增多個圖表？**
答：是的，循環遍歷資料集並使用 `add_chart` 單一表示上下文中的方法。

### 資源

- **文件**：查看詳細指南 [Aspose.Slides文檔](https://reference。aspose.com/slides/python-net/).
- **下載**：從取得最新版本 [發布](https://releases。aspose.com/slides/python-net/).
- **購買和免費試用**：存取許可證選項 [Aspose 購買](https://purchase.aspose.com/buy) 或嘗試 [免費試用](https://releases。aspose.com/slides/python-net/).
- **支援**加入討論 [Aspose 論壇](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}