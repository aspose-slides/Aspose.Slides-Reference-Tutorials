---
title: PowerPoint に相対スケールの高さの画像フレームを追加する
linktitle: PowerPoint に相対スケールの高さの画像フレームを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint プレゼンテーションに相対スケールの高さの画像フレームを追加し、視覚的なコンテンツを強化する方法を学習します。
weight: 15
url: /ja/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションに相対スケールの高さを持つ画像フレームを追加する方法を学習します。
## 前提条件
始める前に、次のものがあることを確認してください。
1. Java 開発キット (JDK) がシステムにインストールされています。
2. Aspose.Slides for Java ライブラリがダウンロードされ、Java プロジェクトに追加されました。

## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ステップ1: プロジェクトを設定する
まず、プロジェクト用のディレクトリが設定されており、Java 環境が適切に構成されていることを確認します。
## ステップ2: プレゼンテーションオブジェクトのインスタンス化
Aspose.Slides を使用して新しいプレゼンテーション オブジェクトを作成します。
```java
Presentation presentation = new Presentation();
```
## ステップ3: 追加する画像を読み込む
プレゼンテーションに追加する画像を読み込みます。
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## ステップ4: スライドに画像フレームを追加する
プレゼンテーションのスライドに画像フレームを追加します。
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## ステップ5: 相対スケールの幅と高さを設定する
画像フレームの相対スケールの幅と高さを設定します。
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## ステップ6: プレゼンテーションを保存する
画像フレームを追加したプレゼンテーションを保存します。
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## 結論
以下の手順に従うと、Aspose.Slides for Java を使用して、PowerPoint プレゼンテーションに相対スケールの高さを持つ画像フレームを簡単に追加できます。さまざまなスケール値を試して、画像の希望する外観を実現してください。

## よくある質問
### この方法を使用して、1 つのスライドに複数の画像フレームを追加できますか?
はい、各画像に対してこの手順を繰り返すことで、スライドに複数の画像フレームを追加できます。
### Aspose.Slides for Java はすべてのバージョンの PowerPoint と互換性がありますか?
Aspose.Slides for Java はさまざまなバージョンの PowerPoint と互換性があり、プレゼンテーションを柔軟に作成できます。
### 写真フレームの位置やサイズをカスタマイズできますか？
もちろん、位置とサイズのパラメータを調整できます。`addPictureFrame`要件に合った方法。
### Aspose.Slides for Java は JPEG 以外の画像形式もサポートしていますか?
はい、Aspose.Slides for Java は、PNG、GIF、BMP など、さまざまな画像形式をサポートしています。
### Aspose.Slides ユーザー向けのコミュニティ フォーラムまたはサポート チャネルはありますか?
はい、ライブラリに関する質問、ディスカッション、サポートについては、Aspose.Slides フォーラムをご覧ください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
