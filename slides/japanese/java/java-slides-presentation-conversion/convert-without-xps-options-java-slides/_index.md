---
title: Java スライドで XPS オプションなしで変換する
linktitle: Java スライドで XPS オプションなしで変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを XPS 形式に変換する方法を学びます。ソース コード付きのステップ バイ ステップ ガイド。
type: docs
weight: 33
url: /ja/java/presentation-conversion/convert-without-xps-options-java-slides/
---

## はじめに Aspose.Slides for Java で XPS オプションを使用せずに PowerPoint を XPS に変換する

このチュートリアルでは、Aspose.Slides for Java を使用して、XPS オプションを指定せずに PowerPoint プレゼンテーションを XPS (XML Paper Specific) ドキュメントに変換するプロセスについて説明します。このタスクを実行するための手順と Java ソース コードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Slides for Java: JavaプロジェクトにAspose.Slides for Javaライブラリがインストールされ、設定されていることを確認してください。[Aspose.Slides for Java の Web サイト](https://downloads.aspose.com/slides/java).

2. Java 開発環境: コンピューターに Java 開発環境が設定されている必要があります。

## ステップ 1: Aspose.Slides for Java をインポートする

Java プロジェクトで、Java ファイルの先頭に必要な Aspose.Slides for Java クラスをインポートします。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ステップ2: PowerPointプレゼンテーションを読み込む

ここで、XPSに変換するPowerPointプレゼンテーションを読み込みます。`"Your Document Directory"` PowerPoint プレゼンテーション ファイルへの実際のパス:

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーションファイルを表すプレゼンテーションオブジェクトをインスタンス化する
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

必ず交換してください`"Convert_XPS.pptx"` PowerPoint ファイルの実際の名前を入力します。

## ステップ3: XPSオプションなしでXPSとして保存する

Aspose.Slides for Java を使用すると、XPS オプションを指定せずに、読み込んだプレゼンテーションを XPS ドキュメントとして簡単に保存できます。方法は次のとおりです。

```java
try {
    //プレゼンテーションをXPSドキュメントに保存する
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

このコードブロックは、プレゼンテーションをXPSドキュメントとして保存します。`"XPS_Output_Without_XPSOption_out.xps"`必要に応じて出力ファイル名を変更できます。

## Java スライドで XPS オプションなしで変換するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションファイルを表すプレゼンテーションオブジェクトをインスタンス化する
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	//プレゼンテーションをXPSドキュメントに保存する
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、XPS オプションを指定せずに PowerPoint プレゼンテーションを XPS ドキュメントに変換する方法を学習しました。Aspose.Slides for Java が提供するオプションを調べることで、変換プロセスをさらにカスタマイズできます。より高度な機能と詳細なドキュメントについては、[Aspose.Slides for Java ドキュメント](https://docs.aspose.com/slides/java/).

## よくある質問

### 変換中に XPS オプションを指定するにはどうすればよいですか?

 PowerPointプレゼンテーションを変換する際にXPSオプションを指定するには、`XpsOptions`クラスを作成し、画像圧縮やフォント埋め込みなどのさまざまなプロパティを設定します。XPS変換に特定の要件がある場合は、[Aspose.Slides for Java ドキュメント](https://docs.aspose.com/slides/java/)詳細については。

### 他の形式で保存するための追加オプションはありますか?

はい、Aspose.Slides for Javaは、XPS以外にもPDF、TIFF、HTMLなど様々な出力形式を提供しています。`SaveFormat`パラメータを呼び出すときに`save`メソッド。サポートされている形式の完全なリストについては、ドキュメントを参照してください。

### 変換プロセス中に例外を処理するにはどうすればよいですか?

変換プロセス中に発生する可能性のあるエラーを適切に処理するために、例外処理を実装することができます。コードに示されているように、`try`そして`finally`ブロックは、例外が発生した場合でも適切なリソースの処分を保証するために使用されます。