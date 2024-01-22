---
title: Aspose.Slides .NET を使用して PowerPoint アニメーションをマスターする
linktitle: スライド上でアニメーションを繰り返す
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを強化します。アニメーションを簡単に制御し、視聴者を魅了し、永続的な印象を残します。
type: docs
weight: 12
url: /ja/net/slide-animation-control/repeat-animation-on-slide/
---
## 導入
ダイナミックなプレゼンテーションの世界では、アニメーションを制御する機能が、聴衆の注意を引きつけ、注目を集める上で極めて重要な役割を果たします。 Aspose.Slides for .NET を使用すると、開発者はスライド内のアニメーション タイプを管理できるようになり、よりインタラクティブで視覚的に魅力的なプレゼンテーションが可能になります。このチュートリアルでは、Aspose.Slides for .NET を使用してスライド上のアニメーション タイプを制御する方法を段階的に説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Slides for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/slides/net/).
2. .NET 開発環境: マシン上に .NET 開発環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトでは、Aspose.Slides が提供する機能を利用するために必要な名前空間をインポートすることから始めます。
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## ステップ 1: プロジェクトをセットアップする
プロジェクト用に新しいディレクトリを作成し、プレゼンテーション ファイルを表す Presentation クラスをインスタンス化します。
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    //コードはここに入力します
}
```
## ステップ 2: エフェクト シーケンスにアクセスする
MainSequence プロパティを使用して、最初のスライドのエフェクト シーケンスを取得します。
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## ステップ 3: 最初のエフェクトにアクセスする
メイン シーケンスの最初のエフェクトを取得して、そのプロパティを操作します。
```csharp
IEffect effect = effectsSequence[0];
```
## ステップ 4: リピート設定を変更する
エフェクトのタイミング/繰り返しプロパティを「スライドの終わりまで」に変更します。
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## ステップ 5: プレゼンテーションを保存する
変更したプレゼンテーションを保存して、変更を視覚化します。
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
これらの手順を繰り返して効果を追加するか、プレゼンテーションの要件に応じてカスタマイズします。
## 結論
Aspose.Slides for .NET を使用すると、PowerPoint プレゼンテーションにダイナミック アニメーションを組み込むことがこれまでになく簡単になります。このステップバイステップのガイドでは、アニメーションの種類を制御するための知識を身につけ、スライドが聴衆に永続的な印象を残すようにします。
## よくある質問
### これらのアニメーションをスライド内の特定のオブジェクトに適用できますか?
はい、シーケンス内の個々のエフェクトにアクセスすることで、特定のオブジェクトをターゲットにすることができます。
### Aspose.Slides は PowerPoint の最新バージョンと互換性がありますか?
Aspose.Slides は、PowerPoint の幅広いバージョンをサポートし、古いバージョンと新しいバージョンの両方との互換性を保証します。
### 追加の例やリソースはどこで見つけられますか?
を探索してください[ドキュメンテーション](https://reference.aspose.com/slides/net/)包括的な例と詳細な説明については、
### Aspose.Slides の一時ライセンスを取得するにはどうすればよいですか?
訪問[ここ](https://purchase.aspose.com/temporary-license/)一時ライセンスの取得については、こちらをご覧ください。
### 助けが必要ですか、それともさらに質問がありますか?
 Aspose.Slides コミュニティに参加してください。[サポートフォーラム](https://forum.aspose.com/c/slides/11).