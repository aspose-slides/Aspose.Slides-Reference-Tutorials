---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 自動在 PowerPoint 簡報中建立 SmartArt 圖形，包括有效提取和儲存縮圖。"
"title": "如何使用 Aspose.Slides for Python 建立和檢索 SmartArt 縮圖"
"url": "/zh-hant/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 建立和檢索 SmartArt 縮圖

## 介紹

創建具有視覺吸引力的簡報對於吸引觀眾的注意力至關重要。增強投影片效果的一個有效方法是在 PowerPoint 簡報中加入 SmartArt 等動態圖形。如果您正在尋找一種自動化的方法來產生這些視覺效果並從中提取縮圖，那麼有關「Aspose.Slides Python」的指南將非常有價值。

使用 Aspose.Slides for Python，您可以輕鬆建立 SmartArt 圖形，存取圖形中的特定節點，檢索這些節點的圖像縮圖，並將這些圖像儲存到您的專案中。本教學將詳細介紹每個步驟。

**您將學到什麼：**
- 如何安裝和設定 Aspose.Slides for Python。
- 在 PowerPoint 簡報中建立 SmartArt 圖形。
- 存取 SmartArt 圖形內的節點。
- 從特定節點提取並保存圖像縮圖。

在開始之前，讓我們先深入研究先決條件。

## 先決條件

在開始之前，請確保已準備好以下內容：

- **所需庫：** 您將需要適用於 Python 的 Aspose.Slides。確保您的環境支援 Python 3.x。
- **環境設定要求：** Python 的工作安裝和適當的 IDE 或文字編輯器（如 VSCode 或 PyCharm）。
- **知識前提：** 對 Python 程式設計有基本的了解，包括函數定義和檔案操作。

## 為 Python 設定 Aspose.Slides

首先，您需要安裝 Aspose.Slides 函式庫。使用 pip 可以輕鬆完成此操作：

```bash
pip install aspose.slides
```

安裝後，如果您希望不受限制地探索所有功能，請取得許可證。您可以先免費試用，申請臨時許可證，或購買以供長期使用。

若要在 Python 環境中初始化 Aspose.Slides，請在腳本開頭匯入庫：

```python
import aspose.slides as slides
```

## 實施指南

讓我們將創建和檢索 SmartArt 縮圖的過程分解為清晰的步驟。

### 步驟 1：建立一個新的示範實例

首先建立簡報的實例。這將是您添加 SmartArt 圖形的容器。

```python
with slides.Presentation() as pres:
```

使用 `with` 確保資源得到正確管理，退出時自動儲存並關閉檔案。

### 步驟 2：將 SmartArt 新增至第一張投影片

接下來，我們將在第一張投影片中新增 SmartArt 圖形。您可以按照以下步驟操作：

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

這會在位置 (10, 10) 處為 SmartArt 圖形添加一個基本循環佈局，尺寸為 400x300 像素。

### 步驟3：訪問第二個節點

存取 SmartArt 內的特定節點。在這個例子中，我們訪問第二個節點：

```python
node = smart.nodes[1]
```

節點從零開始索引；因此， `nodes[1]` 引用清單中的第二個節點。

### 步驟4：檢索影像縮圖

若要取得所選節點內形狀的影像縮圖：

```python
image = node.shapes[0].get_image()
```

這將從指定的 SmartArt 節點中檢索第一個形狀的圖像作為縮圖。

### 步驟5：儲存檢索到的影像

最後，將此縮圖以 JPEG 格式儲存到您想要的位置：

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}