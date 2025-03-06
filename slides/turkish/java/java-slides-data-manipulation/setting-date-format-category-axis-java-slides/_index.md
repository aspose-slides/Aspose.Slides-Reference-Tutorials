---
title: Java Slaytlarında Kategori Ekseni İçin Tarih Formatını Ayarlama
linktitle: Java Slaytlarında Kategori Ekseni İçin Tarih Formatını Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint grafiğinde kategori ekseni için tarih formatını nasıl ayarlayacağınızı öğrenin. Kaynak koduyla adım adım kılavuz.
weight: 26
url: /tr/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarında Kategori Ekseni İçin Tarih Formatını Ayarlamaya Giriş

Bu eğitimde Aspose.Slides for Java'yı kullanarak bir PowerPoint grafiğinde kategori ekseni için tarih formatını nasıl ayarlayacağımızı öğreneceğiz. Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmanıza, değiştirmenize ve yönetmenize olanak tanıyan güçlü bir kitaplıktır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Slides for Java kütüphanesi (şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/java/).
2. Java geliştirme ortamı kuruldu.

## 1. Adım: PowerPoint Sunusu Oluşturun

Öncelikle grafik ekleyeceğimiz bir PowerPoint sunumu oluşturmamız gerekiyor. Gerekli Aspose.Slides sınıflarını içe aktardığınızdan emin olun.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Slayta Grafik Ekleme

Şimdi PowerPoint slaytına bir grafik ekleyelim. Bu örnekte Alan grafiğini kullanacağız.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Adım 3: Grafik Verilerini Hazırlayın

Grafik verilerini ve kategorilerini ayarlayacağız. Bu örnekte tarih kategorilerini kullanacağız.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Tarih kategorileri ekleme
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Veri serisi ekleme
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Adım 4: Kategori Eksenini Özelleştirin
Şimdi kategori eksenini, tarihleri belirli bir formatta (örneğin, yyyy) gösterecek şekilde özelleştirelim.

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Adım 5: Sunuyu Kaydetme
Son olarak PowerPoint sunumunu kaydedin.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak PowerPoint grafiğindeki kategori ekseni için tarih formatını başarıyla ayarladınız.

## Java Slaytlarında Kategori Ekseni İçin Tarih Formatını Ayarlamak İçin Tam Kaynak Kodu

```java
	// Belgeler dizininin yolu.
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

##Çözüm

Aspose.Slides for Java'yı kullanarak Java Slides grafiğindeki kategori ekseninin tarih formatını başarıyla özelleştirdiniz. Bu sayede tarih değerlerini istediğiniz formatta grafiklerinizde sunabilirsiniz. Özel gereksinimlerinize göre daha fazla özelleştirme seçeneğini keşfetmekten çekinmeyin.

## SSS'ler

### Kategori ekseninin tarih biçimini nasıl değiştiririm?

 Kategori ekseninin tarih biçimini değiştirmek için`setNumberFormat` yöntemini kategori ekseninde seçin ve "yyyy-AA-gg" veya "AA/yyyy" gibi istenen tarih formatı modelini sağlayın. Ayarladığınızdan emin olun`setNumberFormatLinkedToSource(false)` Varsayılan biçimi geçersiz kılmak için.

### Aynı sunumda farklı grafikler için farklı tarih formatlarını kullanabilir miyim?

Evet, aynı sunum içerisinde farklı grafiklerde kategori eksenleri için farklı tarih formatları ayarlayabilirsiniz. Her grafik için kategori eksenini gerektiği gibi özelleştirmeniz yeterlidir.

### Grafiğe nasıl daha fazla veri noktası eklerim?

 Grafiğe daha fazla veri noktası eklemek için`getDataPoints().addDataPointForLineSeries`veri serisi üzerinde yöntem ve veri değerlerini sağlar.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
