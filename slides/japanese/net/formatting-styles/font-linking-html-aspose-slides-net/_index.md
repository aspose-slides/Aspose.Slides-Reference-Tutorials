---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET を使用してフォントを直接埋め込むことで、プレゼンテーションを HTML に変換するときに一貫したフォント レンダリングを確保する方法を学習します。"
"title": "Aspose.Slides for .NET を使用して HTML 内のフォントをリンクする方法 - ステップバイステップガイド"
"url": "/ja/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET を使用して HTML 内のフォントをリンクする方法

## 導入

プラットフォーム間で一貫したフォント レンダリングを維持しながらプレゼンテーションを HTML に変換するのは難しい場合があります。 **Aspose.Slides .NET 版** プレゼンテーションで使用されるすべてのフォントを、埋め込みフォント ファイルを通じて HTML 出力内で直接リンクできるようにすることで、シームレスなソリューションを提供します。

このチュートリアルでは、Aspose.Slides for .NET を使用してフォント リンクを実装し、さまざまなプラットフォーム間でデザインの一貫性を確保する方法について説明します。 

**学習内容:**
- Aspose.Slides for .NET で環境を設定する
- HTML変換でフォントをリンクする
- フォント埋め込み用のカスタムコントローラの作成
- 実用的なアプリケーションとパフォーマンスの考慮事項

これを実現するために必要な手順を詳しく見ていきましょう。

## 前提条件

始める前に、以下のものを用意してください。

### 必要なライブラリと依存関係
- **Aspose.Slides .NET 版** ライブラリ: 実装のコアコンポーネント。

### 環境設定要件
- .NET Framework または .NET Core がインストールされた開発環境。

### 知識の前提条件
- C# プログラミングの基本的な理解。
- HTMLとCSS、特に `@font-face` ルール。

## Aspose.Slides for .NET のセットアップ

.NETプロジェクトでAspose.Slidesを使用するには、ライブラリをインストールする必要があります。以下の方法があります。

### .NET CLIの使用
```bash
dotnet add package Aspose.Slides
```

### パッケージマネージャーコンソールの使用
```powershell
Install-Package Aspose.Slides
```

### NuGet パッケージ マネージャー UI 経由
- Visual Studio でプロジェクトを開きます。
- 「NuGet パッケージ マネージャー」に移動します。
- 「Aspose.Slides」を検索し、最新バージョンをインストールします。

### ライセンス取得手順
次の手順に従って、無料の試用ライセンスを取得し、すべての機能を制限なくテストすることができます。
1. **無料トライアル**一時ライセンスをダウンロードする [ここ](https://releases。aspose.com/slides/net/).
2. **一時ライセンス**拡張アクセスを申請する [ここ](https://purchase。aspose.com/temporary-license/).
3. **購入**フル機能を使用するにはライセンスを購入してください [ここ](https://purchase。aspose.com/buy).

### 基本的な初期化とセットアップ
```csharp
// Licenseクラスのインスタンスを作成する
easpose.slides.License license = new aspose.slides.License();

// ファイルパスからライセンスを適用する
license.SetLicense("Aspose.Slides.lic");
```

## 実装ガイド

さて、HTML変換でフォントリンクを実装してみましょう。 **Aspose.Slides .NET 版**。

### 機能概要: HTML 変換におけるフォントのリンク
この機能により、プレゼンテーションで使用されるすべてのフォントが、生成されるHTMLファイル内でフォントファイルを埋め込むことで直接リンクされます。この方法は、異なるブラウザやプラットフォーム間でデザインの一貫性を維持するための堅牢なソリューションを提供します。

#### ステップ1: カスタムコントローラーを作成する
カスタムコントローラークラスを作成する `LinkAllFontsHtmlController` これは `EmbedAllFontsHtmlController`：
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // フォントファイルを保存するディレクトリを設定します
    }
}
```
#### ステップ2: フォント書き込みメソッドを実装する
その `WriteFont` メソッドはフォント データをファイルに書き込み、埋め込み用の対応する HTML コードを生成します。
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // 使用するフォント名を決定し、代替フォントが使用可能な場合はそれを優先します。
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // .woff フォント ファイルのファイル パスを構築します。
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // 指定されたファイル パスにフォント データを書き込みます。
    File.WriteAllBytes(path, fontData);

    // @font-face ルールを使用してフォントを埋め込んだ HTML スタイル ブロックを生成します。
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}