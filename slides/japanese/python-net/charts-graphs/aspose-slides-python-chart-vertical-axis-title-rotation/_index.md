---
"date": "2025-04-23"
"description": "Aspose.Slides for Python を使用してプレゼンテーション内のグラフ タイトルの回転角度を調整し、読みやすさと美しさを向上させる方法を学習します。"
"title": "Aspose.Slides for Python でグラフの縦軸タイトルの回転を設定する方法"
"url": "/ja/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python でグラフの縦軸タイトルの回転を設定する方法

## 導入

データプレゼンテーションでは、グラフの読みやすさを向上させることが非常に重要です。Aspose.Slides for Python を使用してグラフの縦軸タイトルの回転角度を調整することで、タイトルをスライドにきれいに配置したり、目立たせたりすることができます。このチュートリアルでは、回転角度を設定することで、機能性と視覚的な魅力の両方を高める方法を説明します。

**学習内容:**
- Aspose.Slides for Python をインストールして構成する方法。
- スライド内にグラフを追加してカスタマイズする手順。
- グラフタイトルの回転角度を設定するテクニック。
- データ視覚化におけるこれらの機能の実際のアプリケーション。

実装に進む前に、前提条件について説明することから始めましょう。

## 前提条件

始める前に、次のものを用意してください。
- **Python環境**Python 3.x をインストールする [python.org](https://www。python.org/).
- **Aspose.Slides ライブラリ**プレゼンテーションを効果的に操作するには、pip 経由でインストールします。
- **Pythonプログラミングの基礎知識**Python の構文とファイル操作に精通していると、理解しやすくなります。

## Python 用 Aspose.Slides の設定

Aspose.Slidesを使用するには、pipを使ってインストールしてください。ターミナルまたはコマンドプロンプトを開き、以下を実行してください。

```bash
pip install aspose.slides
```

### ライセンス取得手順

Aspose はさまざまなライセンス オプションを提供します。
- **無料トライアル**試用版をダウンロードするには [Asposeのリリースページ](https://releases。aspose.com/slides/python-net/).
- **一時ライセンス**拡張機能の一時ライセンスを取得するには、 [購入ポータル](https://purchase。aspose.com/temporary-license/).
- **購入**ツールが不可欠と思われる場合は、購入を検討してください。 [Aspose 購入ページ](https://purchase。aspose.com/buy).

#### 基本的な初期化とセットアップ

Python スクリプトで Aspose.Slides を初期化する方法は次のとおりです。

```python
import aspose.slides as slides

# プレゼンテーションオブジェクトを作成する
def main():
    with slides.Presentation() as pres:
        # ここにコードを入力します
        pass

if __name__ == "__main__":
    main()
```

## 実装ガイド

### グラフの追加とカスタマイズ

#### 概要

このセクションでは、スライドに集合縦棒グラフを追加し、縦軸タイトルの回転角度を設定してカスタマイズします。

#### 手順:

##### ステップ1: 集合縦棒グラフを追加する

まず、定義された寸法を持つ特定の座標にチャートを追加します。

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # スライド1に集合縦棒グラフを追加する
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### ステップ2: 縦軸のタイトルを設定する

垂直軸タイトルの回転角度を有効にして設定します。

```python
def configure_chart(chart):
    # 縦軸のタイトルを有効にする
    chart.axes.vertical_axis.has_title = True
    
    # 回転角度を90度に設定する
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### ステップ3: プレゼンテーションを保存する

最後に、変更を加えたプレゼンテーションを保存します。

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # プレゼンテーションを保存する
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}