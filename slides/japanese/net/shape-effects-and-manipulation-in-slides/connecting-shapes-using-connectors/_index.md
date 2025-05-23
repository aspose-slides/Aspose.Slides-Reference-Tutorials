---
"description": "Aspose.Slides for .NET のパワーを体験して、プレゼンテーション内の図形を簡単に接続しましょう。ダイナミックコネクタでスライドをさらに魅力的に演出できます。"
"linktitle": "プレゼンテーションでコネクタを使用して図形を接続する"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "Aspose.Slides - .NET でシームレスに図形を接続する"
"url": "/ja/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET でシームレスに図形を接続する

## 導入
プレゼンテーションのダイナミックな世界では、コネクタを使って図形を繋げることで、スライドに洗練された印象を与えることができます。Aspose.Slides for .NET を使えば、開発者はシームレスにこれを実現できます。このチュートリアルでは、各ステップを分かりやすく解説し、理解を深めていただけるように解説します。
## 前提条件
チュートリアルに進む前に、次のものを用意してください。
- C# および .NET フレームワークに関する基本的な知識。
- Aspose.Slides for .NET がインストールされています。まだインストールされていない場合はダウンロードしてください。 [ここ](https://releases。aspose.com/slides/net/).
- 開発環境をセットアップしました。
## 名前空間のインポート
C# コードでは、まず必要な名前空間をインポートします。
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
## 2. プレゼンテーションクラスのインスタンスを作成する
PPTX ファイルを表す Presentation クラスのインスタンスを作成します。
```csharp
using (Presentation input = new Presentation())
{
    // 選択したスライドの図形コレクションにアクセスする
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. スライドに図形を追加する
楕円や四角形など、必要な図形をスライドに追加します。
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. コネクタ図形を追加する
スライドの図形コレクションにコネクタ図形を含めます。
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. コネクタで図形を接続する
コネクタで接続する図形を指定します。
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. コネクタの再配線
図形間の最短パスを自動的に設定するには、reroute メソッドを呼び出します。
```csharp
connector.Reroute();
```
## 7. プレゼンテーションを保存
プレゼンテーションを保存して、接続された図形を表示します。
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 結論
おめでとうございます！Aspose.Slides for .NET を使用して、プレゼンテーションスライド内のコネクタを使って図形を接続することができました。この高度な機能でプレゼンテーションを強化し、聴衆を魅了しましょう。
## よくある質問
### Aspose.Slides for .NET は最新の .NET フレームワークと互換性がありますか?
はい、Aspose.Slides for .NET は、最新の .NET フレームワーク バージョンとの互換性を確保するために定期的に更新されます。
### 1 つのコネクタを使用して 3 つ以上の図形を接続できますか?
はい、コード内のコネクタ ロジックを拡張することで、複数の図形を接続できます。
### 接続できる図形に制限はありますか?
Aspose.Slides for .NET は、基本図形、スマート アート、カスタム図形など、さまざまな図形の接続をサポートしています。
### コネクタの外観をカスタマイズするにはどうすればよいですか?
線のスタイルや色など、コネクタの外観をカスタマイズする方法については、Aspose.Slides のドキュメントを参照してください。
### Aspose.Slides サポートのコミュニティ フォーラムはありますか?
はい、サポートを見つけたり、経験を共有したりできます。 [Aspose.Slides フォーラム](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}