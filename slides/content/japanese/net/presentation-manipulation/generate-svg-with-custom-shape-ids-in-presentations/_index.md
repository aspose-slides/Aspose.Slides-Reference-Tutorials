---
title: プレゼンテーションでカスタム シェイプ ID を使用して SVG を生成する
linktitle: プレゼンテーションでカスタム シェイプ ID を使用して SVG を生成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、カスタム SVG シェイプと ID で魅力的なプレゼンテーションを生成します。ソース コードの例を使用して、インタラクティブなスライドを段階的に作成する方法を学びます。プレゼンテーションの視覚的な魅力とユーザー インタラクションを強化します。
type: docs
weight: 19
url: /ja/net/presentation-manipulation/generate-svg-with-custom-shape-ids-in-presentations/
---

Aspose.Slides for .NET のパワーを活用して、カスタム シェイプ ID を持つ SVG ファイルを生成したいとお考えですか? まさにうってつけです! このステップ バイ ステップのチュートリアルでは、次のソース コード スニペットを使用してプロセスをガイドします。最後には、プレゼンテーションでカスタム シェイプ ID を持つ SVG ファイルを作成する準備が整います。

### はじめる

コードに進む前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for .NET: Aspose.Slides ライブラリがインストールされ、準備ができていることを確認してください。

2. サンプル プレゼンテーション: SVG にエクスポートする図形を含むプレゼンテーション ファイル (例: 「presentation.pptx」) が必要になります。

3. 出力ディレクトリ: SVG ファイルを保存するディレクトリを定義します (例: 「出力ディレクトリ」)。

それでは、コードを段階的に分解してみましょう。

### ステップ1: 環境の設定

このステップでは、必要な変数を初期化し、プレゼンテーション ファイルを読み込みます。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    //ここにコードを入力してください
}
```

交換する`"Your Document Directory"`プレゼンテーション ファイルへの実際のパスを入力します。

### ステップ 2: 図形を SVG として書き込む

このセクションでは、プレゼンテーションの図形を SVG ファイルとして書き込みます。また、SVG 出力をより細かく制御するために、カスタム図形書式設定コントローラーを指定します。

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

必ず交換してください`"pptxFileName.svg"`希望する出力ファイル名を入力します。

### 結論

これで完了です。Aspose.Slides for .NET を使用して、カスタム シェイプ ID を持つ SVG ファイルを正常に生成できました。この強力な機能により、特定のニーズに合わせて SVG 出力をカスタマイズできます。

### よくある質問

1. ### Aspose.Slides for .NET とは何ですか?
   Aspose.Slides for .NET は、.NET アプリケーションで PowerPoint プレゼンテーションを操作するための強力なライブラリです。プログラムでプレゼンテーションを作成、編集、操作するためのさまざまな機能を提供します。

2. ### SVG 生成においてカスタム シェイプのフォーマットが重要なのはなぜですか?
   カスタム シェイプのフォーマットを使用すると、SVG 出力内のシェイプの外観と属性を細かく制御できます。

3. ### Aspose.Slides for .NET を他のプログラミング言語で使用できますか?
   Aspose.Slides for .NET は、特に .NET アプリケーション向けに設計されています。ただし、Aspose は他のプラットフォームや言語用のライブラリも提供しています。

4. ### Aspose.Slides for .NET での SVG 生成には制限がありますか?
   Aspose.Slides for .NET は強力な SVG 生成機能を提供しますが、その可能性を最大限に引き出すにはライブラリのドキュメントを理解することが重要です。

5. ### Aspose.Slides for .NET のその他のリソースやサポートはどこで見つかりますか?
   追加のドキュメントについては、[Aspose.Slides for .NET API リファレンス](https://reference.aspose.com/slides/net/).

さあ、Aspose.Slides for .NET で SVG 生成の無限の可能性を探求してみましょう。楽しいコーディングを！
