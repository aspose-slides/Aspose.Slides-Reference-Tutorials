---
title: Aspose.Slides で SmartArt 子ノートのサムネイルを作成する
linktitle: Aspose.Slides で SmartArt 子ノートのサムネイルを作成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して魅力的な SmartArt 子ノート サムネイルを作成する方法を学びます。ダイナミックなビジュアルでプレゼンテーションのレベルを高めましょう。
weight: 15
url: /ja/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 導入
動的プレゼンテーションの分野では、Aspose.Slides for .NET は強力なツールとして際立っており、開発者に PowerPoint プレゼンテーションをプログラムで操作および強化する機能を提供します。興味深い機能の 1 つは、SmartArt 子ノートのサムネイルを生成して、プレゼンテーションに視覚的な魅力を加える機能です。このステップ バイ ステップ ガイドでは、Aspose.Slides for .NET を使用して SmartArt 子ノートのサムネイルを作成する手順を説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slidesライブラリが.NETプロジェクトに統合されていることを確認してください。統合されていない場合は、[リリースページ](https://releases.aspose.com/slides/net/).
- 開発環境: 実用的な .NET 開発環境をセットアップし、C# プログラミングの基本を理解している必要があります。
- サンプル プレゼンテーション: テスト用に、Child Notes を含む SmartArt を含む PowerPoint プレゼンテーションを作成または入手します。
## 名前空間のインポート
まず、必要な名前空間を C# プロジェクトにインポートします。これらの名前空間は、Aspose.Slides の操作に必要なクラスとメソッドへのアクセスを提供します。
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## ステップ1: プレゼンテーションクラスのインスタンスを作成する
まずインスタンス化して`Presentation`作業する PPTX ファイルを表すクラスです。
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## ステップ2: SmartArtを追加する
次に、プレゼンテーション内のスライドにSmartArtを追加します。この例では、`BasicCycle`レイアウト。
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## ステップ3: ノード参照を取得する
SmartArt 内の特定のノードを操作するには、そのインデックスを使用してその参照を取得します。
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## ステップ4: サムネイルを取得する
SmartArt ノード内の子ノートのサムネイル画像を取得します。
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## ステップ5: サムネイルを保存する
生成されたサムネイル画像を指定されたディレクトリに保存します。
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
プレゼンテーション内の各 SmartArt ノードに対してこれらの手順を繰り返し、必要に応じてレイアウトとスタイルをカスタマイズします。
## 結論
結論として、Aspose.Slides for .NET を使用すると、開発者は魅力的なプレゼンテーションを簡単に作成できます。SmartArt 子ノートのサムネイルを生成する機能により、プレゼンテーションの視覚的な魅力が向上し、動的でインタラクティブなユーザー エクスペリエンスが実現します。
## よくある質問
### Q: 生成されたサムネイルのサイズと形式をカスタマイズできますか?
A: はい、コード内の対応するパラメータを変更することで、サムネイルのサイズと形式を調整できます。
### Q: Aspose.Slides は他の SmartArt レイアウトをサポートしていますか?
A: もちろんです! Aspose.Slides ではさまざまな SmartArt レイアウトが提供されており、プレゼンテーションのニーズに最適なものを選択できます。
### Q: テスト目的で一時ライセンスを利用できますか?
 A: はい、一時ライセンスは以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/)テストと評価のため。
### Q: Aspose.Slides コミュニティでサポートを受けたり、コミュニティとつながったりするには、どこですればよいですか?
 A: をご覧ください[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティと関わり、質問し、解決策を見つけます。
### Q: Aspose.Slides for .NET を購入できますか?
 A: もちろんです！購入オプションをご覧ください[ここ](https://purchase.aspose.com/buy)プロジェクトで Aspose.Slides の可能性を最大限に引き出します。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
