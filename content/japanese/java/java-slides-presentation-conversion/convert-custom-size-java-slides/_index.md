---
title: Java スライドのカスタム サイズで変換する
linktitle: Java スライドのカスタム サイズで変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションをカスタム サイズの TIFF 画像に変換する方法を学びます。開発者向けのコード例を含むステップバイステップのガイド。
type: docs
weight: 31
url: /ja/java/presentation-conversion/convert-custom-size-java-slides/
---

## Java スライドのカスタム サイズでの変換の概要

この記事では、Aspose.Slides for Java API を使用して、PowerPoint プレゼンテーションをカスタム サイズの TIFF 画像に変換する方法を説明します。 Aspose.Slides for Java は、開発者がプログラムで PowerPoint ファイルを操作できるようにする強力なライブラリです。段階的に説明し、このタスクを実行するために必要な Java コードを提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Java 開発キット (JDK) がインストールされている
- Java ライブラリ用の Aspose.Slides

 Aspose.Slides for Java ライブラリは、次の Web サイトからダウンロードできます。[Java 用 Aspose.Slides をダウンロード](https://releases.aspose.com/slides/java/)

## ステップ 1: Aspose.Slides ライブラリをインポートする

まず、Aspose.Slides ライブラリを Java プロジェクトにインポートする必要があります。その方法は次のとおりです。

```java
//必要な import ステートメントを追加します
import com.aspose.slides.*;
```

## ステップ 2: PowerPoint プレゼンテーションをロードする

次に、TIFF イメージに変換する PowerPoint プレゼンテーションをロードする必要があります。交換する`"Your Document Directory"`プレゼンテーション ファイルへの実際のパスを含めます。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーション ファイルを表すプレゼンテーション オブジェクトをインスタンス化します。
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## ステップ 3: TIFF 変換オプションを設定する

次に、TIFF 変換のオプションを設定しましょう。圧縮タイプ、DPI (1 インチあたりのドット数)、画像サイズ、メモの位置を指定します。これらのオプションは要件に応じてカスタマイズできます。

```java
// TiffOptions クラスをインスタンス化する
TiffOptions opts = new TiffOptions();

//圧縮タイプの設定
opts.setCompressionType(TiffCompressionTypes.Default);

//画像のDPIを設定する
opts.setDpiX(200);
opts.setDpiY(100);

//画像サイズの設定
opts.setImageSize(new Dimension(1728, 1078));

//ノートの位置を設定する
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## ステップ 4: TIFF として保存

すべてのオプションを構成したら、指定した設定でプレゼンテーションを TIFF 画像として保存できるようになります。

```java
//プレゼンテーションを指定した画像サイズで TIFF に保存します
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Java スライドのカスタム サイズで変換するための完全なソース コード

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーション ファイルを表すプレゼンテーション オブジェクトをインスタンス化します。
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// TiffOptions クラスをインスタンス化する
	TiffOptions opts = new TiffOptions();
	//圧縮タイプの設定
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	//圧縮の種類
	//デフォルト - デフォルトの圧縮スキーム (LZW) を指定します。
	//なし - 圧縮なしを指定します。
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	//深さは圧縮タイプによって異なり、手動で設定することはできません。
	//解像度の単位は常に「2」（ドット/インチ）と等しくなります。
	//画像のDPIを設定する
	opts.setDpiX(200);
	opts.setDpiY(100);
	//画像サイズの設定
	opts.setImageSize(new Dimension(1728, 1078));
	//プレゼンテーションを指定した画像サイズで TIFF に保存します
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

おめでとう！ Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションをカスタム サイズの TIFF 画像に正常に変換しました。これは、さまざまな目的でプレゼンテーションから高品質の画像を生成する必要がある場合に役立つ機能です。

## よくある質問

### TIFF 画像の圧縮タイプを変更するにはどうすればよいですか?

圧縮タイプを変更するには、`setCompressionType`のメソッド`TiffOptions`クラス。デフォルト、なし、CCITT3、CCITT4、LZW、RLE など、さまざまな圧縮タイプを使用できます。

### TIFF 画像の DPI (1 インチあたりのドット数) を調整できますか?

はい、次を使用して DPI を調整できます。`setDpiX`そして`setDpiY`のメソッド`TiffOptions`クラス。希望の値を設定するだけで画像の解像度を制御できます。

### TIFF 画像内のノートの位置に使用できるオプションは何ですか?

 TIFF 画像内のノートの位置は、`setNotesPosition` BottomFull、BottomTruncated、SlideOnly などのオプションを備えたメソッド。ニーズに最適なものをお選びください。

### TIFF 変換時にカスタム画像サイズを指定することはできますか?

絶対に！カスタム画像サイズを設定するには、`setImageSize`のメソッド`TiffOptions`クラス。出力画像に必要な寸法 (幅と高さ) を指定します。

### Aspose.Slides for Java に関する詳細情報はどこで入手できますか?

 Aspose.Slides for Java の詳細なドキュメントと追加情報については、次のドキュメントを参照してください。[Aspose.Slides for Java API リファレンス](https://reference.aspose.com/slides/java/).