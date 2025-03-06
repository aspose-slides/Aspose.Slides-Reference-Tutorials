---
title: 使用 Java 以預設常規字體儲存 PowerPoint
linktitle: 使用 Java 以預設常規字體儲存 PowerPoint
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 以程式設計方式操作 PowerPoint 簡報。透過逐步教學掌握 Java PowerPoint 處理。
weight: 12
url: /zh-hant/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 介紹
在 Java 開發領域，以程式設計方式建立和操作 PowerPoint 簡報可以大幅提高工作效率和自訂選項。 Aspose.Slides for Java 是一個強大的函式庫，讓開發人員能夠有效地處理 PowerPoint 文件，提供從簡單修改到複雜簡報的一整套功能。
## 先決條件
在深入使用 Aspose.Slides for Java 之前，請確保您已設定以下先決條件：
1. Java 開發工具包 (JDK)：Aspose.Slides for Java 需要 JDK 1.8 或更高版本才能正常運作。
2. Aspose.Slides for Java JAR：從下列位置下載最新版本的 Aspose.Slides for Java[這裡](https://releases.aspose.com/slides/java/).
3. 整合開發環境 (IDE)：使用 IntelliJ IDEA、Eclipse 或您選擇的其他 Java IDE。
4. 對 Java 的基本了解：熟悉 Java 程式語言基礎知識是必要的。

## 導入包
若要開始使用 Aspose.Slides for Java，請匯入必要的套件：
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
這可確保您可以存取 Aspose.Slides for Java 提供的所有類別和方法。
## 第 1 步：設定您的項目
首先，在 IDE 中建立一個新的 Java 項目，並將 Aspose.Slides for Java JAR 檔案包含在專案的建置路徑中。
## 第 2 步：初始化表示對象
實例化一個`Presentation`透過從本機目錄載入現有 PowerPoint 檔案 (.pptx) 來實現物件。
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
//載入簡報
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
代替`"Your Document Directory"`和`"Your Output Directory"`與您的實際文件路徑。
## 步驟 3：使用預設常規字體儲存簡報
使用以下命令指定輸出格式（HTML 和 PDF）的預設常規字體`HtmlOptions`和`PdfOptions`分別。
```java
try {
    // HTML 儲存選項
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    //PDF 儲存選項
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
確保更換`"Arial Black"`和`"Lucida Console"`使用您想要的預設常規字體。

## 結論
透過執行這些步驟，您已經了解如何使用 Aspose.Slides for Java 有效地操作 PowerPoint 簡報。此功能可讓您自動執行任務、自訂簡報並透過進階 PowerPoint 處理功能增強您的 Java 應用程式。
## 常見問題解答
### Aspose.Slides for Java 可以與舊版的 JDK 一起使用嗎？
Aspose.Slides for Java 需要 JDK 1.8 或更高版本才能相容。
### 如何取得 Aspose.Slides for Java 的臨時許可？
您可以從以下地址取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到有關 Aspose.Slides for Java 的更詳細文件？
探索全面的文檔[這裡](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java 是否有社群支援？
是的，您可以獲得社區支持[這裡](https://forum.aspose.com/c/slides/11).
### 我可以免費試用 Aspose.Slides for Java 嗎？
是的，下載免費試用版[這裡](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
