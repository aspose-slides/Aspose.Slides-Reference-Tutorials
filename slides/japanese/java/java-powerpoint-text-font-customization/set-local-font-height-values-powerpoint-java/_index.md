---
"description": "Aspose.SlidesとJavaを使って、PowerPointプレゼンテーションのフォントの高さを調整する方法を学びましょう。スライド内のテキストの書式設定を簡単に強化できます。"
"linktitle": "Javaを使用してPowerPointでローカルフォントの高さの値を設定する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaを使用してPowerPointでローカルフォントの高さの値を設定する"
"url": "/ja/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaを使用してPowerPointでローカルフォントの高さの値を設定する

## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーション内の様々なレベルでフォントの高さを操作する方法を学びます。フォントサイズの制御は、視覚的に魅力的で構造化されたプレゼンテーションを作成する上で不可欠です。様々なテキスト要素のフォントの高さを設定する方法を、ステップバイステップの例で説明します。
## 前提条件
始める前に、次のものがあることを確認してください。
- システムにJava開発キット（JDK）がインストールされている
- Aspose.Slides for Javaライブラリ。ダウンロードできます。 [ここ](https://releases。aspose.com/slides/java/).
- JavaプログラミングとPowerPointプレゼンテーションの基本的な理解
## パッケージのインポート
必要な Aspose.Slides パッケージを Java ファイルに含めるようにしてください。
```java
import com.aspose.slides.*;
```
## ステップ1: プレゼンテーションオブジェクトの初期化
まず、新しい PowerPoint プレゼンテーション オブジェクトを作成します。
```java
Presentation pres = new Presentation();
```
## ステップ2: 図形とテキストフレームを追加する
最初のスライドにテキスト フレームを含む自動シェイプを追加します。
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## ステップ3: テキスト部分を作成する
異なるフォントの高さでテキスト部分を定義します。
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## ステップ4: フォントの高さを設定する
フォントの高さをさまざまなレベルに設定します。
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## ステップ5: プレゼンテーションを保存する
変更したプレゼンテーションをファイルに保存します。
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## 結論
このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint スライド内のフォントの高さをプログラムで調整する方法を説明しました。プレゼンテーション全体、段落、部分など、さまざまなレベルでフォントサイズを調整することで、プレゼンテーション内のテキストの書式設定を細かく制御できます。
## よくある質問
### Aspose.Slides for Java とは何ですか?
Aspose.Slides for Java は、PowerPoint プレゼンテーションをプログラムで操作するための強力な API です。
### Aspose.Slides for Java のドキュメントはどこにありますか?
ドキュメントは以下にあります [ここ](https://reference。aspose.com/slides/java/).
### 購入前に Aspose.Slides for Java を試すことはできますか?
はい、無料トライアルをご利用いただけます [ここ](https://releases。aspose.com/).
### Aspose.Slides for Java のサポートを受けるにはどうすればよいですか?
サポートについては、 [Aspose.Slides フォーラム](https://forum。aspose.com/c/slides/11).
### Aspose.Slides for Java のライセンスはどこで購入できますか?
ライセンスを購入することができます [ここ](https://purchase。aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}