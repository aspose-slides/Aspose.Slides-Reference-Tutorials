---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 調整簡報中圖表標題的旋轉角度，增強可讀性和美觀性。"
"title": "如何在 Aspose.Slides for Python 中設定圖表的垂直軸標題旋轉"
"url": "/zh-hant/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Aspose.Slides for Python 中設定圖表的垂直軸標題旋轉

## 介紹

在數據呈現中，提高圖表的可讀性至關重要。使用 Aspose.Slides for Python 調整圖表垂直軸標題的旋轉角度可以使標題整齊地適合或在幻燈片中脫穎而出。本教學將指導您設定此旋轉角度，以增強功能和視覺吸引力。

**您將學到什麼：**
- 如何安裝和設定 Aspose.Slides for Python。
- 在投影片中新增和自訂圖表的步驟。
- 設定圖表標題旋轉角度的技巧。
- 這些功能在資料視覺化中的實際應用。

在深入實施之前，我們先來了解先決條件。

## 先決條件

在開始之前，請確保您已：
- **Python 環境**：從安裝 Python 3.x [python.org](https://www。python.org/).
- **Aspose.Slides 庫**：透過 pip 安裝以有效地操作簡報。
- **Python程式設計基礎知識**：熟悉 Python 語法和檔案操作將幫助您跟上。

## 為 Python 設定 Aspose.Slides

要使用 Aspose.Slides，請使用 pip 安裝它。打開終端機或命令提示字元並運行：

```bash
pip install aspose.slides
```

### 許可證取得步驟

Aspose 提供不同的許可證選項：
- **免費試用**：從下載試用版 [Aspose 的發佈頁面](https://releases。aspose.com/slides/python-net/).
- **臨時執照**：透過取得擴充功能的臨時許可證 [購買門戶](https://purchase。aspose.com/temporary-license/).
- **購買**：如果您認為該工具不可或缺，請考慮購買，可從 [Aspose購買頁面](https://purchase。aspose.com/buy).

#### 基本初始化和設定

以下是在 Python 腳本中初始化 Aspose.Slides 的方法：

```python
import aspose.slides as slides

# 建立演示對象
def main():
    with slides.Presentation() as pres:
        # 您的程式碼將放在此處
        pass

if __name__ == "__main__":
    main()
```

## 實施指南

### 新增和自訂圖表

#### 概述

在本節中，我們將向您的投影片新增簇狀長條圖，並透過設定其垂直軸標題的旋轉角度對其進行自訂。

#### 步驟：

##### 步驟 1：新增簇狀長條圖

首先在特定座標處新增具有定義尺寸的圖表：

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # 向投影片 1 新增簇狀長條圖
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### 步驟 2：配置垂直軸標題

啟用並設定垂直軸標題的旋轉角度：

```python
def configure_chart(chart):
    # 啟用垂直軸標題
    chart.axes.vertical_axis.has_title = True
    
    # 將旋轉角度設定為90度
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### 步驟 3：儲存簡報

最後，儲存變更後的簡報：

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # 儲存簡報
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}