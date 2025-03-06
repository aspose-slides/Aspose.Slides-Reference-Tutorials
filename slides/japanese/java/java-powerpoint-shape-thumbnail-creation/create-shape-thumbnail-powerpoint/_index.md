---
title: PowerPoint で図形のサムネイルを作成する
linktitle: PowerPoint で図形のサムネイルを作成する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションで図形のサムネイルを生成する方法を学びます。ステップバイステップのガイドが提供されます。
weight: 14
url: /ja/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションで図形のサムネイルを作成する方法について詳しく説明します。Aspose.Slides は、開発者がプログラムで PowerPoint ファイルを操作できるようにする強力なライブラリであり、図形のサムネイルの生成など、さまざまなタスクを自動化できます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Java プログラミングの基礎知識。
- Java 開発キット (JDK) がシステムにインストールされています。
-  Aspose.Slides for Javaライブラリがダウンロードされ、プロジェクトにセットアップされます。ダウンロードはここから行えます。[ここ](https://releases.aspose.com/slides/java/).

## パッケージのインポート
まず、Aspose.Slides の機能を利用するには、Java コードに必要なパッケージをインポートする必要があります。Java ファイルの先頭に次のインポート ステートメントを含めます。
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ステップ1: ドキュメントディレクトリを定義する
```java
String dataDir = "Your Document Directory";
```
交換する`"Your Document Directory"` PowerPoint ファイルを含むディレクトリへのパスを入力します。
## ステップ2: プレゼンテーションオブジェクトのインスタンス化
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
新しいインスタンスを作成する`Presentation`クラスに、PowerPoint ファイルへのパスをパラメーターとして渡します。
## ステップ3: シェイプサムネイルを生成する
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
プレゼンテーションの最初のスライドから目的の図形のサムネイルを取得します。
## ステップ4: サムネイル画像を保存する
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
生成されたサムネイル画像を、指定されたファイル名で PNG 形式でディスクに保存します。

## 結論
結論として、このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションで図形のサムネイルを作成する方法を説明しました。ステップバイステップのガイドに従い、提供されているコード スニペットを利用することで、図形のサムネイルをプログラムで効率的に生成できます。

## よくある質問
### プレゼンテーション内の任意のスライド上の図形のサムネイルを作成できますか?
はい、スライドのインデックスを適切に調整することで、任意のスライド上の図形をターゲットにするようにコードを変更できます。
### Aspose.Slides はサムネイルを保存するために他の画像形式をサポートしていますか?
はい、PNG 以外にも、Aspose.Slides では JPEG、GIF、BMP などのさまざまな画像形式でのサムネイルの保存がサポートされています。
### Aspose.Slides は商用利用に適していますか?
はい、Aspose.Slidesは企業や組織向けに商用ライセンスを提供しています。ライセンスは以下から購入できます。[ここ](https://purchase.aspose.com/buy).
### 購入前に Aspose.Slides を試すことはできますか?
もちろんです！Aspose.Slidesの無料試用版は以下からダウンロードできます。[ここ](https://releases.aspose.com/)その機能と能力を評価するため。
### Aspose.Slides のサポートはどこで受けられますか?
 Aspose.Slidesに関してご質問やサポートが必要な場合は、[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)サポートのための。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
