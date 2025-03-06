---
title: Java を使用してデフォルトの標準フォントで PowerPoint を保存する
linktitle: Java を使用してデフォルトの標準フォントで PowerPoint を保存する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、プログラムで PowerPoint プレゼンテーションを操作する方法を学びます。ステップバイステップのチュートリアルで Java PowerPoint の処理をマスターします。
type: docs
weight: 12
url: /ja/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---
## 導入
Java 開発の分野では、PowerPoint プレゼンテーションをプログラムで作成および操作することで、生産性とカスタマイズ オプションを大幅に向上できます。Aspose.Slides for Java は、開発者が PowerPoint ファイルを効率的に処理できるようにする強力なライブラリであり、単純な変更から複雑なプレゼンテーションまで、包括的な機能セットを提供します。
## 前提条件
Aspose.Slides for Java の使用を開始する前に、次の前提条件が設定されていることを確認してください。
1. Java 開発キット (JDK): Aspose.Slides for Java が正しく機能するには、JDK 1.8 以上が必要です。
2. Aspose.Slides for Java JAR: Aspose.Slides for Javaの最新バージョンをこちらからダウンロードしてください。[ここ](https://releases.aspose.com/slides/java/).
3. 統合開発環境 (IDE): IntelliJ IDEA、Eclipse、または任意の他の Java IDE を使用します。
4. Java の基本的な理解: Java プログラミング言語の基礎を理解している必要があります。

## パッケージのインポート
Aspose.Slides for Java の使用を開始するには、必要なパッケージをインポートします。
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
これにより、Aspose.Slides for Java によって提供されるすべてのクラスとメソッドにアクセスできるようになります。
## ステップ1: プロジェクトを設定する
まず、IDE で新しい Java プロジェクトを作成し、プロジェクトのビルド パスに Aspose.Slides for Java JAR ファイルを含めます。
## ステップ2: プレゼンテーションオブジェクトの初期化
インスタンス化する`Presentation`ローカル ディレクトリから既存の PowerPoint ファイル (.pptx) を読み込んでオブジェクトを作成します。
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
//プレゼンテーションを読み込む
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
交換する`"Your Document Directory"`そして`"Your Output Directory"`実際のファイルパスを入力します。
## ステップ3: デフォルトの標準フォントでプレゼンテーションを保存する
出力形式（HTMLおよびPDF）のデフォルトの標準フォントを指定します。`HtmlOptions`そして`PdfOptions`それぞれ。
```java
try {
    // HTML保存オプション
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    //PDF保存オプション
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
必ず交換してください`"Arial Black"`そして`"Lucida Console"`希望するデフォルトの標準フォントを使用します。

## 結論
これらの手順に従うことで、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションを効果的に操作する方法を学習しました。この機能により、タスクを自動化し、プレゼンテーションをカスタマイズし、高度な PowerPoint 処理機能を使用して Java アプリケーションを強化できます。
## よくある質問
### Aspose.Slides for Java は古いバージョンの JDK でも動作しますか?
Aspose.Slides for Java では、互換性のために JDK 1.8 以上が必要です。
### Aspose.Slides for Java の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスは以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java の詳細なドキュメントはどこで入手できますか?
包括的なドキュメントをご覧ください[ここ](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java にはコミュニティ サポートがありますか?
はい、コミュニティのサポートを受けることができます[ここ](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java を無料で試すことはできますか?
はい、無料試用版をダウンロードしてください[ここ](https://releases.aspose.com/).