---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 自訂 PowerPoint 簡報中的超連結顏色。使用個人化的連結樣式有效地增強您的幻燈片。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中設定超連結顏色"
"url": "/zh-hant/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中設定超連結顏色

## 介紹

使用 Aspose.Slides for Python 可以輕鬆自訂超連結顏色，增強 PowerPoint 簡報的視覺吸引力。本指南將引導您使用 Python 在幻燈片中設定具有特定顏色的超連結。

**您將學到什麼：**
- 如何在 PowerPoint 中的文字形狀內設定超連結顏色。
- 創建具有視覺吸引力的簡報所涉及的步驟。
- Aspose.Slides for Python 的主要功能有助於實現這種客製化。

讓我們深入了解開始之前所需的先決條件。

## 先決條件

在開始之前，請確保您的環境已準備好以下內容：
- **庫和版本：** 安裝 `aspose.slides` 圖書館。確保您的機器上安裝了 Python。
- **環境設定要求：** 本教學假設在 Windows、Mac 或 Linux 上對 Python 進行了基本設定。
- **知識前提：** 熟悉 Python 程式設計將會很有幫助。

## 為 Python 設定 Aspose.Slides

要開始使用 Aspose.Slides for Python，請透過 pip 安裝套件：

```bash
pip install aspose.slides
```

**許可證取得步驟：**
- **免費試用：** 從下載試用版 [Aspose 的發佈頁面](https://releases。aspose.com/slides/python-net/).
- **臨時執照：** 申請臨時執照 [購買頁面](https://purchase.aspose.com/temporary-license/) 以擴展存取權限。
- **購買：** 要完全解鎖功能而不受限制，請考慮從 [Aspose的購買頁面](https://purchase。aspose.com/buy).

**基本初始化：**
安裝並獲得許可後，在腳本中匯入 Aspose.Slides：

```python
import aspose.slides as slides
```

## 實施指南

本節引導您在 PowerPoint 簡報中設定超連結顏色。

### 設定超連結顏色功能

#### 概述

使用 Aspose.Slides for Python 自訂嵌入在文字形狀中的超連結的顏色。這增強了可讀性和視覺吸引力。

##### 步驟 1：建立新簡報

建立簡報的實例：

```python
with slides.Presentation() as presentation:
    # 您的程式碼在這裡
```

##### 步驟 2：新增帶有文字的形狀

在第一張投影片中新增一個矩形並插入包含超連結的文字。

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### 步驟 3：設定超連結屬性

分配超連結並設定其顏色。這 `hyperlink_click` 屬性指定點擊後連結應導航到的位置。

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# 將超連結的顏色來源設定為部分格式並定義填滿類型和顏色。
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### 步驟 4：儲存簡報

將您的簡報儲存到指定目錄：

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}