---
"description": "了解如何使用 Aspose.Slides for Java 存取 PowerPoint 中的內建屬性。本教學將指導您檢索作者、建立日期等資訊。"
"linktitle": "存取 PowerPoint 中的內建屬性"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "存取 PowerPoint 中的內建屬性"
"url": "/zh-hant/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 存取 PowerPoint 中的內建屬性

## 介紹
在本教學中，我們將探討如何使用 Aspose.Slides for Java 存取 PowerPoint 簡報中的內建屬性。 Aspose.Slides 是一個功能強大的函式庫，可讓 Java 開發人員以程式設計方式處理 PowerPoint 簡報，從而實現無縫讀取和修改屬性等任務。
## 先決條件
在開始之前，請確保您符合以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從下載 [這裡](https://www。oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java：從下列位置下載並安裝 Aspose.Slides for Java [此連結](https://releases。aspose.com/slides/java/).

## 導入包
首先，您需要將必要的套件匯入到您的 Java 專案中。在 Java 檔案的開頭加入以下導入語句：
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## 步驟 1：設定演示對象
首先設定 Presentation 物件來代表您想要處理的 PowerPoint 簡報。您可以按照以下步驟操作：
```java
// 包含演示檔案的目錄路徑
String dataDir = "path_to_your_presentation_directory/";
// 實例化 Presentation 類
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## 步驟 2：存取文件屬性
設定 Presentation 物件後，您可以使用 IDocumentProperties 介面存取簡報的內建屬性。以下是檢索各種屬性的方法：
### 類別
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### 目前狀態
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### 建立日期
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### 作者
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### 描述
```java
System.out.println("Description : " + documentProperties.getComments());
```
### 關鍵字
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### 最後修改者
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### 導師
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### 修改日期
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### 演示格式
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### 最後列印日期
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### 生產者之間共享
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### 主題
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### 標題
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## 結論
在本教程中，我們學習如何使用 Aspose.Slides for Java 存取 PowerPoint 簡報中的內建屬性。透過遵循上面概述的步驟，您可以輕鬆地以程式設計方式檢索各種屬性，例如作者、建立日期和標題。
## 常見問題解答
### 我可以使用 Aspose.Slides for Java 修改這些內建屬性嗎？
是的，您可以使用 Aspose.Slides 來修改這些屬性。只需使用 IDocumentProperties 介面提供的適當的 setter 方法。
### Aspose.Slides 是否與不同版本的 PowerPoint 相容？
Aspose.Slides 支援多種 PowerPoint 版本，確保跨各種平台的兼容性。
### 我也可以檢索自訂屬性嗎？
是的，除了內建屬性之外，您還可以使用 Aspose.Slides for Java 檢索和修改自訂屬性。
### Aspose.Slides 提供文件和支援嗎？
是的，您可以在 [Aspose 網站](https://reference。aspose.com/slides/java/).
### Aspose.Slides for Java 有試用版嗎？
是的，您可以從下載免費試用版 [這裡](https://releases。aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}