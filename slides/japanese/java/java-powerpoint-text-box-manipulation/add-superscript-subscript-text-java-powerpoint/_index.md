---
title: Java PowerPoint で上付き文字と下付き文字を追加する
linktitle: Java PowerPoint で上付き文字と下付き文字を追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java PowerPoint プレゼンテーションに上付き文字と下付き文字のテキストを追加する方法を学びます。スライドを強化するのに最適です。
weight: 13
url: /ja/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 導入
魅力的で情報豊富な PowerPoint プレゼンテーションを作成するには、多くの場合、上付き文字や下付き文字などの書式設定機能を使用する必要があります。このチュートリアルでは、Aspose.Slides for Java を使用して、Java PowerPoint プレゼンテーションに上付き文字や下付き文字を組み込むプロセスについて説明します。
## 前提条件
始める前に、次のものがあることを確認してください。
- Java 開発キット (JDK) がシステムにインストールされています。
-  Aspose.Slides for Javaライブラリ。ここからダウンロードできます。[ここ](https://releases.aspose.com/slides/java/).
- Java 開発用にセットアップされた IntelliJ IDEA や Eclipse などの統合開発環境 (IDE)。
- Java プログラミングと PowerPoint プレゼンテーションに関する基本的な知識。

## パッケージのインポート
まず、Aspose.Slides for Java から必要なパッケージをインポートします。
```java
import com.aspose.slides.*;
```
## ステップ1: プレゼンテーションを設定する
```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## ステップ2: スライドにアクセスする
```java
//最初のスライドを取得する
ISlide slide = presentation.getSlides().get_Item(0);
```
## ステップ3: テキストボックスを作成する
```java
//テキストボックスとして機能するオートシェイプを作成する
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## ステップ4: 上付き文字を追加する
```java
//本文の段落を作成する
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
//上付き文字のテキスト部分を作成する
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); //上付き文字のエスケープメントを設定する
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//テキストボックスに上付き文字のメイン段落を追加します
textFrame.getParagraphs().add(mainParagraph);
```
## ステップ5: 下付き文字を追加する
```java
//下付きテキスト用の別の段落を作成する
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
//下付き文字部分を作成する
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); //下付き文字のエスケープメントを設定する
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
//テキストボックスに下付き文字の段落を追加します
textFrame.getParagraphs().add(subscriptParagraph);
```
## ステップ6: プレゼンテーションを保存する
```java
//プレゼンテーションを保存する
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## 結論
このチュートリアルでは、Aspose.Slides for Java を使用して、Java PowerPoint プレゼンテーションに上付き文字と下付き文字を追加する方法について説明しました。これらの手順に従うことで、コンテンツを効果的に伝える、視覚的に魅力的で情報量の多いスライドを作成できます。

## よくある質問
### Aspose.Slides for Java とは何ですか?
Aspose.Slides for Java は、開発者がプログラムによって PowerPoint プレゼンテーションを作成、操作、変換できるようにする強力なライブラリです。
### Aspose.Slides for Java に関する詳細なドキュメントはどこで入手できますか?
詳細なドキュメントは以下をご覧ください[ここ](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java の一時ライセンスを取得するにはどうすればよいですか?
臨時免許証を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java を無料で試すことはできますか?
はい、無料試用版は以下からダウンロードできます。[ここ](https://releases.aspose.com/).
### Aspose.Slides for Java のサポートはどこで受けられますか?
サポートやディスカッションについては、[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
