---
"description": "了解如何使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為自訂大小的 TIFF 映像。為開發人員提供帶有程式碼範例的逐步指南。"
"linktitle": "在 Java Slides 中使用自訂大小進行轉換"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中使用自訂大小進行轉換"
"url": "/zh-hant/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中使用自訂大小進行轉換


## Java Slides 中自訂大小轉換簡介

在本文中，我們將探討如何使用 Aspose.Slides for Java API 將 PowerPoint 簡報轉換為自訂大小的 TIFF 影像。 Aspose.Slides for Java 是一個功能強大的函式庫，可讓開發人員以程式設計方式處理 PowerPoint 檔案。我們將一步一步地為您提供完成此任務所需的 Java 程式碼。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

- 已安裝 Java 開發工具包 (JDK)
- Aspose.Slides for Java 函式庫

您可以從網站下載 Aspose.Slides for Java 函式庫： [下載 Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## 步驟1：導入Aspose.Slides庫

首先，您需要將 Aspose.Slides 庫匯入到您的 Java 專案中。您可以按照以下步驟操作：

```java
// 新增必要的導入語句
import com.aspose.slides.*;
```

## 第 2 步：載入 PowerPoint 簡報

接下來，您需要載入要轉換為 TIFF 影像的 PowerPoint 簡報。代替 `"Your Document Directory"` 使用您的簡報文件的實際路徑。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 實例化代表 Presentation 檔案的 Presentation 對象
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## 步驟 3：設定 TIFF 轉換選項

現在，讓我們設定 TIFF 轉換的選項。我們將指定壓縮類型、DPI（每英吋點數）、影像大小和註解位置。您可以根據您的要求自訂這些選項。

```java
// 實例化 TiffOptions 類
TiffOptions opts = new TiffOptions();

// 設定壓縮類型
opts.setCompressionType(TiffCompressionTypes.Default);

// 設定影像 DPI
opts.setDpiX(200);
opts.setDpiY(100);

// 設定圖像大小
opts.setImageSize(new Dimension(1728, 1078));

// 設定音符位置
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## 步驟 4：另存為 TIFF

配置完所有選項後，您現在可以將簡報儲存為具有指定設定的 TIFF 影像。

```java
// 將簡報儲存為具有指定影像大小的 TIFF
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Java 投影片中自訂大小轉換的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 實例化代表 Presentation 檔案的 Presentation 對象
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// 實例化 TiffOptions 類
	TiffOptions opts = new TiffOptions();
	// 設定壓縮類型
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// 壓縮類型
	// 預設 - 指定預設壓縮方案 (LZW)。
	// 無 - 指定不壓縮。
	// CCITT3
	// CCITT4
	// 低零度
	// 右心室射血分數
	// 深度取決於壓縮類型，無法手動設定。
	// 解析度單位總是等於“2”（每吋點數）
	// 設定影像 DPI
	opts.setDpiX(200);
	opts.setDpiY(100);
	// 設定圖像大小
	opts.setImageSize(new Dimension(1728, 1078));
	// 將簡報儲存為具有指定影像大小的 TIFF
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

恭喜！您已成功使用 Aspose.Slides for Java 將 PowerPoint 簡報轉換為具有自訂大小的 TIFF 映像。當您需要從簡報中產生高品質圖像以用於各種目的時，這可能是一個有價值的功能。

## 常見問題解答

### 如何更改 TIFF 影像的壓縮類型？

您可以透過修改 `setCompressionType` 方法 `TiffOptions` 班級。有不同的壓縮類型可用，例如預設、無、CCITT3、CCITT4、LZW 和 RLE。

### 我可以調整 TIFF 影像的 DPI（每吋點數）嗎？

是的，你可以使用 `setDpiX` 和 `setDpiY` 方法 `TiffOptions` 班級。只需設定所需的值即可控制影像解析度。

### TIFF 影像中註釋位置有哪些可用選項？

TIFF 影像中的註解位置可以使用 `setNotesPosition` 方法具有 BottomFull、BottomTruncated 和 SlideOnly 等選項。選擇最適合您需求的。

### 是否可以為 TIFF 轉換指定自訂影像大小？

絕對地！您可以使用 `setImageSize` 方法 `TiffOptions` 班級。提供您想要的輸出影像的尺寸（寬度和高度）。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多資訊？

有關 Aspose.Slides for Java 的詳細文件和其他信息，請訪問文件： [Aspose.Slides for Java API參考](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}