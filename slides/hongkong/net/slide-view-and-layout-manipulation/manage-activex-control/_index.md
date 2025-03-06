---
title: 在 PowerPoint 中管理 ActiveX 控件
linktitle: 在 PowerPoint 中管理 ActiveX 控件
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for .NET 透過 ActiveX 控制項增強 PowerPoint 簡報。我們的逐步指南涵蓋插入、操作、自訂、事件處理等。
weight: 13
url: /zh-hant/net/slide-view-and-layout-manipulation/manage-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

ActiveX 控制項是強大的元素，可以增強 PowerPoint 簡報的功能和互動性。這些控制項可讓您在投影片中直接嵌入和操作多媒體播放器、資料輸入表單等物件。在本文中，我們將探討如何使用 Aspose.Slides for .NET 管理 PowerPoint 中的 ActiveX 控件，Aspose.Slides for .NET 是一個多功能函式庫，可在 .NET 應用程式中無縫整合和操作 PowerPoint 檔案。

## 將 ActiveX 控制項新增至 PowerPoint 投影片

若要開始將 ActiveX 控制項合併到 PowerPoint 簡報中，請依照下列步驟操作：

1. 建立新的 PowerPoint 簡報：首先，使用 Aspose.Slides for .NET 建立新的 PowerPoint 簡報。您可以參考[Aspose.Slides for .NET API 參考](https://reference.aspose.com/slides/net/)有關如何處理簡報的指導。

2. 新增投影片：使用庫將新投影片新增至簡報中。這將是您要插入 ActiveX 控制項的投影片。

3. 插入 ActiveX 控制項： 現在是時候將 ActiveX 控制項插入到投影片上了。您可以透過以下範例程式碼來實現此目的：

```csharp
//載入簡報
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

//取得要插入 ActiveX 控制項的投影片
ISlide slide = presentation.Slides[0];

//定義 ActiveX 控制項的屬性
int left = 100; //指定左側位置
int top = 100; //指定頂部位置
int width = 200; //指定寬度
int height = 100; //指定高度
string progId = "YourActiveXControl.ProgID"; //指定 ActiveX 控制項的 ProgID

//將 ActiveX 控制項新增至投影片
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

確保更換`"YourActiveXControl.ProgID"`與要插入的 ActiveX 控制項的實際 ProgID。

4. 儲存簡報：插入 ActiveX 控制項後，使用下列程式碼儲存簡報：

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## 以程式方式操作 ActiveX 控件

將 ActiveX 控制項新增至投影片後，您可能想要以程式設計方式操作它。您可以這樣做：

1. 存取 ActiveX 控制項：要存取 ActiveX 控制項的屬性和方法，您需要取得對其的參考。使用以下程式碼從投影片取得控制項：

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. 呼叫方法：您可以使用獲得的參考來呼叫 ActiveX 控制項的方法。例如，如果 ActiveX 控制項有一個名為「Play」的方法，您可以這樣呼叫它：

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. 設定屬性：您也可以透過程式設定 ActiveX 控制項的屬性。例如，如果控制項有一個名為「Volume」的屬性，您可以這樣設定：

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## 自訂 ActiveX 控制項屬性

自訂 ActiveX 控制項的屬性可以大幅增強簡報的使用者體驗。以下是自訂這些屬性的方法：

1. 存取屬性：如前所述，您可以使用下列命令存取 ActiveX 控制項的屬性：`IOleObjectFrame`參考。

2. 設定屬性：使用`SetProperty`方法來設定ActiveX控制項的各種屬性。例如，您可以像這樣變更背景顏色：

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## 處理與 ActiveX 控制項關聯的事件

ActiveX 控制項通常具有可以根據使用者互動觸發操作的關聯事件。以下是處理這些事件的方法：

1. 訂閱事件：首先，訂閱ActiveX控制項所需的事件。例如，如果控制項有「Clicked」事件，您可以像這樣訂閱它：

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    //您的事件處理程式碼在這裡
};
```

## 從投影片中刪除 ActiveX 控制項

如果要從投影片中刪除 ActiveX 控件，請依照下列步驟操作：

1. 存取控制項：使用下列指令取得 ActiveX 控制項的引用`IOleObjectFrame`參考如前所示。

2. 刪除控制項：使用下列程式碼從投影片中刪除控制項：

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## 儲存並匯出修改後的簡報

對簡報進行所有必要的更改後，您可以使用以下程式碼儲存並匯出它：

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## 使用 Aspose.Slides for .NET 的好處

Aspose.Slides for .NET 透過提供使用者友善的 API 簡化了在 PowerPoint 簡報中使用 ActiveX 控制項的流程，該 API 可讓您無縫整合和操作這些控制項。使用 Aspose.Slides for .NET 的一些好處包括：

- 將 ActiveX 控制項輕鬆插入到投影片上。
- 以程式設計方式與控制項互動的綜合方法。
- 簡化控制項屬性的自訂。
- 互動式演示的高效事件處理。
- 簡化了從投影片中刪除控制項的過程。

## 結論

將 ActiveX 控制項合併到 PowerPoint 簡報中可以提高觀眾的互動性和參與度。借助 Aspose.Slides for .NET，您擁有了一個強大的工具來無縫管理 ActiveX 控件，使您能夠創建動態且引人入勝的演示文稿，給人留下持久的印象。

## 常見問題解答

### 如何將 ActiveX 控制項新增至特定投影片？

若要將 ActiveX 控制項新增至特定投影片，您可以使用`AddOleObjectFrame`Aspose.Slides for .NET 提供的方法。此方法可讓您指定要插入的 ActiveX 控制項的位置、大小和 ProgID。

### 我可以透過程式操作 ActiveX 控制項嗎？

是的，您可以使用 Aspose.Slides for .NET 以程式設計方式操作 ActiveX 控制項。透過獲取對`IOleObjectFrame`代表控件，您可以呼叫方法並設定屬性以動態地與控件互動。

### 我如何處理事件

 由ActiveX控制項觸發？

您可以透過使用以下命令訂閱對應的事件來處理由 ActiveX 控制項觸發的事件`EventClick`（或類似的）事件處理程序。這允許您執行特定操作來回應使用者與控制項的互動。

### 是否可以自訂 ActiveX 控制項的外觀？

當然，您可以使用以下命令自訂 ActiveX 控制項的外觀`SetProperty`Aspose.Slides for .NET 提供的方法。此方法使您能夠修改各種屬性，例如背景顏色、字體樣式等。

### 我可以從投影片中刪除 ActiveX 控制項嗎？

是的，您可以使用以下命令從幻燈片中刪除 ActiveX 控件`Remove`的方法`Shapes`收藏。將引用傳遞給`IOleObjectFrame`將控制項表示為參數`Remove`方法，並且控制項將從幻燈片中刪除。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
