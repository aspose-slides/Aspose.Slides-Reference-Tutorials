---
"date": "2025-04-24"
"description": "了解如何使用 Aspose.Slides for Python 建立 PowerPoint 表格。本逐步指南簡化了流程，確保了簡報的一致性。"
"title": "使用 Aspose.Slides 和 Python 建立 PowerPoint 表格&#58;逐步指南"
"url": "/zh-hant/python-net/tables/create-powerpoint-tables-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 和 Python 建立 PowerPoint 表格

以程式設計方式在 PowerPoint 簡報中建立表格可以節省您的時間並確保跨文件的一致性。無論您是產生報告、建立培訓材料還是開發自動演示工具，使用 Aspose.Slides for Python 都可以將表格建立無縫整合到您的程式碼庫中，從而簡化此過程。本逐步指南將引導您完成使用 Aspose.Slides 和 Python 在第一張投影片上建立 PowerPoint 表格的步驟。

## 您將學到什麼：
- 如何使用 Python 設定 Aspose.Slides 環境
- 在 PowerPoint 投影片中建立表格的逐步說明
- 將表格整合到簡報的實際應用
- 使用 Aspose.Slides 時的效能注意事項

讓我們深入了解先決條件並開始吧！

### 先決條件

在開始之前，請確保您的環境設定正確。您需要準備以下物品：
1. **Python 環境**：確保您的系統上安裝了 Python 3.x。
2. **Aspose.Slides for Python**：這個函式庫將成為我們處理 PowerPoint 檔案的主要工具。
3. **開發 IDE 或文字編輯器**：例如 PyCharm、VSCode 或任何您喜歡的編輯器。

### 為 Python 設定 Aspose.Slides

若要開始使用 Aspose.Slides for Python，請依照下列步驟操作：

**透過 pip 安裝：**

```bash
pip install aspose.slides
```

**許可證取得：** 
- **免費試用**：從下載免費試用版 [Aspose 網站](https://releases。aspose.com/slides/python-net/).
- **臨時執照**：請造訪此處以取得臨時許可證，以便更長時間使用 [關聯](https://purchase。aspose.com/temporary-license/).
- **購買**：如需完整功能，請考慮購買其許可證 [購買頁面](https://purchase。aspose.com/buy).

**基本初始化：**

安裝後，您可以開始在 Python 腳本中使用 Aspose.Slides。導入庫如下所示：

```python
import aspose.slides as slides
```

### 實施指南

現在我們已經設定好了環境，讓我們開始建立表格。

#### 在投影片上建立表格

**概述**：我們將建立一個簡單的表格並將其新增至 PowerPoint 簡報的第一張投影片中。 

##### 步驟 1：建立演示類別的實例

這 `Presentation` 類別代表一個PPT檔。在這裡，我們將開啟或建立一個新的簡報：

```python
with slides.Presentation() as pres:
    # 演示實例在此上下文管理器區塊內使用。
```

##### 第 2 步：存取第一張投影片

訪問第一張投影片允許我們在那裡添加表格：

```python
slide = pres.slides[0]  # 這將獲取簡報中的第一張投影片。
```

##### 步驟 3：定義表格尺寸並將其新增至投影片

定義列寬和行高，然後在指定座標（x=50，y=50）處新增表格：

```python
dbl_cols = [50, 50, 50]  # 列寬
dbl_rows = [50, 30, 30, 30, 30]  # 行高

table = slide.shapes.add_table(50, 50, dbl_cols, dbl_rows)  # 將表格新增至投影片。
```

##### 步驟 4：用文字填滿表格單元格

遍歷表中的每個單元格並添加文字：

```python
for row in table.rows:
    for cell in row:
        tf = cell.text_frame
        tf.text = "T" + str(cell.first_row_index) + str(cell.first_column_index)
        
        if tf.paragraphs:  # 確保有需要修改的段落。
            tf.paragraphs[0].portions[0].portion_format.font_height = 10
            tf.paragraphs[0].paragraph_format.bullet.type = slides.BulletType.NONE
```

##### 步驟 5：儲存簡報

最後，將簡報儲存到指定位置：

```python
pres.save("YOUR_OUTPUT_DIRECTORY/tables_create_table_out.ppt\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}