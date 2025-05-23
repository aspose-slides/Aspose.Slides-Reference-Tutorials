---
"description": "Aspose.Slides kullanarak Java Slaytlarında PowerPoint grafiklerine özel hata çubuklarının nasıl ekleneceğini öğrenin. Hassas veri görselleştirmesi için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarına Özel Hata Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarına Özel Hata Ekleme"
"url": "/tr/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarına Özel Hata Ekleme


## Aspose.Slides Kullanarak Java Slaytlarına Özel Hata Çubukları Eklemeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumundaki bir grafiğe özel hata çubuklarının nasıl ekleneceğini öğreneceksiniz. Hata çubukları, bir grafikteki veri noktalarındaki değişkenliği veya belirsizliği göstermek için kullanışlıdır.

## Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Projenizde Aspose.Slides for Java kütüphanesi kurulu ve yapılandırılmış.
- Java geliştirme ortamı kuruldu.

## Adım 1: Boş Bir Sunum Oluşturun

Öncelikle boş bir PowerPoint sunumu oluşturun.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
```

## Adım 2: Bir Balon Grafiği Ekleyin

Daha sonra sunuma bir balon grafiği ekleyeceğiz.

```java
// Bir balon grafiği oluşturma
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Adım 3: Özel Hata Çubukları Ekleyin

Şimdi grafik serisine özel hata çubukları ekleyelim.

```java
// Özel Hata çubukları ekleme ve biçimlerini ayarlama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Adım 4: Hata Çubukları Verilerini Ayarlayın

Bu adımda, grafik serisi veri noktalarına erişeceğiz ve her nokta için özel hata çubuğu değerlerini ayarlayacağız.

```java
// Grafik serisi veri noktalarına erişim ve tek tek noktalar için hata çubuğu değerlerinin ayarlanması
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Grafik serisi noktaları için hata çubuklarının ayarlanması
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Adım 5: Sunumu Kaydedin

Son olarak sunumu özel hata çubuklarıyla kaydedin.

```java
// Sunum kaydediliyor
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

İşte bu kadar! Aspose.Slides for Java kullanarak bir PowerPoint sunumundaki bir grafiğe özel hata çubuklarını başarıyla eklediniz.

## Java Slaytlarında Özel Hata Eklemek İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
try
{
	// Bir balon grafiği oluşturma
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Özel Hata çubukları ekleme ve biçimini ayarlama
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Grafik serisi veri noktasına erişim ve bireysel nokta için hata çubuğu değerlerinin ayarlanması
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Grafik serisi noktaları için hata çubuklarının ayarlanması
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Sunum kaydediliyor
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu kapsamlı eğitimde, Aspose.Slides for Java kullanarak grafiklere özel hata çubukları ekleyerek PowerPoint sunumlarınızı nasıl geliştireceğinizi öğrendiniz. Hata çubukları, veri değişkenliği ve belirsizliği hakkında değerli bilgiler sağlayarak grafiklerinizi daha bilgilendirici ve görsel olarak çekici hale getirir.

## SSS

### Hata çubuklarının görünümünü nasıl özelleştirebilirim?

Hata çubuklarının görünümünü, özelliklerini değiştirerek özelleştirebilirsiniz. `IErrorBarsFormat` çizgi stili, çizgi rengi ve hata çubuğu genişliği gibi nesne.

### Diğer grafik türlerine hata çubukları ekleyebilir miyim?

Evet, Aspose.Slides for Java tarafından desteklenen çubuk grafikler, çizgi grafikler ve dağılım grafikleri dahil olmak üzere çeşitli grafik türlerine hata çubukları ekleyebilirsiniz.

### Her veri noktası için farklı hata çubuğu değerleri nasıl ayarlarım?

Yukarıdaki kodda gösterildiği gibi, veri noktaları arasında döngü oluşturabilir ve her nokta için özel hata çubuğu değerleri ayarlayabilirsiniz.

### Belirli veri noktaları için hata çubuklarını gizlemek mümkün müdür?

Evet, tek tek veri noktaları için hata çubuklarının görünürlüğünü, `setVisible` mülkiyeti `IErrorBarsFormat` nesne.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}