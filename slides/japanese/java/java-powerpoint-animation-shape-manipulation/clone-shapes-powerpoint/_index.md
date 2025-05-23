---
"description": "Aspose.Slides for Javaを使用して、PowerPointプレゼンテーション内の図形を複製する方法を学びましょう。このわかりやすいチュートリアルでワークフローを効率化しましょう。"
"linktitle": "PowerPointで図形を複製する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "PowerPointで図形を複製する"
"url": "/ja/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPointで図形を複製する

## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーション内の図形を複製する方法を説明します。図形を複製すると、プレゼンテーション内の既存の図形を複製できます。これは、一貫したレイアウトを作成したり、スライド間で要素を繰り返し表示したりする場合などに特に便利です。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1. Java開発キット（JDK）：システムにJava開発キットがインストールされていることを確認してください。最新バージョンは、以下のサイトからダウンロードしてインストールできます。 [Webサイト](https://www。oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java ライブラリ: Aspose.Slides for Java ライブラリをダウンロードし、Java プロジェクトに含めてください。ダウンロードリンクは以下にあります。 [ここ](https://releases。aspose.com/slides/java/).

## パッケージのインポート
まず、Javaプロジェクトに必要なパッケージをインポートする必要があります。これらのパッケージは、Aspose.Slides for Javaを使用してPowerPointプレゼンテーションを操作するために必要な機能を提供します。
```java
import com.aspose.slides.*;

```
## ステップ1: プレゼンテーションを読み込む
まず、複製したい図形を含むPowerPointプレゼンテーションを読み込む必要があります。 `Presentation` ソースプレゼンテーションをロードするクラス。
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## ステップ2: 図形を複製する
次に、元のプレゼンテーションから図形を複製し、同じプレゼンテーション内の新しいスライドに追加します。これには、元の図形にアクセスし、新しいスライドを作成し、複製した図形を新しいスライドに追加することが含まれます。
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## ステップ3: プレゼンテーションを保存する
最後に、複製された図形を含む変更されたプレゼンテーションを新しいファイルに保存します。
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## 結論
Aspose.Slides for Java を使用してPowerPointプレゼンテーション内の図形を複製するのは非常に簡単で、プレゼンテーション作成ワークフローを効率化できます。このチュートリアルで説明する手順に従うだけで、既存の図形を簡単に複製し、必要に応じてカスタマイズできます。

## よくある質問
### 異なるスライド間で図形を複製できますか?
はい、Aspose.Slides for Java を使用して、プレゼンテーション内の任意のスライドから図形を複製し、別のスライドに追加できます。
### 図形の複製には制限がありますか?
Aspose.Slides for Java は強力な複製機能を提供しますが、複雑な図形やアニメーションは完全に複製されない場合があります。
### 複製した図形をスライドに追加した後で変更できますか?
はい、図形を複製してスライドに追加したら、必要に応じてそのプロパティ、スタイル、コンテンツを変更できます。
### Aspose.Slides for Java は図形以外の要素の複製をサポートしていますか?
はい、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内のスライド、テキスト、画像、その他の要素を複製できます。
### Aspose.Slides for Java の試用版はありますか?
はい、Aspose.Slides for Javaの無料試用版を以下のサイトからダウンロードできます。 [Webサイト](https://releases。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}