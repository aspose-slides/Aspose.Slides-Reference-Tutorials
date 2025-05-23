---
"description": "Aspose.Slides for .NET を使って、カスタム SVG シェイプと ID を使った魅力的なプレゼンテーションを作成できます。インタラクティブなスライドの作成方法を、ソースコード例を使ってステップバイステップで学習できます。プレゼンテーションの視覚的な魅力とユーザーインタラクションを強化しましょう。"
"linktitle": "プレゼンテーションでカスタムシェイプIDを使用してSVGを生成する"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "プレゼンテーションでカスタムシェイプIDを使用してSVGを生成する"
"url": "/ja/net/presentation-manipulation/generate-svg-with-custom-shape-ids-in-presentations/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# プレゼンテーションでカスタムシェイプIDを使用してSVGを生成する


Aspose.Slides for .NET のパワーを活用して、カスタムシェイプ ID 付きの SVG ファイルを生成してみませんか？まさにうってつけです！このステップバイステップのチュートリアルでは、以下のソースコードスニペットを使って手順を解説します。最後まで読めば、プレゼンテーションでカスタムシェイプ ID 付きの SVG ファイルを作成できるようになります。

### はじめる

コードに進む前に、次の前提条件が満たされていることを確認してください。

1. Aspose.Slides for .NET: Aspose.Slides ライブラリがインストールされ、準備ができていることを確認してください。

2. サンプル プレゼンテーション: SVG にエクスポートする図形を含むプレゼンテーション ファイル (例: 「presentation.pptx」) が必要です。

3. 出力ディレクトリ: SVG ファイルを保存するディレクトリを定義します (例: 「出力ディレクトリ」)。

それでは、コードを段階的に分解してみましょう。

### ステップ1: 環境の設定

このステップでは、必要な変数を初期化し、プレゼンテーション ファイルを読み込みます。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // ここにコードを入力してください
}
```

交換する `"Your Document Directory"` プレゼンテーション ファイルへの実際のパスを入力します。

### ステップ2: 図形をSVGとして書き込む

このセクションでは、プレゼンテーションの図形をSVGファイルとして出力します。また、SVG出力をより細かく制御するために、カスタム図形フォーマットコントローラーも指定します。

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

必ず交換してください `"pptxFileName.svg"` 希望する出力ファイル名を入力します。

### 結論

これで完了です！Aspose.Slides for .NET を使って、カスタムシェイプID付きのSVGファイルを生成できました。この強力な機能を使えば、SVG出力をニーズに合わせてカスタマイズできます。

### よくある質問

1. ### Aspose.Slides for .NET とは何ですか?
   Aspose.Slides for .NETは、.NETアプリケーションでPowerPointプレゼンテーションを操作するための堅牢なライブラリです。プログラムによるプレゼンテーションの作成、編集、操作のための様々な機能を提供します。

2. ### SVG 生成においてカスタム シェイプのフォーマットが重要なのはなぜですか?
   カスタム シェイプのフォーマットを使用すると、SVG 出力内のシェイプの外観と属性を細かく制御できます。

3. ### Aspose.Slides for .NET を他のプログラミング言語で使用できますか?
   Aspose.Slides for .NETは.NETアプリケーション向けに特別に設計されています。ただし、Asposeは他のプラットフォームや言語向けのライブラリも提供しています。

4. ### Aspose.Slides for .NET での SVG 生成には制限がありますか?
   Aspose.Slides for .NET は強力な SVG 生成機能を提供しますが、その可能性を最大限に引き出すにはライブラリのドキュメントを理解することが重要です。

5. ### Aspose.Slides for .NET に関するその他のリソースやサポートはどこで入手できますか?
   追加のドキュメントについては、 [Aspose.Slides for .NET API リファレンス](https://reference。aspose.com/slides/net/).

さあ、Aspose.Slides for .NET で SVG 生成の無限の可能性を探求してみましょう。楽しいコーディングを！


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}