---
title: Java スライドで XPS オプションを使用せずに変換する
linktitle: Java スライドで XPS オプションを使用せずに変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを XPS 形式に変換する方法を学びます。ソースコード付きのステップバイステップガイド。
type: docs
weight: 33
url: /ja/java/presentation-conversion/convert-without-xps-options-java-slides/
---

## Aspose.Slides for Java の XPS オプションを使用せずに PowerPoint を XPS に変換する

このチュートリアルでは、XPS オプションを指定せずに、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションを XPS (XML Paper Difference) ドキュメントに変換するプロセスを説明します。このタスクを達成するための段階的な手順と Java ソース コードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1.  Aspose.Slides for Java: Aspose.Slides for Java ライブラリが Java プロジェクトにインストールされ、構成されていることを確認します。からダウンロードできます。[Aspose.Slides for Java Web サイト](https://downloads.aspose.com/slides/java).

2. Java 開発環境: コンピュータ上に Java 開発環境がセットアップされている必要があります。

## ステップ 1: Aspose.Slides for Java をインポートする

Java プロジェクトで、Java ファイルの先頭に必要な Aspose.Slides for Java クラスをインポートします。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ステップ 2: PowerPoint プレゼンテーションをロードする

次に、XPS に変換する PowerPoint プレゼンテーションを読み込みます。交換する`"Your Document Directory"`PowerPoint プレゼンテーション ファイルへの実際のパスを置き換えます。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーション ファイルを表す Presentation オブジェクトをインスタンス化します。
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

必ず交換してください`"Convert_XPS.pptx"` PowerPoint ファイルの実際の名前を付けます。

## ステップ 3: XPS オプションを使用せずに XPS として保存する

Aspose.Slides for Java を使用すると、XPS オプションを指定せずに、ロードされたプレゼンテーションを XPS ドキュメントとして簡単に保存できます。その方法は次のとおりです。

```java
try {
    //プレゼンテーションを XPS ドキュメントに保存する
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

このコード ブロックは、プレゼンテーションを次の名前の XPS ドキュメントとして保存します。`"XPS_Output_Without_XPSOption_out.xps"`。必要に応じて出力ファイル名を変更できます。

## Java スライドで XPS オプションを使用しないで変換するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーション ファイルを表す Presentation オブジェクトをインスタンス化します。
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	//プレゼンテーションを XPS ドキュメントに保存する
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

このチュートリアルでは、Aspose.Slides for Java を使用して、XPS オプションを指定せずに PowerPoint プレゼンテーションを XPS ドキュメントに変換する方法を学習しました。 Aspose.Slides for Java が提供するオプションを検討することで、変換プロセスをさらにカスタマイズできます。より高度な機能と詳細なドキュメントについては、次のサイトを参照してください。[Aspose.Slides for Java ドキュメント](https://docs.aspose.com/slides/java/).

## よくある質問

### 変換中に XPS オプションを指定するにはどうすればよいですか?

 PowerPoint プレゼンテーションの変換中に XPS オプションを指定するには、`XpsOptions`クラスを作成し、画像圧縮やフォントの埋め込みなどのさまざまなプロパティを設定します。 XPS 変換に関する特定の要件がある場合は、「[Aspose.Slides for Java ドキュメント](https://docs.aspose.com/slides/java/)詳細については。

### 他の形式で保存するための追加オプションはありますか?

はい、Aspose.Slides for Java は、XPS 以外にも PDF、TIFF、HTML などのさまざまな出力形式を提供します。を変更することで、希望の出力形式を指定できます。`SaveFormat`を呼び出すときのパラメータ`save`方法。サポートされている形式の完全なリストについては、ドキュメントを参照してください。

### 変換プロセス中に例外を処理するにはどうすればよいですか?

例外処理を実装すると、変換プロセス中に発生する可能性のあるエラーを適切に処理できます。コードに示すように、`try`そして`finally`ブロックは、例外が発生した場合でもリソースが適切に破棄されるようにするために使用されます。