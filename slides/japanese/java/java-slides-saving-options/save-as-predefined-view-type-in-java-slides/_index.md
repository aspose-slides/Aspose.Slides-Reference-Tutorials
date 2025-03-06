---
title: Java スライドで定義済みのビュー タイプとして保存
linktitle: Java スライドで定義済みのビュー タイプとして保存
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java スライドで定義済みのビュー タイプを設定する方法を学びます。コード例と FAQ を含むステップ バイ ステップ ガイド。
weight: 10
url: /ja/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java スライドで定義済みビュー タイプとして保存する方法の概要

このステップバイステップ ガイドでは、Aspose.Slides for Java を使用して、定義済みのビュー タイプでプレゼンテーションを保存する方法について説明します。このタスクを正常に完了するために必要なコードと説明を提供します。

## 前提条件

始める前に、以下のものを用意してください。

- Java プログラミングの基礎知識。
- Aspose.Slides for Java ライブラリがインストールされました。
- 選択した統合開発環境 (IDE)。

## 環境の設定

開始するには、次の手順に従って開発環境をセットアップします。

1. IDE で新しい Java プロジェクトを作成します。
2. Aspose.Slides for Java ライブラリを依存関係としてプロジェクトに追加します。

環境がセットアップされたので、コードを進めていきましょう。

## ステップ1: プレゼンテーションの作成

定義済みのビュー タイプでプレゼンテーションを保存する方法を示すために、まず新しいプレゼンテーションを作成します。プレゼンテーションを作成するコードは次のとおりです。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションファイルを開く
Presentation presentation = new Presentation();
```

このコードでは、新しい`Presentation`PowerPoint プレゼンテーションを表すオブジェクトです。

## ステップ2: ビュータイプの設定

次に、プレゼンテーションのビュー タイプを設定します。ビュー タイプは、プレゼンテーションを開いたときにどのように表示されるかを定義します。この例では、「スライド マスター ビュー」に設定します。コードは次のとおりです。

```java
//ビュータイプの設定
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

上記のコードでは、`setLastView`方法の`ViewProperties`ビュータイプを設定するクラス`SlideMasterView`必要に応じて他のビュー タイプを選択することもできます。

## ステップ3: プレゼンテーションを保存する

プレゼンテーションを作成し、ビューの種類を設定したら、プレゼンテーションを保存します。PPTX 形式で保存します。コードは次のとおりです。

```java
//プレゼンテーションを保存しています
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

このコードでは、`save`方法の`Presentation`指定されたファイル名と形式でプレゼンテーションを保存するクラス。

## Java スライドで定義済みビュー タイプとして保存するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションファイルを開く
Presentation presentation = new Presentation();
try
{
	//ビュータイプの設定
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	//プレゼンテーションを保存しています
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、Java で定義済みのビュー タイプでプレゼンテーションを保存する方法を学習しました。提供されているコードと手順に従うことで、プレゼンテーションのビュー タイプを簡単に設定し、希望の形式で保存できます。

## よくある質問

### 表示タイプを「スライド マスター表示」以外に変更するにはどうすればよいですか?

表示タイプを「スライドマスター表示」以外に変更するには、`ViewType.SlideMasterView`希望するビュータイプ、例えば`ViewType.NormalView`または`ViewType.SlideSorterView`ビュー タイプを設定するコード内にあります。

### プレゼンテーション内の個々のスライドの表示プロパティを設定できますか?

はい、Aspose.Slides for Java を使用して、個々のスライドのビュー プロパティを設定できます。プレゼンテーション内のスライドを反復処理することで、各スライドのプロパティに個別にアクセスして操作できます。

### プレゼンテーションを他のどのような形式で保存できますか?

Aspose.Slides for Javaは、PPTX、PDF、TIFF、HTMLなど、さまざまな出力形式をサポートしています。適切なオプションを使用して、プレゼンテーションを保存するときに希望する形式を指定できます。`SaveFormat`列挙値。

### Aspose.Slides for Java はプレゼンテーションのバッチ処理に適していますか?

はい、Aspose.Slides for Java はバッチ処理タスクに適しています。Java コードを使用して、複数のプレゼンテーションの処理を自動化し、変更を適用し、一括保存することができます。

### Aspose.Slides for Java の詳細情報とドキュメントはどこで入手できますか?

 Aspose.Slides for Java に関する包括的なドキュメントとリファレンスについては、次のドキュメント Web サイトをご覧ください。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
