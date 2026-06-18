---
date: '2026-06-08'
description: Aspose.Slides for Java kullanarak .NET sunumlarında grafiklere seri eklemeyi
  ve yığılmış sütun grafiklerini özelleştirmeyi öğrenin.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Aspose.Slides for Java ile .NET'te Grafiklere Seri Ekle
url: /tr/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak .NET Sunumlarında Grafik Özelleştirmeyi Ustalıkla Öğrenme

## Giriş
Veri odaklı sunumlar dünyasında, grafikler ham sayıları etkileyici görsel hikayelere dönüştüren vazgeçilmez araçlardır. Özellikle .NET sunum dosyaları içinde programlı olarak **add series to chart** (grafiğe seri ekleme) yapmanız gerektiğinde görev göz korkutucu görünebilir. Neyse ki, **Aspose.Slides for Java**, grafik oluşturma ve özelleştirmeyi basit hale getiren güçlü, dil bağımsız bir API sunar—hedef formatınız bir .NET PPTX olsa bile. Bu rehber, serileri eklemeyi, yığılmış sütun grafiği oluşturmayı ve boşluk genişliği gibi görsel yönleri ince ayarlamayı adım adım gösterir, böylece dinamik, veri açısından zengin ve profesyonel görünümlü slaytlar üretebilirsiniz.

## Hızlı Yanıtlar
`Presentation` sınıfı bir PPTX dosyasını temsil eder ve `slide.getShapes().addChart(...)` bir grafik şekli ekler. Bir seri eklemek için `chart.getChartData().getSeries().add(...)` kullanın ve `setGapWidth()` boşluğu ayarlar.

- **Bir sunuma başlamak için birincil sınıf nedir?** `Presentation` – bellekte bir PPTX dosyasını temsil eder.  
- **Hangi yöntem bir slayta grafik ekler?** `slide.getShapes().addChart(...)` slaytta grafik nesnesini oluşturur.  
- **Yeni bir seri nasıl eklenir?** `chart.getChartData().getSeries().add(...)` yeni bir veri serisi ekler.  
- **Sütunlar arasındaki boşluk genişliğini değiştirebilir miyim?** Evet—`chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (değer yüzde olarak) çağırın.  
- **Üretim için lisansa ihtiyacım var mı?** Kesinlikle—geçerli bir Aspose.Slides for Java lisansı tüm özelliklerin kilidini açar ve değerlendirme filigranlarını kaldırır.

## “add series to chart” nedir?
Bir grafiğe seri eklemek, grafiğin ayrı bir görsel öğe (ör. ayrı bir sütun grubu) olarak render ettiği yeni bir veri noktası koleksiyonu eklemek anlamına gelir. Her seri kendi değerlerine, renklerine ve biçimlendirmesine sahip olabilir, bu da birden fazla veri kümesinin yan yana karşılaştırılmasını sağlar.

## .NET sunumlarını değiştirmek için Aspose.Slides for Java neden kullanılmalı?
Aspose.Slides for Java, Microsoft Office kurulumuna ihtiyaç duymadan .NET PowerPoint görüntüleyicileriyle tam uyumlu PPTX dosyaları oluşturmanıza veya düzenlemenize olanak tanır. Sunucu taraflı, çapraz platform bir çözümle .NET PPTX dosyaları oluşturmanız veya güncellemeniz, 50+ grafik türünü desteklemesi ve belgeyi belleğe tamamen yüklemeden 500 MB’a kadar dosyaları işlemesi gerektiğinde Aspose.Slides for Java’yı kullanın. API’si Java, Kotlin, Scala veya herhangi bir JVM dilinde çalışır ve .NET geliştiricilerin beklediği aynı çıktıyı üretir.

## Önkoşullar
- **Aspose.Slides for Java** kütüphanesi (sürüm 25.4 veya üzeri).  
- Maven, Gradle veya manuel JAR indirme.  
- Temel Java bilgisi ve PPTX dosya yapısına aşinalık.

## Aspose.Slides for Java Kurulumu
### Maven Kurulumu
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kurulumu
`build.gradle` dosyanıza bu satırı ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, resmi sürüm sayfasından en son JAR dosyasını edinin: [Aspose.Slides for Java sürümleri](https://releases.aspose.com/slides/java/).

**Lisans Edinme**  
Ücretsiz deneme sürümüyle başlamak için geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) indirin. Üretim kullanımı için tüm özelliklerin kilidini açan ve değerlendirme filigranlarını kaldıran tam bir lisans satın alın.

## Adım Adım Uygulama Kılavuzu
Her adımın altında, orijinal öğreticiden değiştirilmemiş kısa bir kod parçacığı ve ardından ne yaptığının açıklamasını bulacaksınız.

### Adım 1: Boş Bir Sunum Oluşturma
`Presentation`, bellekte bir PowerPoint dosyasını temsil eden giriş sınıfıdır.

```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Temiz bir PPTX dosyasıyla başlarız; bu, grafik eklemek için bir tuval sağlar.*

