---
title: プレゼンテーションでカスタムシェイプ ID を使用して SVG を生成する
linktitle: プレゼンテーションでカスタムシェイプ ID を使用して SVG を生成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、カスタム SVG 形状と ID を使用して魅力的なプレゼンテーションを生成します。ソース コードの例を使用して、インタラクティブなスライドを作成する方法を段階的に学習します。プレゼンテーションの視覚的な魅力とユーザー インタラクションを強化します。
type: docs
weight: 19
url: /ja/net/presentation-manipulation/generate-svg-with-custom-shape-ids-in-presentations/
---

Aspose.Slides for .NET の機能を利用して、カスタム形状 ID を持つ SVG ファイルを生成したいと考えていますか?あなたは正しい場所にいます！このステップバイステップのチュートリアルでは、次のソース コード スニペットを使用してプロセスを説明します。最終的には、プレゼンテーション内でカスタム形状 ID を持つ SVG ファイルを作成する準備が整っていることになります。

### はじめる

コードに入る前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for .NET: Aspose.Slides ライブラリがインストールされ、すぐに使用できることを確認してください。

2. サンプル プレゼンテーション: SVG にエクスポートする図形を含むプレゼンテーション ファイル (例: 「presentation.pptx」) が必要です。

3. 出力ディレクトリ: SVG ファイルを保存するディレクトリを定義します (例: 「出力ディレクトリ」)。

それでは、コードを段階的に分解してみましょう。

### ステップ 1: 環境のセットアップ

このステップでは、必要な変数を初期化し、プレゼンテーション ファイルをロードします。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    //コードはここに入力します
}
```

交換する`"Your Document Directory"`プレゼンテーション ファイルへの実際のパスを含めます。

### ステップ 2: 図形を SVG として書き込む

このセクションでは、プレゼンテーションの図形を SVG ファイルとして書き込みます。また、SVG 出力をより詳細に制御するために、カスタム形状書式設定コントローラーも指定します。

```csharp
using (FileStream stream = new FileStream(dataDir + "pptxFileName.svg", FileMode.OpenOrCreate))
{
    SVGOptions svgOptions = new SVGOptions
    {
        ShapeFormattingController = new CustomSvgShapeFormattingController()
    };

    pres.Slides[0].WriteAsSvg(stream, svgOptions);
}
```

必ず交換してください`"pptxFileName.svg"`希望の出力ファイル名を付けます。

### 結論

そして、それができました！ Aspose.Slides for .NET を使用して、カスタム形状 ID を持つ SVG ファイルを正常に生成しました。この強力な機能により、特定のニーズに合わせて SVG 出力をカスタマイズできます。

### よくある質問

1. ### Aspose.Slides for .NET とは何ですか?
   Aspose.Slides for .NET は、.NET アプリケーションで PowerPoint プレゼンテーションを操作するための堅牢なライブラリです。プレゼンテーションをプログラムで作成、編集、操作するためのさまざまな機能を提供します。

2. ### SVG 生成においてカスタム シェイプの書式設定が重要なのはなぜですか?
   カスタム形状の書式設定を使用すると、SVG 出力内の形状の外観と属性をきめ細かく制御できます。

3. ### Aspose.Slides for .NET を他のプログラミング言語で使用できますか?
   Aspose.Slides for .NET は、.NET アプリケーション向けに特別に設計されています。ただし、Aspose は他のプラットフォームや言語用のライブラリも提供します。

4. ### Aspose.Slides for .NET での SVG 生成に制限はありますか?
   Aspose.Slides for .NET は強力な SVG 生成機能を提供しますが、その可能性を最大限に活用するには、ライブラリのドキュメントを理解することが不可欠です。

5. ### Aspose.Slides for .NET のその他のリソースとサポートはどこで入手できますか?
   追加のドキュメントについては、次のサイトを参照してください。[Aspose.Slides for .NET API リファレンス](https://reference.aspose.com/slides/net/).

さあ、Aspose.Slides for .NET を使用して SVG 生成の無限の可能性を探ってみましょう。コーディングを楽しんでください!
