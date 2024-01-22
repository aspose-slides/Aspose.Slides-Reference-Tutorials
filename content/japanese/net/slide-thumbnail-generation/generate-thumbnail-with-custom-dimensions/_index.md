---
title: カスタム サイズを使用してスライドにサムネイルを生成する
linktitle: カスタム ディメンションを使用したサムネイルの生成
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションからカスタム サムネイル画像を生成する方法を学びます。ユーザーエクスペリエンスと機能を強化します。
type: docs
weight: 13
url: /ja/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

PowerPoint プレゼンテーションのカスタム サムネイル画像の作成は、インタラクティブなアプリケーションの構築、ユーザー エクスペリエンスの向上、さまざまなプラットフォーム向けのコンテンツの最適化のいずれの場合でも、貴重な資産となります。このチュートリアルでは、Aspose.Slides for .NET ライブラリを使用して PowerPoint プレゼンテーションからカスタム サムネイル画像を生成するプロセスを説明します。この強力なライブラリを使用すると、.NET アプリケーションでプログラムによって PowerPoint ファイルを操作、変換、および拡張できます。

## 前提条件

カスタム サムネイル画像の生成に入る前に、次の前提条件が満たされていることを確認してください。

### 1. .NET 用の Aspose.Slides

 Aspose.Slides for .NET ライブラリをプロジェクトにインストールする必要があります。まだお持ちでない場合は、必要なドキュメントとダウンロード リンクを見つけてください。[ここ](https://reference.aspose.com/slides/net/).

### 2. PowerPoint プレゼンテーション

カスタム サムネイル画像を生成する PowerPoint プレゼンテーションがあることを確認してください。このプレゼンテーションは、プロジェクト ディレクトリ内でアクセスできる必要があります。

### 3. 開発環境

このチュートリアルに従うには、C# を使用した .NET プログラミングの実用的な知識と、Visual Studio などの開発環境がセットアップされている必要があります。

前提条件を説明したので、カスタム サムネイルを生成するプロセスを段階的な手順に分けて説明しましょう。

## 名前空間のインポート

まず、必要な名前空間を C# コードに含める必要があります。これらの名前空間を使用すると、Aspose.Slides を操作し、PowerPoint プレゼンテーションを操作できます。

```csharp
using Aspose.Slides;
using System.Drawing;
```

## ステップ 1: プレゼンテーションをロードする

まず、カスタム サムネイル イメージを生成する PowerPoint プレゼンテーションを読み込みます。これは、Aspose.Slides ライブラリを使用して実現されます。

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

//プレゼンテーション ファイルを表す Presentation クラスをインスタンス化します。
using (Presentation pres = new Presentation(srcFileName))
{
    //サムネイル生成用のコードはここに入力します
}
```

## ステップ 2: スライドにアクセスする

ロードされたプレゼンテーション内で、カスタム サムネイル画像を生成する特定のスライドにアクセスする必要があります。スライドはインデックスで選択できます。

```csharp
//最初のスライドにアクセスします (必要に応じてインデックスを変更できます)
ISlide sld = pres.Slides[0];
```

## ステップ 3: カスタム サムネイルのサイズを定義する

カスタム サムネイル画像の希望のサイズを指定します。アプリケーションの要件に応じて、幅と高さをピクセル単位で定義できます。

```csharp
int desiredX = 1200; //幅
int desiredY = 800;  //身長
```

## ステップ 4: スケーリング係数を計算する

スライドのアスペクト比を維持するには、スライドのサイズと希望の寸法に基づいて X 寸法と Y 寸法の倍率を計算します。

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## ステップ 5: サムネイル画像を生成する

指定したカスタム寸法でスライドの実物大画像を作成し、JPEG 形式でディスクに保存します。

```csharp
//実物大の画像を作成する
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

//画像を JPEG 形式でディスクに保存します
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

これらの手順を完了すると、PowerPoint プレゼンテーションからカスタム サムネイル画像が正常に生成されるはずです。

## 結論

Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションからカスタム サムネイル画像を生成することは、アプリケーションのユーザー エクスペリエンスと機能を強化できる貴重なスキルです。このチュートリアルで概説されている手順に従うことで、特定の要件を満たすカスタム サムネイルを簡単に作成できます。

---

## FAQ（よくある質問）

### Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、開発者が .NET アプリケーションでプログラム的に PowerPoint プレゼンテーションを操作できるようにする強力なライブラリです。

### Aspose.Slides for .NET のドキュメントはどこで見つけられますか?
ドキュメントを見つけることができます[ここ](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET は無料で使用できますか?
 Aspose.Slides for .NET は商用ライブラリです。価格とライセンス情報を確認できます[ここ](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET を使用するには高度なプログラミング スキルが必要ですか?
.NET プログラミングの知識がある程度あると役に立ちますが、Aspose.Slides for .NET は、PowerPoint プレゼンテーションの操作を簡素化するユーザー フレンドリーな API を提供します。

### Aspose.Slides for .NET のテクニカル サポートは利用できますか?
はい、テクニカル サポートとコミュニティ フォーラムにアクセスできます。[ここ](https://forum.aspose.com/).