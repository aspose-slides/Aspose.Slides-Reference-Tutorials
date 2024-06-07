---
title: PowerPoint で OLE オブジェクト データを変更する
linktitle: PowerPoint で OLE オブジェクト データを変更する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint の OLE オブジェクト データを変更する方法を学びます。効率的で簡単な更新のためのステップ バイ ステップ ガイドです。
type: docs
weight: 14
url: /ja/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---
## 導入
PowerPoint プレゼンテーションの OLE オブジェクト データを変更することは、各スライドを手動で編集せずに埋め込みコンテンツを更新する必要がある場合に重要なタスクになります。この包括的なガイドでは、PowerPoint プレゼンテーションの処理用に設計された強力なライブラリである Aspose.Slides for Java を使用して、プロセスを順を追って説明します。熟練した開発者でも、初心者でも、このチュートリアルは役立ち、簡単に理解できます。
## 前提条件
コードに進む前に、開始するために必要なものがすべて揃っていることを確認しましょう。
1.  Java開発キット（JDK）：システムにJDKがインストールされていることを確認してください。ここからダウンロードできます。[Oracleのサイト](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java: 最新バージョンを以下からダウンロードしてください。[Aspose.Slides ダウンロード ページ](https://releases.aspose.com/slides/java/).
3. 統合開発環境 (IDE): IntelliJ IDEA、Eclipse、NetBeans などの任意の Java IDE を使用できます。
4.  Aspose.Cells for Java: OLEオブジェクト内の埋め込みデータを変更するために必要です。ダウンロードはこちら[Aspose.Cells ダウンロード ページ](https://releases.aspose.com/cells/java/).
5. プレゼンテーションファイル: OLEオブジェクトが埋め込まれたPowerPointファイルを用意します。このチュートリアルでは、次のように名前を付けます。`ChangeOLEObjectData.pptx`.
## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートしましょう。
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

それでは、プロセスをシンプルで管理しやすいステップに分解してみましょう。
## ステップ1: PowerPointプレゼンテーションを読み込む
まず、OLE オブジェクトを含む PowerPoint プレゼンテーションを読み込む必要があります。
```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## ステップ2: OLEオブジェクトを含むスライドにアクセスする
次に、OLE オブジェクトが埋め込まれているスライドを取得します。
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ステップ3: スライド内のOLEオブジェクトを見つける
スライド内の図形を反復処理して、OLE オブジェクトを見つけます。
```java
OleObjectFrame ole = null;
// Oleフレームのすべてのシェイプをトラバースする
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## ステップ4: OLEオブジェクトから埋め込みデータを抽出する
OLE オブジェクトが見つかった場合は、その埋め込まれたデータを抽出します。
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## ステップ 5: Aspose.Cells を使用して埋め込みデータを変更する
ここで、Aspose.Cells を使用して、埋め込まれたデータ (この場合は Excel ワークブック) を読み取って変更します。
```java
    Workbook wb = new Workbook(msln);
    //ワークブックデータを変更する
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## ステップ 6: 変更したデータを OLE オブジェクトに保存する
必要な変更を行った後、変更したブックを OLE オブジェクトに保存します。
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## ステップ7: 更新したプレゼンテーションを保存する
最後に、更新された PowerPoint プレゼンテーションを保存します。
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 結論
Aspose.Slides for Java を使用して PowerPoint プレゼンテーションの OLE オブジェクト データを更新するプロセスは、簡単な手順に分解すれば簡単です。このガイドでは、プレゼンテーションの読み込み、埋め込まれた OLE データへのアクセスと変更、更新されたプレゼンテーションの保存について説明しました。これらの手順に従うと、PowerPoint スライドに埋め込まれたコンテンツをプログラムで効率的に管理および更新できます。
## よくある質問
### PowerPoint の OLE オブジェクトとは何ですか?
OLE (オブジェクトのリンクと埋め込み) オブジェクトを使用すると、Excel スプレッドシートなどの他のアプリケーションのコンテンツを PowerPoint スライドに埋め込むことができます。
### Aspose.Slides を他のプログラミング言語で使用できますか?
はい、Aspose.Slides は .NET、Python、C を含む複数の言語をサポートしています。++.
### PowerPoint で OLE オブジェクトを変更するには Aspose.Cells が必要ですか?
はい、OLE オブジェクトが Excel スプレッドシートである場合は、それを変更するには Aspose.Cells が必要になります。
### Aspose.Slides の試用版はありますか?
はい、[無料トライアル](https://releases.aspose.com/) Aspose.Slides の機能をテストします。
### Aspose.Slides のドキュメントはどこにありますか?
詳細なドキュメントは[Aspose.Slides ドキュメント ページ](https://reference.aspose.com/slides/java/).