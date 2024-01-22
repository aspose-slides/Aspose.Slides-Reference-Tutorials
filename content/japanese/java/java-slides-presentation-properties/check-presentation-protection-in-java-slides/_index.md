---
title: Java スライドのプレゼンテーション保護をチェックする
linktitle: Java スライドのプレゼンテーション保護をチェックする
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Java スライドのプレゼンテーション保護をチェックする方法を学びます。このステップバイステップのガイドでは、書き込み保護チェックとオープン保護チェックのコード例を示します。
type: docs
weight: 15
url: /ja/java/presentation-properties/check-presentation-protection-in-java-slides/
---

## Java スライドでのプレゼンテーション保護のチェックの概要

このチュートリアルでは、Aspose.Slides for Java を使用してプレゼンテーションの保護をチェックする方法を検討します。プレゼンテーションの書き込み保護のチェックとオープン保護のチェックという 2 つのシナリオについて説明します。各シナリオの段階的なコード例を提供します。

## 前提条件

始める前に、Java プロジェクトに Aspose.Slides for Java ライブラリが設定されていることを確認してください。 Aspose Web サイトからダウンロードして、プロジェクトの依存関係に追加できます。

### Maven の依存関係

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

交換する`your_version_here`使用している Aspose.Slides for Java のバージョンを変更します。

## ステップ 1: 書き込み保護を確認する

プレゼンテーションがパスワードで書き込み保護されているかどうかを確認するには、`IPresentationInfo`インターフェース。これを行うコードは次のとおりです。

```java
//ソースプレゼンテーションのパス
String pptxFile = "path_to_presentation.pptx";

// IPresentationInfo インターフェイス経由で書き込み保護パスワードを確認する
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

交換する`"path_to_presentation.pptx"`プレゼンテーション ファイルへの実際のパスと`"password_here"`書き込み保護パスワード付き。

## ステップ 2: オープン保護をチェックする

プレゼンテーションを開くためのパスワードが保護されているかどうかを確認するには、`IPresentationInfo`インターフェース。これを行うコードは次のとおりです。

```java
//ソースプレゼンテーションのパス
String pptFile = "path_to_presentation.ppt";

// IPresentationInfo インターフェイス経由でプレゼンテーションのオープン保護を確認する
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

交換する`"path_to_presentation.ppt"`プレゼンテーション ファイルへの実際のパスを含めます。

## Java スライドのプレゼンテーション保護をチェックするための完全なソース コード

```java
//ソースプレゼンテーションのパス
String pptxFile = RunExamples.getDataDir_PresentationProperties() + "modify_pass2.pptx";
String pptFile = RunExamples.getDataDir_PresentationProperties() + "open_pass1.ppt";
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
// IPresentationInfo インターフェイス経由でプレゼンテーションのオープン保護を確認する
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して Java スライドのプレゼンテーション保護をチェックする方法を学びました。書き込み保護のチェックとオープン保護のチェックという 2 つのシナリオについて説明しました。これらのチェックを Java アプリケーションに統合して、保護されたプレゼンテーションを効果的に処理できるようになりました。

## よくある質問

### Java 用の Aspose.Slides を入手するにはどうすればよいですか?

Aspose.Slides for Java は、Aspose Web サイトからダウンロードすることも、前提条件セクションに示されているように、Maven 依存関係としてプロジェクトに追加することもできます。

### プレゼンテーションの書き込み保護とオープン保護の両方をチェックできますか?

はい、提供されているコード例を使用して、プレゼンテーションの書き込み保護とオープン保護の両方を確認できます。

### 保護パスワードを忘れた場合はどうすればよいですか?

プレゼンテーションの保護パスワードを忘れた場合、それを回復する組み込みの方法はありません。このような事態を避けるために、必ずパスワードを記録してください。

### Aspose.Slides for Java は最新の PowerPoint ファイル形式と互換性がありますか?

はい、Aspose.Slides for Java は、.pptx ファイルを含む最新の PowerPoint ファイル形式をサポートしています。