---
"description": "この包括的なステップバイステップのチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint の図形に 3D 回転効果を適用する方法を学習します。"
"linktitle": "PowerPointの図形に3D回転効果を適用する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "PowerPointの図形に3D回転効果を適用する"
"url": "/ja/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPointの図形に3D回転効果を適用する

## 導入
PowerPointプレゼンテーションをワンランクアップさせる準備はできていますか？3D回転効果を追加することで、スライドをよりダイナミックで魅力的なものにすることができます。経験豊富な開発者の方にも、初心者の方にも、このステップバイステップのチュートリアルでは、Aspose.Slides for Javaを使ってPowerPointの図形に3D回転効果を適用する方法をご紹介します。さあ、始めましょう！
## 前提条件
始める前に、以下のものが用意されていることを確認してください。
1. Java開発キット（JDK）：システムにJDKがインストールされていることを確認してください。JDKは以下からダウンロードできます。 [Oracleのウェブサイト](https://www。oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java: Aspose.Slides for Javaの最新バージョンを以下のサイトからダウンロードしてください。 [ダウンロードリンク](https://releases。aspose.com/slides/java/).
3. 統合開発環境 (IDE): コーディングには IntelliJ IDEA や Eclipse などの IDE を使用します。
4. 有効な免許証：免許証をお持ちでない場合は、 [一時ライセンス](https://purchase.aspose.com/temporary-license/) 機能を試してみましょう。
## パッケージのインポート
まず、Javaプロジェクトに必要なパッケージをインポートしましょう。これらのインポートは、Aspose.Slidesでプレゼンテーションや図形を扱うのに役立ちます。
```java
import com.aspose.slides.*;

```
## ステップ1: プロジェクトの設定
コードに進む前に、プロジェクト環境を設定してください。プロジェクトの依存関係にAspose.Slides for Javaが追加されていることを確認してください。
Aspose.Slides をプロジェクトに追加します。
1. Aspose.Slides JARファイルを以下からダウンロードします。 [ダウンロードページ](https://releases。aspose.com/slides/java/).
2. これらの JAR ファイルをプロジェクトのビルド パスに追加します。
## ステップ2: 新しいPowerPointプレゼンテーションを作成する
この手順では、新しい PowerPoint プレゼンテーションを作成します。
```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
// プレゼンテーションクラスのインスタンスを作成する
Presentation pres = new Presentation();
```
このコード スニペットは、図形を追加する新しいプレゼンテーション オブジェクトを初期化します。
## ステップ3: 長方形を追加する
次に、最初のスライドに長方形を追加しましょう。
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
このコードは、最初のスライドの指定された位置とサイズに長方形を追加します。
## ステップ4: 長方形に3D回転を適用する
ここで、長方形に 3D 回転効果を適用してみましょう。
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
ここでは、深度、カメラの回転角度、カメラの種類、照明の種類を設定して、長方形に 3D の外観を与えます。
## ステップ5: 線図形を追加する
スライドに別の図形、今度は線を追加しましょう。
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
このコードはスライド上に線の形状を配置します。
## ステップ6: 線に3D回転を適用する
最後に、線の形状に 3D 回転効果を適用します。
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
長方形と同様に、線の形状の 3D プロパティを設定します。
## ステップ7: プレゼンテーションを保存する
図形を追加して構成したら、プレゼンテーションを保存します。
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
このコードは、指定されたファイル名で、希望の形式でプレゼンテーションを保存します。
## 結論
おめでとうございます！Aspose.Slides for Javaを使用して、PowerPointプレゼンテーションの図形に3D回転効果を適用できました。これらの手順に従うことで、視覚的に魅力的でダイナミックなプレゼンテーションを作成できます。さらにカスタマイズしたり、より高度な機能を使用したりするには、 [Aspose.Slides ドキュメント](https://reference。aspose.com/slides/java/).
## よくある質問
### Aspose.Slides for Java とは何ですか?
Aspose.Slides for Java は、PowerPoint プレゼンテーションをプログラムで作成、変更、操作するための強力な API です。
### Aspose.Slides for Java を無料で試すことはできますか?
はい、 [無料トライアル](https://releases.aspose.com/) または [一時ライセンス](https://purchase.aspose.com/temporary-license/) 機能をテストします。
### Aspose.Slides で 3D 効果を追加できる図形の種類は何ですか?
長方形、線、楕円、カスタム図形などのさまざまな図形に 3D 効果を追加できます。
### Aspose.Slides for Java のサポートを受けるにはどうすればよいですか?
訪問することができます [サポートフォーラム](https://forum.aspose.com/c/slides/11) サポートや問題についての話し合いのため。
### Aspose.Slides for Java を商用プロジェクトで使用できますか?
はい、ただしライセンスを購入する必要があります。 [購入ページ](https://purchase。aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}