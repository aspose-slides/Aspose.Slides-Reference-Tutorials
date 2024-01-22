---
title: Java スライドのルート ディレクトリ ClsId
linktitle: Java スライドのルート ディレクトリ ClsId
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Java プレゼンテーション用に Aspose.Slides でルート ディレクトリ ClsId を設定する方法を学習します。 CLSID を使用してハイパーリンクの動作をカスタマイズします。
type: docs
weight: 10
url: /ja/java/media-controls/root-directory-clsid-in-java-slides/
---

## Aspose.Slides for Java でのルート ディレクトリ ClsId の設定の概要

Aspose.Slides for Java では、ルート ディレクトリ ClsId を設定できます。これは、プレゼンテーション内のハイパーリンクがアクティブ化されたときにルート ディレクトリとして使用されるアプリケーションを指定するために使用される CLSID (クラス識別子) です。このガイドでは、これを行う方法を段階的に説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
-  Aspose.Slides for Java ライブラリがプロジェクトに追加されました。からダウンロードできます[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/).
- Java 開発用にセットアップされたコード エディターまたは統合開発環境 (IDE)。

## ステップ 1: 新しいプレゼンテーションを作成する

まず、Aspose.Slides for Java を使用して新しいプレゼンテーションを作成しましょう。この例では、空のプレゼンテーションを作成します。

```java
//出力ファイル名
String resultPath = "your_output_path/pres.ppt"; //「your_output_path」を目的の出力ディレクトリに置き換えます。
Presentation pres = new Presentation();
```

上記のコードでは、出力プレゼンテーション ファイルのパスを定義し、新しいファイルを作成します。`Presentation`物体。

## ステップ 2: ルート ディレクトリの ClsId を設定する

ルート ディレクトリの ClsId を設定するには、次のインスタンスを作成する必要があります。`PptOptions`をクリックして、目的の CLSID を設定します。 CLSID は、ハイパーリンクがアクティブ化されたときにルート ディレクトリとして使用されるアプリケーションを表します。

```java
PptOptions pptOptions = new PptOptions();
// CLSID を「Microsoft Powerpoint.Show.8」に設定します。
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

上記のコードでは、`PptOptions`オブジェクトを作成し、CLSID を「Microsoft Powerpoint.Show.8」に設定します。これを、ルート ディレクトリとして使用するアプリケーションの CLSID に置き換えることができます。

## ステップ 3: プレゼンテーションを保存する

次に、ルート ディレクトリ ClsId を設定してプレゼンテーションを保存しましょう。

```java
//プレゼンテーションを保存する
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

このステップでは、プレゼンテーションを指定した場所に保存します。`resultPath`とともに`PptOptions`以前に作成しました。

## ステップ 4: クリーンアップ

忘れずに処分してください`Presentation`オブジェクトを使用して、割り当てられたリソースを解放します。

```java
if (pres != null) {
    pres.dispose();
}
```

## Java スライドのルート ディレクトリ ClsId の完全なソース コード

```java
//出力ファイル名
String resultPath = RunExamples.getOutPath() + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//CLSID を「Microsoft Powerpoint.Show.8」に設定します。
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	//プレゼンテーションを保存する
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## 結論

Aspose.Slides for Java でルート ディレクトリ ClsId が正常に設定されました。これにより、プレゼンテーション内でハイパーリンクがアクティブになったときにルート ディレクトリとして使用されるアプリケーションを指定できます。特定の要件に応じて CLSID をカスタマイズできます。

## よくある質問

### 特定のアプリケーションの CLSID を見つけるにはどうすればよいですか?

特定のアプリケーションの CLSID を見つけるには、アプリケーションの開発者が提供するドキュメントまたはリソースを参照できます。 CLSID は COM オブジェクトに割り当てられる一意の識別子であり、通常は各アプリケーションに固有です。

### ルート ディレクトリにカスタム CLSID を設定できますか?

はい、ルート ディレクトリにカスタム CLSID を設定するには、次のコマンドを使用して目的の CLSID 値を指定します。`setRootDirectoryClsid`コード例に示すように、メソッド。これにより、プレゼンテーション内でハイパーリンクがアクティブになっているときに、特定のアプリケーションをルート ディレクトリとして使用できます。

### ルート ディレクトリの ClsId を設定しないとどうなりますか?

ルート ディレクトリ ClsId を設定しない場合、デフォルトの動作は、プレゼンテーションを開くために使用されるビューアまたはアプリケーションによって異なります。ハイパーリンクがアクティブ化されると、独自のデフォルト アプリケーションをルート ディレクトリとして使用する場合があります。

### 個々のハイパーリンクのルート ディレクトリの ClsId を変更できますか?

いいえ、ルート ディレクトリ ClsId は通常、プレゼンテーション レベルで設定され、プレゼンテーション内のすべてのハイパーリンクに適用されます。個々のハイパーリンクに異なるアプリケーションを指定する必要がある場合は、コード内でそれらのハイパーリンクを個別に処理する必要がある場合があります。

### 使用できる CLSID に制限はありますか?

使用できる CLSID は通常、システムにインストールされているアプリケーションによって決まります。ハイパーリンクを処理できる有効なアプリケーションに対応する CLSID を使用する必要があります。無効な CLSID を使用すると、予期しない動作が発生する可能性があることに注意してください。