---
"description": "使用 Aspose.Slides for Java 優化您的 PowerPoint 簡報。學習設定屬性、停用加密、新增密碼保護並輕鬆儲存。"
"linktitle": "在 Java 投影片中儲存屬性"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 投影片中儲存屬性"
"url": "/zh-hant/java/saving-options/save-properties-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中儲存屬性


## Java 投影片中儲存屬性的介紹

在本教學中，我們將指導您使用 Aspose.Slides for Java 在 PowerPoint 簡報中儲存屬性的過程。您將學習如何設定文件屬性、停用文件屬性的加密、設定密碼來保護您的簡報以及將其儲存到文件中。我們將為您提供逐步說明和原始程式碼範例。

## 先決條件

在開始之前，請確保已將 Aspose.Slides for Java 程式庫整合到您的 Java 專案中。您可以從 Aspose 網站下載該庫 [這裡](https://downloads。aspose.com/slides/java).

## 步驟 1：導入所需庫

首先，導入必要的類別和庫：

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 步驟 2：建立演示對象

實例化一個 Presentation 物件來代表您的 PowerPoint 簡報。您可以建立新的簡報或載入現有的簡報。在此範例中，我們將建立一個新的簡報。

```java
// 您要儲存簡報的目錄路徑
String dataDir = "Your Document Directory";

// 實例化 Presentation 對象
Presentation presentation = new Presentation();
```

## 步驟 3：設定文檔屬性

您可以設定各種文件屬性，例如標題、作者、關鍵字等。在這裡，我們將設定一些常用屬性：

```java
// 設定簡報的標題
presentation.getDocumentProperties().setTitle("My Presentation");

// 設定簡報的作者
presentation.getDocumentProperties().setAuthor("John Doe");

// 設定簡報的關鍵字
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## 步驟 4：停用文件屬性加密

預設情況下，Aspose.Slides 會對文件屬性進行加密。如果要停用文件屬性的加密，請使用下列程式碼：

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## 步驟5：設定密碼保護簡報

您可以使用密碼保護您的簡報以限制存取。使用 `encrypt` 設定密碼的方法：

```java
// 設定密碼來保護簡報
presentation.getProtectionManager().encrypt("your_password");
```

代替 `"your_password"` 使用您想要的密碼。

## 步驟 6：儲存簡報

最後，將簡報儲存到文件中。在此範例中，我們將其儲存為 PPTX 檔案：

```java
// 將簡報儲存到文件
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

代替 `"Password_Protected_Presentation_out.pptx"` 使用您想要的檔案名稱和路徑。

## Java 投影片中保存屬性的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 實例化代表 PPT 檔案的 Presentation 對象
Presentation presentation = new Presentation();
try
{
	//....在這裡做一些工作.....
	// 在密碼保護模式下設定對文件屬性的存取權限
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// 設定密碼
	presentation.getProtectionManager().encrypt("pass");
	// 將簡報儲存到文件
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中儲存文件屬性。您可以設定各種屬性，停用文件屬性的加密，設定保護密碼，並以所需的格式儲存簡報。

## 常見問題解答

### 如何在 Aspose.Slides for Java 中設定文件屬性？

要在 Aspose.Slides for Java 中設定文件屬性，您可以使用 `DocumentProperties` 班級。以下是如何設定標題、作者和關鍵字等屬性的範例：

```java
// 設定簡報的標題
presentation.getDocumentProperties().setTitle("My Presentation");

// 設定簡報的作者
presentation.getDocumentProperties().setAuthor("John Doe");

// 設定簡報的關鍵字
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### 禁用文檔屬性加密的目的是什麼？

停用文檔屬性加密可讓您儲存未加密的文檔元資料。當您希望無需輸入密碼即可看到和存取文件屬性（例如標題、作者等）時，此功能很有用。

您可以使用以下程式碼停用加密：

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### 如何使用 Aspose.Slides for Java 透過密碼保護我的 PowerPoint 簡報？

若要使用密碼保護您的 PowerPoint 簡報，您可以使用 `encrypt` 提供的方法 `ProtectionManager` 班級。設定密碼的方法如下：

```java
// 設定密碼來保護簡報
presentation.getProtectionManager().encrypt("your_password");
```

代替 `"your_password"` 使用您想要的密碼。

### 我可以將簡報儲存為 PPTX 以外的其他格式嗎？

是的，您可以將簡報儲存為 Aspose.Slides for Java 支援的各種格式，例如 PPT、PDF 等。若要以不同的格式儲存，請更改 `SaveFormat` 參數 `presentation.save` 方法。例如，儲存為 PDF：

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### 保存後是否需要處理Presentation物件？

處置 Presentation 物件以釋放系統資源是一種很好的做法。您可以使用 `finally` 區塊以確保正確處置，如程式碼範例所示：

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

這有助於防止應用程式出現記憶體洩漏。

### 如何了解有關 Aspose.Slides for Java 及其功能的更多資訊？

您可以在以下位置瀏覽 Aspose.Slides for Java 文檔 [這裡](https://docs.aspose.com/slides/java/) 有關使用該庫的詳細資訊、教程和範例。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}