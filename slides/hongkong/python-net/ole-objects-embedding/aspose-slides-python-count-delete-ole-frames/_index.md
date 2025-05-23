---
"date": "2025-04-23"
"description": "透過本逐步指南了解如何使用 Aspose.Slides 有效管理 PowerPoint 簡報中的 OLE 物件框架。"
"title": "使用 Aspose.Slides for Python 統計並刪除 PowerPoint 中的 OLE 物件框架"
"url": "/zh-hant/python-net/ole-objects-embedding/aspose-slides-python-count-delete-ole-frames/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Python 統計並刪除 OLE 物件框架

在現代數位領域，有效的演示管理至關重要。本教學將教你如何使用 **Aspose.Slides for Python** 統計和刪除 PowerPoint 簡報中的 OLE（物件連結和嵌入）框架，優化內容品質和文件效能。

## 您將學到什麼
- 計算投影片中 OLE 物件框架的總數和空數
- 從簡報中刪除嵌入的二進位對象
- 使用 Python 設定 Aspose.Slides
- 應用實際應用並考慮效能影響

準備好簡化您的簡報管理了嗎？讓我們開始吧！

### 先決條件
在開始之前，請確保您已：
- **Python 環境**：在您的系統上安裝 Python 3.x。
- **Aspose.Slides for Python**：使用pip安裝： `pip install aspose。slides`.
- **執照**：利用免費試用版或從取得臨時許可證 [Aspose](https://purchase.aspose.com/temporary-license/) 評估期間取得全部功能。

對 Python 和 PowerPoint 文件處理的基本了解對新手來說是有益的。

### 為 Python 設定 Aspose.Slides
使用 pip 安裝庫：
```bash
pip install aspose.slides
```

#### 許可證取得步驟
1. **免費試用**：透過免費試用探索功能。
2. **臨時執照**：從 [Aspose臨時許可證](https://purchase.aspose.com/temporary-license/) 在評估期間解鎖全部功能。
3. **購買**：如需長期使用，請考慮從 [Aspose 購買](https://purchase。aspose.com/buy).

#### 基本初始化和設定
首先在腳本中導入 Aspose.Slides：
```python
import aspose.slides as slides
```

### 實施指南
本指南涵蓋了計數 OLE 框架和刪除嵌入的二進位檔案。

#### 計算 OLE 物件框架
了解 OLE 框架的數量有助於有效地管理內容。

##### 概述
計算 OLE 框架以評估內容組成並為修改做準備。

##### 實施步驟
1. **導入 Aspose.Slides**：確保庫已導入。
2. **定義函數**：
   ```python
def get_ole_object_frame_count（投影片集合）：
    ole_frames_count，empty_ole_frames_count = 0，0
    
    for slide in slides_collection:
        for shape in slide.shapes:
            if isinstance(shape, slides.OleObjectFrame):
                ole_frames_count += 1
                embedded_data = shape.embedded_data.embedded_file_data
                
                if not embedded_data or len(embedded_data) == 0:
                    empty_ole_frames_count += 1
    
    return ole_frames_count, empty_ole_frames_count
```
3. **解釋**：
   - The function iterates through each slide and shape in the presentation.
   - It checks if a shape is an `OleObjectFrame` and counts it.
   - An OLE frame with no embedded data is considered empty.

##### Key Configuration Options
- Customize this function by modifying conditions or adding other shape type checks as needed.

#### Deleting Embedded Binary Objects
Removing unused binaries reduces file size and boosts performance.

##### Overview
Streamline your presentation by deleting all embedded binaries upon loading the document.

##### Implementation Steps
1. **Set Load Options**:
   Configure load options to delete binaries automatically.
   ```python
def delete_embedded_binary_objects():
    load_options = slides.LoadOptions()
    load_options.delete_embedded_binary_objects = True
    
    with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/OlePptx.pptx", load_options) as pres:
        ole_frames_count, empty_ole_frames_count = get_ole_object_frame_count(pres.slides)
        print(f"Number of OLE frames in source presentation = {ole_frames_count}")
        print(f"Number of empty OLE frames in source presentation = {empty_ole_frames_count}")

        pres.save("YOUR_OUTPUT_DIRECTORY/OlePptx-out.pptx", slides.export.SaveFormat.PPTX)

    with slides.Presentation("YOUR_OUTPUT_DIRECTORY/OlePptx-out.pptx") as out_pres:
        ole_frames_count, empty_ole_frames_count = get_ole_object_frame_count(out_pres.slides)
        print(f"Number of OLE frames in resulting presentation = {ole_frames_count}")
        print(f"Number of empty OLE frames in resulting presentation = {empty_ole_frames_count}")
```
2. **Explanation**:
   - `LoadOptions` 配置為刪除二進位。
   - 修改後的簡報已儲存，並再次驗證計數。

##### 故障排除提示
- 確保檔案路徑指定正確。
- 如果面臨功能限制，請驗證 Aspose.Slides 授權是否有效。

### 實際應用
1. **內容審核**：快速識別簡報中多餘的嵌入物件。
2. **文件大小優化**：減少簡報大小以實現更快的載入速度和更好的儲存效率。
3. **資料安全**：從 OLE 框架中刪除敏感資料以防止未經授權的存取。
4. **與文件管理系統集成**：作為文件生命週期管理的一部分，自動執行清理過程。

### 性能考慮
- **優化資源**：定期檢查未使用的 OLE 物件以保持高效率的資源使用。
- **記憶體管理**：明智地使用 Python 的垃圾收集，特別是對於可能需要額外處理的大型簡報。

### 結論
透過利用 Aspose.Slides for Python，您可以大幅增強簡報管理工作流程。本教學為您提供了有效計算和刪除 OLE 框架的工具，從而優化內容品質和檔案效能。

下一步是什麼？嘗試將這些功能整合到更大的自動化管道中或探索其他 Aspose.Slides 功能！

### 常見問題部分
1. **什麼是 OLE 物件框架？**
   - OLE 框架在 PowerPoint 投影片中嵌入外部對象，如 Excel 表、PDF 文件等。
2. **我可以自訂嵌入式二進位檔案的刪除標準嗎？**
   - 是的，透過調整載入選項或在儲存簡報之前添加邏輯。
3. **如何有效地處理具有許多 OLE 框架的大型簡報？**
   - 使用批次並優化記憶體使用以防止效能瓶頸。
4. **與其他函式庫相比，Aspose.Slides 有哪些優勢？**
   - 全面支援各種格式、先進的操作能力和強大的授權選項。
5. **使用 Aspose.Slides 是否需要付費？**
   - 可以免費試用，但要完全存取則需要購買許可證或取得臨時許可證以用於評估目的。

### 資源
- [Aspose.Slides文檔](https://reference.aspose.com/slides/python-net/)
- [下載 Aspose.Slides for Python](https://releases.aspose.com/slides/python-net/)
- [購買許可證](https://purchase.aspose.com/buy)
- [免費試用和臨時許可證](https://releases.aspose.com/slides/python-net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}