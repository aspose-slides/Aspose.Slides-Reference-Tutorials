---
"date": "2025-04-22"
"description": "Aspose.Slides for Python を使って、PowerPoint プレゼンテーションのグラフにパーセンテージラベルを簡単に表示する方法を学びましょう。データの視覚化を強化するのに最適です。"
"title": "Aspose.Slides for Python を使用してチャートにパーセンテージラベルを表示する方法 - 包括的なガイド"
"url": "/ja/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python を使用してチャートにパーセンテージラベルを表示する方法

## 導入

プレゼンテーションやレポートでは、データを効果的に視覚化することが非常に重要です。特に、割合や分布を明確に強調したい場合はなおさらです。しかし、もしこれらのパーセンテージをグラフに直接表示する必要がある場合はどうでしょうか？この包括的なガイドでは、 **Python 用 Aspose.Slides** パーセンテージ値をグラフ上のラベルとして簡単に表示できます。

### 学習内容:
- Aspose.Slides for Python を使用して PowerPoint プレゼンテーションにグラフを作成し、埋め込む方法。
- グラフ上でデータ ポイントをパーセンテージ ラベルとして表示します。
- PowerPoint プレゼンテーションを効率的に保存および管理します。

データに洞察力に富んだビジュアルを追加する準備はできましたか? コードに進む前に、まず必要なものを確認しましょう。

## 前提条件

始める前に、以下のものを用意してください。
- **Python 用 Aspose.Slides**: このライブラリは、PowerPoint プレゼンテーションをプログラムで作成および操作するために不可欠です。
- **Python環境**Python プログラミングと環境設定に関する基本的な理解。
- **PIP パッケージマネージャー**Aspose.Slides をインストールするために使用されます。

## Python 用 Aspose.Slides の設定

Aspose.Slides の使用を開始するには、まずインストールする必要があります。

```bash
pip install aspose.slides
```

### ライセンス取得手順:
無料トライアルで始めるか、一時ライセンスを取得してAspose.Slidesの全機能をお試しください。さらに長期間ご利用いただくには、サブスクリプションのご購入をご検討ください。

#### 基本的な初期化とセットアップ

インストールしたら、次のようにプレゼンテーション環境を初期化します。

```python
import aspose.slides as slides

# プレゼンテーションオブジェクトを初期化する
def create_presentation():
    with slides.Presentation() as presentation:
        # ここにあなたのコード
```

## 実装ガイド

設定が完了したら、グラフにパーセンテージを表示してみましょう。

### グラフの作成とデータの追加

#### 概要
各データ ポイントのパーセンテージ ラベルが付いた積み上げ縦棒グラフを作成し、閲覧者が正確な割合を一目で確認できるようにします。

##### ステップ1：スライドにグラフを追加する

```python
# プレゼンテーションの最初のスライドにアクセスする
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # 積み上げ縦棒グラフを追加する
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

このコードスニペットは、最初のスライドに基本的なグラフを追加します。 `add_chart` メソッドは、グラフの種類と位置およびサイズを指定します。

##### ステップ2: カテゴリの合計値を計算する

```python
def calculate_totals(chart):
    total_for_category = []
    # 各カテゴリのすべての系列の値を合計します
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

このループは、シリーズ全体のすべてのデータ ポイントの合計を計算します。これは、パーセンテージ計算に重要です。

#### パーセンテージラベルの設定

##### ステップ3: シリーズデータポイントを構成する

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # 不要な情報を非表示にするためにデフォルトのラベルオプションを設定する
        series.labels.default_data_label_format.show_legend_key = False
        
        # パーセンテージラベルを計算して設定する
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # パーセンテージ値を含むテキスト部分を作成する
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # 既存のラベルをクリアし、新しいパーセンテージラベルを追加します
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # 他のデータラベル要素を非表示にする
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

このセグメントは、各データ ポイントを処理して合計に対する割合を計算し、それをラベルとして割り当てます。

### プレゼンテーションを保存する

```python
def save_presentation(presentation, output_directory):
    # 変更を加えたプレゼンテーションを保存する
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}