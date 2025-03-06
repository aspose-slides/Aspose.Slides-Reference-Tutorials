---
title: Aspose.Slides .NET で PowerPoint アニメーションをマスターする
linktitle: スライド上でアニメーションを繰り返す
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを強化します。アニメーションを簡単に制御し、視聴者を魅了し、永続的な印象を残します。
weight: 12
url: /ja/net/slide-animation-control/repeat-animation-on-slide/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 導入
プレゼンテーションのダイナミックな世界では、アニメーションを制御する機能は、視聴者の関心を引き付け、捕らえる上で重要な役割を果たします。Aspose.Slides for .NET を使用すると、開発者はスライド内のアニメーションの種類を管理できるため、よりインタラクティブで視覚的に魅力的なプレゼンテーションが可能になります。このチュートリアルでは、Aspose.Slides for .NET を使用してスライド上のアニメーションの種類を制御する方法を段階的に説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Slides for .NETライブラリ: ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/slides/net/).
2. .NET 開発環境: マシンに .NET 開発環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトでは、まず Aspose.Slides が提供する機能を活用するために必要な名前空間をインポートします。
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## ステップ1: プロジェクトの設定
プロジェクト用の新しいディレクトリを作成し、プレゼンテーション ファイルを表す Presentation クラスをインスタンス化します。
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    //ここにコードを入力してください
}
```
## ステップ2: エフェクトシーケンスにアクセスする
MainSequence プロパティを使用して、最初のスライドのエフェクト シーケンスを取得します。
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## ステップ3: 最初のエフェクトにアクセスする
メインシーケンスの最初の効果を取得して、そのプロパティを操作します。
```csharp
IEffect effect = effectsSequence[0];
```
## ステップ4: 繰り返し設定を変更する
エフェクトのタイミング/繰り返しプロパティを「スライドの最後まで」に変更します。
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## ステップ5: プレゼンテーションを保存する
変更したプレゼンテーションを保存して、変更を視覚化します。
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
追加の効果を得るにはこれらの手順を繰り返し、プレゼンテーションの要件に応じてカスタマイズします。
## 結論
Aspose.Slides for .NET を使用すると、PowerPoint プレゼンテーションに動的なアニメーションを組み込むことがこれまでになく簡単になります。このステップ バイ ステップ ガイドでは、アニメーションの種類を制御するための知識を身に付け、スライドが視聴者に永続的な印象を残すようにします。
## よくある質問
### これらのアニメーションをスライド内の特定のオブジェクトに適用できますか?
はい、シーケンス内の個々のエフェクトにアクセスすることで、特定のオブジェクトをターゲットにすることができます。
### Aspose.Slides は最新の PowerPoint バージョンと互換性がありますか?
Aspose.Slides は、幅広いバージョンの PowerPoint をサポートしており、古いバージョンと新しいバージョンの両方との互換性が保証されます。
### 追加の例やリソースはどこで見つかりますか?
探索する[ドキュメンテーション](https://reference.aspose.com/slides/net/)包括的な例と詳細な説明については、こちらをご覧ください。
### Aspose.Slides の一時ライセンスを取得するにはどうすればよいですか?
訪問[ここ](https://purchase.aspose.com/temporary-license/)一時ライセンスの取得に関する情報。
### ヘルプが必要ですか、またはさらに質問がありますか?
 Aspose.Slidesコミュニティに参加しましょう[サポートフォーラム](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
