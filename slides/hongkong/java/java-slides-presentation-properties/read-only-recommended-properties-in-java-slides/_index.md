---
"description": "了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 簡報中啟用唯讀推薦屬性。請依照我們的逐步指南和原始程式碼範例來增強演示安全性。"
"linktitle": "Java 投影片中的唯讀推薦屬性"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的唯讀推薦屬性"
"url": "/zh-hant/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的唯讀推薦屬性


## Java 投影片中啟用唯讀推薦屬性的介紹

在本教學中，我們將探討如何使用 Aspose.Slides for Java 為 PowerPoint 簡報啟用唯讀推薦屬性。當您想要鼓勵用戶查看簡報而不做任何更改時，只讀推薦屬性會很有用。這些屬性表明簡報應該以唯讀模式開啟。我們將為您提供逐步指南以及 Java 原始程式碼來實現此目的。

## 先決條件

在我們開始之前，請確保您的專案中已經設定了 Aspose.Slides for Java 程式庫。您可以從 [Aspose.Slides for Java 網站](https://products。aspose.com/slides/java/).

## 步驟 1：建立新的 PowerPoint 簡報

我們將首先使用 Aspose.Slides for Java 建立一個新的 PowerPoint 簡報。如果您已經有演示文稿，則可以跳過此步驟。

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

在上面的程式碼中，我們定義了輸出 PowerPoint 檔案的路徑並建立了一個新的簡報物件。

## 步驟 2：啟用唯讀推薦屬性

現在，讓我們為簡報啟用「只讀推薦」屬性。

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

在此程式碼片段中，我們使用 `getProtectionManager().setReadOnlyRecommended(true)` 方法將「只讀推薦」屬性設為 `true`。這可確保當有人開啟簡報時，系統會提示他們以唯讀模式開啟它。

## 步驟 3：儲存簡報

最後，我們在啟用「建議只讀」屬性的情況下儲存簡報。

## Java 投影片中唯讀推薦屬性的完整原始碼

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 為 PowerPoint 簡報啟用「唯讀推薦」屬性。當您想要限制編輯並鼓勵查看者以唯讀模式使用簡報時，此功能會很有用。您可以透過為簡報設定密碼來進一步增強安全性。

## 常見問題解答

### 如何停用「推薦只讀」屬性？

若要停用「唯讀推薦」屬性，只需使用下列程式碼：

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### 我可以為「建議只讀」簡報設定密碼嗎？

是的，您可以使用 Aspose.Slides for Java 為唯讀推薦簡報設定密碼。您可以使用 `setPassword` 方法為簡報設定密碼。如果設定了密碼，即使在唯讀模式下，使用者也需要輸入密碼才能開啟簡報。

```java
pres.getProtectionManager().setPassword("YourPassword");
```

記得更換 `"YourPassword"` 使用您想要的密碼。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}