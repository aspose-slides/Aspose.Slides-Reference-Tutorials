---
title: PowerPoint の ActiveX コントロールを介してビデオをリンクする
linktitle: ActiveX コントロール経由でビデオをリンクする
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してビデオを PowerPoint スライドにリンクする方法を学びます。このステップバイステップ ガイドには、リンクされたビデオを使用してインタラクティブで魅力的なプレゼンテーションを作成するためのソース コードとヒントが含まれています。
type: docs
weight: 12
url: /ja/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---
Aspose.Slides for .NET を使用したプレゼンテーション内の ActiveX コントロールを介したビデオのリンク

Aspose.Slides for .NET では、ActiveX コントロールを使用してプログラムでビデオをプレゼンテーション スライドにリンクできます。これにより、ビデオ コンテンツをスライド内で直接再生できるインタラクティブなプレゼンテーションを作成できます。このステップバイステップ ガイドでは、Aspose.Slides for .NET を使用してビデオをプレゼンテーション スライドにリンクするプロセスを説明します。

## 前提条件:
- Visual Studio (またはその他の .NET 開発環境)
-  .NET ライブラリの Aspose.Slides。からダウンロードできます[ここ](https://releases.aspose.com/slides/net/).

## ステップ 1: 新しいプロジェクトを作成する
好みの .NET 開発環境 (Visual Studio など) で新しいプロジェクトを作成し、Aspose.Slides for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
プロジェクトに、Aspose.Slides を操作するために必要な名前空間をインポートします。

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## ステップ 3: プレゼンテーションをロードする
リンクされたビデオを追加する PowerPoint プレゼンテーションを読み込みます。

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    //リンクされたビデオを追加するコードはここにあります
}
```

## ステップ 4: ActiveX コントロールを追加する
のインスタンスを作成します。`IOleObjectFrame`ActiveX コントロールをスライドに追加するインターフェイス:

```csharp
ISlide slide = presentation.Slides[0]; //ビデオを追加するスライドを選択します
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

上記のコードでは、640x480 のサイズの ActiveX コントロール フレームをスライドに追加しています。ビデオの埋め込みによく使用される ShockwaveFlash ActiveX コントロールの ProgID を指定しています。

## ステップ 5: ActiveX コントロールのプロパティを設定する
ActiveX コントロールのプロパティを設定して、リンクされたビデオ ソースを指定します。

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); //実際のビデオ ファイル パスに置き換えます
oleObjectFrame.AlternativeText = "Linked Video";
```

交換する`"YourVideoPathHere"`ビデオファイルへの実際のパスを含めます。の`AlternativeText`プロパティは、リンクされたビデオの説明を提供します。

## ステップ 6: プレゼンテーションを保存する
変更したプレゼンテーションを保存します。

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## よくある質問:

### スライド上のリンクされたビデオのサイズと位置を指定するにはどうすればよいですか?
 ActiveX コントロール フレームの寸法と位置は、`AddOleObjectFrame`方法。 4 つの数値引数は、それぞれ左上隅の X 座標と Y 座標、フレームの幅と高さを表します。

### このアプローチを使用して、異なる形式のビデオをリンクできますか?
はい、その形式に適切な ActiveX コントロールが利用できる限り、さまざまな形式のビデオをリンクできます。たとえば、このガイドで使用されている ShockwaveFlash ActiveX コントロールは、Flash ビデオ (SWF) に適しています。他の形式の場合は、異なる ProgID を使用する必要がある場合があります。

### リンクされたビデオのサイズに制限はありますか?
リンクされたビデオのサイズは、プレゼンテーションの全体的なサイズとパフォーマンスに影響を与える可能性があります。ビデオをプレゼンテーションにリンクする前に、Web 再生用にビデオを最適化することをお勧めします。

### 結論：
このガイドで説明されている手順に従うことで、Aspose.Slides for .NET を使用してプレゼンテーション内の ActiveX コントロール経由でビデオを簡単にリンクできます。この機能を使用すると、マルチメディア コンテンツをシームレスに組み込んだ魅力的でインタラクティブなプレゼンテーションを作成できます。

詳細と高度なオプションについては、以下を参照してください。[Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/).