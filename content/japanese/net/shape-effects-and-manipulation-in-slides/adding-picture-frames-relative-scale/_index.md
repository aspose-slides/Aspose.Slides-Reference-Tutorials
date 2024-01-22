---
title: Aspose.Slides .NET を使用したピクチャ フレームの追加チュートリアル
linktitle: Aspose.Slides での相対スケール高さを持つピクチャ フレームの追加
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET で相対的なスケールの高さを指定してピクチャ フレームを追加する方法を学びます。シームレスなプレゼンテーションを行うには、このステップバイステップのガイドに従ってください。
type: docs
weight: 17
url: /ja/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## 導入
Aspose.Slides for .NET は、開発者が .NET アプリケーションで PowerPoint プレゼンテーションを簡単に作成、操作、変換できるようにする強力なライブラリです。このチュートリアルでは、Aspose.Slides for .NET を使用して、相対スケール高さを持つピクチャ フレームを追加するプロセスについて詳しく説明します。このステップバイステップのガイドに従って、プレゼンテーション作成スキルを向上させてください。
## 前提条件
始める前に、以下のものがあることを確認してください。
- C# プログラミング言語の基本的な知識。
- Visual Studio またはその他の推奨される C# 開発環境がインストールされていること。
- Aspose.Slides for .NET ライブラリがプロジェクトに追加されました。
## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートします。この手順により、Aspose.Slides ライブラリによって提供されるクラスと機能にアクセスできるようになります。
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ステップ 1: プロジェクトをセットアップする
まず、好みの開発環境で新しい C# プロジェクトを作成します。 Aspose.Slides for .NET ライブラリを参照して、必ずプロジェクトに追加してください。
## ステップ 2: プレゼンテーションと画像をロードする
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //プレゼンテーション画像コレクションに追加する画像を読み込みます
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    //...
}
```
このステップでは、新しいプレゼンテーション オブジェクトを作成し、プレゼンテーションに追加する画像を読み込みます。
## ステップ 3: スライドにピクチャ フレームを追加する
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
次に、プレゼンテーションの最初のスライドに図枠を追加します。要件に応じて、形状の種類、位置、寸法などのパラメータを調整します。
## ステップ 4: 相対スケールの幅と高さを設定する
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
目的のスケーリング効果を実現するには、ピクチャ フレームの相対的なスケールの高さと幅を設定します。
## ステップ 5: プレゼンテーションを保存する
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
最後に、追加されたピクチャ フレームを含むプレゼンテーションを、指定した出力形式で保存します。
## 結論
おめでとう！ Aspose.Slides for .NET を使用して、相対的なスケールの高さを指定してピクチャ フレームを追加する方法を学習しました。さまざまな画像、位置、スケールを試して、ニーズに合わせた視覚的に魅力的なプレゼンテーションを作成します。
## よくある質問
### Aspose.Slides for .NET を他のプログラミング言語で使用できますか?
Aspose.Slides は主に .NET 言語をサポートしていますが、さまざまなプラットフォームとの互換性について他の Aspose 製品を検討することもできます。
### Aspose.Slides for .NET の詳細なドキュメントはどこで見つけられますか?
を参照してください。[ドキュメンテーション](https://reference.aspose.com/slides/net/)包括的な情報と例については、こちらをご覧ください。
### Aspose.Slides for .NET に利用できる無料トライアルはありますか?
はい、入手できます[無料トライアル](https://releases.aspose.com/)ライブラリの機能を評価します。
### Aspose.Slides for .NET のサポートを受けるにはどうすればよいですか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティや Aspose の専門家に支援を求めてください。
### Aspose.Slides for .NET はどこで購入できますか?
 Aspose.Slides for .NET は、[購入ページ](https://purchase.aspose.com/buy).