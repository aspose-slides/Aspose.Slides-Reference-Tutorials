---
"description": "Java Slaytlarında Aspose.Slides for Java'yı kullanarak grafik çizim alanı boyutlarının nasıl alınacağını öğrenin. PowerPoint otomasyon becerilerinizi geliştirin."
"linktitle": "Java Slaytlarında Grafik Çizim Alanından Genişlik ve Yükseklik Alın"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafik Çizim Alanından Genişlik ve Yükseklik Alın"
"url": "/tr/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik Çizim Alanından Genişlik ve Yükseklik Alın


## giriiş

Grafikler, PowerPoint sunumlarında verileri görselleştirmenin güçlü bir yoludur. Bazen, grafik içindeki öğeleri yeniden boyutlandırma veya yeniden konumlandırma gibi çeşitli nedenlerle bir grafiğin çizim alanının boyutlarını bilmeniz gerekebilir. Bu kılavuz, Java ve Java için Aspose.Slides kullanarak çizim alanının genişliğinin ve yüksekliğinin nasıl elde edileceğini gösterecektir.

## Ön koşullar

Koda dalmadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Kütüphaneyi Aspose web sitesinden indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Ortamı Kurma

Java projenize Aspose.Slides for Java kütüphanesinin eklendiğinden emin olun. Bunu, kütüphaneyi projenizin bağımlılıklarına ekleyerek veya JAR dosyasını elle ekleyerek yapabilirsiniz.

## Adım 2: Bir PowerPoint Sunumu Oluşturma

Bir PowerPoint sunumu oluşturarak ve ona bir slayt ekleyerek başlayalım. Bu, grafiğimiz için bir kapsayıcı görevi görecektir.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Yer değiştirmek `"Your Document Directory"` belge dizininize giden yol ile.

## Adım 3: Grafik Ekleme

Şimdi slayta kümelenmiş bir sütun grafiği ekleyelim. Ayrıca grafik düzenini de doğrulayacağız.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Bu kod, (100, 100) konumunda (500, 350) boyutlarında kümelenmiş bir sütun grafiği oluşturur.

## Adım 4: Arsa Alanı Boyutlarını Elde Etme

Grafiğin çizim alanının genişliğini ve yüksekliğini almak için aşağıdaki kodu kullanabiliriz:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Şimdi değişkenler `x`, `y`, `w`, Ve `h` arsa alanının X-koordinatı, Y-koordinatı, genişliği ve yüksekliği için ilgili değerleri içerir.

## Adım 5: Sunumu Kaydetme

Son olarak sunumu grafikle birlikte kaydedin.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Değiştirdiğinizden emin olun `"Chart_out.pptx"` İstediğiniz çıktı dosya adı ile.

## Java Slaytlarında Grafik Çizim Alanından Genişlik ve Yükseklik Almak İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Sunuyu grafikle kaydet
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu makalede, Java Slaytları'nda Aspose.Slides for Java API'sini kullanarak bir grafiğin çizim alanının genişliğini ve yüksekliğini nasıl elde edeceğinizi ele aldık. Bu bilgi, PowerPoint sunumları içindeki grafiklerinizin düzenini dinamik olarak ayarlamanız gerektiğinde değerli olabilir.

## SSS

### Grafik türünü kümelenmiş sütunlardan farklı bir şeye nasıl değiştirebilirim?

Grafik türünü değiştirerek değiştirebilirsiniz. `ChartType.ClusteredColumn` İstenilen grafik türü numaralandırmasıyla, örneğin `ChartType.Line` veya `ChartType.Pie`.

### Grafiğin diğer özelliklerini değiştirebilir miyim?

Evet, Aspose.Slides for Java API'sini kullanarak veriler, etiketler ve biçimlendirme gibi grafiğin çeşitli özelliklerini değiştirebilirsiniz. Daha fazla ayrıntı için belgelere bakın.

### Aspose.Slides for Java profesyonel PowerPoint otomasyonu için uygun mudur?

Evet, Aspose.Slides for Java, Java uygulamalarında PowerPoint görevlerini otomatikleştirmek için güçlü bir kütüphanedir. Sunumlar, slaytlar, şekiller, grafikler ve daha fazlasıyla çalışmak için kapsamlı özellikler sunar.

### Aspose.Slides for Java hakkında daha fazla bilgi nasıl edinebilirim?

Aspose.Slides for Java dokümantasyon sayfasında kapsamlı dokümanlar ve örnekler bulabilirsiniz [Burada](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}