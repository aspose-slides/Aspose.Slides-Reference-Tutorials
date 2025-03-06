---
title: PowerPoint に埋め込みビデオ フレームを追加する
linktitle: PowerPoint に埋め込みビデオ フレームを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: このステップバイステップのチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint にビデオ フレームを埋め込む方法を説明します。プレゼンテーションを簡単に強化できます。
weight: 21
url: /ja/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint に埋め込みビデオ フレームを追加する

## 導入
PowerPoint プレゼンテーションにビデオを追加すると、プレゼンテーションがより魅力的で有益なものになります。Aspose.Slides for Java を使用すると、ビデオをスライドに直接簡単に埋め込むことができます。このチュートリアルでは、プロセスについてステップごとに説明し、コードのすべての部分とその機能について理解できるようにします。経験豊富な開発者でも、初心者でも、このガイドは、埋め込みビデオを使用してプレゼンテーションを強化するのに役立ちます。
## 前提条件
コードに進む前に、次の前提条件が満たされていることを確認してください。
1. Java 開発キット (JDK): マシンに JDK がインストールされていることを確認してください。
2. Aspose.Slides for Java: Aspose.Slides for Java ライブラリをダウンロードしてインストールします。
3. 統合開発環境 (IDE): より優れた開発エクスペリエンスを得るには、IntelliJ IDEA や Eclipse などの IDE を使用します。
4. ビデオ ファイル: PowerPoint プレゼンテーションに埋め込みたいビデオ ファイルがあります。
## パッケージのインポート
まず、Aspose.Slides を操作するために必要なパッケージをインポートする必要があります。これらのインポートは、スライド、ビデオ、プレゼンテーション ファイルの管理に役立ちます。
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## ステップ1: 環境を設定する
コーディングを始める前に、環境が正しく設定されていることを確認してください。これには、必要なディレクトリの作成とビデオ ファイルの準備が含まれます。
```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
//ディレクトリがまだ存在しない場合は作成します。
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## ステップ2: プレゼンテーションクラスのインスタンスを作成する
インスタンスを作成する`Presentation`クラス。このクラスは PowerPoint ファイルを表します。
```java
// PPTXを表すプレゼンテーションクラスをインスタンス化する
Presentation pres = new Presentation();
```
## ステップ3: 最初のスライドを取得する
ビデオを埋め込むプレゼンテーションの最初のスライドにアクセスします。
```java
//最初のスライドを取得する
ISlide sld = pres.getSlides().get_Item(0);
```
## ステップ4: プレゼンテーションにビデオを追加する
ビデオ ファイルをプレゼンテーションに埋め込みます。ビデオ パスが正しく指定されていることを確認します。
```java
//プレゼンテーション内にビデオを埋め込む
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## ステップ5: スライドにビデオフレームを追加する
スライド上にビデオ フレームを作成し、その寸法と位置を設定します。
```java
//ビデオフレームを追加
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## ステップ6: ビデオフレームのプロパティを構成する
ビデオをビデオ フレームに設定し、再生モードや音量などの再生設定を構成します。
```java
//ビデオをビデオフレームに設定する
vf.setEmbeddedVideo(vid);
//ビデオの再生モードと音量を設定する
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## ステップ7: プレゼンテーションを保存する
埋め込まれたビデオを含むプレゼンテーションを指定したディレクトリに保存します。
```java
// PPTXファイルをディスクに書き込む
pres.save(resultPath, SaveFormat.Pptx);
```
## ステップ8: リソースをクリーンアップする
最後に、プレゼンテーション オブジェクトを破棄してリソースを解放します。
```java
//プレゼンテーションオブジェクトを破棄する
if (pres != null) pres.dispose();
```
## 結論
Aspose.Slides for Java を使用して PowerPoint プレゼンテーションにビデオを埋め込むのは、簡単なプロセスです。このガイドで説明されている手順に従うことで、魅力的なビデオ コンテンツでプレゼンテーションを強化できます。練習を重ねれば完璧になります。さまざまなビデオを埋め込んでプロパティを調整し、ニーズに最適なものを見つけてください。
## よくある質問
### 1 つのスライドに複数のビデオを埋め込むことはできますか?
はい、複数のビデオ フレームを追加することで、1 つのスライドに複数のビデオを埋め込むことができます。
### ビデオの再生を制御するにはどうすればよいですか?
再生は、`setPlayMode`そして`setVolume`の`IVideoFrame`クラス。
### Aspose.Slides ではどのようなビデオ形式がサポートされていますか?
Aspose.Slides は、MP4、AVI、WMV などさまざまなビデオ形式をサポートしています。
### Aspose.Slides を使用するにはライセンスが必要ですか?
はい、Aspose.Slides を使用するには有効なライセンスが必要です。評価用に一時ライセンスを取得できます。
### ビデオフレームのサイズと位置をカスタマイズできますか?
はい、ビデオ フレームを追加するときに適切なパラメータを設定することで、サイズと位置をカスタマイズできます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
