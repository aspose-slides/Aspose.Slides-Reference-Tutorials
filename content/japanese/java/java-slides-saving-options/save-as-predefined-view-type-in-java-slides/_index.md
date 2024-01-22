---
title: Java スライドで事前定義されたビュー タイプとして保存
linktitle: Java スライドで事前定義されたビュー タイプとして保存
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java Slides で事前定義されたビュー タイプを設定する方法を学びます。コード例と FAQ を含むステップバイステップのガイド。
type: docs
weight: 10
url: /ja/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

## Java スライドで事前定義されたビュー タイプとして保存する方法の概要

このステップバイステップ ガイドでは、Aspose.Slides for Java を使用して、事前定義されたビュー タイプでプレゼンテーションを保存する方法を説明します。このタスクを正常に実行するために必要なコードと説明を提供します。

## 前提条件

始める前に、以下のものがあることを確認してください。

- Java プログラミングの基本的な知識。
- Aspose.Slides for Java ライブラリがインストールされています。
- 任意の統合開発環境 (IDE)。

## 環境のセットアップ

開始するには、次の手順に従って開発環境をセットアップします。

1. IDE で新しい Java プロジェクトを作成します。
2. Aspose.Slides for Java ライブラリを依存関係としてプロジェクトに追加します。

環境がセットアップされたので、コードを進めてみましょう。

## ステップ 1: プレゼンテーションを作成する

定義済みのビュー タイプでプレゼンテーションを保存する方法を示すために、まず新しいプレゼンテーションを作成します。プレゼンテーションを作成するコードは次のとおりです。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションファイルを開く
Presentation presentation = new Presentation();
```

このコードでは、新しい`Presentation`PowerPoint プレゼンテーションを表すオブジェクト。

## ステップ 2: ビューの種類を設定する

次に、プレゼンテーションのビュー タイプを設定します。ビューの種類は、プレゼンテーションを開いたときにどのように表示されるかを定義します。ここでは例として「スライドマスタービュー」に設定します。コードは次のとおりです。

```java
//ビュータイプの設定
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

上記のコードでは、`setLastView`の方法`ViewProperties`ビュータイプを設定するクラス`SlideMasterView`。必要に応じて、他のビューの種類を選択できます。

## ステップ 3: プレゼンテーションを保存する

プレゼンテーションを作成し、ビューの種類を設定したので、プレゼンテーションを保存します。 PPTX形式で保存します。コードは次のとおりです。

```java
//プレゼンテーションの保存
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

このコードでは、`save`の方法`Presentation`クラスを使用して、指定したファイル名と形式でプレゼンテーションを保存します。

## Java スライドで事前定義されたビュー タイプとして保存するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションファイルを開く
Presentation presentation = new Presentation();
try
{
	//ビュータイプの設定
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	//プレゼンテーションの保存
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、Java で事前定義されたビュー タイプでプレゼンテーションを保存する方法を学習しました。提供されたコードと手順に従うことで、プレゼンテーションのビュー タイプを簡単に設定し、希望の形式で保存できます。

## よくある質問

### 表示タイプを「スライド マスター ビュー」以外に変更するにはどうすればよいですか?

ビューの種類を「スライド マスター ビュー」以外に変更するには、次のように置き換えます。`ViewType.SlideMasterView`などの目的のビュー タイプを使用して、`ViewType.NormalView`または`ViewType.SlideSorterView`、コード内でビューのタイプを設定します。

### プレゼンテーション内の個々のスライドのビュー プロパティを設定できますか?

はい、Aspose.Slides for Java を使用して、個々のスライドのビュー プロパティを設定できます。プレゼンテーション内のスライドを繰り返し処理することで、各スライドのプロパティに個別にアクセスして操作できます。

### プレゼンテーションを他にどのような形式で保存できますか?

Aspose.Slides for Java は、PPTX、PDF、TIFF、HTML などを含むさまざまな出力形式をサポートしています。プレゼンテーションを保存するときに、適切な形式を使用して希望の形式を指定できます。`SaveFormat`列挙値。

### Aspose.Slides for Java はプレゼンテーションのバッチ処理に適していますか?

はい、Aspose.Slides for Java はバッチ処理タスクに適しています。 Java コードを使用して、複数のプレゼンテーションの処理を自動化し、変更を適用し、一括保存できます。

### Aspose.Slides for Java の詳細情報とドキュメントはどこで入手できますか?

 Aspose.Slides for Java に関連する包括的なドキュメントとリファレンスについては、次のドキュメント Web サイトを参照してください。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).