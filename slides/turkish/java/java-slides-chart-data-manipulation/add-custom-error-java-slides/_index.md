---
title: Java Slaytlarına Özel Hata Ekleme
linktitle: Java Slaytlarına Özel Hata Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java Slides'daki PowerPoint grafiklerine özel hata çubuklarının nasıl ekleneceğini öğrenin. Hassas veri görselleştirmesi için kaynak kodlu adım adım kılavuz.
weight: 11
url: /tr/java/chart-data-manipulation/add-custom-error-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides Kullanarak Java Slaytlarına Özel Hata Çubukları Eklemeye Giriş

Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumundaki bir grafiğe özel hata çubuklarının nasıl ekleneceğini öğreneceksiniz. Hata çubukları, bir grafikteki veri noktalarındaki değişkenliği veya belirsizliği görüntülemek için kullanışlıdır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Slides for Java kütüphanesi projenizde kurulu ve yapılandırılmıştır.
- Bir Java geliştirme ortamı kuruldu.

## 1. Adım: Boş Bir Sunu Oluşturun

Öncelikle boş bir PowerPoint sunusu oluşturun.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
```

## 2. Adım: Kabarcık Grafiği Ekleyin

Daha sonra sunuma bir kabarcık grafiği ekleyeceğiz.

```java
// Kabarcık grafiği oluşturma
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## 3. Adım: Özel Hata Çubukları Ekleyin

Şimdi grafik serisine özel hata çubukları ekleyelim.

```java
// Özel Hata çubukları ekleme ve formatlarını ayarlama
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Adım 4: Hata Çubukları Verilerini Ayarlayın

Bu adımda grafik serisi veri noktalarına erişeceğiz ve her nokta için özel hata çubuğu değerlerini ayarlayacağız.

```java
// Grafik serisi veri noktalarına erişme ve tek tek noktalar için hata çubuğu değerlerini ayarlama
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Grafik serisi noktaları için hata çubuklarını ayarlama
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Adım 5: Sunuyu Kaydetme

Son olarak sunuyu özel hata çubuklarıyla kaydedin.

```java
// Sunum kaydediliyor
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Bu kadar! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir grafiğe özel hata çubuklarını başarıyla eklediniz.

## Java Slaytlarına Özel Hata Eklemek İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
try
{
	// Kabarcık grafiği oluşturma
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Özel Hata çubukları ekleme ve biçimini ayarlama
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Grafik serisi veri noktasına erişme ve tek tek noktalar için hata çubukları değerlerini ayarlama
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Grafik serisi noktaları için hata çubuklarını ayarlama
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

Bu kapsamlı eğitimde Aspose.Slides for Java kullanarak grafiklere özel hata çubukları ekleyerek PowerPoint sunumlarınızı nasıl geliştireceğinizi öğrendiniz. Hata çubukları, veri değişkenliği ve belirsizliğine ilişkin değerli bilgiler sağlayarak grafiklerinizi daha bilgilendirici ve görsel olarak çekici hale getirir.

## SSS'ler

### Hata çubuklarının görünümünü nasıl özelleştiririm?

 Özelliklerini değiştirerek hata çubuklarının görünümünü özelleştirebilirsiniz.`IErrorBarsFormat` çizgi stili, çizgi rengi ve hata çubuğu genişliği gibi nesne.

### Diğer grafik türlerine hata çubukları ekleyebilir miyim?

Evet, Aspose.Slides for Java tarafından desteklenen çubuk grafikler, çizgi grafikler ve dağılım grafikleri dahil çeşitli grafik türlerine hata çubukları ekleyebilirsiniz.

### Her veri noktası için farklı hata çubuğu değerlerini nasıl ayarlarım?

Yukarıdaki kodda gösterildiği gibi, veri noktaları arasında geçiş yapabilir ve her nokta için özel hata çubuğu değerleri ayarlayabilirsiniz.

### Belirli veri noktalarına ilişkin hata çubuklarını gizlemek mümkün müdür?

 Evet, ayrı ayrı veri noktaları için hata çubuklarının görünürlüğünü ayarlayarak kontrol edebilirsiniz.`setVisible` mülkiyeti`IErrorBarsFormat` nesne.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
