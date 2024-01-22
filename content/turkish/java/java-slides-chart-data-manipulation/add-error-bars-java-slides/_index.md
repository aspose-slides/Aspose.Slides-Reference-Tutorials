---
title: Java Slaytlarına Hata Çubukları Ekleme
linktitle: Java Slaytlarına Hata Çubukları Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java'da PowerPoint grafiklerine hata çubuklarının nasıl ekleneceğini öğrenin. Hata çubuklarını özelleştirmek için kaynak kodlu adım adım kılavuz.
type: docs
weight: 13
url: /tr/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Aspose.Slides Kullanarak Java Slaytlarına Hata Çubukları Eklemeye Giriş

Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint slaytındaki bir grafiğe hata çubuklarının nasıl ekleneceğini göstereceğiz. Hata çubukları, bir grafikteki veri noktalarının değişkenliği veya belirsizliği hakkında değerli bilgiler sağlar. Bir kabarcık grafiği oluşturacağız ve ona hata çubukları ekleyeceğiz. Başlayalım!

## Önkoşullar

Başlamadan önce Java projenizde Aspose.Slides for Java kitaplığının kurulu olduğundan ve kurulduğundan emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Web sitesi](https://downloads.aspose.com/slides/java).

## 1. Adım: Boş Bir Sunu Oluşturun

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
```

Bu adımda hata çubuklarının bulunduğu grafiğimizi ekleyeceğimiz boş bir sunum oluşturuyoruz.

## 2. Adım: Kabarcık Grafiği Oluşturun

```java
// Kabarcık grafiği oluşturma
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Burada bir kabarcık grafiği oluşturup slayttaki konumunu ve boyutlarını belirtiyoruz.

## 3. Adım: Hata Çubukları Ekleme ve Formatı Ayarlama

```java
// Hata çubukları ekleme ve formatını ayarlama
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

Bu adımda grafiğe hata çubukları ekliyoruz ve formatlarını ayarlıyoruz. Değerleri, türleri ve diğer özellikleri değiştirerek hata çubuklarını özelleştirebilirsiniz.

- `errBarX` X ekseni boyunca hata çubuklarını temsil eder.
- `errBarY` Y ekseni boyunca hata çubuklarını temsil eder.
- Hem X hem de Y hata çubuklarını görünür hale getiriyoruz.
- `setValueType` hata çubukları için değer türünü belirtir (örneğin, Sabit veya Yüzde).
- `setValue` hata çubuklarının değerini ayarlar.
- `setType` hata çubuklarının türünü tanımlar (örn. Artı veya Eksi).
-  Hata çubuğu çizgilerinin genişliğini kullanarak ayarlıyoruz.`getFormat().getLine().setWidth(2)`.
- `setEndCap`hata çubuklarına uç kapaklarının eklenip eklenmeyeceğini belirtir.

## 4. Adım: Sunuyu Kaydetme

```java
// Sunum kaydediliyor
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Son olarak, eklenen hata çubuklarıyla birlikte sunumu belirtilen konuma kaydediyoruz.

Bu kadar! Aspose.Slides for Java'yı kullanarak PowerPoint slaytındaki bir grafiğe hata çubuklarını başarıyla eklediniz.

## Java Slaytlarına Hata Çubukları Eklemek İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
try
{
	// Kabarcık grafiği oluşturma
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Hata çubukları ekleme ve formatını ayarlama
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Sunum kaydediliyor
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak grafiklere hata çubukları ekleyerek PowerPoint sunumlarınızı nasıl geliştirebileceğinizi araştırdık. Hata çubukları, veri değişkenliği ve belirsizliklerine ilişkin değerli bilgiler sağlayarak sunumlarınızı daha bilgilendirici ve görsel olarak çekici hale getirir.

## SSS'ler

### Hata çubuklarının görünümünü nasıl daha da özelleştirebilirim?

Hata çubuklarını, 3. Adımda gösterildiği gibi çizgi stili, renk ve genişlik gibi özelliklerini değiştirerek özelleştirebilirsiniz.

### Farklı grafik türlerine hata çubukları ekleyebilir miyim?

Evet, Aspose.Slides for Java'nın desteklediği çeşitli grafik türlerine hata çubukları ekleyebilirsiniz. İstenilen grafik türünü oluşturmanız ve aynı hata çubuğu özelleştirme adımlarını uygulamanız yeterlidir.

### Slayttaki grafiğin konumunu ve boyutunu nasıl ayarlayabilirim?

 Parametreleri ayarlayarak grafiğin konumunu ve boyutlarını kontrol edebilirsiniz.`addChart` Yöntem, Adım 2'de gösterildiği gibi.

### Aspose.Slides for Java hakkında daha fazla bilgiyi nerede bulabilirim?

 Şuraya başvurabilirsiniz:[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/) Kütüphanenin kullanımı hakkında detaylı bilgi için.