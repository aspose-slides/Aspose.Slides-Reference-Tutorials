---
"description": "Aspose.Slides for Java を使用して、Java スライドのプレゼンテーション保護をチェックする方法を学びます。このステップバイステップガイドでは、書き込み保護とオープン保護のチェックのコード例を紹介します。"
"linktitle": "Javaスライドのプレゼンテーション保護を確認する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのプレゼンテーション保護を確認する"
"url": "/ja/java/presentation-properties/check-presentation-protection-in-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのプレゼンテーション保護を確認する


## Javaスライドでのプレゼンテーション保護のチェックの概要

このチュートリアルでは、Aspose.Slides for Java を使用してプレゼンテーションの保護を確認する方法を説明します。プレゼンテーションの書き込み保護とオープン保護の2つのシナリオを取り上げます。それぞれのシナリオについて、ステップバイステップのコード例を示します。

## 前提条件

始める前に、JavaプロジェクトにAspose.Slides for Javaライブラリがセットアップされていることを確認してください。Asposeのウェブサイトからダウンロードし、プロジェクトの依存関係に追加できます。

### Maven依存関係

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

交換する `your_version_here` 使用している Aspose.Slides for Java のバージョンによって異なります。

## ステップ1: 書き込み保護を確認する

プレゼンテーションがパスワードで書き込み保護されているかどうかを確認するには、 `IPresentationInfo` インターフェースです。これを実行するコードは次のとおりです。

```java
// ソースプレゼンテーションのパス
String pptxFile = "path_to_presentation.pptx";

// IPresentationInfoインターフェース経由で書き込み保護パスワードを確認する
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

交換する `"path_to_presentation.pptx"` プレゼンテーションファイルへの実際のパスと `"password_here"` 書き込み保護パスワードを使用します。

## ステップ2: オープン保護を確認する

プレゼンテーションを開くためのパスワードが保護されているかどうかを確認するには、 `IPresentationInfo` インターフェースです。これを実行するコードは次のとおりです。

```java
// ソースプレゼンテーションのパス
String pptFile = "path_to_presentation.ppt";

// IPresentationInfo インターフェース経由でプレゼンテーションのオープン保護をチェックする
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

交換する `"path_to_presentation.ppt"` プレゼンテーション ファイルへの実際のパスを入力します。

## Javaスライドのプレゼンテーション保護をチェックするための完全なソースコード

```java
//ソースプレゼンテーションのパス
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// IPresentationInfoインターフェース経由で書き込み保護パスワードを確認する
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// IProtectionManagerインターフェース経由で書き込み保護パスワードを確認する
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// IPresentationInfo インターフェース経由でプレゼンテーションのオープン保護をチェックする
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドのプレゼンテーション保護をチェックする方法を学びました。書き込み保護とオープン保護の2つのシナリオを取り上げました。これらのチェック機能を Java アプリケーションに統合することで、保護されたプレゼンテーションを効果的に処理できるようになります。

## よくある質問

### Aspose.Slides for Java を入手するにはどうすればよいですか?

Aspose.Slides for Java は、Aspose Web サイトからダウンロードすることも、前提条件セクションに示されているように、プロジェクトに Maven 依存関係として追加することもできます。

### プレゼンテーションの書き込み保護とオープン保護の両方をチェックできますか?

はい、提供されているコード例を使用して、プレゼンテーションの書き込み保護とオープン保護の両方をチェックできます。

### 保護パスワードを忘れた場合はどうすればいいですか?

プレゼンテーションの保護パスワードを忘れた場合、復元する方法は標準では用意されていません。このような事態を避けるために、パスワードは必ず記録しておいてください。

### Aspose.Slides for Java は最新の PowerPoint ファイル形式と互換性がありますか?

はい、Aspose.Slides for Java は、.pptx ファイルを含む最新の PowerPoint ファイル形式をサポートしています。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}