---
title: Java スライドのカテゴリ軸の日付形式を設定する
linktitle: Java スライドのカテゴリ軸の日付形式を設定する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint グラフのカテゴリ軸の日付形式を設定する方法を学習します。ソースコード付きのステップバイステップガイド。
type: docs
weight: 26
url: /ja/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## Java スライドのカテゴリ軸の日付形式の設定の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint グラフのカテゴリ軸の日付形式を設定する方法を学習します。 Aspose.Slides for Java は、PowerPoint プレゼンテーションをプログラムで作成、操作、管理できる強力なライブラリです。

## 前提条件

始める前に、以下のものがあることを確認してください。

1.  Aspose.Slides for Java ライブラリ (次からダウンロードできます)[ここ](https://releases.aspose.com/slides/java/).
2. Java開発環境のセットアップ。

## ステップ 1: PowerPoint プレゼンテーションを作成する

まず、グラフを追加する PowerPoint プレゼンテーションを作成する必要があります。必要な Aspose.Slides クラスがインポートされていることを確認してください。

```java
//ドキュメントディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ 2: スライドにグラフを追加する

次に、PowerPoint スライドにグラフを追加しましょう。この例では面グラフを使用します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## ステップ 3: チャート データを準備する

チャートデータとカテゴリーを設定していきます。この例では、日付カテゴリを使用します。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

//日付カテゴリの追加
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

//データシリーズの追加
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## ステップ 4: カテゴリ軸をカスタマイズする
次に、特定の形式 (yyyy など) で日付を表示するようにカテゴリ軸をカスタマイズしましょう。

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## ステップ 5: プレゼンテーションを保存する
最後に、PowerPoint プレゼンテーションを保存します。

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

それでおしまい！ Aspose.Slides for Java を使用して、PowerPoint グラフのカテゴリ軸の日付形式を正常に設定できました。

## Java スライドのカテゴリ軸の日付形式を設定するための完全なソース コード

```java
	//ドキュメントディレクトリへのパス。
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

＃＃結論

Aspose.Slides for Java を使用して、Java Slides グラフのカテゴリ軸の日付形式を正常にカスタマイズしました。これにより、日付値をグラフ上に希望の形式で表示できるようになります。特定の要件に基づいて、さらにカスタマイズ オプションを自由に検討してください。

## よくある質問

### カテゴリ軸の日付形式を変更するにはどうすればよいですか?

カテゴリ軸の日付形式を変更するには、`setNumberFormat`カテゴリ軸のメソッドを選択し、「yyyy-MM-dd」や「MM/yyyy」など、目的の日付形式パターンを指定します。必ず設定してください`setNumberFormatLinkedToSource(false)`デフォルトの形式をオーバーライドします。

### 同じプレゼンテーション内の異なるグラフに異なる日付形式を使用できますか?

はい、同じプレゼンテーション内の異なるグラフのカテゴリ軸に異なる日付形式を設定できます。必要に応じて、各グラフのカテゴリ軸をカスタマイズするだけです。

### グラフにさらにデータ ポイントを追加するにはどうすればよいですか?

グラフにさらにデータ ポイントを追加するには、`getDataPoints().addDataPointForLineSeries`データ系列に対するメソッドを使用し、データ値を提供します。