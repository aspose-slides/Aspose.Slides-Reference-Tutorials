---
title: PowerPoint の接続サイトを使用して図形を接続する
linktitle: PowerPoint の接続サイトを使用して図形を接続する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint で図形を接続する方法を学びます。プレゼンテーションを簡単に自動化します。
weight: 19
url: /ja/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint の接続サイトを使用して図形を接続する

## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint の接続サイトを使用して図形を接続する方法について説明します。この強力なライブラリを使用すると、PowerPoint プレゼンテーションをプログラムで操作できるため、図形の接続などのタスクをシームレスかつ効率的に実行できます。
## 前提条件
始める前に、以下のものを用意してください。
1.  Java開発キット（JDK）：システムにJavaがインストールされていることを確認してください。ダウンロードしてインストールできます。[Webサイト](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Javaを以下のサイトからダウンロードしてインストールします。[ダウンロードページ](https://releases.aspose.com/slides/java/).
3. 統合開発環境 (IDE): IntelliJ IDEA、Eclipse、NetBeans などの Java 開発用の IDE を選択します。

## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。
```java
import com.aspose.slides.*;

```
## ステップ1: 図形コレクションへのアクセス
選択したスライドの図形コレクションにアクセスします。
```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// PPTXファイルを表すプレゼンテーションクラスをインスタンス化する
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## ステップ2: コネクタシェイプの追加
スライド シェイプ コレクションにコネクタ シェイプを追加します。
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## ステップ3: オートシェイプの追加
楕円や長方形などの自動図形を追加します。
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## ステップ4: 図形をコネクタに結合する
図形をコネクタに結合します。
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## ステップ5: 接続サイトインデックスの設定
図形の目的の接続サイト インデックスを設定します。
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## 結論
このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint の接続サイトを使用して図形を接続する方法を学習しました。この知識があれば、PowerPoint プレゼンテーションを簡単に自動化およびカスタマイズできるようになります。
## よくある質問
### Aspose.Slides for Java は他の PowerPoint 操作タスクにも使用できますか?
はい、Aspose.Slides for Java は、PowerPoint プレゼンテーションの作成、編集、変換のための幅広い機能を提供します。
### Aspose.Slides for Java は無料で使用できますか?
 Aspose.Slides for Javaは商用ライブラリですが、無料トライアルでその機能を試すことができます。[ここ](https://releases.aspose.com/)始めましょう。
### Aspose.Slides for Java の使用中に問題が発生した場合、サポートを受けることはできますか?
はい、Asposeコミュニティフォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java の一時ライセンスは利用できますか?
はい、テストや評価の目的で一時ライセンスをご利用いただけます。[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java のライセンスはどこで購入できますか?
ライセンスはAsposeのウェブサイトから購入できます。[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
