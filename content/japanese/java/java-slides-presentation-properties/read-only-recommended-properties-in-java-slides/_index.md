---
title: Java スライドの読み取り専用の推奨プロパティ
linktitle: Java スライドの読み取り専用の推奨プロパティ
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java PowerPoint プレゼンテーションで読み取り専用の推奨プロパティを有効にする方法について説明します。プレゼンテーションのセキュリティを強化するには、ソース コードの例を含むステップバイステップ ガイドに従ってください。
type: docs
weight: 17
url: /ja/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

## Java スライドでの読み取り専用の推奨プロパティの有効化の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションの読み取り専用の推奨プロパティを有効にする方法を説明します。読み取り専用の推奨プロパティは、ユーザーに変更を加えずにプレゼンテーションを表示するように促したい場合に役立ちます。これらのプロパティは、プレゼンテーションを読み取り専用モードで開く必要があることを示唆しています。これを実現するためのステップバイステップのガイドと Java ソース コードを提供します。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリがプロジェクトに設定されていることを確認してください。からダウンロードできます。[Aspose.Slides for Java Web サイト](https://products.aspose.com/slides/java/).

## ステップ 1: 新しい PowerPoint プレゼンテーションを作成する

まず、Aspose.Slides for Java を使用して新しい PowerPoint プレゼンテーションを作成します。すでにプレゼンテーションがある場合は、この手順をスキップできます。

```java
String outPptxPath = RunExamples.getOutPath() + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

上記のコードでは、出力 PowerPoint ファイルのパスを定義し、新しいプレゼンテーション オブジェクトを作成しました。

## ステップ 2: 読み取り専用の推奨プロパティを有効にする

次に、プレゼンテーションの読み取り専用の推奨プロパティを有効にしましょう。

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

このコード スニペットでは、`getProtectionManager().setReadOnlyRecommended(true)`読み取り専用の推奨プロパティをに設定するメソッド`true`。これにより、誰かがプレゼンテーションを開いたときに、読み取り専用モードで開くように求められます。

## ステップ 3: プレゼンテーションを保存する

最後に、「読み取り専用推奨」プロパティを有効にしてプレゼンテーションを保存します。

## Java スライドの読み取り専用推奨プロパティの完全なソース コード

```java
String outPptxPath = RunExamples.getOutPath() + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションの読み取り専用の推奨プロパティを有効にする方法を学習しました。この機能は、編集を制限し、閲覧者にプレゼンテーションを読み取り専用モードで使用するよう促す場合に役立ちます。プレゼンテーションにパスワードを設定すると、セキュリティをさらに強化できます。

## よくある質問

### 読み取り専用の推奨プロパティを無効にするにはどうすればよいですか?

読み取り専用の推奨プロパティを無効にするには、次のコードを使用します。

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### 読み取り専用の推奨プレゼンテーションにパスワードを設定できますか?

はい、Aspose.Slides for Java を使用して、読み取り専用の推奨プレゼンテーションにパスワードを設定できます。使用できます`setPassword`プレゼンテーションのパスワードを設定するメソッド。パスワードが設定されている場合、読み取り専用モードであっても、ユーザーはプレゼンテーションを開くためにパスワードを入力する必要があります。

```java
pres.getProtectionManager().setPassword("YourPassword");
```

忘れずに交換してください`"YourPassword"`希望のパスワードを入力します。