---
title: PowerPoint で Web ソースからビデオ フレームを追加する
linktitle: PowerPoint で Web ソースからビデオ フレームを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して Web ソースからビデオ フレームを追加し、PowerPoint プレゼンテーションを強化する方法を学習します。
type: docs
weight: 18
url: /ja/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---
## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して、YouTube などの Web ソースからビデオ フレームを PowerPoint プレゼンテーションに追加する方法を学びます。これらのステップ バイ ステップの指示に従うことで、魅力的なマルチメディア要素を組み込むことでプレゼンテーションを強化できます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Java プログラミングの基礎知識。
- システムに JDK (Java Development Kit) がインストールされています。
-  Aspose.Slides for Javaライブラリがダウンロードされ、Javaプロジェクトに追加されました。ダウンロードはこちらから行えます。[ここ](https://releases.aspose.com/slides/java/).
- Web ソース (YouTube など) にアクセスするためのアクティブなインターネット接続。

## パッケージのインポート
まず、必要なパッケージを Java プロジェクトにインポートします。
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## ステップ1: PowerPointプレゼンテーションオブジェクトを作成する
PowerPoint プレゼンテーションを表す Presentation オブジェクトを初期化します。
```java
Presentation pres = new Presentation();
```
## ステップ2: ビデオフレームを追加する
次に、プレゼンテーションにビデオ フレームを追加しましょう。このフレームには、Web ソースからのビデオが含まれます。addVideoFrame メソッドを使用します。
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
「VIDEO_ID」を、埋め込みたい YouTube 動画の ID に置き換えます。
## ステップ3: ビデオ再生モードを設定する
ビデオ フレームの再生モードを設定します。この例では、自動に設定します。
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## ステップ4: サムネイルを読み込む
視覚的な魅力を高めるために、ビデオのサムネイルを読み込みます。この手順では、Web ソースからサムネイル画像を取得します。
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## ステップ5: プレゼンテーションを保存する
最後に、変更したプレゼンテーションを保存します。
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
「YOUR_DIRECTORY」を、プレゼンテーションを保存するディレクトリに置き換えます。

## 結論
おめでとうございます。Aspose.Slides for Java を使用して、PowerPoint に Web ソースからビデオ フレームを追加する方法を学習しました。ビデオなどのマルチメディア要素を組み込むと、プレゼンテーションのインパクトとエンゲージメントが大幅に向上します。
## よくある質問
### YouTube 以外のソースからビデオを追加できますか?
はい、埋め込み可能なリンクが提供されている限り、さまざまな Web ソースからビデオを追加できます。
### 埋め込みビデオを再生するにはインターネット接続が必要ですか?
はい、Web ソースからビデオをストリーミングするには、アクティブなインターネット接続が必要です。
### ビデオフレームの外観をカスタマイズできますか?
もちろんです! Aspose.Slides には、ビデオ フレームの外観と動作をカスタマイズするための幅広いオプションが用意されています。
### Aspose.Slides はすべてのバージョンの PowerPoint と互換性がありますか?
Aspose.Slides は幅広いバージョンの PowerPoint をサポートしており、さまざまなプラットフォーム間での互換性が確保されています。
### Aspose.Slides のその他のリソースやサポートはどこで見つかりますか?
訪問することができます[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)支援、ドキュメント、コミュニティ サポート。