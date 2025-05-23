---
"date": "2025-04-16"
"description": "了解如何在 Aspose.Slides for .NET 中實作字體回退規則，以確保您的簡報能夠正確顯示不同語言和腳本的文字。"
"title": "如何在 Aspose.Slides for .NET&#58; 中設定字體後備規則綜合指南"
"url": "/zh-hant/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 如何在 Aspose.Slides for .NET 中設定字體回退規則：綜合指南

## 介紹

使用 Aspose.Slides for .NET 建立簡報有時需要處理特定字體無法支援的字符，例如泰米爾語或日語平假名。設定字體後備規則對於確保您的簡報正確顯示各種語言和符號的文字至關重要。

在本教程中，我們將指導您使用 Aspose.Slides for .NET 實作字體回退規則。從安裝到實際應用，本指南可確保您的簡報無論內容如何都能保持視覺一致性。

**您將學到什麼：**
- 為不同的腳本定義 Unicode 範圍。
- 為不支援的字元設定後備字體。
- 在實際示範場景中套用字體回退。
- 優化效能和與其他系統整合的技巧。

讓我們先回顧一下先決條件。

## 先決條件

在開始之前，請確保您已：

- **Aspose.Slides for .NET** 已安裝庫。使用以下任一方法進行安裝：
  - **.NET CLI**： 跑步 `dotnet add package Aspose.Slides`
  - **套件管理器**： 執行 `Install-Package Aspose.Slides`
  - **NuGet 套件管理器 UI**：搜尋並安裝最新版本。
- 使用 .NET Core 或 .NET Framework（4.5 或更高版本）設定的開發環境。
- 對 C# 程式設計有基本的了解。

## 設定 Aspose.Slides for .NET

要開始使用 Aspose.Slides，請從 [Aspose 網站](https://purchase.aspose.com/buy)。設定方法如下：

1. **安裝**：請按照上面提到的安裝步驟進行。
2. **許可證設定**：
   - 使用以下命令將您的許可證文件載入到您的專案中：
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

此設定可讓您開始使用 Aspose.Slides for .NET。

## 實施指南

在本節中，我們將以清晰的步驟概述設定字體後備規則的過程。

### 1. 定義 Unicode 範圍和備用字體

每個腳本或符號集都需要特定的 Unicode 範圍和相應的後備字體以確保正確顯示。

#### 泰米爾文字

- **概述**：當主要字體缺乏支援時，使用“Vijaya”表示泰米爾字元。

**實施步驟：**

##### 步驟 1：定義 Unicode 範圍
```csharp
uint startUnicodeIndexTamil = 0x0B80; // 泰米爾山脈的起點
uint endUnicodeIndexTamil = 0x0BFF;   // 泰米爾語範圍的結束
```
此程式碼片段定義了泰米爾字元的 Unicode 範圍。

##### 步驟 2：建立後備規則
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
在這裡，我們使用“Vijaya”作為替代字體創建後備規則。

#### 日語平假名

- **概述**：對於不支援的平假名字符，請使用“MS Mincho”或“MS Gothic”。

**實施步驟：**

##### 步驟 1：定義 Unicode 範圍
```csharp
uint startUnicodeIndexHiragana = 0x3040; // 平假名範圍的起始
uint endUnicodeIndexHiragana = 0x309F;   // 平假名範圍的結束
```
此程式碼片段設定了平假名的 Unicode 邊界。

##### 步驟 2：建立後備規則
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
此規則為平假名字元指定了多種後備字體。

#### 表情符號

- **概述**：確保表情符號使用適當的字體顯示，例如「Segoe UI Emoji」。

**實施步驟：**

##### 步驟 1：定義 Unicode 範圍
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // 表情符號範圍的開始
uint endUnicodeIndexEmoji = 0x1F64F;   // 表情符號範圍結束
```
這定義了表情符號的 Unicode 範圍。

##### 步驟 2：建立後備規則
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}