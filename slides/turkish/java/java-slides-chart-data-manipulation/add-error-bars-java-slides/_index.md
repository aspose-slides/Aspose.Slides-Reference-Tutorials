---
"description": "Aspose.Slides kullanarak Java'da PowerPoint grafiklerine hata çubuklarının nasıl ekleneceğini öğrenin. Hata çubuklarını özelleştirmek için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarına Hata Çubukları Ekleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarına Hata Çubukları Ekleme"
"url": "/tr/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarına Hata Çubukları Ekleme


## Aspose.Slides Kullanarak Java Slaytlarına Hata Çubukları Eklemeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint slaydındaki bir grafiğe hata çubuklarının nasıl ekleneceğini göstereceğiz. Hata çubukları, bir grafikteki veri noktalarının değişkenliği veya belirsizliği hakkında değerli bilgiler sağlar. Bir balon grafiği oluşturacağız ve ona hata çubukları ekleyeceğiz. Başlayalım!

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Kütüphaneyi şuradan indirebilirsiniz: [Aspose web sitesi](https://downloads.aspose.com/slides/java).

## Adım 1: Boş Bir Sunum Oluşturun

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
```

Bu adımda hata çubuklarıyla grafiğimizi ekleyeceğimiz boş bir sunum oluşturuyoruz.

## Adım 2: Bir Balon Grafiği Oluşturun

```java
// Bir balon grafiği oluşturma
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Burada bir kabarcık grafiği oluşturuyoruz ve slayttaki konumunu ve boyutlarını belirliyoruz.

## Adım 3: Hata Çubukları Ekleme ve Biçim Ayarlama

```java
// Hata çubuklarının eklenmesi ve biçiminin ayarlanması
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

Bu adımda, grafiğe hata çubukları ekleriz ve biçimlerini ayarlarız. Değerleri, türleri ve diğer özellikleri değiştirerek hata çubuklarını özelleştirebilirsiniz.

- `errBarX` X ekseni boyunca hata çubuklarını temsil eder.
- `errBarY` Y ekseni boyunca hata çubuklarını temsil eder.
- Hem X hem de Y hata çubuklarını görünür hale getiriyoruz.
- `setValueType` hata çubukları için değer türünü belirtir (örneğin, Sabit veya Yüzde).
- `setValue` hata çubukları için değeri ayarlar.
- `setType` hata çubuklarının türünü tanımlar (örneğin, Artı veya Eksi).
- Hata çubuğu çizgilerinin genişliğini kullanarak ayarladık `getFormat().getLine().setWidth(2)`.
- `setEndCap` hata çubuklarına uç kapaklarının dahil edilip edilmeyeceğini belirtir.

## Adım 4: Sunumu Kaydedin

```java
// Sunum kaydediliyor
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Son olarak, eklenen hata çubuklarıyla sunumu belirtilen bir yere kaydediyoruz.

İşte bu kadar! Aspose.Slides for Java kullanarak bir PowerPoint slaydındaki bir grafiğe hata çubukları başarıyla eklediniz.

## Java Slaytlarında Hata Çubukları Eklemek İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Boş sunum oluşturma
Presentation presentation = new Presentation();
try
{
	// Bir balon grafiği oluşturma
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Hata çubuklarının eklenmesi ve biçiminin ayarlanması
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

Bu eğitimde, Aspose.Slides for Java kullanarak grafiklere hata çubukları ekleyerek PowerPoint sunumlarınızı nasıl geliştirebileceğinizi inceledik. Hata çubukları, veri değişkenliği ve belirsizlikleri hakkında değerli içgörüler sunarak sunumlarınızı daha bilgilendirici ve görsel olarak çekici hale getirir.

## SSS

### Hata çubuklarının görünümünü nasıl daha fazla özelleştirebilirim?

Adım 3'te gösterildiği gibi, çizgi stili, renk ve genişlik gibi özelliklerini değiştirerek hata çubuklarını özelleştirebilirsiniz.

### Farklı grafik türlerine hata çubukları ekleyebilir miyim?

Evet, Aspose.Slides for Java tarafından desteklenen çeşitli grafik türlerine hata çubukları ekleyebilirsiniz. Sadece istediğiniz grafik türünü oluşturun ve aynı hata çubuğu özelleştirme adımlarını izleyin.

### Slayttaki grafiğin konumunu ve boyutunu nasıl ayarlayabilirim?

Parametreleri ayarlayarak grafiğin konumunu ve boyutlarını kontrol edebilirsiniz. `addChart` Yöntem, Adım 2'de gösterildiği gibi.

### Aspose.Slides for Java hakkında daha fazla bilgiyi nerede bulabilirim?

Şuraya başvurabilirsiniz: [Java belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/) Kütüphanenin kullanımı hakkında detaylı bilgi için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}