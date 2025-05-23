---
"date": "2025-04-23"
"description": "Aspose.Slides for Python を使用して PowerPoint で SmartArt グラフィックを作成およびカスタマイズし、動的な組織図でプレゼンテーションを強化する方法を学習します。"
"title": "Aspose.Slides for Python を使用して PowerPoint で SmartArt を作成およびカスタマイズする方法"
"url": "/ja/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python を使用して PowerPoint で SmartArt を作成およびカスタマイズする方法

## 導入

プレゼンテーションは、組織構造やブレインストーミングセッションを視覚的に表現するための重要なツールです。Aspose.Slides for Pythonを使えば、SmartArtグラフィックを簡単に作成・カスタマイズできます。このチュートリアルでは、PowerPointスライドに組織図のSmartArtグラフィックを追加する方法を説明します。

**学習内容:**
- Aspose.Slides for Python を使用して PowerPoint に SmartArt グラフィックを追加します。
- SmartArt ノードのレイアウトをカスタマイズします。
- プレゼンテーションを効率的に保存およびエクスポートします。

環境の設定を始めましょう!

## 前提条件

SmartArt グラフィックの作成を始める前に、次の前提条件が満たされていることを確認してください。

### 必要なライブラリ
- **Python 用 Aspose.Slides**: まだインストールしていない場合は、pip を使用してこのライブラリをインストールします。

### 環境設定要件
- 動作する Python のインストール (3.x を推奨)。
- Python プログラミングの基本的な理解。
- Microsoft PowerPoint に精通していれば役立ちますが、必須ではありません。

## Python 用 Aspose.Slides の設定

開始するには、Python 環境で Aspose.Slides ライブラリを設定します。

**Pip インストール:**
```bash
pip install aspose.slides
```

### ライセンス取得手順
Aspose はさまざまなライセンス オプションを提供します。
- **無料トライアル**全機能を評価するには一時ライセンスをダウンロードしてください。
- **一時ライセンス**短期使用のための無料の一時ライセンスを取得します。
- **購入**長期プロジェクトの場合はサブスクリプションの購入を検討してください。

### 基本的な初期化とセットアップ

インストールしたら、次のように Aspose.Slides を使用して Python スクリプトを初期化します。

```python
import aspose.slides as slides

# プレゼンテーションクラスを、slides.Presentation() でプレゼンテーションとして初期化します。
    # SmartArt を追加するためのコードをここに入力します
```

## 実装ガイド

ここで、Aspose.Slides for Python を使用して PowerPoint に SmartArt を追加およびカスタマイズするプロセスを詳しく説明します。

### SmartArtグラフィックの追加

#### 概要
新しいスライドを作成し、組織図タイプの SmartArt グラフィックを追加します。

```python
import aspose.slides as slides

# slides.Presentation() をプレゼンテーションとして使用して、プレゼンテーション インスタンスを作成します。
    # 指定された寸法のSmartArtを位置（10, 10）に追加します。
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### パラメータとメソッドの目的
- **x, y**: スライド上の SmartArt グラフィックの位置。
- **幅、高さ**適切な視認性を確保するための寸法。
- **レイアウトタイプ**SmartArt レイアウトの種類 (この場合は組織図) を指定します。

### 組織図レイアウトのカスタマイズ

#### 概要
レイアウトを LEFT_HANGING に設定して、SmartArt グラフィックの最初のノードをカスタマイズします。

```python
# 最初のノードを左吊りレイアウトに設定する
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### 主要な設定オプションの説明
- **組織図レイアウトタイプ**ノードの表示方法を決定し、読みやすさと美観を向上させます。

### プレゼンテーションを保存する

最後に、プレゼンテーションを指定したディレクトリに保存します。

```python
# プレゼンテーションを SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\ で保存します。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}