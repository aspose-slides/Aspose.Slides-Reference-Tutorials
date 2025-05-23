---
"date": "2025-04-24"
"description": "了解如何透過使用 Aspose.Slides for Python 設定本地字體高度來自訂文本，從而增強簡報的視覺吸引力。"
"title": "使用 Aspose.Slides for Python 設定簡報中的本機字體高度"
"url": "/zh-hant/python-net/formatting-styles/aspose-slides-python-local-font-heights/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Python 設定簡報中的本機字體高度

在當今這個以簡報為主導的世界裡，客製化幻燈片至關重要。無論您是向投資者推銷還是在會議上演講，您的演講方式與您演講的內容一樣重要。那就是 **Aspose.Slides for Python** 提供工具來輕鬆創建視覺震撼的簡報。本教學將指導您使用 Aspose.Slides 設定文字框架內的局部字體高度 - 此功能可確保您的關鍵訊息脫穎而出。

## 您將學到什麼
- 如何在單一文字框架內設定不同的字體高度。
- 在 Aspose.Slides 中建立和操作文字方塊的步驟。
- 使用 Python 和 Aspose.Slides 優化簡報的最佳實務。

在開始簡報客製化之旅之前，讓我們先介紹一下先決條件！

### 先決條件
在開始之前，請確保您已具備以下條件：
- **Aspose.Slides for Python**：操作 PowerPoint 投影片所需的主要庫。我們將很快介紹安裝和設定。
- **Python 環境**：對 Python 程式設計的基本了解至關重要。
- **開發設定**：確保您的環境（例如，IDE 或文字編輯器）支援 Python。

### 為 Python 設定 Aspose.Slides
#### 安裝
首先，您需要安裝 Aspose.Slides 函式庫。這可以透過 pip 輕鬆完成：
```bash
pip install aspose.slides
```
此命令將為您的系統下載並安裝最新版本的 Aspose.Slides。

#### 許可證獲取
為了獲得完整功能，建議取得許可證：
- **免費試用**：從免費試用開始探索所有功能。
- **臨時執照**：如果您需要更多時間進行評估，請申請臨時許可證。
- **購買**：為了長期使用，請考慮購買許可證。

安裝庫並取得許可證後，在腳本中初始化 Aspose.Slides：
```python
import aspose.slides as slides

# 如果適用，請在此處使用許可代碼進行初始化
```
現在我們已經介紹如何設定 Aspose.Slides for Python，讓我們繼續實作核心功能。

## 實施指南
### 設定文字框架中的本地字體高度
此功能可讓您自訂單一框架內的文字部分 - 非常適合強調簡報的特定部分。
#### 概述
透過局部修改字體高度，您可以吸引人們注意關鍵短語或部分，而無需改變整體佈局。本教學介紹如何為段落中的各個部分設定不同的高度。
#### 實施步驟
##### 步驟 1：初始化簡報並新增形狀
首先建立一個新的簡報並新增一個放置文字的形狀：
```python
def set_local_font_height_values():
    with slides.Presentation() as pres:
        # 在第一張投影片中新增矩形
        new_shape = pres.slides[0].shapes.add_auto_shape(
            slides.ShapeType.RECTANGLE, 100, 100, 400, 75, False)
```
在這裡，我們添加一個具有指定座標和尺寸的矩形。
##### 步驟 2：建立文字框架
接下來，在新新增的形狀內建立一個空白文字方塊：
```python
        # 建立空文本框架
        new_shape.add_text_frame("")
        new_shape.text_frame.paragraphs[0].portions.clear()
```
清除現有部分可確保在乾淨的狀態下新增自訂文字。
##### 步驟 3：新增和自訂文字部分
在段落中新增兩個不同的文字部分，然後自訂其字體高度：
```python
        # 新增不同高度的文字部分
        portion0 = slides.Portion("Sample text with first portion")
        portion1 = slides.Portion(" and second portion.")
        
        new_shape.text_frame.paragraphs[0].portions.add(portion0)
        new_shape.text_frame.paragraphs[0].portions.add(portion1)

        # 設定字體高度
        pres.default_text_style.get_level(0).default_portion_format.font_height = 24
        new_shape.text_frame.paragraphs[0].paragraph_format.default_portion_format.font_height = 40
        
        new_shape.text_frame.paragraphs[0].portions[0].portion_format.font_height = 55
        new_shape.text_frame.paragraphs[0].portions[1].portion_format.font_height = 18
```
這 `font_height` 此參數對於設定每個部分的視覺突出性至關重要。
##### 步驟 4：儲存簡報
最後，儲存您的簡報：
```python
        # 儲存到指定目錄
        pres.save("YOUR_OUTPUT_DIRECTORY/text_SetLocalFontHeightValues_out.pptx", slides.export.SaveFormat.PPTX)
```
### 實際應用
1. **強調重點**：使用不同高度的字體來突出商業提案中的關鍵要素。
2. **創造視覺層次**：透過區分投影片文字中的標題和副標題來增強可讀性。
3. **客製化學習材料**：客製化教育內容，以提高學生的參與度。

### 性能考慮
- **優化文字管理**：盡量減少每段的部分數量以提高效能。
- **資源使用情況**：監控記憶體使用情況，尤其是在處理大型簡報時。
- **高效率的記憶體管理**：使用後立即關閉簡報以釋放資源。

## 結論
恭喜！您已經掌握了使用 Aspose.Slides for Python 設定本地字體高度的方法。這項技能將使您能夠創建更動態、更吸引人的演示文稿，以滿足觀眾的需求。

### 後續步驟
- 嘗試其他文字自訂，例如顏色和樣式。
- 探索將 Aspose.Slides 與其他資料來源或應用程式整合。

準備好嘗試了嗎？在您的下一個演示專案中開始實施這些技術！

## 常見問題部分
**問題 1：我可以使用 Aspose.Slides for Python 更改字體顏色和高度嗎？**
A1：是的，您可以透過訪問 `portion_format` 特性。

**Q2：如何申請 Aspose.Slides 臨時許可證？**
A2：依照指示申請臨時駕照 [Aspose 網站](https://purchase。aspose.com/temporary-license/).

**Q3：設定字體高度時有哪些常見問題？**
A3：確保部分存在於有效段落內，並檢查正確的座標值。

**Q4：Aspose.Slides 與所有 Python 版本相容嗎？**
A4：建議使用 Python 3.6 或更新版本，以確保相容性。

**Q5：如何在多張投影片中自動建立文字框架？**
A5：使用循環遍歷投影片集合併套用文字方塊自訂程式碼。

## 資源
- **文件**：有關詳細的 API 參考，請訪問 [Aspose 文檔](https://reference。aspose.com/slides/python-net/).
- **下載**：取得最新版本 [Aspose 下載](https://releases。aspose.com/slides/python-net/).
- **購買**：要購買許可證，請前往 [Aspose 購買頁面](https://purchase。aspose.com/buy).
- **免費試用**：立即開始免費試用 [Aspose 免費試用](https://releases。aspose.com/slides/python-net/).
- **支援**：如有疑問或需要支持，請訪問 [Aspose 論壇](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}