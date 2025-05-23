---
"date": "2025-04-22"
"description": "PythonとAspose.Slidesを使ってドーナツグラフを作成する方法を学びましょう。このステップバイステップガイドでは、セットアップ、カスタマイズ、そしてプレゼンテーションをより効果的にするためのベストプラクティスを解説します。"
"title": "Aspose.Slides を使用して Python でドーナツ チャートを作成する方法 - ステップバイステップ ガイド"
"url": "/ja/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides を使用して Python でドーナツ チャートを作成する方法: ステップバイステップ ガイド

データビジュアライゼーションにおいて、情報を効果的に提示することは、理解と意思決定に大きな影響を与えます。ビジネスプレゼンテーションを作成する場合でも、複雑なデータセットを分析する場合でも、チャートは不可欠なツールです。様々なチャートの種類の中でも、ドーナツチャートは、直感的な中心の穴を通して比例的なデータを表す魅力的な方法です。このステップバイステップガイドでは、プレゼンテーション操作のための強力なライブラリであるAspose.Slidesを使用して、Pythonでドーナツチャートを作成する方法を解説します。

## 学ぶ内容
- Aspose.Slides for Python の設定と使用方法
- プレゼンテーションスライドにドーナツグラフを追加する手順
- チャート内のシリーズとカテゴリのカスタマイズ
- ラベル、色、爆発効果などの視覚要素を調整する
- Aspose.Slides のパフォーマンスを最適化するためのベストプラクティス

## 前提条件
始める前に、次のものを用意してください。
- **Python環境**マシンに Python 3.x がインストールされています。
- **Python 用 Aspose.Slides**: pip を使用してこのライブラリをインストールします。
- **Pythonプログラミングの基礎理解**ループとオブジェクト指向プログラミングの知識が役立ちます。

## Python 用 Aspose.Slides の設定
まず、pip 経由で Aspose.Slides ライブラリをインストールします。

```bash
pip install aspose.slides
```

### ライセンス取得
Asposeは、期間限定で機能を制限なくお試しいただける無料トライアルを提供しています。トライアルの取得方法は以下の通りです。
1. 訪問 [無料トライアル](https://releases.aspose.com/slides/python-net/) ページ。
2. 指示に従って一時ライセンスをダウンロードして適用します。

継続してご利用いただくには、 [購入ページ](https://purchase。aspose.com/buy).

### 基本的な初期化
Aspose.Slides をセットアップした後、次のように初期化します。

```python
import aspose.slides as slides

# Presentation クラスのインスタンスを作成します。
with slides.Presentation() as pres:
    # プレゼンテーションを操作するためのコードをここに記述します。

# 変更を加えたらプレゼンテーションを保存します。
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## 実装ガイド
Aspose.Slides をセットアップしたら、次の手順に従って、プレゼンテーションにスライドごとにドーナツ グラフを追加します。

### 新しいプレゼンテーションの作成とスライドの追加
まず、 `Presentation` クラス：

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # このコンテキスト内でスライドにアクセスしたり、スライドを作成したりします。
```

### 最初のスライドにドーナツグラフを追加する
最初のスライドにアクセスし、 `add_chart` 方法。チャートの種類を次のように指定します。 `DOUGHNUT`位置とサイズとともに:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### チャートデータの設定
既存のデータをクリアし、凡例を非表示にするなどの設定を構成します。

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### シリーズとカテゴリの追加
ドーナツグラフに複数の系列とカテゴリを追加します。特定のプロパティを持つ15の系列を作成する方法は次のとおりです。

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

同様にカテゴリを追加します。

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # 各シリーズにデータ ポイントを追加します。
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # 各データ ポイントの外観をカスタマイズします。
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # 最後のシリーズのラベル設定を構成します。
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### プレゼンテーションを保存する
最後に、プレゼンテーションを指定したディレクトリに保存します。

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## 実用的な応用
ドーナツ グラフは用途が広く、次のようなさまざまなシナリオで使用できます。
1. **予算配分**各部門が割り当てられた資金をどのように使用しているかを表示します。
2. **市場シェア分析**競合製品または競合企業の市場シェアを比較します。
3. **調査結果**好みや満足度に関するアンケートの質問に対する回答を視覚化します。

## パフォーマンスに関する考慮事項
Aspose.Slides を使用する際に最適なパフォーマンスを確保するには:
- 使用後にオブジェクトを適切に破棄することで、メモリの使用量を最小限に抑えます。
- 必要な場合にのみプレゼンテーションをメモリに読み込み、できるだけ早く閉じます。
- 多数のグラフを扱う場合は、スライドのバッチ処理を検討してください。

## 結論
このガイドでは、Aspose.Slides for Python を使って動的なドーナツグラフを作成する方法を学習しました。これらの視覚化は、データをより理解しやすく魅力的なものにすることで、プレゼンテーションの質を高めます。ライブラリの機能をさらに探求し、グラフをさらにカスタマイズして最適化しましょう。

## FAQセクション
1. **ライセンスを購入せずに Aspose.Slides を使用できますか?**
   - はい、評価目的で無料試用ライセンスから始めることができます。
2. **Aspose.Slides でグラフの色を変更するにはどうすればよいですか?**
   - 使用 `fill_format` プロパティを使用して、グラフ要素に希望の色を設定します。
3. **チャートを画像としてエクスポートすることは可能ですか?**
   - はい、ライブラリのレンダリング機能を使用して、グラフを含むスライドを画像形式でレンダリングできます。
4. **グラフを追加するときによくある問題は何ですか?**
   - グラフを保存または表示する前に、すべてのデータ ポイントとカテゴリが適切に追加されていることを確認してください。
5. **Aspose.Slides を他の Python ライブラリと統合できますか?**
   - もちろんです！Pandas などのライブラリと一緒に使用することで、データ操作機能を強化できます。

## リソース
- [Aspose.Slides ドキュメント](https://reference.aspose.com/slides/python-net/)
- [Aspose.Slides をダウンロード](https://releases.aspose.com/slides/python-net/)
- [ライセンスを購入する](https://purchase.aspose.com/buy)
- [無料トライアルと一時ライセンス](https://releases.aspose.com/slides/python-net/)
- [Aspose コミュニティフォーラム](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}