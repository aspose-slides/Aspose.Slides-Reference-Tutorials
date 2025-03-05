---
title: プレゼンテーションを XAML 形式にエクスポート
linktitle: プレゼンテーションを XAML 形式にエクスポート
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーションを XAML 形式にエクスポートする方法を学びます。インタラクティブなコンテンツを簡単に作成できます。
type: docs
weight: 27
url: /ja/net/presentation-conversion/export-presentation-to-xaml-format/
---

ソフトウェア開発の世界では、複雑なタスクを簡素化できるツールが不可欠です。Aspose.Slides for .NET は、PowerPoint プレゼンテーションをプログラムで操作できるようにするツールの 1 つです。このステップバイステップのチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーションを XAML 形式にエクスポートする方法を説明します。 

## Aspose.Slides for .NET の紹介

チュートリアルに進む前に、Aspose.Slides for .NET について簡単に紹介します。これは、開発者が Microsoft PowerPoint 自体を必要とせずに PowerPoint プレゼンテーションを作成、変更、変換、管理できるようにする強力なライブラリです。Aspose.Slides for .NET を使用すると、PowerPoint プレゼンテーションに関連するさまざまなタスクを自動化して、開発プロセスをより効率的にすることができます。

## 前提条件

このチュートリアルを実行するには、次のものが必要です。

1. Aspose.Slides for .NET: Aspose.Slides for .NET ライブラリがインストールされ、.NET プロジェクトで使用できる状態になっていることを確認します。

2. ソース プレゼンテーション: XAML 形式にエクスポートする PowerPoint プレゼンテーション (PPTX) があります。このプレゼンテーションへのパスを確認してください。

3. 出力ディレクトリ: 生成された XAML ファイルを保存するディレクトリを選択します。

## ステップ1: プロジェクトを設定する

この最初のステップでは、プロジェクトをセットアップし、必要なコンポーネントがすべて準備されていることを確認します。プロジェクトに Aspose.Slides for .NET ライブラリへの参照を追加したことを確認します。

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
//ソースプレゼンテーションへのパス
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

交換する`"Your Document Directory"`ソース PowerPoint プレゼンテーションを含むディレクトリへのパスを指定します。また、生成された XAML ファイルが保存される出力ディレクトリも指定します。

## ステップ 2: プレゼンテーションを XAML にエクスポートする

次に、PowerPoint プレゼンテーションを XAML 形式にエクスポートします。これを実現するには、Aspose.Slides for .NET を使用します。 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    //変換オプションを作成する
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    //独自の出力節約サービスを定義する
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    //スライドを変換する
    pres.Save(xamlOptions);

    //XAMLファイルを出力ディレクトリに保存する
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

このコードスニペットでは、ソースプレゼンテーションを読み込み、XAML変換オプションを作成し、カスタム出力保存サービスを定義します。`NewXamlSaver`次に、XAML ファイルを指定された出力ディレクトリに保存します。

## ステップ 3: カスタム XAML セーバー クラス

カスタムXAMLセーバーを実装するには、次のクラスを作成します。`NewXamlSaver`を実装する`IXamlOutputSaver`インターフェース。

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

このクラスは、XAML ファイルを出力ディレクトリに保存する処理を処理します。

## 結論

おめでとうございます。Aspose.Slides for .NET を使用して PowerPoint プレゼンテーションを XAML 形式にエクスポートする方法を学習しました。これは、プレゼンテーションの操作を伴うプロジェクトに取り組むときに役立つスキルです。

PowerPoint 自動化タスクを強化するために、Aspose.Slides for .NET のその他の機能や機能を自由に探索してください。

## よくある質問

1. ### Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、PowerPoint プレゼンテーションをプログラムで操作するための .NET ライブラリです。

2. ### Aspose.Slides for .NET はどこで入手できますか?
 Aspose.Slides for .NETは以下からダウンロードできます。[ここ](https://purchase.aspose.com/buy).

3. ### 無料トライアルはありますか？
はい、Aspose.Slides for .NETの無料トライアルを入手できます。[ここ](https://releases.aspose.com/).

4. ### Aspose.Slides for .NET の一時ライセンスを取得するにはどうすればよいですか?
臨時免許証を取得できます[ここ](https://purchase.aspose.com/temporary-license/).

5. ### Aspose.Slides for .NET のサポートはどこで受けられますか?
サポートやコミュニティのディスカッションを見つけることができます[ここ](https://forum.aspose.com/).

その他のチュートリアルやリソースについては、[Aspose.Slides API ドキュメント](https://reference.aspose.com/slides/net/).