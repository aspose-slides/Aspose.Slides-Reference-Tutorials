---
title: Java Slaytlarında Bireysel Seriler İçin Negatifse Tersine Çevir
linktitle: Java Slaytlarında Bireysel Seriler İçin Negatifse Tersine Çevir
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: PowerPoint sunumlarındaki grafik görsellerini geliştirmek için Aspose.Slides for Java'daki Negatifse Tersine Çevir özelliğini nasıl kullanacağınızı öğrenin.
weight: 11
url: /tr/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Bireysel Seriler için Negatifse Tersine Çevirmeye Giriş

Aspose.Slides for Java, sunumlarla çalışmak için güçlü araçlar sağlar ve ilginç özelliklerden biri de veri serilerinin grafiklerde nasıl görüntüleneceğini kontrol edebilme yeteneğidir. Bu makalede, Java Slaytlar'daki bireysel seriler için "Negatifse Tersine Çevir" özelliğinin nasıl kullanılacağını inceleyeceğiz. Bu özellik, bir grafikteki olumsuz veri noktalarını görsel olarak ayırt etmenize olanak tanıyarak sunumlarınızı daha bilgilendirici ve ilgi çekici hale getirir.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Projenizi Kurma

Başlamak için tercih ettiğiniz Entegre Geliştirme Ortamında (IDE) yeni bir Java projesi oluşturun. Projeniz ayarlandıktan sonra, Java Slaytlar'daki ayrı seriler için "Negatifse Tersine Çevir" özelliğini uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Aspose.Slides Kitaplığını ekleyin

Öncelikle Aspose.Slides kütüphanesini projenize dahil etmeniz gerekiyor. Bunu, kütüphane JAR dosyasını projenizin sınıf yoluna ekleyerek yapabilirsiniz. Bu adım, PowerPoint sunumlarıyla çalışmak için gerekli tüm sınıflara ve yöntemlere erişebilmenizi sağlar.

```java
import com.aspose.slides.*;
```

## Adım 2: Bir Sunu Oluşturun

 Şimdi Aspose.Slides'ı kullanarak yeni bir PowerPoint sunumu oluşturalım. Sunuyu kaydetmek istediğiniz dizini kullanarak tanımlayabilirsiniz.`dataDir` değişken.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 3. Adım: Grafik Ekleme

Bu adımda sunuma bir grafik ekleyeceğiz. Örnek olarak kümelenmiş bir sütun grafiği kullanacağız. İhtiyaçlarınıza göre farklı grafik türlerini seçebilirsiniz.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Adım 4: Grafik Veri Serisini Yapılandırma

Daha sonra grafiğin veri serisini yapılandıracağız. "Negatifse Tersine Çevir" özelliğini göstermek için hem pozitif hem de negatif değerleri içeren örnek bir veri kümesi oluşturacağız.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Seriye veri noktaları ekleme
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## Adım 5: "Negatifse Tersine Çevir" seçeneğini uygulayın

Şimdi "Negatifse Tersine Çevir" özelliğini veri noktalarından birine uygulayacağız. Bu, negatif olduğunda söz konusu veri noktasının rengini görsel olarak tersine çevirir.

```java
series.get_Item(0).setInvertIfNegative(false); // Varsayılan olarak ters çevirme
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Üçüncü veri noktasının rengini ters çevirin
```

## Adım 6: Sunuyu Kaydetme

Son olarak sunuyu belirttiğiniz dizine kaydedin.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Java Slaytlarındaki Bireysel Seriler İçin Negatifse Tersine Çevirme İçin Kaynak Kodunu Tamamlayın

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java'yı kullanarak Java Slides'taki bireysel seriler için "Negatifse Tersine Çevir" özelliğinin nasıl kullanılacağını öğrendik. Bu özellik, grafiklerinizde olumsuz veri noktalarını vurgulamanıza olanak tanıyarak sunumlarınızı görsel olarak daha çekici ve bilgilendirici hale getirmenize olanak tanır.

## SSS'ler

### Aspose.Slides for Java'daki "Negatifse Tersine Çevir" özelliğinin amacı nedir?

Aspose.Slides for Java'daki "Negatifse Ters Çevir" özelliği, grafiklerdeki negatif veri noktalarını görsel olarak ayırt etmenize olanak tanır. Belirli veri noktalarını vurgulayarak sunumlarınızı daha bilgilendirici ve ilgi çekici hale getirmeye yardımcı olur.

### Aspose.Slides kütüphanesini Java projeme nasıl dahil edebilirim?

Aspose.Slides kütüphanesini Java projenize dahil etmek için kütüphane JAR dosyasını projenizin sınıf yoluna eklemeniz gerekir. Bu, PowerPoint sunumlarıyla çalışmak için gerekli tüm sınıflara ve yöntemlere erişmenizi sağlar.

### "Negatifse Tersine Çevir" özelliğiyle farklı grafik türlerini kullanabilir miyim?

Evet, "Negatifse Tersine Çevir" özelliğiyle farklı grafik türlerini kullanabilirsiniz. Bu öğreticide örnek olarak kümelenmiş sütun grafiğini kullandık ancak gereksinimlerinize göre bu özelliği çeşitli grafik türlerine uygulayabilirsiniz.

### Ters çevrilmiş veri noktalarının görünümünü özelleştirmek mümkün mü?

Evet, ters çevrilmiş veri noktalarının görünümünü özelleştirebilirsiniz. Aspose.Slides for Java, "Negatifse Ters Çevir" ayarı nedeniyle ters çevrildiğinde veri noktalarının rengini ve stilini kontrol etme seçenekleri sunar.

### Aspose.Slides for Java belgelerine nereden erişebilirim?

Aspose.Slides for Java belgelerine şu adresten ulaşabilirsiniz:[Burada](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
