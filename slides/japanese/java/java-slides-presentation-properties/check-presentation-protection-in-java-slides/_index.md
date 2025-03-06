---
title: Java スライドのプレゼンテーション保護を確認する
linktitle: Java スライドのプレゼンテーション保護を確認する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドのプレゼンテーション保護をチェックする方法を学びます。このステップバイステップ ガイドでは、書き込み保護とオープン保護のチェックのコード例を示します。
weight: 15
url: /ja/java/presentation-properties/check-presentation-protection-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java スライドでのプレゼンテーション保護の確認の概要

このチュートリアルでは、Aspose.Slides for Java を使用してプレゼンテーション保護を確認する方法について説明します。プレゼンテーションの書き込み保護の確認とオープン保護の確認という 2 つのシナリオについて説明します。各シナリオについて、ステップバイステップのコード例を示します。

## 前提条件

始める前に、Java プロジェクトに Aspose.Slides for Java ライブラリが設定されていることを確認してください。Aspose Web サイトからダウンロードして、プロジェクトの依存関係に追加できます。

### Maven 依存関係

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

交換する`your_version_here`使用している Aspose.Slides for Java のバージョンに応じて異なります。

## ステップ1: 書き込み保護を確認する

プレゼンテーションがパスワードで書き込み保護されているかどうかを確認するには、`IPresentationInfo`インターフェース。これを行うためのコードは次のとおりです。

```java
//ソースプレゼンテーションのパス
String pptxFile = "path_to_presentation.pptx";

// IPresentationInfo インターフェイス経由で書き込み保護パスワードを確認する
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

交換する`"path_to_presentation.pptx"`プレゼンテーションファイルへの実際のパスと`"password_here"`書き込み保護パスワードを使用します。

## ステップ2: オープン保護を確認する

プレゼンテーションを開くためのパスワードで保護されているかどうかを確認するには、`IPresentationInfo`インターフェース。これを行うためのコードは次のとおりです。

```java
//ソースプレゼンテーションのパス
String pptFile = "path_to_presentation.ppt";

// IPresentationInfo インターフェイス経由でプレゼンテーションのオープン保護をチェックする
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

交換する`"path_to_presentation.ppt"`プレゼンテーション ファイルへの実際のパスを入力します。

## Java スライドのプレゼンテーション保護をチェックするための完全なソース コード

```java
//ソースプレゼンテーションのパス
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// IPresentationInfo インターフェイス経由で書き込み保護パスワードを確認する
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
//IProtectionManager インターフェイス経由で書き込み保護パスワードを確認する
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
// IPresentationInfo インターフェイス経由でプレゼンテーションのオープン保護をチェックする
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドのプレゼンテーション保護をチェックする方法を学びました。書き込み保護のチェックとオープン保護のチェックという 2 つのシナリオを取り上げました。これらのチェックを Java アプリケーションに統合して、保護されたプレゼンテーションを効果的に処理できるようになりました。

## よくある質問

### Aspose.Slides for Java を入手するにはどうすればよいですか?

Aspose.Slides for Java は、Aspose Web サイトからダウンロードするか、前提条件セクションに示されているように、プロジェクトに Maven 依存関係として追加することができます。

### プレゼンテーションの書き込み保護とオープン保護の両方をチェックできますか?

はい、提供されているコード例を使用して、プレゼンテーションの書き込み保護とオープン保護の両方をチェックできます。

### 保護パスワードを忘れた場合はどうすればいいですか?

プレゼンテーションの保護パスワードを忘れた場合、それを回復する方法は組み込まれていません。このような状況を避けるために、パスワードを必ず記録しておいてください。

### Aspose.Slides for Java は最新の PowerPoint ファイル形式と互換性がありますか?

はい、Aspose.Slides for Java は、.pptx ファイルを含む最新の PowerPoint ファイル形式をサポートしています。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
