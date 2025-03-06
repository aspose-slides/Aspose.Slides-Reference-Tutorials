---
title: 使用 Aspose.Slides 從 PowerPoint 超連結中提取音頻
linktitle: 從超連結中提取音頻
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 使用 Aspose.Slides for .NET 從 PowerPoint 簡報中的超連結中提取音訊。輕鬆增強您的多媒體項目。
weight: 12
url: /zh-hant/net/audio-and-video-extraction/extract-audio-from-hyperlink/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


在多媒體簡報領域，音訊在增強幻燈片的整體影響力方面發揮著至關重要的作用。您是否曾經遇到過帶有音訊超連結的 PowerPoint 演示文稿，並想知道如何提取音訊以供其他用途？透過 Aspose.Slides for .NET，您可以輕鬆完成此任務。在本逐步指南中，我們將引導您完成從 PowerPoint 簡報中的超連結中提取音訊的過程。

## 先決條件

在我們深入了解提取過程之前，請確保您具備以下先決條件：

### 1. .NET 函式庫的 Aspose.Slides

您需要在開發環境中安裝 Aspose.Slides for .NET 程式庫。如果還沒有，您可以從以下網站下載：[Aspose.Slides for .NET 文檔](https://reference.aspose.com/slides/net/).

### 2. 帶有音訊超連結的 PowerPoint 簡報

確保您有一個 PowerPoint 簡報 (PPTX)，其中包含具有關聯音訊的超連結。這將是您從中提取音訊的來源。

## 導入命名空間

首先，讓我們在 C# 專案中匯入必要的命名空間，以便有效地使用 Aspose.Slides for .NET。這些命名空間對於處理 PowerPoint 簡報和從超連結中提取音訊至關重要。

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

現在我們已經具備了先決條件並導入了所需的命名空間，讓我們將提取過程分解為多個步驟。

## 第 1 步：定義文檔目錄

首先指定 PowerPoint 簡報所在的目錄。您可以更換`"Your Document Directory"`與文檔目錄的實際路徑。

```csharp
string dataDir = "Your Document Directory";
```

## 第 2 步：載入 PowerPoint 簡報

使用 Aspose.Slides 載入包含音訊超連結的 PowerPoint 簡報 (PPTX)。代替`"HyperlinkSound.pptx"`與簡報的實際檔案名稱。

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    //繼續下一步。
}
```

## 第三步：取得超連結聲音

從 PowerPoint 投影片中取得第一個形狀的超連結。如果超連結有關聯的聲音，我們將繼續提取它。

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    //繼續下一步。
}
```

## 第四步：從超連結中提取音頻

如果超連結有關聯的聲音，我們可以將其提取為位元組數組並將其儲存為媒體檔案。

```csharp
//提取位元組數組中的超連結聲音
byte[] audioData = link.Sound.BinaryData;

//指定要儲存提取的音訊的路徑
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

//將提取的音訊儲存到媒體文件
File.WriteAllBytes(outMediaPath, audioData);
```

恭喜！您已使用 Aspose.Slides for .NET 成功從 PowerPoint 簡報中的超連結提取音訊。現在，提取的音訊可用於多媒體專案中的其他目的。

## 結論

Aspose.Slides for .NET 提供了一個強大且使用者友好的解決方案，可從 PowerPoint 簡報中的超連結中提取音訊。透過本指南中概述的步驟，您可以透過重複使用簡報中的音訊內容來輕鬆增強您的多媒體專案。

### 常見問題 (FAQ)

### Aspose.Slides for .NET 是免費的函式庫嗎？
不，Aspose.Slides for .NET 是一個商業庫，但您可以透過下載免費試用版來探索其功能和文檔[這裡](https://releases.aspose.com/).

### 我可以從 PPT 等舊版 PowerPoint 格式的超連結中提取音訊嗎？
是的，Aspose.Slides for .NET 支援 PPTX 和 PPT 格式以從超連結中提取音訊。

### 是否有支援 Aspose.Slides 的社群論壇？
是的，您可以獲得協助並分享您使用 Aspose.Slides 的經驗[Aspose.Slides 社群論壇](https://forum.aspose.com/).

### 我可以為短期專案購買 Aspose.Slides 的臨時授權嗎？
是的，您可以透過存取取得 Aspose.Slides for .NET 的臨時授權來滿足您的短期專案需求[這個連結](https://purchase.aspose.com/temporary-license/).

### 除了 MPG 之外，是否還支援提取其他音訊格式？
Aspose.Slides for .NET 可讓您提取各種格式的音頻，不僅限於 MPG。提取後您可以將其轉換為您喜歡的格式。

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
