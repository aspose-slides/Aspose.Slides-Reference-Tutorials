---
title: スケール係数サムネイルを作成
linktitle: スケール係数サムネイルを作成
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、Java でスケール係数サムネイルを作成する方法を学びます。ステップバイステップの手順を説明したわかりやすいガイドです。
weight: 12
url: /ja/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# スケール係数サムネイルを作成

## 導入
このチュートリアルでは、Aspose.Slides for Java を使用してスケール係数サムネイルを作成する手順を説明します。ステップバイステップの手順に従って、希望する結果を実現してください。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Java 開発キット (JDK) がシステムにインストールされています。
- Aspose.Slides for Java ライブラリがダウンロードされ、Java プロジェクトに設定されます。
- Java プログラミング言語の基本的な理解。

## パッケージのインポート
まず、Java コードで Aspose.Slides を操作するために必要なパッケージをインポートします。 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

ここで、提供された例を複数のステップに分解してみましょう。
## ステップ1: ドキュメントディレクトリを設定する
PowerPoint プレゼンテーション ファイルが保存されているドキュメント ディレクトリへのパスを定義します。
```java
String dataDir = "Your Document Directory";
```
交換する`"Your Document Directory"`実際のドキュメント ディレクトリへのパスを入力します。
## ステップ2: プレゼンテーションオブジェクトのインスタンスを作成する
PowerPoint プレゼンテーション ファイルを表す Presentation クラスのインスタンスを作成します。
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
必ず交換してください`"HelloWorld.pptx"`PowerPoint プレゼンテーション ファイルの名前を入力します。
## ステップ3: フルスケール画像を作成する
プレゼンテーションから目的のスライドのフルスケール画像を生成します。
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
このコードは、プレゼンテーションの最初のスライドにある最初の図形のサムネイルを取得します。
## ステップ4: 画像を保存する
生成された画像を PNG 形式でディスクに保存します。
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
必ず交換してください`"Scaling Factor Thumbnail_out.png"`希望する出力ファイル名を指定します。

## 結論
結論として、Aspose.Slides for Java を使用してスケール係数サムネイルを正常に作成できました。提供されている手順に従うことで、この機能を Java アプリケーションに簡単に統合できます。
## よくある質問
### Aspose.Slides for Java はどの Java IDE でも使用できますか?
はい、Aspose.Slides for Java は、Eclipse、IntelliJ IDEA、NetBeans などの任意の Java 統合開発環境 (IDE) で使用できます。
### Aspose.Slides for Java の無料試用版はありますか?
はい、Aspose.Slides for Javaの無料トライアルをご利用いただくには、[Webサイト](https://releases.aspose.com/).
### Aspose.Slides for Java のサポートはどこで見つかりますか?
 Aspose.Slides for Javaのサポートについては、[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java を購入するにはどうすればよいですか?
 Aspose.Slides for Javaは以下から購入できます。[購入ページ](https://purchase.aspose.com/buy).
### Aspose.Slides for Java を使用するには一時ライセンスが必要ですか?
はい、臨時免許証は[一時ライセンスページ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
