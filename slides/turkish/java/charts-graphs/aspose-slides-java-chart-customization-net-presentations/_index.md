---
date: '2026-01-17'
description: Aspose.Slides for Java kullanarak .NET sunumlarında grafiklere seri eklemeyi
  ve yığılmış sütun grafiklerini özelleştirmeyi öğrenin.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Aspose.Slides for Java ile .NET’te Grafik’e Seri Ekle
url: /tr/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak .NET Sunumlarında Grafik Özelleştirme Ustalığı

## Giriiş
Veri‑odaklı sunumlar dünyasında, ayrıntılı ham profilli, etkileyici görsel hikayelere dönüştürülen vazgeçilmez araçlardır. **grafiğe seri ekle** süreç programlı olarak, özellikle .NET sunum dosyaları içindeki kayıtlarda görevin gözlenmemesi. Neyse ki, **Aspose.Slides for Java**, grafik oluşturma ve birleştirmeyi basitleştiren güçlü, dil‑bağımsız bir API sunar—hedef formatınız bir .NETPPTX olsa bile.

Bu öğreticide **grafiğe seri ekleme** nasıl eklenecek, yığılmış sütun (yığılmış sütun) tipinde **grafik nasıl eklenir** nasıl ekleyeceğinizi ve bölünmüş genişliği (boşluk genişliği) gibi görsel ayrıntıları nasıl ince ayarlarınızı keşfedeceksiniz. Sonunda dinamik ve doğrulayıcı slaytlar oluşturabilecek ve bunları profesyonel bir görünüme kavuşturabileceksiniz.

**Ne Öğreneceksiniz**
- Aspose.Slides kullanarak boş bir sunum nasıl oluşturulur?
- Bir slayta **yığılmış sütun grafiği ekle** nasıl eklenir
- **Serileri grafiğe ekle** nasıl yapılır ve kategoriler nasıl seçilir
- Veri bölümleri nasıl yapılandırılır ve görsel ayarlar nasıl ayrılır?

Geliştirmenizi ortamı hazırlayalım.

## Hızlı Cevaplar
- **Sunum başlatmak için kullanılan temel sınıf nedir?** `Presentation`
- **Bir slayta grafik ekleyen yöntem hangisidir?** `slide.getShapes().addChart(...)`
- **Yeni bir seri nasıl eklenir?** `chart.getChartData().getSeries().add(...)`
- **Çubuklar arasındaki boşluk genişliğini değiştirebilir miyim?** Evet, seri grubunda `setGapWidth()` kullanarak.
- **Üretim için lisansa ihtiyacım var mı?** Evet, geçerli bir Aspose.Slides for Java lisansı gereklidir.

## “Grafiğe seri eklemek” nedir?

Bir grafiğe seri eklemek, grafiğin ayrı bir görsel öğe (örneğin, yeni bir çubuk, çizgi veya dilim) olarak işleyeceği yeni bir veri koleksiyonu eklemek anlamına gelir. Her serinin kendine ait değerleri, renkleri ve biçimlendirmesi olabilir; bu da birden fazla veri setini yan yana karşılaştırmanıza olanak tanır.

## .NET sunumlarını değiştirmek için neden Aspose.Slides for Java kullanmalısınız?

- **Çapraz platform**: Java kodunu bir kez yazın ve .NET uygulamaları tarafından kullanılan PPTX dosyalarını hedefleyin.

- **COM veya Office bağımlılığı yok**: Sunucularda, CI işlem hatlarında ve konteynerlerde çalışır.

- **Zengin grafik API'si**: Yığılmış sütun grafikleri de dahil olmak üzere 50'den fazla grafik türünü destekler.

## Önkoşullar
1. **Aspose.Slides for Java** kütüphanesi (sürüm 25.4 veya üzeri).

2. Maven veya Gradle derleme aracı veya manuel JAR indirme.

3. Temel Java bilgisi ve PPTX yapısına aşinalık.

