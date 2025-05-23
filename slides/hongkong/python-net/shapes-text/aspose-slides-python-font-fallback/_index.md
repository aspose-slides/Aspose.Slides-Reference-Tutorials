---
"date": "2025-04-24"
"description": "了解如何使用 Aspose.Slides for Python 建立和管理字型回退規則，以確保您的簡報在不同系統上保持一致。"
"title": "掌握 Aspose.Slides for Python 中的字體回退&#58;綜合指南"
"url": "/zh-hant/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握 Aspose.Slides for Python 中的字體回退：綜合指南

## 介紹

在建立簡報時，字體相容性問題可能很棘手，尤其是當主要字體不支援 Unicode 字元時。 **Aspose.Slides for Python** 透過字體後備規則提供強大的解決方案，確保您的簡報在各種系統中的視覺吸引力和可讀性。

在本指南中，我們將探討如何使用 Aspose.Slides for Python 建立和管理字型回退規則。您將學習：
- 使用 Aspose.Slides 設定您的環境
- 建立字型後備規則集合
- 透過根據 Unicode 範圍新增或刪除字型來管理這些規則
- 將規則套用至簡報並將投影片渲染為影像

讓我們從準備您的環境開始。

## 先決條件

確保您的環境已準備好執行此任務。您需要準備以下物品：
1. **Aspose.Slides for Python**：此庫管理字體後備規則。
2. **Python 環境**：確保已安裝 Python（3.6 或更高版本）。
3. **Python 基礎知識**：熟悉 Python 語法和概念將有助於我們深入研究程式碼片段。

## 為 Python 設定 Aspose.Slides

### 安裝

首先，使用 pip 安裝 Aspose.Slides 函式庫：

```bash
pip install aspose.slides
```

### 許可證獲取

Aspose 提供免費試用許可證，讓使用者無限制地探索其功能。取得方法如下：
- 訪問 [Aspose 的購買頁面](https://purchase.aspose.com/buy) 用於購買選項或取得臨時許可證。
- 或者，從下載免費試用版 [下載部分](https://releases。aspose.com/slides/python-net/).

### 基本初始化

安裝後，在 Python 腳本中初始化 Aspose.Slides：

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## 實施指南

### 建立和管理字體後備規則

#### 概述

字體後備規則可確保簡報中的所有字元都具有適當的字體，從而保持具有獨特字元集的語言的可讀性。

#### 實施步驟

**1. 建立字體後備規則集合**

首先建立一個集合來定義後備字體：

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. 新增字體後備規則**

定義指定 Unicode 範圍和後備字體的規則：

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **參數**： `0x400` 是 Unicode 範圍的起始， `0x4FF` 是結束，並且 `"Times New Roman"` 是後備字體。

**3. 管理現有規則**

迭代每個規則以根據需要修改它們：

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. 刪除規則**

如果有必要，請從您的集合中刪除第一條規則：

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### 將字體回退規則套用至簡報並渲染圖像

#### 概述

設定字體後備規則後，將其應用於演示文稿，以確保文字在必要時使用指定的後備字體。

#### 實施步驟

**1.初始化您的環境**

準備輸入和輸出的目錄：

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. 將後備規則套用至簡報**

載入您的簡報檔案並套用字體規則：

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}