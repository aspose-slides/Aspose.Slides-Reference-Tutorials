---
"description": "Aspose.Slides for .NET を使用して、ビデオをPowerPointスライドにリンクする方法を学びましょう。このステップバイステップガイドには、リンクされたビデオを使ったインタラクティブで魅力的なプレゼンテーションを作成するためのソースコードとヒントが含まれています。"
"linktitle": "ActiveXコントロール経由でビデオをリンクする"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "PowerPoint の ActiveX コントロール経由でビデオをリンクする"
"url": "/ja/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint の ActiveX コントロール経由でビデオをリンクする

Aspose.Slides for .NET を使用してプレゼンテーション内の ActiveX コントロール経由でビデオをリンクする

Aspose.Slides for .NETでは、ActiveXコントロールを使用して、プログラム的にビデオをプレゼンテーションスライドにリンクできます。これにより、スライド内でビデオコンテンツを直接再生できるインタラクティブなプレゼンテーションを作成できます。このステップバイステップガイドでは、Aspose.Slides for .NETを使用してビデオをプレゼンテーションスライドにリンクする手順を詳しく説明します。

## 前提条件:
- Visual Studio (またはその他の .NET 開発環境)
- Aspose.Slides for .NETライブラリ。こちらからダウンロードできます。 [ここ](https://releases。aspose.com/slides/net/).

## ステップ1: 新しいプロジェクトを作成する
好みの .NET 開発環境 (Visual Studio など) で新しいプロジェクトを作成し、Aspose.Slides for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
プロジェクトで、Aspose.Slides を操作するために必要な名前空間をインポートします。

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## ステップ3: プレゼンテーションを読み込む
リンクされたビデオを追加する PowerPoint プレゼンテーションを読み込みます。

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // リンクされたビデオを追加するためのコードをここに入力します
}
```

## ステップ4: ActiveXコントロールを追加する
インスタンスを作成する `IOleObjectFrame` スライドに ActiveX コントロールを追加するためのインターフェイス:

```csharp
ISlide slide = presentation.Slides[0]; // ビデオを追加したいスライドを選択します
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

上記のコードでは、スライドに640x480サイズのActiveXコントロールフレームを追加しています。動画の埋め込みによく使用されるShockwaveFlash ActiveXコントロールのProgIDを指定しています。

## ステップ5: ActiveXコントロールのプロパティを設定する
リンクされたビデオ ソースを指定するには、ActiveX コントロールのプロパティを設定します。

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // 実際のビデオファイルパスに置き換えます
oleObjectFrame.AlternativeText = "Linked Video";
```

交換する `"YourVideoPathHere"` 動画ファイルの実際のパスを入力します。 `AlternativeText` プロパティは、リンクされたビデオの説明を提供します。

## ステップ6: プレゼンテーションを保存する
変更したプレゼンテーションを保存します。

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## よくある質問:

### スライド上のリンクされたビデオのサイズと位置を指定するにはどうすればよいですか?
ActiveXコントロールフレームのサイズと位置は、 `AddOleObjectFrame` メソッド。4つの数値引数は、それぞれ左上隅のX座標とY座標、およびフレームの幅と高さを表します。

### この方法を使用して、異なる形式のビデオをリンクできますか?
はい、適切なActiveXコントロールが利用可能であれば、様々な形式のビデオをリンクできます。例えば、このガイドで使用されているShockwaveFlash ActiveXコントロールは、Flashビデオ（SWF）に適しています。他の形式の場合は、異なるProgIDを使用する必要がある場合があります。

### リンクされたビデオのサイズに制限はありますか?
リンクされたビデオのサイズは、プレゼンテーション全体のサイズとパフォーマンスに影響を与える可能性があります。プレゼンテーションにリンクする前に、ビデオをWeb再生用に最適化することをお勧めします。

### 結論：
このガイドで概説されている手順に従うことで、Aspose.Slides for .NET を使用して、プレゼンテーション内の ActiveX コントロールを介してビデオを簡単にリンクできます。この機能により、マルチメディアコンテンツをシームレスに組み込んだ、魅力的でインタラクティブなプレゼンテーションを作成できます。

詳細と高度なオプションについては、 [Aspose.Slides for .NET ドキュメント](https://reference。aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}