## Java için Aspose.Slides Kurulumu
### Maven Kurulumu
Aşağıdaki bağımlılığı `pom.xml` dosyanıza ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kurulumu
`build.gradle` dosyanıza şu satırı ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en son JAR dosyasını resmi sürüm sayfasından indirin: [Aspose.Slides for Java sürümleri](https://releases.aspose.com/slides/java/).

**Lisans Edinimi**
[Buradan](https://purchase.aspose.com/temporary-license/) geçici bir lisans indirerek ücretsiz deneme sürümüyle başlayın. Üretim kullanımı için, tüm özelliklerin kilidini açmak üzere tam bir lisans satın alın.

## Adım Adım Uygulama Kılavuzu
Her adımın altında, ne yaptığının açıklamasıyla birlikte kısa bir kod parçacığı (orijinal eğitimden değiştirilmemiş) bulacaksınız.

### Adım 1: Boş Bir Sunum Oluşturma
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*We start with a clean PPTX file, which gives us a canvas for adding charts.*

### Adım 2: Slayda Yığılmış Sütun Grafiği Ekleyin
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*The `addChart` method creates a **add stacked column chart** and places it at the top‑left corner of the slide.*

### Adım 3: Grafiğe Seriler Ekleyin (Birincil Amaç)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Here we **add series to chart** – each call creates a new data series that will appear as a separate column group.*

### Adım 4: Grafiğe Kategoriler Ekleyin
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Categories act as the X‑axis labels, giving meaning to each column.*

### Adım 5: Seri Verilerini Doldurun
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Data points give each series its numeric values, which the chart will render as bar heights.*

### Adım 6: Grafik Seri Grubu için Boşluk Genişliğini Ayarlayın
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Adjusting the gap width improves readability, especially when many categories are present.*

## Yaygın Kullanım Alanları
- **Finansal raporlama** – İş birimleri genelinde üç aylık gelirleri karşılaştırın.

- **Proje panoları** – Ekip başına görev tamamlama yüzdelerini gösterin.

- **Pazarlama analitiği** – Kampanya performansını yan yana görselleştirin.

## Performans İpuçları
- Bellek yükünü azaltmak için birden fazla grafik oluştururken **`Presentation` nesnesini yeniden kullanın.**

- Görsel hikaye için gerekli olan veri noktalarının sayısını sınırlayın.**

- Kaynakları serbest bırakmak için kaydettikten sonra **nesneleri atın** (`presentation.dispose()`).**

## Sıkça Sorulan Sorular
**S: Yığılmış sütun grafiğinin dışında başka grafik türleri ekleyebilir miyim?**
C: Evet, Aspose.Slides çizgi, pasta, alan ve daha birçok grafik türünü destekler.

**S: .NET çıktısı için ayrı bir lisansa ihtiyacım var mı?**
C: Hayır, aynı Java lisansı, .NET PPTX dosyaları da dahil olmak üzere tüm çıktı formatları için geçerlidir.

**S: Grafiğin renk paletini nasıl değiştiririm?**
C: `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` kullanın ve istediğiniz `Color` değerini ayarlayın.

**S: Veri etiketlerini programatik olarak eklemek mümkün mü?**
C: Kesinlikle. Değerleri görüntülemek için `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` çağrısını yapın.

**S: Mevcut bir sunumu güncellemem gerekirse ne yapmalıyım?**
C: Dosyayı `new Presentation("existing.pptx")` ile yükleyin, grafiği değiştirin ve tekrar kaydedin.

## Sonuç
Artık Aspose.Slides for Java kullanarak .NET sunumlarında **grafiğe seri ekleme**, **yığılmış sütun grafiği** oluşturma ve görünümünü ince ayar yapma konusunda eksiksiz, uçtan uca bir kılavuza sahipsiniz. Paydaşları etkileyen ilgi çekici görsel raporlar oluşturmak için farklı grafik türleri, renkler ve veri kaynaklarıyla deneyler yapın.

---

**Son Güncelleme:** 17.01.2026
**Test Edilen Sürüm:** Aspose.Slides for Java 25.4 (jdk16)
**Yazar:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
