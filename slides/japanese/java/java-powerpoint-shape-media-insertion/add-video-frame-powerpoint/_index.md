---
title: PowerPoint にビデオ フレームを追加する
linktitle: PowerPoint にビデオ フレームを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、ビデオ コンテンツを PowerPoint プレゼンテーションにシームレスに統合する方法を学びます。マルチメディア要素を含むスライドで視聴者を魅了します。
weight: 17
url: /ja/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションにビデオ フレームを追加する手順を説明します。これらのステップ バイ ステップの指示に従うことで、ビデオ コンテンツをプレゼンテーションにシームレスかつ簡単に統合できるようになります。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
- システムにJava開発キット（JDK）がインストールされている
- Aspose.Slides for Java ライブラリがダウンロードされ、Java プロジェクトにセットアップされました
## パッケージのインポート
まず、Java コードで Aspose.Slides 機能を利用するために必要なパッケージをインポートする必要があります。 
```java
import com.aspose.slides.*;

import java.io.File;
```
## ステップ1: ドキュメントディレクトリを設定する
PowerPoint ファイルを保存するためのディレクトリが設定されていることを確認してください。
```java
String dataDir = "Your Document Directory";
```
## ステップ2: プレゼンテーションオブジェクトを作成する
インスタンス化する`Presentation` PowerPoint ファイルを表すクラス。
```java
Presentation pres = new Presentation();
```
## ステップ3: スライドにビデオフレームを追加する
最初のスライドを取得し、それにビデオ フレームを追加します。
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## ステップ4: 再生モードと音量を設定する
ビデオフレームの再生モードと音量を設定します。
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## ステップ5: プレゼンテーションを保存する
変更した PowerPoint ファイルをディスクに保存します。
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## 結論
おめでとうございます! Aspose.Slides for Java を使用して PowerPoint プレゼンテーションにビデオ フレームを追加する方法を学習しました。マルチメディア要素を組み込むことでプレゼンテーションを強化し、視聴者を効果的に引き付けることができます。
## よくある質問
### PowerPoint プレゼンテーションに任意の形式のビデオを追加できますか?
Aspose.Slides は、AVI、WMV、MP4 など、さまざまなビデオ形式をサポートしています。形式が PowerPoint と互換性があることを確認してください。
### Aspose.Slides はさまざまなバージョンの Java と互換性がありますか?
はい、Aspose.Slides for Java は JDK バージョン 6 以降と互換性があります。
### ビデオフレームのサイズと位置を調整するにはどうすればよいですか?
ビデオフレームの寸法と座標は、`addVideoFrame`方法。
### ビデオの再生設定を制御できますか?
はい、ビデオ フレームの再生モードと音量は、好みに応じて設定できます。
### Aspose.Slides の詳細なサポートとリソースはどこで見つかりますか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)支援、ドキュメント、コミュニティ サポート。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