### Adım 2: Slayta Yığılmış Sütun Grafiği Ekleme
`Chart`, bir slayt içindeki grafik şekli temsil eder. `ChartType.StackedColumn` yığılmış sütun grafiğini belirtir.

```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*`addChart` yöntemi bir **yığılmış sütun grafiği** oluşturur ve slaydın sol‑üst köşesine yerleştirir.*

### Adım 3: Grafik'e Seri Ekleme (Ana Hedef)
`Series`, bir grafikte tek bir veri serisini kapsar.

```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Burada **add series to chart** yapıyoruz – her çağrı, ayrı bir sütun grubu olarak görünecek yeni bir veri serisi oluşturur.*

### Adım 4: Grafik'e Kategoriler Ekleme
`Category`, grafik verileri için X‑eksen etiketi tanımlar.

```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Kategoriler X‑eksen etiketleri olarak görev yapar ve her sütuna anlam kazandırır.*

### Adım 5: Seri Verilerini Doldurma
`DataPoint`, belirli bir kategori için bir serinin sayısal değerini tutar.

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
*Veri noktaları, her seriye sayısal değerler sağlar; grafik bu değerleri çubuk yüksekliği olarak gösterir.*

### Adım 6: Grafik Seri Grubu İçin Boşluk Genişliğini Ayarlama
`SeriesGroup`, bir seri grubunun düzen özelliklerini, örneğin boşluk genişliğini kontrol eder.

```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Boşluk genişliğini ayarlamak, özellikle çok sayıda kategori olduğunda okunabilirliği artırır.*

## Yaygın Kullanım Senaryoları
- **Finansal raporlama** – iş birimleri arasında çeyrek gelirlerini karşılaştırın.  
- **Proje panoları** – ekip başına görev tamamlama yüzdelerini gösterin.  
- **Pazarlama analitiği** – kampanya performansını yan yana görselleştirin.  
Bu senaryolar, bireysel kategorilerin toplam içindeki katkılarını vurguladığı için **yığılmış sütun grafik örneği**nden faydalanır.

## Performans İpuçları
- **`Presentation` nesnesini yeniden kullanın** birden fazla grafik oluştururken bellek yükünü azaltmak için.  
- **Veri noktası sayısını sınırlayın** sadece görsel hikaye için gerekli olanlarla; Aspose.Slides 10.000 noktayı işleyebilir, ancak render hızı ~5.000 sonrası düşer.  
- **Nesneleri serbest bırakın** (`presentation.dispose()`) kaydettikten sonra kaynakları boşaltmak ve bellek sızıntılarını önlemek için.

## Sık Sorulan Sorular
**S: Yığılmış sütun dışında başka grafik türleri ekleyebilir miyim?**  
C: Evet, Aspose.Slides çizgi, pasta, alan, radar, balon ve 50+ diğer grafik türünü destekler; hepsi aynı `addChart` yöntemiyle erişilebilir.

**S: .NET çıktısı için ayrı bir lisansa ihtiyacım var mı?**  
C: Hayır, aynı Java lisansı .NET PPTX dosyaları dahil tüm çıktı formatları için çalışır.

**S: Grafiğin renk paletini nasıl değiştiririm?**  
C: `series.getFormat().getFill().setFillType(FillType.Solid)` kullanın ve ardından her seri için istenen `Color` nesnesini ayarlayın.

**S: Veri etiketlerini programlı olarak eklemek mümkün mü?**  
C: Kesinlikle. Her sütunda sayısal değeri göstermek için `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` çağırın.

**S: Mevcut bir sunumu güncellemem gerekirse ne yapmalıyım?**  
C: Dosyayı `new Presentation("existing.pptx")` ile yükleyin, aynı API çağrılarını kullanarak grafiği değiştirin ve diske tekrar kaydedin.

## Sonuç
Artık **add series to chart** nasıl yapılır, **yığılmış sütun grafiği** nasıl oluşturulur ve Aspose.Slides for Java kullanarak .NET sunumlarında görünümü nasıl ince ayar yapılır konusunda eksiksiz, uçtan uca bir kılavuza sahipsiniz. Farklı grafik türleri, renkler ve veri kaynaklarıyla deney yaparak paydaşları etkileyen ve veri odaklı kararları yönlendiren etkileyici görsel raporlar oluşturabilirsiniz.

---

**Son Güncelleme:** 2026-06-08  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (JDK 16)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [.NET'te Aspose.Slides kullanarak Yüzde Tabanlı Yığılmış Sütun Grafikler Nasıl Oluşturulur](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Aspose.Slides .NET ile Ana Grafik Serisi Oluşturma ve Manipülasyonu – Etkili Veri Görselleştirme](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Aspose.Slides .NET ile Belirli Grafik Seri Veri Noktalarını Temizleme](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}