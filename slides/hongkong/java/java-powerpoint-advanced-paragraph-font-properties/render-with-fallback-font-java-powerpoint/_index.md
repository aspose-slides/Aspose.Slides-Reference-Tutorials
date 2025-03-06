---
title: 在 Java PowerPoint 中使用後備字體進行渲染
linktitle: 在 Java PowerPoint 中使用後備字體進行渲染
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 在 Java PowerPoint 簡報中呈現具有後備字體的文字。請遵循此逐步指南以實現無縫實施。
weight: 13
url: /zh-hant/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
在 Java 中建立和操作 PowerPoint 簡報可能具有挑戰性，但使用 Aspose.Slides，您可以有效率地完成此任務。一項重要功能是能夠使用後備字體呈現文字。本文提供了有關如何使用 Aspose.Slides for Java 在 PowerPoint 投影片中實現後備字體的詳細逐步指南。
## 先決條件
在深入實施之前，讓我們確保您擁有所需的一切：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Slides for Java：您可以從[Aspose.Slides for Java 下載頁面](https://releases.aspose.com/slides/java/).
3. 整合開發環境 (IDE)：像 IntelliJ IDEA 或 Eclipse 這樣的 IDE 將使您的開發過程更加順利。
4. 依賴項：將 Aspose.Slides 包含在專案的依賴項中。
## 導入包
首先，我們需要在 Java 程式中匯入必要的套件。
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
讓我們將這個過程分解為可管理的步驟。
## 第 1 步：設定您的項目
在編寫任何程式碼之前，請確保您的專案設定正確。這包括將 Aspose.Slides 庫新增到您的專案中。您可以從以下位置下載庫來完成此操作[用於 Java 的 Aspose.Slides](https://releases.aspose.com/slides/java/)並將其添加到您的建置路徑中。
## 第 2 步：初始化字型回退規則
您需要建立一個實例`IFontFallBackRulesCollection`類別並為其添加規則。這些規則定義特定 Unicode 範圍的字型後備。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立規則集合的新實例
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
//制定多項規則
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## 步驟 3：修改後備規則
在此步驟中，我們將透過刪除現有後備字體並更新特定 Unicode 範圍的規則來修改後備規則。
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    //嘗試從已載入的規則中刪除 FallBack 字體“Tahoma”
    fallBackRule.remove("Tahoma");
    //指定範圍的更新規則
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//從清單中刪除任何現有規則
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## 第 4 步：載入簡報
載入要修改的 PowerPoint 簡報。
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## 步驟 5：為簡報指派後備規則
將準備好的後備規則指派給簡報的字型管理器。
```java
try {
    //指派準備好的規則清單以供使用
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    //使用初始化的規則集合渲染縮圖並將其儲存為 PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 第6步：儲存並測試
最後，保存您的工作並測試實施，以確保一切按預期工作。如果遇到任何問題，請仔細檢查您的設定並確保正確新增所有依賴項。
## 結論
透過遵循本指南，您可以使用 Aspose.Slides for Java 在 PowerPoint 簡報中有效地呈現具有後備字體的文字。此過程可確保您的簡報保持一致的格式，即使主要字體不可用也是如此。快樂編碼！
## 常見問題解答
### 什麼是 Java 版 Aspose.Slides？
Aspose.Slides for Java 是一個函式庫，可讓開發人員在 Java 應用程式中建立、修改和渲染 PowerPoint 簡報。
### 如何將 Aspose.Slides 加入我的專案中？
您可以從以下位置下載該程式庫[Aspose.Slides 下載頁面](https://releases.aspose.com/slides/java/)並將其添加到專案的建置路徑中。
### 什麼是後備字體？
後備字體是指定字體不可用或不支援某些字元時使用的替代字體。
### 我可以使用多個後備規則嗎？
是的，您可以新增多個後備規則來處理不同的 Unicode 範圍和字型。
### 我可以在哪裡獲得 Aspose.Slides 的支援？
您可以從以下方面獲得支持[Aspose.Slides 支援論壇](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
