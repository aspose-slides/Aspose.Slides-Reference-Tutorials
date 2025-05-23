---
"description": "了解如何使用 Aspose.Slides for Java 在 Java Slides 中設定預定義視圖類型。包含程式碼範例和常見問題的逐步指南。"
"linktitle": "在 Java Slides 中儲存為預定義視圖類型"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java Slides 中儲存為預定義視圖類型"
"url": "/zh-hant/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中儲存為預定義視圖類型


## Java Slides 中「另存為預定義視圖類型」簡介

在本逐步指南中，我們將探討如何使用 Aspose.Slides for Java 儲存具有預先定義視圖類型的簡報。我們將為您提供成功完成此任務所需的程式碼和解釋。

## 先決條件

在開始之前，請確保您具備以下條件：

- Java 程式設計基礎知識。
- 已安裝 Java 函式庫的 Aspose.Slides。
- 您選擇的整合開發環境 (IDE)。

## 設定您的環境

首先，請按照以下步驟設定您的開發環境：

1. 在您的 IDE 中建立一個新的 Java 專案。
2. 將 Aspose.Slides for Java 程式庫作為依賴項新增至您的專案中。

現在您的環境已經設定好了，讓我們繼續編寫程式碼。

## 步驟 1：建立簡報

為了示範如何儲存具有預先定義視圖類型的簡報，我們首先建立一個新的簡報。以下是建立簡報的程式碼：

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 開啟簡報文件
Presentation presentation = new Presentation();
```

在這段程式碼中，我們創造一個新的 `Presentation` 對象，代表我們的 PowerPoint 簡報。

## 步驟2：設定視圖類型

接下來，我們將設定簡報的視圖類型。視圖類型定義了簡報開啟時的顯示方式。在此範例中，我們將其設定為「投影片母版檢視」。程式碼如下：

```java
// 設定視圖類型
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

在上面的程式碼中，我們使用 `setLastView` 方法 `ViewProperties` 設定視圖類型的類 `SlideMasterView`。您可以根據需要選擇其他視圖類型。

## 步驟3：儲存簡報

現在我們已經建立了簡報並設定了視圖類型，是時候儲存簡報了。我們將把它儲存為 PPTX 格式。程式碼如下：

```java
// 儲存簡報
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

在此程式碼中，我們使用 `save` 方法 `Presentation` 類別使用指定的檔案名稱和格式儲存簡報。

## Java 投影片中儲存為預先定義檢視類型的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 開啟簡報文件
Presentation presentation = new Presentation();
try
{
	// 設定視圖類型
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// 儲存簡報
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 在 Java 中保存具有預定義視圖類型的簡報。透過遵循提供的程式碼和步驟，您可以輕鬆設定簡報的視圖類型並將其儲存為所需的格式。

## 常見問題解答

### 如何將檢視類型變更為「投影片母版檢視」以外的其他檢視？

若要將檢視類型變更為「投影片母版檢視」以外的其他類型，只需替換 `ViewType.SlideMasterView` 使用所需的視圖類型，例如 `ViewType.N或者malView` or `ViewType.SlideSorterView`，在我們設定視圖類型的程式碼中。

### 我可以為簡報中的單一投影片設定視圖屬性嗎？

是的，您可以使用 Aspose.Slides for Java 為單一投影片設定檢視屬性。您可以透過遍歷簡報中的投影片來分別存取和操作每張投影片的屬性。

### 我可以用什麼其他格式儲存我的簡報？

Aspose.Slides for Java 支援各種輸出格式，包括 PPTX、PDF、TIFF、HTML 等。您可以在儲存簡報時使用適當的 `SaveFormat` 枚舉值。

### Aspose.Slides for Java 是否適合簡報的批次處理？

是的，Aspose.Slides for Java 非常適合批次任務。您可以使用 Java 程式碼自動處理多個簡報、套用變更並批次儲存它們。

### 在哪裡可以找到有關 Aspose.Slides for Java 的更多資訊和文件？

有關 Aspose.Slides for Java 的綜合文件和參考資料，請造訪文件網站： [Aspose.Slides for Java 文檔](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}