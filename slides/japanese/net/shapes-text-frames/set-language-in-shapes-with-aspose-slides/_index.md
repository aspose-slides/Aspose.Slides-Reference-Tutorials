---
"date": "2025-04-16"
"description": "Aspose.Slides for .NET を使用して、図形内のテキストの言語属性を設定する方法を学びます。このガイドでは、オートシェイプの追加、言語IDの設定、プレゼンテーションの保存について説明します。"
"title": "Aspose.Slides for .NET を使用して PowerPoint 図形の言語を設定する方法"
"url": "/ja/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET を使用して PowerPoint 図形の言語を設定する方法

デジタルプレゼンテーションの世界では、コンテンツのアクセシビリティと適切なフォーマットを複数の言語間で確保することが困難な場合があります。Aspose.Slides for .NET を使えば、PowerPoint スライド内の図形内のテキストに言語属性を簡単に設定できます。この機能は、多言語ドキュメントの作成やグローバルなコミュニケーションにおける一貫性の確保に特に役立ちます。

**学習内容:**
- 自動シェイプを追加し、そこにテキストを挿入します。
- Aspose.Slides を使用してテキスト部分の言語 ID を設定します。
- カスタム構成でプレゼンテーションを保存します。

この機能をシームレスに実装する方法について詳しく見ていきましょう。

## 前提条件

始める前に、以下のものを用意してください。

- **ライブラリと依存関係**Aspose.Slides for .NET がインストールされている必要があります。このライブラリは、C# で PowerPoint プレゼンテーションを操作するために不可欠です。
  
- **環境設定**.NET Core または .NET Framework を備えた開発環境が必要です。

- **知識の前提条件**基本的な C# プログラミング概念に精通し、オブジェクト指向プログラミングの原則を理解していると役立ちます。

## Aspose.Slides for .NET のセットアップ

始めるには、Aspose.Slidesライブラリをインストールする必要があります。以下のいずれかの方法でインストールできます。

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**パッケージマネージャー**
```powershell
Install-Package Aspose.Slides
```

**NuGet パッケージ マネージャー UI**
「Aspose.Slides」を検索し、最新バージョンをインストールします。

### ライセンス取得

一時ライセンスをダウンロードして無料トライアルを開始できます。 [ここ](https://purchase.aspose.com/temporary-license/)継続してご利用いただくには、以下のライセンスの購入をご検討ください。 [このリンク](https://purchase。aspose.com/buy).

セットアップの準備ができたら、プロジェクトで Aspose.Slides を初期化します。

```csharp
using Aspose.Slides;
```

## 実装ガイド

準備が完了したら、図形テキストの言語を設定する機能を実装しましょう。

### 機能の概要: 図形テキスト言語の設定

この機能を使用すると、PowerPoint 図形内のテキストの言語を指定できます。言語 ID を設定することで、スペルチェックなどの言語固有の機能が正しく適用されるようになります。

#### ステップ1: プレゼンテーションの初期化

まず、 `Presentation` クラス。

```csharp
using (Presentation pres = new Presentation())
{
    // ここにあなたのコード
}
```

これにより、操作する新しい PowerPoint プレゼンテーション オブジェクトが初期化されます。

#### ステップ2: 自動シェイプとテキストフレームを追加する

スライドに長方形の図形を追加し、その中にテキストを挿入します。

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

ここ、 `AddAutoShape` 最初のスライドに四角形を追加します。パラメータで位置とサイズを定義します。

#### ステップ3: 言語IDを設定する

図形内のテキスト部分の言語を設定します。

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

これにより、スペルチェックの言語として英語 (英国) が割り当てられます。

#### ステップ4: プレゼンテーションを保存する

最後に、プレゼンテーションを指定したパスに保存します。

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}