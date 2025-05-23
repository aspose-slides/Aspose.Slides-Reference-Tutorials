---
"description": "了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 中設定字體回退以確保文字顯示的一致性。"
"linktitle": "在 Java PowerPoint 中設定字型回退"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java PowerPoint 中設定字型回退"
"url": "/zh-hant/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java PowerPoint 中設定字型回退

## 介紹
在本教學中，我們將深入研究使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中設定字型回退的複雜度。字型回退對於確保簡報中的文字在不同的裝置和作業系統上正確顯示至關重要，即使所需的字型不可用。
## 先決條件
在開始之前，請確保您具備以下條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
- Aspose.Slides for Java 函式庫。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).
- 對 Java 程式語言有基本的了解。
- 整合開發環境 (IDE)，例如 IntelliJ IDEA 或 Eclipse。

## 導入包
首先，在您的 Java 類別中包含必要的 Aspose.Slides for Java 套件：
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## 步驟 1：初始化字型回退規則
若要設定字型後備，您需要定義指定 Unicode 範圍和對應後備字型的規則。初始化這些規則的方法如下：
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## 步驟 2：套用字體後備規則
接下來，將這些規則套用到需要設定字體回退的簡報或投影片中。以下是將這些規則套用至 PowerPoint 簡報中的投影片的範例：
```java
// 假設投影片是你的投影片對象
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## 結論
使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中設定字體回退對於確保在不同環境中保持一致的文字顯示至關重要。透過定義本教學中簡報的後備規則，您可以處理特定字體不可用的情況，從而保持簡報的完整性。

## 常見問題解答
### PowerPoint 簡報中的字型回退是什麼？
字型回退透過使用可用字型取代未安裝的字型來確保文字正確顯示。
### 如何下載適用於 Java 的 Aspose.Slides？
您可以從以下位置下載 Aspose.Slides for Java [這裡](https://releases。aspose.com/slides/java/).
### Aspose.Slides for Java 是否與所有 Java IDE 相容？
是的，Aspose.Slides for Java 與流行的 Java IDE（如 IntelliJ IDEA 和 Eclipse）相容。
### 我可以獲得 Aspose 產品的臨時許可證嗎？
是的，Aspose 產品的臨時許可證可以從 [這裡](https://purchase。aspose.com/temporary-license/).
### 在哪裡可以找到對 Aspose.Slides for Java 的支援？
有關 Aspose.Slides for Java 的支持，請訪問 [Aspose 論壇](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}