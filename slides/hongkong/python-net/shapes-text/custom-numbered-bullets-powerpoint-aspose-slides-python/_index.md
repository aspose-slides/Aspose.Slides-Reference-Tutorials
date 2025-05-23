---
"date": "2025-04-24"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 中建立自訂編號項目符號清單。使用獨特的格式增強您的簡報。"
"title": "使用 Aspose.Slides for Python 在 PowerPoint 中自訂編號項目符號列表"
"url": "/zh-hant/python-net/shapes-text/custom-numbered-bullets-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Python 在 PowerPoint 中自訂編號項目符號列表

## 介紹
您是否希望提升 PowerPoint 簡報的視覺吸引力，使其超越預設的項目符號？無論是公司報告、學術講座或商務會議，自訂項目符號清單都可以更有效地吸引和留住觀眾的注意力。和 **Aspose.Slides for Python**，您可以根據自己獨特的格式需求靈活地自訂編號項目符號。

在本綜合指南中，我們將示範如何使用 Python 在 PowerPoint 中使用 Aspose.Slides 設定自訂編號項目符號。透過將此功能整合到您的簡報中，您可以獲得專業而精緻的外觀。

**您將學到什麼：**
- 為 Python 設定 Aspose.Slides
- 建立自訂編號項目符號列表
- 以程式設計方式配置項目符號設定
- 優化效能並解決常見問題

讓我們開始吧！確保一切準備就緒，可以繼續下一步。

## 先決條件
在使用 Aspose.Slides for Python 實作自訂編號項目符號之前，請確保您已：

### 所需庫：
- **Aspose.Slides for Python**：用於建立和處理 PowerPoint 簡報的強大庫。

### 環境設定：
- 您的系統上安裝了 Python 3.x。
- 對 Python 程式設計概念的基本了解很有幫助，但不是強制性的。

## 為 Python 設定 Aspose.Slides
首先，安裝 `aspose.slides` 使用 pip 的庫：

```bash
pip install aspose.slides
```

### 許可證取得：
Aspose.Slides 是一款商業產品，提供免費試用版以測試其功能。您可以獲得臨時許可證或購買許可證以便繼續使用。

- **免費試用**：無限制存取基本功能。
- **臨時執照**：在 Aspose 網站上請求暫時獲得完全存取權。
- **購買**：考慮購買長期專案的許可證。

### 基本初始化：
安裝完成後，請按如下方式初始化您的簡報：

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # 您的程式碼在這裡...
```

此設定準備了在 PowerPoint 投影片中新增自訂編號項目符號的環境。

## 實施指南
讓我們深入研究如何建立自訂編號項目符號清單。每個步驟都被分解，以便於清晰和易於實施。

### 新增帶有文字框的矩形
#### 概述：
首先，新增一個包含項目符號文字方塊的形狀。

```python
# 在第一張投影片中新增矩形
shape = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 200, 200, 400, 200)
```
- **參數解釋**： 這 `add_auto_shape` 方法採用形狀類型（矩形）、位置（x 和 y 座標）和尺寸（寬度和高度）的參數。

### 配置文字框架
#### 概述：
存取矩形的文字方塊來新增項目符號。

```python
# 存取已建立的自動形狀的文字框
text_frame = shape.text_frame

# 刪除任何預設現有段落（如果存在）
text_frame.paragraphs.clear()
```
- **目的**：確保在添加自訂項目符號之前一切正常。

### 新增自訂編號項目符號
#### 概述：
新增具有特定項目符號設定的段落：

```python
# 新增帶有自訂編號項目符號的段落
for start_number, bullet_text in [(2, "bullet 2"), (3, "bullet 3"), (7, "bullet 7")]:
    paragraph = slides.Paragraph()
    paragraph.text = bullet_text
    paragraph.paragraph_format.depth = 4
    paragraph.paragraph_format.bullet.numbered_bullet_start_with = start_number
    paragraph.paragraph_format.bullet.type = slides.BulletType.NUMBERED
    text_frame.paragraphs.add(paragraph)
```
- **配置**：每個段落都以特定的數字開頭，從而提供靈活性並可控演示格式。

### 儲存簡報
最後，儲存您配置的簡報：

```python
# 儲存簡報\presentation.save("YOUR_OUTPUT_DIRECTORY/text_set_custom_bullets_number_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}