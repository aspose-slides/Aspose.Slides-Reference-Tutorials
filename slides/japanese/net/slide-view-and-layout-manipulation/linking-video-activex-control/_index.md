---
title: PowerPoint の ActiveX コントロール経由でビデオをリンクする
linktitle: ActiveX コントロール経由でビデオをリンクする
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してビデオを PowerPoint スライドにリンクする方法を学びます。このステップ バイ ステップ ガイドには、リンクされたビデオを使用してインタラクティブで魅力的なプレゼンテーションを作成するためのソース コードとヒントが含まれています。
weight: 12
url: /ja/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

Aspose.Slides for .NET を使用してプレゼンテーションで ActiveX コントロール経由でビデオをリンクする

Aspose.Slides for .NET では、ActiveX コントロールを使用して、プログラムによってビデオをプレゼンテーション スライドにリンクできます。これにより、ビデオ コンテンツをスライド内で直接再生できるインタラクティブなプレゼンテーションを作成できます。このステップ バイ ステップ ガイドでは、Aspose.Slides for .NET を使用してビデオをプレゼンテーション スライドにリンクするプロセスについて説明します。

## 前提条件:
- Visual Studio (またはその他の .NET 開発環境)
-  Aspose.Slides for .NETライブラリ。ここからダウンロードできます。[ここ](https://releases.aspose.com/slides/net/).

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
    //リンクされたビデオを追加するためのコードはここに記入します
}
```

## ステップ4: ActiveXコントロールを追加する
インスタンスを作成する`IOleObjectFrame`スライドに ActiveX コントロールを追加するためのインターフェイス:

```csharp
ISlide slide = presentation.Slides[0]; //ビデオを追加するスライドを選択します
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

上記のコードでは、スライドに 640x480 サイズの ActiveX コントロール フレームを追加しています。ビデオの埋め込みによく使用される ShockwaveFlash ActiveX コントロールの ProgID を指定しています。

## ステップ5: ActiveXコントロールのプロパティを設定する
リンクされたビデオ ソースを指定するには、ActiveX コントロールのプロパティを設定します。

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); //実際のビデオファイルパスに置き換えます
oleObjectFrame.AlternativeText = "Linked Video";
```

交換する`"YourVideoPathHere"`ビデオファイルの実際のパスを入力します。`AlternativeText`プロパティは、リンクされたビデオの説明を提供します。

## ステップ6: プレゼンテーションを保存する
変更したプレゼンテーションを保存します。

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## よくある質問:

### スライド上のリンクされたビデオのサイズと位置を指定するにはどうすればよいですか?
ActiveXコントロールフレームの寸法と位置は、`AddOleObjectFrame`メソッド。4 つの数値引数は、それぞれ左上隅の X 座標と Y 座標、およびフレームの幅と高さを表します。

### この方法を使用して、異なる形式のビデオをリンクできますか?
はい、適切な ActiveX コントロールがその形式に使用できる限り、さまざまな形式のビデオをリンクできます。たとえば、このガイドで使用されている ShockwaveFlash ActiveX コントロールは、Flash ビデオ (SWF) に適しています。他の形式の場合は、異なる ProgID を使用する必要がある場合があります。

### リンクされたビデオのサイズに制限はありますか?
リンクされたビデオのサイズは、プレゼンテーションの全体的なサイズとパフォーマンスに影響する可能性があります。プレゼンテーションにリンクする前に、ビデオを Web 再生用に最適化することをお勧めします。

### 結論：
このガイドで説明されている手順に従うと、Aspose.Slides for .NET を使用して、プレゼンテーションで ActiveX コントロールを介してビデオを簡単にリンクできます。この機能を使用すると、マルチメディア コンテンツをシームレスに組み込んだ魅力的でインタラクティブなプレゼンテーションを作成できます。

詳細と高度なオプションについては、[Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
