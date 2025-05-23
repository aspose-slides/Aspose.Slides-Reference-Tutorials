---
"description": "Aspose.Slides for Javaを使用して、PowerPointグラフのカテゴリ軸に日付形式を設定する方法を学びます。ソースコード付きのステップバイステップガイドです。"
"linktitle": "Javaスライドのカテゴリ軸の日付形式を設定する"
"second_title": "Aspose.Slides Java PowerPoint 処理 API"
"title": "Javaスライドのカテゴリ軸の日付形式を設定する"
"url": "/ja/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Javaスライドのカテゴリ軸の日付形式を設定する


## Javaスライドのカテゴリ軸の日付形式設定の概要

このチュートリアルでは、Aspose.Slides for Java を使用して、PowerPoint グラフのカテゴリ軸に日付形式を設定する方法を学びます。Aspose.Slides for Java は、PowerPoint プレゼンテーションをプログラムで作成、操作、管理できる強力なライブラリです。

## 前提条件

始める前に、次のものがあることを確認してください。

1. Aspose.Slides for Javaライブラリ（以下からダウンロードできます） [ここ](https://releases。aspose.com/slides/java/).
2. Java開発環境をセットアップしました。

## ステップ1: PowerPointプレゼンテーションを作成する

まず、グラフを追加するPowerPointプレゼンテーションを作成する必要があります。必要なAspose.Slidesクラスがインポートされていることを確認してください。

```java
// ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ステップ2: スライドにグラフを追加する

それでは、PowerPointスライドにグラフを追加してみましょう。この例では、面グラフを使用します。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## ステップ3: チャートデータの準備

グラフのデータとカテゴリーを設定します。この例では、日付カテゴリーを使用します。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// 日付カテゴリの追加
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// データ系列の追加
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## ステップ4: カテゴリ軸をカスタマイズする
ここで、カテゴリ軸をカスタマイズして、日付を特定の形式 (例: yyyy) で表示してみましょう。

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## ステップ5: プレゼンテーションを保存する
最後に、PowerPoint プレゼンテーションを保存します。

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

これで完了です。Aspose.Slides for Java を使用して、PowerPoint グラフのカテゴリ軸の日付形式を正常に設定できました。

## Javaスライドのカテゴリ軸の日付形式を設定するための完全なソースコード

```java
	// ドキュメント ディレクトリへのパス。
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
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
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

Aspose.Slides for Java を使用して、Java スライドチャートのカテゴリ軸の日付形式をカスタマイズできました。これにより、チャート上で日付値を希望の形式で表示できるようになります。ご自身の要件に合わせて、さらにカスタマイズオプションを自由に検討してみてください。

## よくある質問

### カテゴリ軸の日付形式を変更するにはどうすればよいですか?

カテゴリ軸の日付形式を変更するには、 `setNumberFormat` カテゴリー軸のメソッドを選択し、「yyyy-MM-dd」や「MM/yyyy」などの希望する日付形式パターンを指定します。 `setNumberFormatLinkedToSource(false)` デフォルトの形式を上書きします。

### 同じプレゼンテーション内の異なるグラフに異なる日付形式を使用できますか?

はい、同じプレゼンテーション内の異なるグラフのカテゴリ軸に異なる日付形式を設定できます。必要に応じて、各グラフのカテゴリ軸をカスタマイズするだけです。

### グラフにデータポイントを追加するにはどうすればよいですか?

チャートにデータポイントを追加するには、 `getDataPoints().addDataPointForLineSeries` データ シリーズにメソッドを適用し、データ値を提供します。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}