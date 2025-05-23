---
"description": "了解如何使用 Java Slides 中的自訂文件屬性增強 PowerPoint 簡報。使用 Aspose.Slides for Java 的程式碼範例的逐步指南。"
"linktitle": "在 Java Slides 中新增自訂文件屬性"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中新增自訂文件屬性"
"url": "/zh-hant/java/presentation-properties/add-custom-document-properties-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中新增自訂文件屬性


## Java Slides 中新增自訂文件屬性的簡介

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 為 PowerPoint 簡報新增自訂文件屬性的過程。自訂文件屬性可讓您儲存有關簡報的其他資訊以供參考或分類。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。

## 步驟1：導入所需的包

```java
import com.aspose.slides.*;
```

## 第 2 步：建立新簡報

首先，您需要建立一個新的演示物件。您可以按照如下方式進行操作：

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 實例化 Presentation 類
Presentation presentation = new Presentation();
```

## 步驟3：取得文件屬性

接下來，您將檢索簡報的文檔屬性。這些屬性包括標題、作者等內建屬性以及您可以新增的自訂屬性。

```java
// 取得文檔屬性
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## 步驟 4：新增自訂屬性

現在，讓我們為簡報新增自訂屬性。自訂屬性由名稱和值組成。您可以使用它們來儲存您想要的任何資訊。

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## 步驟 5：取得特定索引處的屬性名稱

您也可以檢索特定索引處的自訂屬性的名稱。如果您需要使用特定屬性，這將很有用。

```java
// 取得特定索引處的屬性名稱
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## 步驟 6：刪除選定的屬性

如果您想要刪除自訂屬性，您可以透過指定其名稱來實現。在這裡，我們刪除在步驟 5 中獲得的屬性。

```java
// 刪除選定的屬性
documentProperties.removeCustomProperty(getPropertyName);
```

## 步驟 7：儲存簡報

最後，將新增和刪除的自訂屬性的簡報儲存到文件中。

```java
// 儲存簡報
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## 在 Java 投影片中新增自訂文件屬性的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 實例化 Presentation 類
Presentation presentation = new Presentation();
// 取得文檔屬性
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// 新增自訂屬性
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// 取得特定索引處的屬性名稱
String getPropertyName = documentProperties.getCustomPropertyName(2);
// 刪除選定的屬性
documentProperties.removeCustomProperty(getPropertyName);
// 儲存簡報
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## 結論

您已經了解如何使用 Aspose.Slides 為 Java 中的 PowerPoint 簡報新增自訂文件屬性。自訂屬性對於儲存與您的簡報相關的附加資訊很有價值。您可以根據特定用例的需要擴展這些知識以包含更多自訂屬性。

## 常見問題解答

### 如何檢索自訂屬性的值？

若要檢索自訂屬性的值，您可以使用 `get_Item` 方法 `documentProperties` 目的。例如：

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### 我可以新增不同資料類型的自訂屬性嗎？

是的，您可以新增各種資料類型的自訂屬性，包括數字、字串、日期等，如範例所示。 Aspose.Slides for Java 可以無縫處理不同的資料類型。

### 我可以新增的自訂屬性數量有限制嗎？

您可以新增的自訂屬性的數量沒有嚴格限制。但是請記住，添加過多的屬性可能會影響簡報文件的效能和大小。

### 如何列出簡報中的所有自訂屬性？

您可以循環遍歷所有自訂屬性來列出它們。以下是如何執行此操作的範例：

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

此程式碼將顯示簡報中所有自訂屬性的名稱和值。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}