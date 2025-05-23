---
"description": "Aspose.Slides for Java を使用して、Java PowerPoint プレゼンテーションで読み取り専用推奨プロパティを有効にする方法を学びます。プレゼンテーションのセキュリティを強化するには、ソースコード例を含むステップバイステップのガイドに従ってください。"
"linktitle": "Javaスライドの読み取り専用推奨プロパティ"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドの読み取り専用推奨プロパティ"
"url": "/ja/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドの読み取り専用推奨プロパティ


## Javaスライドで読み取り専用の推奨プロパティを有効にする方法の紹介

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションの読み取り専用推奨プロパティを有効にする方法を説明します。読み取り専用推奨プロパティは、ユーザーにプレゼンテーションを変更せずに閲覧するよう促したい場合に便利です。これらのプロパティは、プレゼンテーションを読み取り専用モードで開くことを推奨します。この設定を実現するための手順を Java ソースコードとともにご説明します。

## 前提条件

始める前に、プロジェクトにAspose.Slides for Javaライブラリがセットアップされていることを確認してください。ダウンロードは以下から行えます。 [Aspose.Slides for Java ウェブサイト](https://products。aspose.com/slides/java/).

## ステップ1: 新しいPowerPointプレゼンテーションを作成する

まず、Aspose.Slides for Java を使って新しい PowerPoint プレゼンテーションを作成します。既にプレゼンテーションをお持ちの場合は、この手順をスキップしてください。

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

上記のコードでは、出力 PowerPoint ファイルへのパスを定義し、新しいプレゼンテーション オブジェクトを作成しました。

## ステップ2: 読み取り専用の推奨プロパティを有効にする

ここで、プレゼンテーションの読み取り専用推奨プロパティを有効にしましょう。

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

このコードスニペットでは、 `getProtectionManager().setReadOnlyRecommended(true)` 読み取り専用推奨プロパティを設定する方法 `true`これにより、誰かがプレゼンテーションを開いたときに、読み取り専用モードで開くように求めるメッセージが表示されます。

## ステップ3: プレゼンテーションを保存する

最後に、読み取り専用推奨プロパティを有効にしてプレゼンテーションを保存します。

## Javaスライドの読み取り専用推奨プロパティの完全なソースコード

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
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

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションの「読み取り専用推奨」プロパティを有効にする方法を学習しました。この機能は、編集権限を制限し、閲覧者にプレゼンテーションを読み取り専用モードで使用してもらいたい場合に役立ちます。プレゼンテーションにパスワードを設定することで、セキュリティをさらに強化できます。

## よくある質問

### 読み取り専用推奨プロパティを無効にするにはどうすればいいですか?

読み取り専用推奨プロパティを無効にするには、次のコードを使用します。

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### 読み取り専用推奨プレゼンテーションにパスワードを設定できますか?

はい、Aspose.Slides for Javaを使用して、読み取り専用の推奨プレゼンテーションにパスワードを設定できます。 `setPassword` プレゼンテーションにパスワードを設定する方法。パスワードが設定されている場合、読み取り専用モードであっても、ユーザーはプレゼンテーションを開くためにパスワードを入力する必要があります。

```java
pres.getProtectionManager().setPassword("YourPassword");
```

交換を忘れずに `"YourPassword"` ご希望のパスワードを入力してください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}