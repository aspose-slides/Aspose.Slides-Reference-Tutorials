---
title: Aspose.Slides - .NET で図形をシームレスに接続する
linktitle: プレゼンテーションでコネクタを使用して図形を接続する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: プレゼンテーション内で図形を簡単に接続できる、Aspose.Slides for .NET の機能を試してください。動的コネクタを使用してスライドを強化します。
type: docs
weight: 29
url: /ja/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## 導入
ダイナミックなプレゼンテーションの世界では、コネクタを使用して図形を接続する機能により、スライドに洗練されたレイヤーが追加されます。 Aspose.Slides for .NET は、開発者がこれをシームレスに実現できるようにします。このチュートリアルでは、プロセスをガイドし、明確に理解できるように各ステップを詳しく説明します。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
- C# と .NET Framework の基本的な知識。
-  Aspose.Slides for .NET がインストールされています。そうでない場合は、ダウンロードしてください[ここ](https://releases.aspose.com/slides/net/).
- 開発環境が整いました。
## 名前空間のインポート
C# コードで、必要な名前空間をインポートすることから始めます。
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. ドキュメントディレクトリを設定する
まず、ドキュメントのディレクトリを定義します。
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. プレゼンテーションクラスをインスタンス化する
PPTX ファイルを表す Presentation クラスのインスタンスを作成します。
```csharp
using (Presentation input = new Presentation())
{
    //選択したスライドの図形コレクションへのアクセス
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. スライドに図形を追加する
楕円形や長方形などの必要な図形をスライドに追加します。
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. コネクタ形状の追加
スライドの形状コレクションにコネクタ形状を含めます。
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. コネクタで図形を接続する
コネクタによって接続される形状を指定します。
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. リルートコネクタ
reroute メソッドを呼び出して、シェイプ間の自動最短パスを設定します。
```csharp
connector.Reroute();
```
## 7. プレゼンテーションを保存する
プレゼンテーションを保存して、接続された図形を表示します。
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 結論
おめでとう！ Aspose.Slides for .NET を使用して、プレゼンテーション スライド内のコネクタを使用して図形を接続することに成功しました。この高度な機能を使用してプレゼンテーションを強化し、聴衆を魅了します。
## よくある質問
### Aspose.Slides for .NET は最新の .NET Framework と互換性がありますか?
はい、Aspose.Slides for .NET は、最新の .NET Framework バージョンとの互換性を確保するために定期的に更新されます。
### 1 つのコネクタを使用して 3 つ以上の形状を接続できますか?
コード内のコネクタ ロジックを拡張することで、複数の図形を接続することができます。
### 接続できる形状に制限はありますか?
Aspose.Slides for .NET は、基本的なシェイプ、スマート アート、カスタム シェイプなど、さまざまなシェイプの接続をサポートしています。
### コネクタの外観をカスタマイズするにはどうすればよいですか?
線のスタイルや色など、コネクタの外観をカスタマイズする方法については、Aspose.Slides のドキュメントを参照してください。
### Aspose.Slides サポートのためのコミュニティ フォーラムはありますか?
はい、サポートを見つけたり、経験を共有したりできます。[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).