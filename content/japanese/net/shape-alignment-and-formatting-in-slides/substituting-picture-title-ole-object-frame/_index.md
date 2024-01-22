---
title: Aspose.Slides for .NET を使用した OLE オブジェクトの埋め込みガイド
linktitle: プレゼンテーションスライドの OLE オブジェクトフレームの画像タイトルの置換
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、動的 OLE オブジェクトでプレゼンテーション スライドを強化する方法を学びます。シームレスな統合については、ステップバイステップのガイドに従ってください。
type: docs
weight: 15
url: /ja/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## 導入
ダイナミックで魅力的なプレゼンテーション スライドを作成するには、多くの場合、さまざまなマルチメディア要素を組み込む必要があります。このチュートリアルでは、強力な Aspose.Slides for .NET ライブラリを使用して、プレゼンテーション スライド内の OLE (オブジェクトのリンクと埋め込み) オブジェクト フレームの画像タイトルを置き換える方法を説明します。 Aspose.Slides は、OLE オブジェクトの処理プロセスを簡素化し、プレゼンテーションを簡単に強化するためのツールを開発者に提供します。
## 前提条件
ステップバイステップのガイドに進む前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET ライブラリ: Aspose.Slides for .NET ライブラリがインストールされていることを確認します。からダウンロードできます。[Aspose.Slides .NET ドキュメント](https://reference.aspose.com/slides/net/).
- サンプル データ: プレゼンテーションに OLE オブジェクトとして埋め込むサンプル Excel ファイル (「ExcelObject.xlsx」など) を準備します。さらに、OLE オブジェクトのアイコンとして機能する画像ファイル (「Image.png」など) を用意します。
- 開発環境: Visual Studio や .NET 開発用のその他の推奨 IDE など、必要なツールを備えた開発環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトで、Aspose.Slides を操作するために必要な名前空間をインポートしてください。
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## ステップ 1: ドキュメント ディレクトリを設定する
```csharp
string dataDir = "Your Document Directory";
```
「Your Document Directory」をドキュメント ディレクトリへの実際のパスに置き換えてください。
## ステップ 2: OLE ソース ファイルとアイコン ファイルのパスを定義する
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
これらのパスを、サンプル Excel ファイルおよび画像ファイルへの実際のパスで更新します。
## ステップ 3: プレゼンテーション インスタンスを作成する
```csharp
using (Presentation pres = new Presentation())
{
    //後続のステップのコードはここに配置されます
}
```
の新しいインスタンスを初期化します。`Presentation`クラス。
## ステップ 4: OLE オブジェクト フレームを追加する
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
OLE オブジェクト フレームをスライドに追加し、その位置と寸法を指定します。
## ステップ 5: 画像オブジェクトを追加する
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
画像ファイルを読み取り、画像オブジェクトとしてプレゼンテーションに追加します。
## ステップ 6: キャプションを OLE アイコンに設定する
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
OLE アイコンに必要なキャプションを設定します。
## 結論
Aspose.Slides for .NET を使用して OLE オブジェクトをプレゼンテーション スライドに組み込むのは簡単なプロセスです。このチュートリアルでは、ドキュメント ディレクトリの設定から OLE オブジェクトの追加とカスタマイズまで、重要な手順を説明しました。プレゼンテーションの視覚的な魅力を高めるために、さまざまなファイル タイプとキャプションを試してください。
## よくある質問
### Aspose.Slides を使用して、他の種類のファイルを OLE オブジェクトとして埋め込むことはできますか?
はい、Aspose.Slides は、Excel スプレッドシート、Word ドキュメントなど、さまざまな種類のファイルの埋め込みをサポートしています。
### OLE オブジェクトのアイコンはカスタマイズ可能ですか?
絶対に。プレゼンテーションのテーマに合わせて、デフォルトのアイコンを任意の画像に置き換えることができます。
### Aspose.Slides は OLE オブジェクトを使用したアニメーションをサポートしていますか?
最新バージョンの Aspose.Slides は、OLE オブジェクトの埋め込みと表示に焦点を当てており、OLE オブジェクト内のアニメーションを直接処理しません。
### OLE オブジェクトをスライドに追加した後、プログラムで操作できますか?
確かに。 OLE オブジェクトをプログラムで完全に制御できるため、必要に応じてオブジェクトのプロパティや外観を変更できます。
### 埋め込まれた OLE オブジェクトのサイズに制限はありますか?
サイズ制限はありますが、通常は十分なサイズです。最適なパフォーマンスを確保するために、特定のユースケースでテストすることをお勧めします。