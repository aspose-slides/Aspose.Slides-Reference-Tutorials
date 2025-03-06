---
title: Java スライドのルート ディレクトリ ClsId
linktitle: Java スライドのルート ディレクトリ ClsId
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java プレゼンテーションでルート ディレクトリ ClsId を設定する方法を学びます。CLSID を使用してハイパーリンクの動作をカスタマイズします。
weight: 10
url: /ja/java/media-controls/root-directory-clsid-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java スライドのルート ディレクトリ ClsId


## Aspose.Slides for Java でのルート ディレクトリ ClsId の設定の概要

Aspose.Slides for Java では、プレゼンテーション内のハイパーリンクがアクティブ化されたときにルート ディレクトリとして使用するアプリケーションを指定するために使用される CLSID (クラス識別子) であるルート ディレクトリ ClsId を設定できます。このガイドでは、これを段階的に行う方法について説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

- Java 開発キット (JDK) がシステムにインストールされています。
-  Aspose.Slides for Javaライブラリがプロジェクトに追加されました。ここからダウンロードできます。[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).
- Java 開発用にセットアップされたコード エディターまたは統合開発環境 (IDE)。

## ステップ1: 新しいプレゼンテーションを作成する

まず、Aspose.Slides for Java を使用して新しいプレゼンテーションを作成しましょう。この例では、空のプレゼンテーションを作成します。

```java
//出力ファイル名
String resultPath = "your_output_path/pres.ppt"; // 「your_output_path」を希望の出力ディレクトリに置き換えます。
Presentation pres = new Presentation();
```

上記のコードでは、出力プレゼンテーションファイルのパスを定義し、新しい`Presentation`物体。

## ステップ2: ルートディレクトリのClsIdを設定する

ルートディレクトリClsIdを設定するには、次のインスタンスを作成する必要があります。`PptOptions`目的の CLSID を設定します。CLSID は、ハイパーリンクがアクティブ化されたときにルート ディレクトリとして使用されるアプリケーションを表します。

```java
PptOptions pptOptions = new PptOptions();
// CLSID を「Microsoft Powerpoint.Show.8」に設定します
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

上記のコードでは、`PptOptions`オブジェクトを作成し、CLSID を「Microsoft Powerpoint.Show.8」に設定します。ルート ディレクトリとして使用するアプリケーションの CLSID に置き換えることができます。

## ステップ3: プレゼンテーションを保存する

ここで、ルート ディレクトリの ClsId を設定してプレゼンテーションを保存しましょう。

```java
//プレゼンテーションを保存
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

このステップでは、プレゼンテーションを指定された場所に保存します。`resultPath`とともに`PptOptions`先ほど作成したものです。

## ステップ4: クリーンアップ

処分するのを忘れないでください`Presentation`割り当てられたリソースを解放するオブジェクト。

```java
if (pres != null) {
    pres.dispose();
}
```

## Java スライドのルート ディレクトリ ClsId の完全なソース コード

```java
//出力ファイル名
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//CLSIDを「Microsoft Powerpoint.Show.8」に設定する
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	//プレゼンテーションを保存
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## 結論

Aspose.Slides for Java でルート ディレクトリ ClsId が正常に設定されました。これにより、プレゼンテーションでハイパーリンクがアクティブ化されたときにルート ディレクトリとして使用されるアプリケーションを指定できます。特定の要件に応じて CLSID をカスタマイズできます。

## よくある質問

### 特定のアプリケーションの CLSID を見つけるにはどうすればよいですか?

特定のアプリケーションの CLSID を見つけるには、アプリケーションの開発者が提供するドキュメントまたはリソースを参照してください。CLSID は COM オブジェクトに割り当てられた一意の識別子であり、通常は各アプリケーションに固有です。

### ルート ディレクトリにカスタム CLSID を設定できますか?

はい、ルートディレクトリにカスタムCLSIDを設定するには、`setRootDirectoryClsid`コード例に示すように、メソッドを使用します。これにより、プレゼンテーションでハイパーリンクがアクティブ化されたときに、特定のアプリケーションをルート ディレクトリとして使用できます。

### ルート ディレクトリ ClsId を設定しないとどうなりますか?

ルート ディレクトリ ClsId を設定しない場合、デフォルトの動作はプレゼンテーションを開くために使用されたビューアまたはアプリケーションによって異なります。ハイパーリンクがアクティブ化されると、独自のデフォルト アプリケーションがルート ディレクトリとして使用されることがあります。

### 個々のハイパーリンクのルート ディレクトリ ClsId を変更できますか?

いいえ、ルート ディレクトリ ClsId は通常、プレゼンテーション レベルで設定され、プレゼンテーション内のすべてのハイパーリンクに適用されます。個々のハイパーリンクに異なるアプリケーションを指定する必要がある場合は、コード内でそれらのハイパーリンクを個別に処理する必要がある場合があります。

### 使用できる CLSID に制限はありますか?

使用できる CLSID は、通常、システムにインストールされているアプリケーションによって決まります。ハイパーリンクを処理できる有効なアプリケーションに対応する CLSID を使用する必要があります。無効な CLSID を使用すると、予期しない動作が発生する可能性があることに注意してください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
