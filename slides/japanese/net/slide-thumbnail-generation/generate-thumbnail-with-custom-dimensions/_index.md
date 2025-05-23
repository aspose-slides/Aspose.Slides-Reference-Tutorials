---
"description": "Aspose.Slides for .NET を使用して、PowerPoint プレゼンテーションからカスタムサムネイル画像を生成する方法を学びます。ユーザーエクスペリエンスと機能性を向上させます。"
"linktitle": "カスタムディメンションでサムネイルを生成する"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "スライドにカスタムサイズのサムネイルを生成する"
"url": "/ja/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# スライドにカスタムサイズのサムネイルを生成する


PowerPointプレゼンテーションのカスタムサムネイル画像を作成することは、インタラクティブなアプリケーションの構築、ユーザーエクスペリエンスの向上、あるいは様々なプラットフォーム向けのコンテンツの最適化など、様々な場面で大きなメリットとなります。このチュートリアルでは、Aspose.Slides for .NETライブラリを用いて、PowerPointプレゼンテーションからカスタムサムネイル画像を生成する手順を説明します。この強力なライブラリを使えば、.NETアプリケーションからプログラム的にPowerPointファイルを操作、変換、そして強化することができます。

## 前提条件

カスタム サムネイル画像の生成に進む前に、次の前提条件が満たされていることを確認してください。

### 1. Aspose.Slides for .NET

プロジェクトにAspose.Slides for .NETライブラリがインストールされている必要があります。まだインストールされていない場合は、必要なドキュメントとダウンロードリンクをご覧ください。 [ここ](https://reference。aspose.com/slides/net/).

### 2. PowerPointプレゼンテーション

カスタムサムネイル画像を生成するPowerPointプレゼンテーションがあることを確認してください。このプレゼンテーションはプロジェクトディレクトリ内でアクセスできる必要があります。

### 3. 開発環境

このチュートリアルを実行するには、C# を使用した .NET プログラミングに関する実用的な知識と、Visual Studio などの開発環境がセットアップされている必要があります。

前提条件について説明しましたので、カスタム サムネイルを生成するプロセスを、手順ごとに詳しく説明しましょう。

## 名前空間のインポート

まず、C#コードに必要な名前空間を含める必要があります。これらの名前空間により、Aspose.Slides を操作し、PowerPoint プレゼンテーションを操作できるようになります。

```csharp
using Aspose.Slides;
using System.Drawing;
```

## ステップ1: プレゼンテーションを読み込む

まず、カスタムサムネイル画像を生成するPowerPointプレゼンテーションを読み込みます。これはAspose.Slidesライブラリを使用して実現します。

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// プレゼンテーションファイルを表すPresentationクラスをインスタンス化する
using (Presentation pres = new Presentation(srcFileName))
{
    // サムネイル生成用のコードをここに入力します
}
```

## ステップ2: スライドにアクセスする

読み込まれたプレゼンテーション内で、カスタムサムネイル画像を生成する特定のスライドにアクセスする必要があります。スライドはインデックスで選択できます。

```csharp
// 最初のスライドにアクセスします（必要に応じてインデックスを変更できます）
ISlide sld = pres.Slides[0];
```

## ステップ3: カスタムサムネイルのサイズを定義する

カスタムサムネイル画像の希望するサイズを指定します。アプリケーションの要件に応じて、幅と高さをピクセル単位で定義できます。

```csharp
int desiredX = 1200; // 幅
int desiredY = 800;  // 身長
```

## ステップ4: スケーリング係数を計算する

スライドのアスペクト比を維持するには、スライドのサイズと希望する寸法に基づいて、X 寸法と Y 寸法のスケーリング係数を計算します。

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## ステップ5: サムネイル画像を生成する

指定されたカスタム サイズでスライドのフル スケール画像を作成し、JPEG 形式でディスクに保存します。

```csharp
// 実物大の画像を作成する
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// 画像をJPEG形式でディスクに保存する
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

これらの手順を実行すると、PowerPoint プレゼンテーションからカスタム サムネイル イメージが正常に生成されるはずです。

## 結論

Aspose.Slides for .NET を使用してPowerPointプレゼンテーションからカスタムサムネイル画像を生成することは、アプリケーションのユーザーエクスペリエンスと機能性を向上させる貴重なスキルです。このチュートリアルで説明する手順に従うことで、特定の要件を満たすカスタムサムネイルを簡単に作成できます。

---

## FAQ（よくある質問）

### Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、開発者が .NET アプリケーションでプログラムによって PowerPoint プレゼンテーションを操作できるようにする強力なライブラリです。

### Aspose.Slides for .NET のドキュメントはどこにありますか?
ドキュメントは以下にあります [ここ](https://reference。aspose.com/slides/net/).

### Aspose.Slides for .NET は無料で使用できますか?
Aspose.Slides for .NETは商用ライブラリです。価格とライセンス情報はこちらをご覧ください。 [ここ](https://purchase。aspose.com/buy).

### Aspose.Slides for .NET を使用するには高度なプログラミング スキルが必要ですか?
.NET プログラミングに関する知識があると便利ですが、Aspose.Slides for .NET は、PowerPoint プレゼンテーションの操作を簡素化するユーザーフレンドリーな API を提供します。

### Aspose.Slides for .NET のテクニカル サポートは受けられますか?
はい、テクニカルサポートとコミュニティフォーラムにアクセスできます [ここ](https://forum。aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}