---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂圓環圖。本教學涵蓋設定孔大小、儲存簡報和最佳實務。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中建立自訂孔徑的甜甜圈圖"
"url": "/zh-hant/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中建立自訂孔徑的甜甜圈圖

## 介紹
在 PowerPoint 中建立視覺上吸引人的圖表可以讓您的資料更具吸引力且更易於理解。一個常見的挑戰是以程式方式產生這些圖表時缺乏自訂選項。本教學透過示範如何使用 Aspose.Slides for Python 建立具有自訂孔徑大小的甜甜圈圖來解決此問題。

**關鍵字：** Aspose.Slides Python，圓環圖，自訂孔徑

### 您將學到什麼：
- 設定並使用 Aspose.Slides for Python
- 在 PowerPoint 中建立圓環圖
- 自訂圓環圖的孔徑
- 保存和匯出簡報的最佳實踐

## 先決條件
在開始之前，請確保您已：
- **Python 3.x** 安裝在您的系統上。
- Python 程式設計概念的基本知識。
- 這 `aspose.slides` 庫（下面提供安裝說明）。

## 為 Python 設定 Aspose.Slides
首先，使用 pip 安裝 Aspose.Slides for Python：

```bash
pip install aspose.slides
```

### 許可證獲取
Aspose 提供免費試用，讓您可以探索其功能，不受文件數量或使用時間的限制：
- **免費試用：** 從臨時許可證開始測試全部功能。
- **臨時執照：** 可用於評估目的。
- **購買：** 為了長期使用，請考慮購買許可證。

安裝和設定完成後，您可以開始以程式設計方式建立簡報。初始化 Aspose.Slides 的方法如下：

```python
import aspose.slides as slides

# 初始化演示對象
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # 您的程式碼在此處
```

## 實施指南
本節詳細介紹了使用 Aspose.Slides 在 PowerPoint 中建立和自訂圓環圖所需的步驟。

### 步驟 1：存取和修改投影片
首先，存取簡報的第一張投影片。您將在此處新增自訂圓環圖。

```python
# 存取第一張投影片
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### 步驟2：新增圓環圖
您可以透過指定其位置和大小將圓環圖新增至任何投影片。在這裡，我們將其放置在座標 (50, 50) 處，尺寸為 400x400。

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # 新增圓環圖
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### 步驟3：自訂孔尺寸
調整圓環圖的孔徑很簡單。將其設為 90% 以獲得明顯的效果。

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # 設定自訂孔尺寸
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### 步驟4：儲存簡報
最後，使用所選的檔案名稱將簡報儲存到所需位置。

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # 儲存簡報
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## 實際應用
建立自訂圓環圖在各種情況下都很有用，包括：
- **商業報告：** 透過視覺上不同的部分突顯關鍵績效指標。
- **教育內容：** 向學生或同事說明統計數據。
- **行銷材料：** 展示產品細項或客戶人口統計資料。

透過將圖表匯出為圖像或使用 Aspose 的綜合 API 將其嵌入到 Web 應用程式中，可以與其他系統整合。

## 性能考慮
使用 Aspose.Slides 時，請考慮以下提示以獲得最佳效能：
- 僅載入必要的幻燈片以最大限度地減少資源使用。
- 使用後立即關閉演示文稿，有效管理記憶體。
- 利用批次一次產生多個圖表。

遵循最佳實務可確保您的應用程式平穩且有效率地運作。

## 結論
透過遵循本指南，您已經學習如何使用 Aspose.Slides for Python 在 PowerPoint 中建立具有自訂孔大小的圓環圖。這不僅增強了簡報的視覺吸引力，而且還提供了更大的數據表示靈活性。

為了進一步探索 Aspose.Slides 的功能，請考慮嘗試其他圖表類型和示範功能。編碼愉快！

## 常見問題部分
1. **我可以為環形圖設定的最大孔徑是多少？**
   - 您可以將其設為 100% 以獲得完整的圓形圖表。
2. **我可以使用 Aspose.Slides 修改 PowerPoint 檔案中的現有圖表嗎？**
   - 是的，您可以載入和編輯現有的簡報。
3. **儲存簡報時如何處理錯誤？**
   - 確保輸出路徑可寫入並檢查權限問題。
4. **除了環形圖之外，還支援其他圖表類型嗎？**
   - 當然，Aspose.Slides 支援多種圖表類型。
5. **Aspose.Slides 可以與 Web 應用程式一起使用嗎？**
   - 是的，它的 API 可以整合到後端系統並透過 Web 服務公開。

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