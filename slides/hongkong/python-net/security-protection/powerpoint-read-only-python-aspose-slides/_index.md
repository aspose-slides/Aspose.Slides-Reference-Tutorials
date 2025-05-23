---
"date": "2025-04-23"
"description": "了解如何使用 Aspose.Slides for Python 將 PowerPoint 簡報設定為唯讀並以程式設計方式計算投影片數量。非常適合安全文件共用和自動報告。"
"title": "使用 Aspose.Slides 將 PowerPoint 設定為唯讀並統計投影片數量"
"url": "/zh-hant/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Python 將 PowerPoint 設定為唯讀並計算幻燈片數量

## 介紹
您是否曾面臨分發簡報同時確保其不變的挑戰？或者您可能想要一種簡單的方法來驗證簡報中有多少張投影片而無需打開它？和 **Aspose.Slides for Python**，這些任務就變得簡單了。本教學將引導您將 PowerPoint 簡報設定為唯讀並使用 Aspose.Slides 計算投影片數量，從而為以程式設計方式管理 PowerPoint 檔案提供強大的解決方案。

**您將學到什麼：**
- 如何在 PowerPoint 簡報上設定寫入保護。
- 如何儲存具有唯讀限制的 PowerPoint 檔案。
- 如何載入簡報並有效地計算幻燈片數量。

讓我們深入了解如何在 Python 中無縫地實現這些任務。

## 先決條件
在開始之前，請確保您已：
- **Python 3.6+** 安裝在您的系統上。
- 存取用於安裝軟體包的命令列介面。

您還需要安裝適用於 Python 的 Aspose.Slides。這個強大的程式庫可以直接從您的 Python 環境對 PowerPoint 文件進行進階操作。雖然免費版本的功能有限，但獲得許可證（透過免費試用或購買）可以大幅擴展功能。

## 為 Python 設定 Aspose.Slides
要開始在 Python 中使用 Aspose.Slides，您需要先安裝它。方法如下：

### pip 安裝
在終端機或命令提示字元中執行以下命令：

```bash
pip install aspose.slides
```

這將下載並安裝適用於 Python 的 Aspose.Slides 的最新版本。

### 許可證取得步驟
1. **免費試用**：從免費試用開始探索基本功能。
2. **臨時執照**：取得臨時許可證以在評估期間解鎖全部功能。
3. **購買**：考慮購買許可證以獲得持續的訪問和支持。

獲得許可證文件後，請將其載入到腳本中，如下所示：

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## 實施指南
在本節中，我們將把實作分為兩個主要功能：將簡報設定為唯讀和計數投影片。

### 功能 1：將簡報儲存為唯讀
#### 概述
此功能可讓您對 PowerPoint 檔案設定寫入保護，並確保未輸入密碼就無法修改該檔案。這對於分發收件人應保持不變的簡報特別有用。

#### 步驟
##### 步驟 1：實例化展示對象
首先創建一個 `Presentation` 目的。這代表了 Python 中的 PPT 檔案。

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}