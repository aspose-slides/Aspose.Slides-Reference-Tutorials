---
"description": "使用 Aspose.Slides for .NET 增強 PowerPoint 簡報。輕鬆控制動畫，吸引觀眾並留下持久的印象。"
"linktitle": "在投影片上重複動畫"
"second_title": "Aspose.Slides .NET PowerPoint 處理 API"
"title": "使用 Aspose.Slides .NET 掌握 PowerPoint 動畫"
"url": "/zh-hant/net/slide-animation-control/repeat-animation-on-slide/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Slides .NET 掌握 PowerPoint 動畫

## 介紹
在動態的演示世界中，控制動畫的能力對於吸引和抓住觀眾的注意力起著關鍵作用。 Aspose.Slides for .NET 使開發人員能夠掌控幻燈片中的動畫類型，從而實現更具互動性和視覺吸引力的簡報。在本教學中，我們將逐步探索如何使用 Aspose.Slides for .NET 控制投影片上的動畫類型。
## 先決條件
在深入學習本教程之前，請確保您已滿足以下先決條件：
1. Aspose.Slides for .NET Library：從以下位置下載並安裝該程式庫 [這裡](https://releases。aspose.com/slides/net/).
2. .NET 開發環境：在您的機器上設定 .NET 開發環境。
## 導入命名空間
在您的 .NET 專案中，首先匯入必要的命名空間以利用 Aspose.Slides 提供的功能：
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## 步驟 1：設定項目
為您的專案建立一個新目錄並實例化 Presentation 類別來表示示範檔案。
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // 您的程式碼在此處
}
```
## 第 2 步：存取效果序列
使用 MainSequence 屬性檢索第一張投影片的效果序列。
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## 步驟 3：訪問第一個效果
獲得主序列的第一個效果來操縱其屬性。
```csharp
IEffect effect = effectsSequence[0];
```
## 步驟4：修改重複設定
將效果的“時間/重複”屬性變更為“直到投影片結束”。
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## 步驟 5：儲存簡報
保存修改後的簡報以直觀地看到變化。
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
重複這些步驟以獲得更多效果或根據您的簡報要求進行自訂。
## 結論
使用 Aspose.Slides for .NET 在 PowerPoint 簡報中加入動態動畫從未如此簡單。本逐步指南將為您提供控制動畫類型的知識，確保您的幻燈片給觀眾留下持久的印象。
## 常見問題
### 我可以將這些動畫套用到投影片中的特定物件嗎？
是的，您可以透過存取序列中的各自效果來定位特定物件。
### Aspose.Slides 與最新的 PowerPoint 版本相容嗎？
Aspose.Slides 支援多種 PowerPoint 版本，確保與新舊版本的相容性。
### 在哪裡可以找到更多範例和資源？
探索 [文件](https://reference.aspose.com/slides/net/) 以獲得全面的例子和詳細的解釋。
### 如何獲得 Aspose.Slides 的臨時許可證？
訪問 [這裡](https://purchase.aspose.com/temporary-license/) 有關取得臨時許可證的資訊。
### 需要幫助或有更多問題嗎？
與 Aspose.Slides 社區互動 [支援論壇](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}