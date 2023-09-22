---
title: Java Slaytlarında Grafik Çizim Alanından Genişlik ve Yükseklik Alma
linktitle: Java Slaytlarında Grafik Çizim Alanından Genişlik ve Yükseklik Alma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'ta grafik çizim alanı boyutlarını nasıl alacağınızı öğrenin. PowerPoint otomasyon becerilerinizi geliştirin.
type: docs
weight: 21
url: /tr/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

## giriiş

Grafikler, PowerPoint sunumlarındaki verileri görselleştirmenin güçlü bir yoludur. Bazen, grafik içindeki öğeleri yeniden boyutlandırmak veya yeniden konumlandırmak gibi çeşitli nedenlerle grafiğin çizim alanının boyutlarını bilmeniz gerekebilir. Bu kılavuz, Java ve Aspose.Slides for Java kullanılarak çizim alanının genişliğinin ve yüksekliğinin nasıl elde edileceğini gösterecektir.

## Önkoşullar

 Koda dalmadan önce Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan ve kurulduğundan emin olun. Kütüphaneyi Aspose web sitesinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Ortamı Ayarlama

Aspose.Slides for Java kütüphanesinin Java projenize eklendiğinden emin olun. Bunu, kütüphaneyi projenizin bağımlılıklarına dahil ederek veya JAR dosyasını manuel olarak ekleyerek yapabilirsiniz.

## Adım 2: PowerPoint Sunusu Oluşturma

Bir PowerPoint sunusu oluşturup ona bir slayt ekleyerek başlayalım. Bu, grafiğimiz için kap görevi görecek.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Yer değiştirmek`"Your Document Directory"` belge dizininizin yolu ile.

## 3. Adım: Grafik Ekleme

Şimdi slayta kümelenmiş bir sütun grafiği ekleyelim. Ayrıca grafik düzenini de doğrulayacağız.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Bu kod, (100, 100) konumunda ve boyutları (500, 350) olan kümelenmiş bir sütun grafiği oluşturur.

## Adım 4: Çizim Alanı Boyutlarını Alma

Grafiğin çizim alanının genişliğini ve yüksekliğini almak için aşağıdaki kodu kullanabiliriz:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Şimdi değişkenler`x`, `y`, `w` , Ve`h` çizim alanının X koordinatı, Y koordinatı, genişliği ve yüksekliği için ilgili değerleri içerir.

## Adım 5: Sunumu Kaydetme

Son olarak sunumu grafikle birlikte kaydedin.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Değiştirdiğinizden emin olun`"Chart_out.pptx"` İstediğiniz çıktı dosyası adı ile.

## Java Slaytlarında Grafik Çizim Alanından Genişlik ve Yükseklik Almak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
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

Bu makalede, Aspose.Slides for Java API'sini kullanarak Java Slides'ta bir grafiğin çizim alanının genişliğini ve yüksekliğini nasıl elde edeceğimizi ele aldık. Bu bilgiler, PowerPoint sunumlarındaki grafiklerinizin düzenini dinamik olarak ayarlamanız gerektiğinde değerli olabilir.

## SSS'ler

### Grafik türünü kümelenmiş sütunlardan başka bir şeye nasıl değiştirebilirim?

 Grafik türünü değiştirerek değiştirebilirsiniz.`ChartType.ClusteredColumn` istenen grafik türü numaralandırmasıyla, örneğin`ChartType.Line` veya`ChartType.Pie`.

### Grafiğin diğer özelliklerini değiştirebilir miyim?

Evet, Aspose.Slides for Java API'sini kullanarak grafiğin veriler, etiketler ve formatlama gibi çeşitli özelliklerini değiştirebilirsiniz. Daha fazla ayrıntı için belgelere bakın.

### Aspose.Slides for Java profesyonel PowerPoint otomasyonuna uygun mu?

Evet, Aspose.Slides for Java, Java uygulamalarındaki PowerPoint görevlerini otomatikleştirmek için kullanılan güçlü bir kütüphanedir. Sunumlar, slaytlar, şekiller, grafikler ve daha fazlasıyla çalışmak için kapsamlı özellikler sağlar.

### Aspose.Slides for Java hakkında nasıl daha fazla bilgi edinebilirim?

 Aspose.Slides for Java dokümantasyon sayfasında kapsamlı dokümantasyon ve örnekler bulabilirsiniz.[Burada](https://reference.aspose.com/slides/java/).
