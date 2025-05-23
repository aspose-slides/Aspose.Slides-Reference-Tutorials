---
"date": "2025-04-17"
"description": "環境の設定やグラフの外観の調整など、Aspose.Slides を使用して Java プレゼンテーションでドーナツ グラフを作成およびカスタマイズする方法を学習します。"
"title": "Aspose.Slides for Presentations を使用して Java でドーナツ チャートを作成する方法"
"url": "/ja/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Presentations を使用して Java でドーナツ チャートを作成する方法

## 導入
視覚的に魅力的なプレゼンテーションを作成することは、情報を効果的に伝えるために不可欠です。グラフは、データの分布をより深く理解するための重要な要素です。このチュートリアルでは、Aspose.Slides for Javaを使用してカスタマイズ可能なドーナツグラフを作成する方法を説明します。穴のサイズや位置など、豊富なカスタマイズオプションを備えたグラフを簡単に作成できます。

**学習内容:**
- Aspose.Slides for Java のセットアップ
- プレゼンテーションでドーナツグラフを作成および構成する
- 穴のサイズなどのチャートの美観を調整する
- 新しいグラフを含むプレゼンテーションを保存する

まずは環境設定から始めましょう!

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

### 必要なライブラリとバージョン
Aspose.Slides for Java を使用するには、Maven または Gradle 経由でプロジェクトに含めるか、直接ダウンロードします。

#### 環境設定要件
- 動作する Java 開発キット (JDK)、できればバージョン 8 以上。
- IntelliJ IDEA や Eclipse のような統合開発環境 (IDE)。

### 知識の前提条件
Javaと基本的なプログラミング概念に精通していると有利です。MavenまたはGradleの基礎知識があれば、セットアッププロセスを効率化できます。

## Aspose.Slides for Java のセットアップ
Aspose.Slides をプロジェクトに組み込むには、いくつかの方法があります。

