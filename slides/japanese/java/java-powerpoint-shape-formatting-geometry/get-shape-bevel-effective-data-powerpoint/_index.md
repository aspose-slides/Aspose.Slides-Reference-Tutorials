---
title: PowerPoint でシェイプベベルの有効データを取得する
linktitle: PowerPoint でシェイプベベルの有効データを取得する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して、PowerPoint で図形のベベルの有効データを取得する方法を学びます。魅力的な視覚効果でプレゼンテーションを強化します。
weight: 26
url: /ja/java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 導入
現代のビジネス プレゼンテーションでは、視覚的な魅力が情報を効果的に伝える上で重要な役割を果たします。PowerPoint プレゼンテーションで図形の視覚的なインパクトを高めることができる要素の 1 つがベベル効果です。Aspose.Slides for Java は、ベベル効果を含む図形のさまざまなプロパティにアクセスして操作するための強力なツールを提供します。このチュートリアルでは、Aspose.Slides for Java を使用して図形のベベル効果データを取得する手順を説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Java プログラミング言語の基本的な理解。
2. システムに Java Development Kit (JDK) をインストールしました。
3.  Aspose.Slides for Javaをダウンロードしてインストールしました。ダウンロードはこちらから[ここ](https://releases.aspose.com/slides/java/).
## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートします。
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## ステップ1: ドキュメントディレクトリを設定する
PowerPoint プレゼンテーションが保存されているドキュメント ディレクトリへのパスを定義します。
```java
String dataDir = "Your Document Directory";
```
## ステップ2: プレゼンテーションを読み込む
Aspose.Slides ライブラリを使用して PowerPoint プレゼンテーションを読み込みます。
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## ステップ3: ベベル有効データを取得する
シェイプの有効なベベル データにアクセスします。
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## ステップ4: ベベルプロパティを印刷する
有効形状の上面レリーフ プロパティを出力します。
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## 結論
このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint で図形のベベルの有効データを取得する方法を説明しました。これらの手順に従うことで、図形のさまざまなプロパティに簡単にアクセスして操作し、プレゼンテーションの視覚的な魅力を高めることができます。
## よくある質問
### 複数の図形に同時にベベル効果を適用できますか?
はい、スライド内の図形を反復処理し、必要に応じてベベル効果を適用できます。
### Aspose.Slides はベベル以外の 3D 効果もサポートしていますか?
はい、Aspose.Slides は、PowerPoint プレゼンテーションの図形に適用できる幅広い 3D 効果を提供します。
### Aspose.Slides はさまざまなバージョンの PowerPoint と互換性がありますか?
Aspose.Slides は、さまざまなバージョンの PowerPoint との互換性を確保し、さまざまな環境間でシームレスに作業できるようにします。
### ベベル効果のプロパティをさらにカスタマイズできますか?
もちろん、ベベル効果のプロパティを完全に制御し、要件に応じてカスタマイズできます。
### Aspose.Slides のその他のリソースやサポートはどこで見つかりますか?
訪問することができます[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)ご質問、サポート、追加リソースについては、こちらをご覧ください。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
