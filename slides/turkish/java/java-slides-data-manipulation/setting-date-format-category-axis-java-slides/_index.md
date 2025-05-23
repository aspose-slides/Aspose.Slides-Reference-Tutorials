---
"description": "Aspose.Slides for Java kullanarak bir PowerPoint grafiğindeki kategori ekseni için tarih biçiminin nasıl ayarlanacağını öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Kategori Ekseninin Tarih Biçimini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Kategori Ekseninin Tarih Biçimini Ayarlama"
"url": "/tr/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Kategori Ekseninin Tarih Biçimini Ayarlama


## Java Slaytlarında Kategori Ekseninde Tarih Biçimini Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint grafiğindeki kategori ekseni için bir tarih biçiminin nasıl ayarlanacağını öğreneceğiz. Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmanıza, düzenlemenize ve yönetmenize olanak tanıyan güçlü bir kütüphanedir.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Java kütüphanesi için Aspose.Slides (buradan indirebilirsiniz) [Burada](https://releases.aspose.com/slides/java/).
2. Java geliştirme ortamı kuruldu.

## Adım 1: Bir PowerPoint Sunumu Oluşturun

Öncelikle, bir grafik ekleyeceğimiz bir PowerPoint sunumu oluşturmamız gerekiyor. Gerekli Aspose.Slides sınıflarını içe aktardığınızdan emin olun.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Slayda Bir Grafik Ekleyin

Şimdi PowerPoint slaydına bir grafik ekleyelim. Bu örnekte Alan grafiği kullanacağız.

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

// Veri serileri ekleme
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Adım 4: Kategori Eksenini Özelleştirin
Şimdi, tarihleri belirli bir biçimde (örneğin, yyyy) görüntüleyecek şekilde kategori eksenini özelleştirelim.

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Adım 5: Sunumu Kaydedin
Son olarak PowerPoint sunumunuzu kaydedin.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Aspose.Slides for Java kullanarak bir PowerPoint grafiğindeki kategori ekseni için bir tarih biçimini başarıyla ayarladınız.

## Java Slaytlarında Kategori Ekseninin Tarih Biçimini Ayarlamak İçin Tam Kaynak Kodu

```java
	// Belgeler dizinine giden yol.
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

Java Slides grafiğindeki kategori ekseni için tarih biçimini Aspose.Slides for Java kullanarak başarıyla özelleştirdiniz. Bu, grafiklerinizde tarih değerlerini istediğiniz biçimde sunmanızı sağlar. Belirli gereksinimlerinize göre daha fazla özelleştirme seçeneğini keşfetmekten çekinmeyin.

## SSS

### Kategori ekseninin tarih biçimini nasıl değiştirebilirim?

Kategori ekseninin tarih biçimini değiştirmek için şunu kullanın: `setNumberFormat` Kategori ekseninde yöntemi kullanın ve "yyyy-AA-gg" veya "AA/yyyy" gibi istenen tarih biçimi desenini sağlayın. Ayarladığınızdan emin olun `setNumberFormatLinkedToSource(false)` varsayılan formatı geçersiz kılmak için.

### Aynı sunumdaki farklı grafikler için farklı tarih biçimleri kullanabilir miyim?

Evet, aynı sunumdaki farklı grafiklerdeki kategori eksenleri için farklı tarih biçimleri ayarlayabilirsiniz. Her grafik için kategori eksenini gerektiği gibi özelleştirebilirsiniz.

### Grafiğe daha fazla veri noktası nasıl eklerim?

Grafiğe daha fazla veri noktası eklemek için şunu kullanın: `getDataPoints().addDataPointForLineSeries` Veri serisi üzerinde yöntem uygulayın ve veri değerlerini sağlayın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}