---
"date": "2025-04-23"
"description": "了解如何使用 Python 中的 Aspose.Slides 將 PowerPoint 簡報 (PPTX) 轉換為 HTML 同時保留字體。本指南提供了有關優化字體嵌入的逐步說明和提示。"
"title": "使用 Aspose.Slides for Python 將 PPTX 轉換為 HTML 並保留字體"
"url": "/zh-hant/python-net/presentation-management/convert-pptx-html-preserving-fonts-aspose-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides for Python 將 PPTX 轉換為 HTML 並保留字體

## 介紹

將 PowerPoint 簡報 (PPTX) 轉換為 HTML 格式同時保留原始字體可能具有挑戰性，尤其是當您希望排除某些預設字體的嵌入時。有了“Aspose.Slides for Python”，這項任務就變得簡單了。本教學將指導您使用 Python 中的 Aspose.Slides 將 PPTX 檔案轉換為保留字體的 HTML。

**您將學到什麼：**
- 如何安裝和設定 Aspose.Slides for Python
- 將 PowerPoint 簡報 (PPTX) 轉換為 HTML 同時保留字體
- 從嵌入中排除特定的預設字體
- 優化轉換過程中的效能

在開始之前，讓我們先回顧一下先決條件！

## 先決條件

在轉換 PPTX 檔案之前，請確保您已具備以下條件：

### 所需的庫和版本：
- **Aspose.Slides for Python**：本教程中使用的主要庫。確保與您的設定相容。

### 環境設定要求：
- 一個正常運作的 Python 環境（建議使用 Python 3.x）。
- 存取命令列介面或終端。

### 知識前提：
- 對 Python 程式設計有基本的了解。
- 熟悉如何處理作業系統中的檔案路徑和目錄。

## 為 Python 設定 Aspose.Slides

要開始使用 Aspose.Slides，您需要安裝它。方法如下：

**Pip安裝：**

```bash
pip install aspose.slides
```

此命令安裝最新版本的 Aspose.Slides for Python，允許完全存取其功能。

### 許可證取得步驟：
- **免費試用**：立即下載免費試用 [這裡](https://releases。aspose.com/slides/python-net/).
- **臨時執照**申請臨時執照 [這裡](https://purchase.aspose.com/temporary-license/) 如果你需要更多時間。
- **購買**：考慮購買完整許可證 [這裡](https://purchase.aspose.com/buy) 可供長期使用。

### 基本初始化和設定：

安裝後，請在 Python 腳本中匯入該庫，如下所示：

```python
import aspose.slides as slides
```

此行對於存取 Aspose.Slides 功能至關重要。

## 實施指南

在本節中，我們將轉換過程分解為易於管理的步驟。

### 將 PPTX 轉換為 HTML 並保留原始字體

#### 概述：
此實現的主要功能是轉換 PowerPoint 演示文稿，同時保留其原始字體並從嵌入中排除特定的預設字體。這對於在網路演示中保持品牌一致性特別有用。

#### 逐步實施：

**1. 定義輸入和輸出路徑**

設定輸入 PPTX 檔案所在的目錄以及要儲存輸出 HTML 檔案的目錄。

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. 開啟簡報文件**

使用 Aspose.Slides' `Presentation` 載入 PPTX 檔案的類別：

```python
with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    # 您的轉換代碼將會放在這裡。
```

此上下文管理器確保操作後資源已正確釋放。

**3. 建立自訂字體嵌入控制器**

使用以下方法排除嵌入某些字體 `EmbedAllFontsHtmlController`：

```python
font_name_exclude_list = ["Calibri", "Arial"]
embed_fonts_controller = slides.export.EmbedAllFontsHtmlController(font_name_exclude_list)
```

這裡，「Calibri」和「Arial」被排除在 HTML 輸出中嵌入。

**4.配置 HTML 匯出選項**

設定 `HtmlOptions` 在控制器中使用自訂字體格式化程式：

```python
html_options_embed = slides.export.HtmlOptions()
html_options_embed.html_formatter = slides.export.HtmlFormatter.create_custom_formatter(embed_fonts_controller)
```

此步驟確保僅將必要的字體嵌入到最終輸出中。

**5. 將簡報儲存為 HTML**

最後，使用您指定的選項將簡報儲存為 HTML 檔案：

```python
pres.save(out_dir + "convert_to_html_with_preserving_original_fonts_out.html", 
          slides.export.SaveFormat.HTML, html_options_embed)
```

### 故障排除提示：
- 確保路徑設定正確且可存取。
- 檢查系統上是否有任何可能影響轉換的缺失字體檔案。

## 實際應用

以下是此功能非常有用的一些實際場景：

1. **入口網站**：將簡報轉換為 HTML，以便無縫整合到 Web 應用程式中，而不會遺失品牌字體。
2. **文件管理系統**：將簡報嵌入內部門戶，同時保留文件保真度。
3. **電子學習平台**：使用轉換後的 HTML 檔案作為線上課程的一部分，保持一致的外觀和感覺。

## 性能考慮

為確保轉換期間的最佳性能：
- **優化記憶體使用**：透過及時關閉未使用的資源來管理資源分配。
- **批次處理**：批量轉換多個簡報以減少開銷。
- **使用最新的庫版本**：始終使用最新版本的 Aspose.Slides 來獲得改進的功能和修復錯誤。

## 結論

恭喜！您已經了解如何使用 Aspose.Slides for Python 將 PPTX 檔案轉換為 HTML，同時保留原始字體。此方法可確保您的簡報在各個平台上保持其預期的外觀。

**後續步驟：**
- 探索其他 Aspose.Slides 功能，例如 PDF 轉換或影像擷取。
- 針對不同的用例嘗試不同的字體嵌入選項。

準備好嘗試了嗎？在您的專案中實施此解決方案並觀察差異！

## 常見問題部分

1. **使用 Aspose.Slides Python 的系統需求是什麼？**
   - 需要相容版本的 Python 3.x，以及用於庫安裝的 pip。

2. **我可以從嵌入中排除兩種以上的字體嗎？**
   - 是的，你可以修改 `font_name_exclude_list` 包含您想要排除的任意數量的字體。

3. **轉換過程中如何處理大型 PPTX 檔案？**
   - 考慮分段處理它們或最佳化資源使用，如效能考量中所述。

4. **在哪裡可以找到有關 Aspose.Slides 功能的更多資訊？**
   - 這 [官方文檔](https://reference.aspose.com/slides/python-net/) 提供全面的指南和範例。

5. **如果我遇到問題，有哪些支援選項？**
   - 加入 [Aspose 論壇](https://forum.aspose.com/c/slides/11) 尋求社群驅動的解決方案或透過其管道尋求官方支援。

## 資源
- **文件**： [Aspose.Slides文檔](https://reference.aspose.com/slides/python-net/)
- **下載**： [Aspose.Slides Python版本](https://releases.aspose.com/slides/python-net/)
- **購買**： [購買 Aspose.Slides 許可證](https://purchase.aspose.com/buy)
- **免費試用**： [Aspose.Slides 免費試用](https://releases.aspose.com/slides/python-net/)
- **臨時執照**： [申請臨時執照](https://purchase.aspose.com/temporary-license/)
- **支援**： [Aspose 支援論壇](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}