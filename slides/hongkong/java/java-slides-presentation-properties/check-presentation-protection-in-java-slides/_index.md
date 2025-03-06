---
title: 檢查 Java 投影片中的簡報保護
linktitle: 檢查 Java 投影片中的簡報保護
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 檢查 Java 投影片中的簡報保護。本逐步指南提供了寫入和開放保護檢查的程式碼範例。
weight: 15
url: /zh-hant/java/presentation-properties/check-presentation-protection-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 在 Java 投影片中檢查簡報保護簡介

在本教程中，我們將探討如何使用 Aspose.Slides for Java 檢查演示保護。我們將介紹兩種情況：檢查簡報的寫入保護和檢查開啟保護。我們將為每個場景提供逐步程式碼範例。

## 先決條件

在開始之前，請確保您已在 Java 專案中設定了 Aspose.Slides for Java 程式庫。您可以從 Aspose 網站下載它並將其新增至專案的依賴項。

### Maven依賴

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

代替`your_version_here`與您正在使用的 Aspose.Slides for Java 版本。

## 第 1 步：檢查寫入保護

若要檢查簡報是否受密碼寫保護，您可以使用`IPresentationInfo`介面.這是執行此操作的程式碼：

```java
//來源簡報的路徑
String pptxFile = "path_to_presentation.pptx";

//透過IPresentationInfo介面檢查寫入保護密碼
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

代替`"path_to_presentation.pptx"`與簡報文件的實際路徑和`"password_here"`與寫保護密碼。

## 步驟 2：檢查開放保護

若要檢查簡報是否受開啟密碼保護，您可以使用`IPresentationInfo`介面.這是執行此操作的程式碼：

```java
//來源簡報的路徑
String pptFile = "path_to_presentation.ppt";

//透過 IPresentationInfo 介面檢查示範開放保護
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

代替`"path_to_presentation.ppt"`與簡報文件的實際路徑。

## Java 投影片中檢查簡報保護的完整原始碼

```java
//源演示的路徑
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
//透過IPresentationInfo介面檢查寫入保護密碼
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
//透過IProtectionManager介面檢查寫入保護密碼
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
//透過 IPresentationInfo 介面檢查示範開放保護
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 檢查 Java 投影片中的簡報保護。我們討論了兩種場景：檢查寫入保護和檢查開放保護。現在您可以將這些檢查整合到您的 Java 應用程式中，以有效地處理受保護的簡報。

## 常見問題解答

### 如何取得 Java 版 Aspose.Slides？

您可以從 Aspose 網站下載 Aspose.Slides for Java 或將其新增為專案中的 Maven 依賴項，如先決條件部分所示。

### 我可以同時檢查簡報的寫入保護和開啟保護嗎？

是的，您可以使用提供的程式碼範例檢查簡報的寫入保護和開啟保護。

### 忘記保護密碼怎麼辦？

如果您忘記了簡報的保護密碼，則沒有內建方法可以恢復它。請務必記錄您的密碼以避免此類情況的發生。

### Aspose.Slides for Java 是否與最新的 PowerPoint 檔案格式相容？

是的，Aspose.Slides for Java 支援最新的 PowerPoint 文件格式，包括 .pptx 檔案。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
