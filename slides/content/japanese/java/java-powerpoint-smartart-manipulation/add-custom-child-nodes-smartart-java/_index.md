---
title: Java を使用して SmartArt にカスタム子ノードを追加する
linktitle: Java を使用して SmartArt にカスタム子ノードを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides で Java を使用して、PowerPoint プレゼンテーションの SmartArt にカスタム子ノードを追加する方法を学びます。プロフェッショナルなグラフィックでスライドを簡単に強化できます。
type: docs
weight: 11
url: /ja/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---
## 導入
SmartArt は PowerPoint の強力な機能で、ユーザーはこれを使用してプロフェッショナルなグラフィックをすばやく簡単に作成できます。このチュートリアルでは、Java と Aspose.Slides を使用して SmartArt にカスタム子ノードを追加する方法を学習します。
## 前提条件
始める前に、以下のものを用意してください。
1. Java 開発キット (JDK): システムに Java がインストールされていることを確認します。
2.  Aspose.Slides for Java: Aspose.Slides for Javaをこちらからダウンロードしてインストールします。[ここ](https://releases.aspose.com/slides/java/).

## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。
```java
import com.aspose.slides.*;
```
## ステップ1: プレゼンテーションを読み込む
SmartArt にカスタム子ノードを追加する PowerPoint プレゼンテーションを読み込みます。
```java
String dataDir = "Your Document Directory";
//希望のプレゼンテーションをロードする
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## ステップ2: スライドにSmartArtを追加する
次に、スライドに SmartArt を追加してみましょう。
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## ステップ3: SmartArt図形を移動する
SmartArt 図形を新しい位置に移動します。
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## ステップ4: 図形の幅を変更する
SmartArt 図形の幅を変更します。
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## ステップ5: 図形の高さを変更する
SmartArt 図形の高さを変更します。
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## ステップ6: 図形を回転する
SmartArt 図形を回転します。
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## ステップ7: プレゼンテーションを保存する
最後に、変更したプレゼンテーションを保存します。
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## 結論
このチュートリアルでは、Java と Aspose.Slides を使用して SmartArt にカスタム子ノードを追加する方法を学習しました。これらの手順に従うことで、カスタマイズされたグラフィックでプレゼンテーションを強化し、より魅力的でプロフェッショナルなものにすることができます。
## よくある質問
### Aspose.Slides for Java を使用して、さまざまな種類の SmartArt レイアウトを追加できますか?
はい、Aspose.Slides for Java はさまざまな SmartArt レイアウトをサポートしており、プレゼンテーションのニーズに最適なレイアウトを選択できます。
### Aspose.Slides for Java は、さまざまなバージョンの PowerPoint と互換性がありますか?
Aspose.Slides for Java は、さまざまなバージョンの PowerPoint とシームレスに連携するように設計されており、プラットフォーム間での互換性と一貫性を保証します。
### SmartArt 図形の外観をプログラムでカスタマイズできますか?
もちろんです! Aspose.Slides for Java を使用すると、デザインの好みに合わせて SmartArt 図形の外観、サイズ、色、レイアウトをプログラムでカスタマイズできます。
### Aspose.Slides for Java はドキュメントとサポートを提供しますか?
はい、Aspose Web サイトで包括的なドキュメントやコミュニティ サポート フォーラムにアクセスできます。
### Aspose.Slides for Java の試用版はありますか?
はい、購入前に Aspose.Slides for Java の無料試用版を Web サイトからダウンロードして、その機能や性能を調べることができます。[ここ](https://releases.aspose.com/slides/java/).