**メイヴン:**
この依存関係を `pom.xml` ファイル：
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**グレード:**
これをあなたの `build.gradle` ファイル：
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接ダウンロード:**
または、最新バージョンを以下からダウンロードしてください。 [Aspose.Slides for Java リリース](https://releases。aspose.com/slides/java/).

### ライセンス取得
- **無料トライアル**まず試用版をダウンロードして、Aspose.Slides の機能を調べてください。
- **一時ライセンス**制限なしで拡張機能を利用するための一時ライセンスを取得します。
- **購入**継続して使用する場合はライセンスを購入する必要があります。

ライブラリをセットアップし、環境の準備ができたら、ドーナツ チャートの実装に進みましょう。

## 実装ガイド

### ドーナツグラフを作成する
Aspose.Slides を使ってカスタマイズされたドーナツグラフを含むプレゼンテーションを作成するには、いくつかの手順が必要です。わかりやすくするために、以下に手順を分けて説明します。

#### プレゼンテーションオブジェクトの初期化
まず、 `Presentation` PowerPoint ドキュメントを表すクラスです。
```java
// PPTXドキュメントを表すプレゼンテーションクラスのインスタンスを作成する
Presentation presentation = new Presentation();
```
この手順では、スライドやグラフを追加できるプレゼンテーションを初期化します。

#### スライドにドーナツグラフを追加する
最初のスライドにアクセスし (または必要に応じて作成し)、ドーナツ グラフを追加します。
```java
// プレゼンテーションの最初のスライドにアクセスする
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // 位置は(50, 50)、サイズは400x400
```
このコードスニペットは、最初のスライドにドーナツグラフを追加します。パラメータは、スライド上の位置とサイズを定義します。

#### ドーナツの穴のサイズを設定する
ドーナツ グラフにユニークな外観を与えるには、穴のサイズを調整します。
```java
// ドーナツグラフの穴のサイズを90%に設定する
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
ここでは穴のサイズを90%に設定し、ほぼ真円になるようにしています。デザインのニーズに合わせてこの値を調整してください。

#### プレゼンテーションを保存
グラフを設定したら、プレゼンテーションを保存します。
```java
// プレゼンテーションをPPTX形式で指定されたディレクトリに保存します。
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
この行は変更を次のファイルに書き込みます `DoughnutHoleSize_out.pptx` 指定されたディレクトリに保存されます。

#### クリーンアップリソース
最後に、プレゼンテーション オブジェクトを破棄します。
```java
// プレゼンテーションオブジェクトを破棄してリソースを解放する
if (presentation != null) presentation.dispose();
```
このステップは、リソース管理とメモリ リークの回避に不可欠です。

### 実用的な応用
ドーナツグラフは多用途に使えます。ドーナツグラフが活躍する場面をいくつかご紹介します。
1. **予算配分**予算が部門間でどのように配分されているかを表示します。
2. **調査結果**複数選択の回答を含む質問への回答を視覚化します。
3. **ウェブサイトのトラフィックソース**さまざまなソースからのトラフィックの割合を表示します。

### パフォーマンスに関する考慮事項
Aspose.Slides を使用する場合は、最適なパフォーマンスを得るために次のヒントを考慮してください。
- 不要になったオブジェクトを破棄してメモリを管理します。
- メモリ使用量を最小限に抑えるには、大規模なデータ セットにストリームを使用します。
- 可能な場合はインスタンスを再利用してコードを最適化します。

## 結論
おめでとうございます！Aspose.Slides for Javaを使ってドーナツグラフを作成およびカスタマイズする方法を学びました。このチュートリアルでは、ライブラリの設定、プレゼンテーションへのグラフの追加、そして外観の調整について説明しました。

Aspose.Slides の機能をさらに詳しく調べるには、他の種類のグラフを試したり、プレゼンテーション自動化機能を詳しく調べたりすることを検討してください。

**次のステップ:**
- さまざまなチャート構成を試してください。
- より高度な機能については、Aspose.Slides の追加のドキュメントを参照してください。

独自のドーナツ グラフを作成する準備はできましたか? 次のプロジェクトでこのソリューションを実装してみてください。

## FAQセクション
1. **ドーナツ グラフのセグメントの色を調整できますか?**
   はい、セグメントの色をカスタマイズできます。 `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` 塗りつぶしの種類を設定し、希望の色を指定します。

2. **グラフにデータ ラベルを追加するにはどうすればよいですか?**
   使用 `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` プログラムでデータ ポイントとラベルを追加する同様の方法もあります。

3. **PPTX以外の形式でチャートを保存することは可能ですか?**
   もちろんです! Aspose.Slides は、PDF、XPS、PNG や JPEG などの画像形式など、さまざまな出力形式をサポートしています。

4. **プレゼンテーションの保存中にエラーが発生した場合はどうなりますか?**
   ディレクトリパスが正しいこと、および指定された場所への書き込み権限があることを確認してください。使用しているAspose.Slidesのバージョンが、保存しようとしているファイル形式をサポートしているかどうかを確認してください。

5. **ライブ データ ソースを使用してグラフの更新を自動化できますか?**
   はい、API またはデータベースを Java アプリケーションに統合することで、必要に応じてグラフ データを動的に更新し、プレゼンテーションを更新できます。

## リソース
- **ドキュメント**詳細なAPIリファレンスについては、 [Aspose.Slides for Java](https://reference。aspose.com/slides/java/).
- **ダウンロード**最新のライブラリバージョンを入手する [Aspose.Slides リリース](https://releases。aspose.com/slides/java/).
- **購入**フルアクセスをご希望の場合は、ライセンスをご購入ください。 [Aspose 購入](https://purchase。aspose.com/buy).
- **無料トライアル**ダウンロード ページで入手可能な無料試用版で Aspose.Slides を試してみてください。
- **一時ライセンス**制限なしで拡張テストを実行するための一時ライセンスを取得します。
- **サポート**ご質問がありましたら、 [Asposeフォーラム](https://forum.aspose.com/c/slides/11) 援助をお願いします。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}