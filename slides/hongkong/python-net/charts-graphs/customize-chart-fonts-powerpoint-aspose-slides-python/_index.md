---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides 和 Python 自訂 PowerPoint 簡報中的圖表字體。請依照本指南了解詳細步驟和實際應用。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中自訂圖表字體"
"url": "/zh-hant/python-net/charts-graphs/customize-chart-fonts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中自訂圖表字體

## 介紹
您是否希望使用 Python 增強 PowerPoint 簡報中圖表的視覺吸引力？你並不孤單！許多開發人員在嘗試以程式設計方式自訂圖表字體時面臨挑戰。本指南將引導您使用下列方法設定 PowerPoint 中圖表的字型屬性 **Aspose.Slides for Python**。透過掌握這些技巧，您可以毫不費力地創建視覺上引人注目且專業的幻燈片。

在本教程中，我們將介紹：
- 為 Python 設定 Aspose.Slides
- 輕鬆自訂圖表字體
- 適用於您專案的實際應用

讓我們開始確保您已準備好一切！

### 先決條件
在深入研究之前，請確保您已滿足以下先決條件：
1. **Python 環境**：確保您已安裝 Python（版本 3.6 或更高版本）。
2. **Aspose.Slides for Python**：您需要這個庫來操作 PowerPoint 文件。
3. **基礎知識**：熟悉 Python 程式設計並對使用函式庫有基本的了解將會有所幫助。

## 為 Python 設定 Aspose.Slides
首先，您需要安裝 `aspose.slides` 使用 pip 的庫：

```bash
pip install aspose.slides
```

### 許可證取得步驟
- **免費試用**：從下載免費試用版 [Aspose 官方網站](https://releases。aspose.com/slides/python-net/).
- **臨時執照**：如需進行更廣泛的測試，請透過其取得臨時許可證 [購買頁面](https://purchase。aspose.com/temporary-license/).
- **購買**：如果您發現該工具非常符合您的需求，請考慮從 [Aspose購買網站](https://purchase。aspose.com/buy).

安裝並獲得許可後，在 Python 中初始化 Aspose.Slides：

```python
import aspose.slides as slides

# 使用 slides.Presentation() 初始化 Presentation 物件作為 pres:
    # 您的程式碼在此處
```

## 實施指南
在本節中，我們將逐步探討如何設定圖表字體屬性。

### 添加簇狀長條圖
首先，讓我們在簡報中加入一個聚集長條圖：

```python
# 在指定的位置和大小添加簇狀長條圖。
chart = pres.slides[0].shapes.add_chart(
    slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 500, 400
)
```
**解釋**：此程式碼片段將新圖表新增至簡報的第一張投影片中。這 `add_chart` 此方法要求您指定圖表類型及其在投影片上的位置和大小。

### 設定字體屬性
接下來，讓我們設定圖表中文字的字體高度：

```python
# 設定圖表中文字的字體高度。
chart.text_format.portion_format.font_height = 20
```
**解釋**：此行調整圖表中所有文字部分的字體大小。這 `font_height` 屬性以點為單位指定，您可以調整此值以滿足您的設計需求。

### 顯示數據標籤
為了增強可讀性，我們將在數據標籤上顯示值：

```python
# 在第一個系列的資料標籤上顯示值。
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```
**解釋**：此設定可確保第一個系列中的每個資料點都顯示其值。這對於一眼傳達精確的訊息特別有用。

### 儲存您的簡報
最後，將簡報儲存到所需位置：

```python
# 將簡報儲存到指定的輸出目錄。
pres.save(
    "YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_chart_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}