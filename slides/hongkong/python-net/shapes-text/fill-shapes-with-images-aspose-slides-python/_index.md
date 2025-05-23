---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 在 PowerPoint 簡報中以圖片填滿形狀。透過本逐步教學增強您的投影片。"
"title": "如何使用 Aspose.Slides for Python 在 PowerPoint 中用圖片填滿形狀&#58;逐步指南"
"url": "/zh-hant/python-net/shapes-text/fill-shapes-with-images-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何使用 Aspose.Slides for Python 在 PowerPoint 中以圖片填滿形狀

## 介紹
無論您是商務人士還是希望吸引觀眾的教育工作者，創建具有視覺吸引力的 PowerPoint 簡報都至關重要。使用 Aspose.Slides for Python 增強投影片的一種方法是用圖片填滿形狀。此功能可讓您添加獨特且富有創意的設計，使您的內容脫穎而出。

無論您是程式設計簡報的新手還是尋求自動執行重複性任務的方法，本指南都將向您展示如何使用 Aspose.Slides for Python 有效地用圖像填滿形狀。

**您將學到什麼：**
- 如何設定使用 Aspose.Slides 的環境
- 在 PowerPoint 簡報中使用影像填滿形狀的過程
- 優化效能和解決常見問題的技巧

讓我們深入了解開始之前所需的先決條件！

## 先決條件
在開始之前，請確保您已：

### 所需的庫和相依性：
- **Aspose.Slides for Python**：透過 pip 安裝以實現對 PowerPoint 簡報的操作。
- **Python 3.6 或更高版本**：確保您的環境支援最新的 Python 功能。

### 環境設定要求：
- Python 的工作安裝
- 存取終端機或命令提示字元來安裝軟體包

### 知識前提：
- 對 Python 程式設計有基本的了解
- 熟悉使用 Python 處理檔案和目錄

有了這些先決條件，我們就可以設定 Python 的 Aspose.Slides 了。

## 為 Python 設定 Aspose.Slides
首先，您需要安裝 Aspose.Slides 函式庫。這個強大的工具能夠以程式設計方式無縫建立和操作 PowerPoint 簡報。

### Pip安裝：
在終端機或命令提示字元中執行以下命令：

```bash
pip install aspose.slides
```

這將從 PyPI 下載並安裝最新版本的 Aspose.Slides for Python。

### 許可證取得步驟：
- **免費試用**： 使用 [Aspose 的免費試用版](https://releases.aspose.com/slides/python-net/) 免費評估功能。
- **臨時執照**：透過訪問取得臨時許可證 [臨時執照](https://purchase。aspose.com/temporary-license/).
- **購買**：如需長期使用，您可以購買許可證 [Aspose 購買頁面](https://purchase。aspose.com/buy).

### 基本初始化和設定：
安裝完成後，在 Python 腳本中初始化 Aspose.Slides 以開始處理簡報：

```python
import aspose.slides as slides

# 初始化簡報類別以讀取或建立新的簡報
pres = slides.Presentation()
```

設定好庫之後，讓我們繼續實現特定的功能。

## 實施指南
我們將把實施過程分為兩個關鍵部分：用圖片填滿形狀和儲存 PowerPoint 簡報。 

### 用圖片填滿形狀
此功能可讓您使用影像填充各種形狀來增強投影片的效果，為您的簡報增添專業感或主題一致性。

#### 步驟1：導入Aspose.Slides
首先導入必要的模組：

```python
import aspose.slides as slides
```

#### 第 2 步：定義影像路徑
指定輸入和輸出目錄的路徑：

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

代替 `"YOUR_DOCUMENT_DIRECTORY/"` 使用您的影像來源目錄路徑和 `"YOUR_OUTPUT_DIRECTORY/"` 以及您想要儲存最終簡報的位置。

#### 步驟3：建立示範實例
實例化 `Presentation` 類，代表一個 PowerPoint 文件：

```python
with slides.Presentation() as pres:
    slide = pres.slides[0]
```

在這裡，我們訪問簡報的第一張投影片。您可以根據需要修改或新增投影片。

#### 步驟 4：新增並配置形狀
在投影片中新增自動形狀並配置其填滿類型：

```python
shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 75, 150)
shape.fill_format.fill_type = slides.FillType.PICTURE
```

此程式碼在指定座標處新增一個矩形，其尺寸為寬度 75、高度 150。

#### 步驟5：設定圖片填滿模式
定義影像如何填滿形狀：

```python
shape.fill_format.picture_fill_format.picture_fill_mode = slides.PictureFillMode.TILE
```

使用 `TILE` 模式將影像平鋪在形狀的整個區域，從而產生無縫圖案效果。

#### 步驟6：載入並分配圖像
載入圖像並將其添加到演示文稿中：

```python
img = slides.Images.from_file(data_dir + "image2.jpg")
imgx = pres.images.add_image(img)
shape.fill_format.picture_fill_format.picture.image = imgx
```

此步驟涉及載入 `image2.jpg` 從您的目錄中，將其新增至影像集合，並將其指定為形狀的填充。

#### 步驟 7：儲存簡報
最後，儲存填滿形狀的簡報：

```python
pres.save(out_dir + "shapes_filltype_picture_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}