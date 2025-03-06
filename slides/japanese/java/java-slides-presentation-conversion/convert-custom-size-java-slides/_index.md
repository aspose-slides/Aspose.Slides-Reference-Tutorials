---
title: Java スライドでカスタム サイズに変換する
linktitle: Java スライドでカスタム サイズに変換する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションをカスタム サイズの TIFF 画像に変換する方法を学びます。開発者向けのコード例を含むステップ バイ ステップ ガイド。
weight: 31
url: /ja/java/presentation-conversion/convert-custom-size-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java スライドでカスタム サイズに変換する方法の紹介

この記事では、Aspose.Slides for Java API を使用して、PowerPoint プレゼンテーションをカスタム サイズの TIFF 画像に変換する方法について説明します。Aspose.Slides for Java は、開発者がプログラムで PowerPoint ファイルを操作できるようにする強力なライブラリです。このタスクを実行するために必要な Java コードを段階的に説明します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Java開発キット（JDK）がインストールされている
- Aspose.Slides for Java ライブラリ

 Aspose.Slides for Java ライブラリは、次の Web サイトからダウンロードできます。[Aspose.Slides for Java をダウンロード](https://releases.aspose.com/slides/java/)

## ステップ1: Aspose.Slidesライブラリをインポートする

まず、Aspose.Slides ライブラリを Java プロジェクトにインポートする必要があります。手順は次のとおりです。

```java
//必要なインポート文を追加する
import com.aspose.slides.*;
```

## ステップ2: PowerPointプレゼンテーションを読み込む

次に、TIFF画像に変換するPowerPointプレゼンテーションを読み込む必要があります。`"Your Document Directory"`プレゼンテーション ファイルへの実際のパスを入力します。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーションファイルを表すプレゼンテーションオブジェクトをインスタンス化する
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## ステップ3: TIFF変換オプションを設定する

次に、TIFF 変換のオプションを設定します。圧縮タイプ、DPI (インチあたりのドット数)、画像サイズ、注釈の位置を指定します。これらのオプションは、必要に応じてカスタマイズできます。

```java
// TiffOptionsクラスをインスタンス化する
TiffOptions opts = new TiffOptions();

//圧縮タイプの設定
opts.setCompressionType(TiffCompressionTypes.Default);

//画像DPIの設定
opts.setDpiX(200);
opts.setDpiY(100);

//画像サイズの設定
opts.setImageSize(new Dimension(1728, 1078));

//音符の位置を設定する
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## ステップ4: TIFFとして保存

すべてのオプションが設定されたら、指定した設定でプレゼンテーションを TIFF 画像として保存できるようになります。

```java
//指定した画像サイズでプレゼンテーションをTIFFに保存します
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Java スライドでカスタム サイズに変換するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションファイルを表すプレゼンテーションオブジェクトをインスタンス化する
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// TiffOptionsクラスをインスタンス化する
	TiffOptions opts = new TiffOptions();
	//圧縮タイプの設定
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	//圧縮タイプ
	//デフォルト - デフォルトの圧縮方式 (LZW) を指定します。
	//なし - 圧縮を指定しません。
	// CCITT3
	// CCITT4
	//翻訳
	//RLE
	//深さは圧縮タイプによって異なり、手動で設定することはできません。
	//解像度の単位は常に「2」（1インチあたりのドット数）です。
	//画像DPIの設定
	opts.setDpiX(200);
	opts.setDpiY(100);
	//画像サイズの設定
	opts.setImageSize(new Dimension(1728, 1078));
	//指定した画像サイズでプレゼンテーションをTIFFに保存します
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

おめでとうございます! Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションをカスタム サイズの TIFF 画像に正常に変換できました。これは、さまざまな目的でプレゼンテーションから高品質の画像を生成する必要がある場合に役立つ機能です。

## よくある質問

### TIFF 画像の圧縮タイプを変更するにはどうすればよいですか?

圧縮タイプを変更するには、`setCompressionType`方法`TiffOptions`クラス。デフォルト、なし、CCITT3、CCITT4、LZW、RLE など、さまざまな圧縮タイプが利用可能です。

### TIFF 画像の DPI (インチあたりのドット数) を調整できますか?

はい、DPIを調整できます。`setDpiX`そして`setDpiY`方法`TiffOptions`クラス。必要な値を設定するだけで、画像の解像度を制御できます。

### TIFF 画像内のメモの位置に使用できるオプションは何ですか?

 TIFF画像内のノートの位置は、`setNotesPosition` BottomFull、BottomTruncated、SlideOnly などのオプションがあるメソッド。ニーズに最適なものを選択してください。

### TIFF 変換時にカスタム画像サイズを指定することは可能ですか?

もちろんです！カスタム画像サイズを設定するには、`setImageSize`方法`TiffOptions`クラス。出力画像に必要な寸法 (幅と高さ) を指定します。

### Aspose.Slides for Java の詳細情報はどこで入手できますか?

 Aspose.Slides for Java の詳細なドキュメントと追加情報については、次のドキュメントをご覧ください。[Aspose.Slides for Java API リファレンス](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
