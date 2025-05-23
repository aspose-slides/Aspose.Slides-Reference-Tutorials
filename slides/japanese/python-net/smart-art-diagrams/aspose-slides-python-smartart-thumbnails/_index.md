---
"date": "2025-04-23"
"description": "Aspose.Slides for Python を使用して、サムネイルを効率的に抽出して保存するなど、PowerPoint プレゼンテーションでの SmartArt グラフィックの作成を自動化する方法を学習します。"
"title": "Aspose.Slides for Python を使用して SmartArt サムネイルを作成および取得する方法"
"url": "/ja/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Python を使用して SmartArt サムネイルを作成および取得する方法

## 導入

視覚的に魅力的なプレゼンテーションを作成することは、聴衆の注目を集めるために不可欠です。スライド資料を効果的に強化する方法の一つは、PowerPointプレゼンテーションにSmartArtなどの動的なグラフィックを組み込むことです。これらのビジュアルを自動生成し、サムネイルを抽出する方法をお探しなら、「Aspose.Slides Python」に関するこのガイドが非常に役立ちます。

Aspose.Slides for Python を使えば、SmartArt グラフィックを簡単に作成し、グラフィック内の特定のノードにアクセスし、それらのノードの画像サムネイルを取得し、プロジェクト用に保存することができます。このチュートリアルでは、各ステップを詳しく説明します。

**学習内容:**
- Aspose.Slides for Python をインストールして設定する方法。
- PowerPoint プレゼンテーションで SmartArt グラフィックを作成します。
- SmartArt グラフィック内のノードにアクセスします。
- 特定のノードから画像のサムネイルを抽出して保存します。

始める前に前提条件を詳しく見ていきましょう。

## 前提条件

始める前に、次のものが準備されていることを確認してください。

- **必要なライブラリ:** Aspose.Slides for Pythonが必要です。環境がPython 3.xをサポートしていることを確認してください。
- **環境設定要件:** Python の有効なインストールと、VSCode や PyCharm などの適切な IDE またはテキスト エディター。
- **知識の前提条件:** 関数定義やファイル操作を含む、Python プログラミングの基本的な理解。

## Python 用 Aspose.Slides の設定

まず、Aspose.Slidesライブラリをインストールする必要があります。これはpipを使えば簡単にできます。

```bash
pip install aspose.slides
```

インストール後、すべての機能を制限なくご利用になりたい場合はライセンスを取得してください。無料トライアルから始めることも、一時ライセンスを申請することも、長期使用のためにライセンスを購入することもできます。

Python 環境で Aspose.Slides を初期化するには、スクリプトの先頭でライブラリをインポートします。

```python
import aspose.slides as slides
```

## 実装ガイド

SmartArt サムネイルを作成して取得するためのプロセスを明確な手順に分解してみましょう。

### ステップ1: 新しいプレゼンテーションインスタンスを作成する

まず、プレゼンテーションのインスタンスを作成します。これがSmartArtグラフィックを追加するコンテナになります。

```python
with slides.Presentation() as pres:
```

使用 `with` リソースが適切に管理され、終了時にファイルが自動的に保存されて閉じられるようになります。

### ステップ2: 最初のスライドにSmartArtを追加する

次に、最初のスライドにSmartArtグラフィックを追加します。手順は以下のとおりです。

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

これにより、位置 (10, 10) に 400 x 300 ピクセルの寸法の SmartArt グラフィックの基本サイクル レイアウトが追加されます。

### ステップ3: 2番目のノードにアクセスする

SmartArt内の特定のノードにアクセスします。この例では、2番目のノードにアクセスします。

```python
node = smart.nodes[1]
```

ノードは0から始まるインデックスが付けられます。つまり、 `nodes[1]` リスト内の 2 番目のノードを参照します。

### ステップ4: 画像のサムネイルを取得する

選択したノード内の図形の画像サムネイルを取得するには:

```python
image = node.shapes[0].get_image()
```

これにより、指定された SmartArt ノードから最初の図形の画像をサムネイルとして取得します。

### ステップ5: 取得した画像を保存する

最後に、このサムネイルを JPEG 形式で目的の場所に保存します。

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}