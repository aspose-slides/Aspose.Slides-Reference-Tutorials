---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 中自動建立和格式化矩形形狀。輕鬆提升您的演講技巧。"
"title": "使用 Aspose.Slides for Python 在 PowerPoint 中自動產生矩形形狀"
"url": "/zh-hant/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和格式化矩形
## 介紹
您是否曾發現自己需要快速為 PowerPoint 簡報添加自訂形狀，但卻因缺乏自動化而苦苦掙扎？如果您厭倦了逐張投影片手動格式化矩形，那麼本教學可以幫助您。利用“Aspose.Slides for Python”，我們只需幾行程式碼即可自動新增和設定矩形形狀的樣式。在本指南結束時，您將掌握：
- 以程式設計方式建立矩形形狀
- 應用顏色和線條樣式等格式選項
- 輕鬆儲存您的簡報
讓我們深入了解如何改變您的幻燈片創建過程！
### 先決條件
在開始編碼之前，請確保您已準備好以下內容：
- **Python** 安裝在您的機器上（建議使用 3.6 或更高版本）
- **Aspose.Slides for Python** 庫，允許我們操作 PowerPoint 簡報
- 對 Python 程式設計概念有基本的了解，並熟悉使用 pip 安裝套件
## 為 Python 設定 Aspose.Slides
### 安裝
若要安裝 Aspose.Slides 套件，請開啟終端機或命令提示字元並執行：
```bash
pip install aspose.slides
```
此命令從 PyPI 取得並安裝最新版本的 Aspose.Slides for Python。
### 許可證獲取
Aspose.Slides 是一款商業產品，但您可以使用免費試用授權開始使用它。取得方法如下：
1. **免費試用：** 訪問 [Aspose 免費試用](https://releases.aspose.com/slides/python-net/) 並報名參加評估。
2. **臨時執照：** 如需不受限制地進行更廣泛的測試，請申請臨時許可證 [臨時許可證頁面](https://purchase。aspose.com/temporary-license/).
3. **購買：** 當您準備上線時，透過 [Aspose 購買頁面](https://purchase。aspose.com/buy).
一旦獲得，請按照文件在您的專案中應用您的許可證。
### 基本初始化
以下是如何初始化 Python 的 Aspose.Slides：
```python
import aspose.slides as slides
\# 初始化Presentation類
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
此程式碼片段設定了一個新的簡報並確認它已準備好進行操作。
## 實施指南
### 建立矩形
#### 概述
在本節中，我們將重點介紹如何使用 Aspose.Slides for Python 在 PowerPoint 投影片中新增矩形形狀。
#### 建立形狀的步驟
1. **開啟或建立簡報：**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # 我們將在這裡添加矩形
   ```
2. **存取投影片：**
   檢索我們想要新增形狀的第一張投影片。
   ```python
   slide = pres.slides[0]
   ```
3. **新增矩形形狀：**
   使用 `add_auto_shape` 方法在投影片上建立一個矩形。
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - 參數： `ShapeType.RECTANGLE`，x 位置（50），y 位置（150），寬度（150），高度（50）。
### 格式化矩形
#### 概述
接下來，我們將對矩形套用格式，包括填滿顏色和線條樣式。
#### 格式化步驟
1. **填充顏色：**
   為矩形的背景設定具有特定顏色的實心填滿。
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **線條樣式：**
   自訂矩形的線條，包括其顏色和寬度。
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **儲存簡報：**
   最後，將簡報儲存到文件中。
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}