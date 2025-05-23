---
"description": "Aspose.Slides for Java を使って、PowerPoint プレゼンテーションでコネクタを使って図形を接続する方法を学びましょう。初心者向けのステップバイステップのチュートリアルです。"
"linktitle": "PowerPoint でコネクタを使用して図形を接続する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "PowerPoint でコネクタを使用して図形を接続する"
"url": "/ja/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint でコネクタを使用して図形を接続する

## 導入
このチュートリアルでは、Aspose.Slides for Java を使って、PowerPoint プレゼンテーションでコネクタを使って図形を接続する方法を学びます。ステップバイステップの手順に従って、図形を効率的に接続し、視覚的に魅力的なスライドを作成しましょう。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
- Java プログラミング言語に関する基本的な知識。
- システムに Java Development Kit (JDK) をインストールしました。
- Aspose.Slides for Javaをダウンロードしてセットアップしました。まだインストールしていない場合は、こちらからダウンロードできます。 [ここ](https://releases。aspose.com/slides/java/).
- Eclipse や IntelliJ IDEA などのコード エディター。

## パッケージのインポート
まず、Java プロジェクトで Aspose.Slides を操作するために必要なパッケージをインポートします。
```java
import com.aspose.slides.*;

```
## ステップ1: プレゼンテーションクラスのインスタンス化
インスタンス化する `Presentation` 作業中の PPTX ファイルを表すクラスです。
```java
// ドキュメント ディレクトリへのパス。                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## ステップ2: 図形コレクションにアクセスする
図形とコネクタを追加する、選択したスライドの図形コレクションにアクセスします。
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## ステップ3: 図形を追加する
スライドに必要な図形を追加します。この例では、楕円と長方形を追加します。
```java
// オートシェイプ楕円を追加
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// オートシェイプ四角形を追加
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## ステップ4: コネクタを追加する
スライド シェイプ コレクションにコネクタ シェイプを追加します。
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## ステップ5: 図形をコネクタに結合する
図形をコネクタに接続します。
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## ステップ6: コネクタの再ルーティング
図形間の最短パスを自動的に設定するには、reroute を呼び出します。
```java
connector.reroute();
```
## ステップ7: プレゼンテーションを保存する
コネクタを使用して図形を接続した後、プレゼンテーションを保存します。
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
最後に、Presentation オブジェクトを破棄することを忘れないでください。
```java
if (input != null) input.dispose();
```
これで、Aspose.Slides for Java を使用して、PowerPoint でコネクタを使用して図形を正常に接続することができました。

## 結論
このチュートリアルでは、Aspose.Slides for Java を使って、PowerPoint プレゼンテーションでコネクタを使って図形を接続する方法を学びました。これらの簡単な手順に従うだけで、視覚的に魅力的な図やフローチャートを作成し、プレゼンテーションをより魅力的にすることができます。
## よくある質問
### Aspose.Slides for Java でコネクタの外観をカスタマイズできますか?
はい、プレゼンテーションのニーズに合わせて、色、線のスタイル、太さなど、コネクタのさまざまなプロパティをカスタマイズできます。
### Aspose.Slides for Java はすべてのバージョンの PowerPoint と互換性がありますか?
Aspose.Slides for Java は、PPTX、PPT、ODP など、さまざまな PowerPoint 形式をサポートしています。
### 1 つのコネクタで 3 つ以上の図形を接続できますか?
はい、Aspose.Slides for Java が提供する複雑なコネクタを使用して、複数の図形を接続できます。
### Aspose.Slides for Java は図形にテキストを追加する機能をサポートしていますか?
はい、Aspose.Slides for Java を使用すると、プログラムによって図形やコネクタにテキストを簡単に追加できます。
### Aspose.Slides for Java ユーザー向けのコミュニティ フォーラムまたはサポート チャネルはありますか?
はい、Aspose.Slides フォーラムでは役立つリソースを見つけたり、質問したり、他のユーザーと交流したりできます。 [ここ](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}