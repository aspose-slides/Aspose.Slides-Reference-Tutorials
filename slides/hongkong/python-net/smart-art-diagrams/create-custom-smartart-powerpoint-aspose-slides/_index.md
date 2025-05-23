---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂 SmartArt 圖形，並使用動態組織結構圖增強您的簡報。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂 SmartArt"
"url": "/zh-hant/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中建立和自訂 SmartArt

## 介紹

簡報是直觀地展示組織結構或腦力激盪會議的重要工具。使用 Aspose.Slides for Python，您可以輕鬆建立和自訂 SmartArt 圖形。本教學將引導您在 PowerPoint 投影片中新增組織結構圖 SmartArt 圖形。

**您將學到什麼：**
- 使用 Aspose.Slides for Python 在 PowerPoint 中加入 SmartArt 圖形。
- 自訂 SmartArt 節點的佈局。
- 有效率地保存和匯出簡報。

讓我們開始設定您的環境！

## 先決條件

在開始建立 SmartArt 圖形之前，請確保您符合以下先決條件：

### 所需庫
- **Aspose.Slides for Python**：如果尚未完成，請使用 pip 安裝此程式庫。

### 環境設定要求
- Python 的工作安裝（建議使用 3.x）。
- 對 Python 程式設計有基本的了解。
- 熟悉 Microsoft PowerPoint 會有所幫助，但不是必要的。

## 為 Python 設定 Aspose.Slides

首先，在您的 Python 環境中設定 Aspose.Slides 庫：

**Pip安裝：**
```bash
pip install aspose.slides
```

### 許可證取得步驟
Aspose 提供多種許可選項：
- **免費試用**：下載臨時許可證以評估全部功能。
- **臨時執照**：取得免費的臨時許可證以供短期使用。
- **購買**：考慮購買長期專案的訂閱。

### 基本初始化和設定

安裝完成後，使用 Aspose.Slides 初始化您的 Python 腳本，如下所示：

```python
import aspose.slides as slides

# 使用 slides.Presentation() 初始化 Presentation 類別作為簡報：
    # 新增 SmartArt 的程式碼將在此處顯示
```

## 實施指南

現在讓我們分解使用 Aspose.Slides for Python 在 PowerPoint 中新增和自訂 SmartArt 的過程。

### 新增 SmartArt 圖形

#### 概述
建立新投影片並在其中新增組織結構圖類型 SmartArt 圖形：

```python
import aspose.slides as slides

# 建立一個簡報實例\使用 slides.Presentation() 作為簡報：
    # 在位置 (10, 10) 中新增指定尺寸的 SmartArt
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### 參數和方法目的
- **x, y**：SmartArt 圖形在投影片上的位置。
- **寬度、高度**：適當可見性的尺寸。
- **佈局類型**：指定 SmartArt 佈局的類型，在本例中為組織結構圖。

### 自訂組織結構圖佈局

#### 概述
透過將佈局設為 LEFT_HANGING 來自訂 SmartArt 圖形中的第一個節點：

```python
# 將第一個節點設定為左掛佈局
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### 關鍵配置選項說明
- **組織結構圖佈局類型**：確定節點的顯示方式，增強可讀性和美感。

### 儲存簡報

最後，將您的簡報儲存到指定目錄：

```python
# 使用 SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\ 儲存簡報

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}