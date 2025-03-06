---
title: Java を使用して PowerPoint で部分四角形を取得する
linktitle: Java を使用して PowerPoint で部分四角形を取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: この詳細なステップバイステップのチュートリアルで、Aspose.Slides for Java を使用して PowerPoint で部分四角形を取得する方法を学びます。Java 開発者に最適です。
type: docs
weight: 12
url: /ja/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---
## 導入
Aspose.Slides for Java を使用すると、Java で動的なプレゼンテーションを簡単に作成できます。このチュートリアルでは、Aspose.Slides を使用して PowerPoint で部分四角形を取得する方法について詳しく説明します。環境の設定からコードの詳細な説明まで、すべてを網羅します。それでは、始めましょう。
## 前提条件
コードに進む前に、スムーズに理解するために必要なものがすべて揃っていることを確認しましょう。
1. Java 開発キット (JDK): マシンに JDK 8 以上がインストールされていることを確認してください。
2.  Aspose.Slides for Java: 最新バージョンをダウンロード[ここ](https://releases.aspose.com/slides/java/).
3. 統合開発環境 (IDE): Eclipse、IntelliJ IDEA、または任意の他の Java IDE。
4. Java の基礎知識: Java プログラミングの理解が必須です。
## パッケージのインポート
まず最初に、必要なパッケージをインポートしましょう。これには、タスクを効率的に処理するための Aspose.Slides やその他のパッケージが含まれます。
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## ステップ1: プレゼンテーションの設定
最初のステップは、新しいプレゼンテーションを作成することです。これが作業用のキャンバスになります。
```java
Presentation pres = new Presentation();
```
## ステップ2: テーブルの作成
次に、プレゼンテーションの最初のスライドに表を追加しましょう。この表には、テキストを追加するセルが含まれます。
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## ステップ3: セルに段落を追加する
次に、段落を作成し、表内の特定のセルに追加します。これには、既存のテキストをクリアしてから、新しい段落を追加することが含まれます。
```java
//段落を作成する
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
//表のセルにテキストを追加する
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## ステップ4: オートシェイプにテキストフレームを追加する
プレゼンテーションをよりダイナミックにするために、オートシェイプにテキスト フレームを追加し、その配置を設定します。
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## ステップ5: 座標の計算
表のセルの左上隅の座標を取得する必要があります。これにより、図形を正確に配置できるようになります。
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## ステップ6: 段落と部分にフレームを追加する
使用方法`IParagraph.getRect()`そして`IPortion.getRect()`メソッドを使用すると、段落や部分にフレームを追加できます。これには、段落や部分を反復処理し、その周りに図形を作成し、外観をカスタマイズすることが含まれます。
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## ステップ 7: オートシェイプ段落にフレームを追加する
同様に、オートシェイプの段落にフレームを追加して、プレゼンテーションの視覚的な魅力を高めます。
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## ステップ8: プレゼンテーションを保存する
最後に、プレゼンテーションを指定したパスに保存します。
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## ステップ9: クリーンアップ
リソースを解放するためにプレゼンテーション オブジェクトを破棄することをお勧めします。
```java
if (pres != null) pres.dispose();
```
## 結論
おめでとうございます! Aspose.Slides for Java を使用して PowerPoint で部分四角形を取得する方法を学習しました。この強力なライブラリは、動的で視覚的に魅力的なプレゼンテーションをプログラムで作成するための可能性の世界を開きます。Aspose.Slides をさらに深く理解し、プレゼンテーションをさらに強化するためのその他の機能を調べてください。
## よくある質問
### Aspose.Slides for Java とは何ですか?
Aspose.Slides for Java は、開発者がプログラムで PowerPoint プレゼンテーションを作成、変更、操作できるようにする強力なライブラリです。
### Aspose.Slides for Java を商用プロジェクトで使用できますか?
はい、Aspose.Slides for Javaは商用プロジェクトでも使用できます。ライセンスは以下から購入できます。[ここ](https://purchase.aspose.com/buy).
### Aspose.Slides for Java の無料試用版はありますか?
はい、無料トライアルはここからダウンロードできます。[ここ](https://releases.aspose.com/).
### Aspose.Slides for Java のドキュメントはどこにありますか?
ドキュメントは入手可能です[ここ](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java のサポートを受けるにはどうすればよいですか?
 Asposeフォーラムからサポートを受けることができます[ここ](https://forum.aspose.com/c/slides/11).