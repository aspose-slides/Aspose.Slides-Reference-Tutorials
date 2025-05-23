---
"description": "Aspose.Slides for Java を使用して、Java スライドで定義済みのビュータイプを設定する方法を学びます。コード例と FAQ を含むステップバイステップガイドです。"
"linktitle": "Javaスライドで定義済みのビュータイプとして保存"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドで定義済みのビュータイプとして保存"
"url": "/ja/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドで定義済みのビュータイプとして保存


## Javaスライドで定義済みのビュータイプとして保存する方法の紹介

このステップバイステップガイドでは、Aspose.Slides for Java を使用して、定義済みのビュータイプでプレゼンテーションを保存する方法を説明します。このタスクを正常に完了するために必要なコードと説明を提供します。

## 前提条件

始める前に、以下のものを用意してください。

- Java プログラミングの基礎知識。
- Aspose.Slides for Java ライブラリがインストールされました。
- 選択した統合開発環境 (IDE)。

## 環境の設定

開始するには、次の手順に従って開発環境を設定します。

1. IDE で新しい Java プロジェクトを作成します。
2. Aspose.Slides for Java ライブラリを依存関係としてプロジェクトに追加します。

環境がセットアップされたので、コードを進めていきましょう。

## ステップ1：プレゼンテーションの作成

定義済みのビュータイプでプレゼンテーションを保存する方法を説明するために、まず新しいプレゼンテーションを作成します。プレゼンテーションを作成するコードは次のとおりです。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションファイルを開く
Presentation presentation = new Presentation();
```

このコードでは、新しい `Presentation` これは PowerPoint プレゼンテーションを表すオブジェクトです。

## ステップ2: ビュータイプの設定

次に、プレゼンテーションの表示タイプを設定します。表示タイプは、プレゼンテーションを開いたときにどのように表示されるかを定義します。この例では、「スライドマスター表示」に設定します。コードは次のとおりです。

```java
// ビュータイプの設定
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

上記のコードでは、 `setLastView` の方法 `ViewProperties` ビュータイプを設定するクラス `SlideMasterView`必要に応じて他のビュー タイプを選択することもできます。

## ステップ3: プレゼンテーションを保存する

プレゼンテーションを作成し、表示形式を設定したら、次はプレゼンテーションを保存します。PPTX形式で保存します。コードは次のとおりです。

```java
// プレゼンテーションを保存しています
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

このコードでは、 `save` の方法 `Presentation` 指定されたファイル名と形式でプレゼンテーションを保存するクラス。

## Javaスライドで定義済みビュータイプとして保存するための完全なソースコード

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションファイルを開く
Presentation presentation = new Presentation();
try
{
	// ビュータイプの設定
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// プレゼンテーションを保存しています
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、Java で定義済みのビュータイプでプレゼンテーションを保存する方法を学習しました。提供されているコードと手順に従うことで、プレゼンテーションのビュータイプを簡単に設定し、希望の形式で保存できます。

## よくある質問

### 表示タイプを「スライド マスター表示」以外に変更するにはどうすればよいですか?

表示タイプを「スライドマスター表示」以外のものに変更するには、 `ViewType.SlideMasterView` 希望するビュータイプ、例えば `ViewType.NまたはmalView` or `ViewType.SlideSorterView`ビュー タイプを設定するコード内にあります。

### プレゼンテーション内の個々のスライドの表示プロパティを設定できますか?

はい、Aspose.Slides for Java を使用すると、個々のスライドのビュープロパティを設定できます。プレゼンテーション内のスライドを反復処理することで、各スライドのプロパティに個別にアクセスして操作できます。

### プレゼンテーションを他のどのような形式で保存できますか?

Aspose.Slides for Javaは、PPTX、PDF、TIFF、HTMLなど、様々な出力形式をサポートしています。適切なオプションを使用して、プレゼンテーションを保存するときに希望の形式を指定できます。 `SaveFormat` 列挙値。

### Aspose.Slides for Java はプレゼンテーションのバッチ処理に適していますか?

はい、Aspose.Slides for Javaはバッチ処理タスクに最適です。Javaコードを使用して、複数のプレゼンテーションの処理を自動化し、変更を適用して一括保存できます。

### Aspose.Slides for Java の詳細情報やドキュメントはどこで入手できますか?

Aspose.Slides for Java に関する包括的なドキュメントとリファレンスについては、次のドキュメント Web サイトをご覧ください。 [Aspose.Slides for Java ドキュメント](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}