---
title: 在 Java PowerPoint 中設定字型回退
linktitle: 在 Java PowerPoint 中設定字型回退
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 中設定字體後備，以確保文字顯示一致。
weight: 16
url: /zh-hant/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
在本教學中，我們將深入研究使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中設定字型後備的複雜度。字型後備對於確保簡報中的文字在不同裝置和作業系統上正確顯示至關重要，即使所需的字型不可用。
## 先決條件
在我們開始之前，請確保您具備以下條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Slides。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).
- 對 Java 程式語言有基本的了解。
- 整合開發環境 (IDE)，例如 IntelliJ IDEA 或 Eclipse。

## 導入包
首先，在 Java 類別中包含必要的 Aspose.Slides for Java 套件：
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## 第 1 步：初始化字型回退規則
若要設定後備字體，您需要定義指定 Unicode 範圍和對應後備字體的規則。以下是初始化這些規則的方法：
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## 第 2 步：套用字體後備規則
接下來，您將這些規則套用到需要設定字體後備的簡報或投影片。以下是將這些規則套用至 PowerPoint 簡報中的投影片的範例：
```java
//假設投影片是您的 Slide 對象
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## 結論
使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中設定字型後備對於確保不同環境中文字顯示的一致性至關重要。透過定義本教學中簡報的後備規則，您可以處理特定字體不可用的情況，從而保持簡報的完整性。

## 常見問題解答
### PowerPoint 簡報中的備用字體是什麼？
字型後備可透過以可用字型取代未安裝的字型來確保文字正確顯示。
### 如何下載 Java 版 Aspose.Slides？
您可以從以下位置下載 Aspose.Slides for Java：[這裡](https://releases.aspose.com/slides/java/).
### Aspose.Slides for Java 是否與所有 Java IDE 相容？
是的，Aspose.Slides for Java 與 IntelliJ IDEA 和 Eclipse 等流行的 Java IDE 相容。
### 我可以獲得 Aspose 產品的臨時許可證嗎？
是的，可以從以下位置取得 Aspose 產品的臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到 Aspose.Slides for Java 的支援？
有關 Aspose.Slides for Java 的支持，請訪問[Aspose論壇](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
