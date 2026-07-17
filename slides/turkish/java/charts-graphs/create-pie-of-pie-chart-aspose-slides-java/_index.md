---
date: '2026-07-17'
description: Aspose.Slides for Java kullanarak Pie of Pie chart oluşturup PowerPoint'e
  chart eklemeyi öğrenin. İçerir setup, code, customization ve saving as PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java ile PowerPoint'e chart ekleyin. Bu kılavuz,
  birkaç dakika içinde Pie of Pie chart oluşturmayı, customize etmeyi ve PPTX olarak
  kaydetmeyi gösterir.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: PowerPoint'e Chart Ekle – Java'da Pie of Pie Chart Oluştur
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: PowerPoint'e Chart Ekle – Java'da Aspose.Slides ile Pie of Pie Chart Oluştur
url: /tr/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint'e Grafik Ekle – Java ile Aspose.Slides Kullanarak Pie of Pie Grafiği Oluşturma

## Grafikler ve Çizelgeler

### Giriş

Modern veri odaklı sunumlarda, **PowerPoint'e grafik eklemek** genellikle ham sayıları görsel içgörüye dönüştürmenin en hızlı yoludur. Normal bir pasta grafiği birkaç kategori için iyi çalışır, ancak birkaç dilim çok küçük olduğunda okunamaz hâle gelir. *Pie of Pie* grafiği, bu küçük dilimleri ikincil bir pasta grafiğine ayırarak sorunu çözer; ana grafik temiz kalır ve ayrıntılar erişilebilir olur.

Bu öğreticide, Aspose.Slides for Java kullanarak bir Pie of Pie grafiği oluşturarak **PowerPoint'e grafik eklemeyi** öğreneceksiniz. Ortam kurulumundan, grafik oluşturma, etiket özelleştirme, bölme‑konum ayarı ve sonunda sunumu PPTX dosyası olarak kaydetmeye kadar adımları göstereceğiz. Sonunda, karmaşık grafikleri herhangi bir slayt destesine yerleştirmeye hazır olacaksınız.

## Hızlı Yanıtlar
Aspose.Slides'ta, `Presentation` bir PPTX dosyasını temsil eder, `ChartType.PieOfPie` Pie of Pie grafiğini seçer, `setShowValue(true)` etiketlerde değerleri gösterir ve `save` dosyayı yazar.

- **PowerPoint manipülasyonu için birincil sınıf nedir?** `Presentation` – bellekte tüm bir PPTX dosyasını temsil eder.  
- **Küçük dilimler için ikincil bir pasta oluşturan grafik türü hangisidir?** `ChartType.PieOfPie`.  
- **Her dilimde değerleri nasıl gösterirsiniz?** `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)` ayarlayın.  
- **Dosyayı doğrudan PPTX olarak kaydedebilir misiniz?** Evet – `presentation.save("output.pptx", SaveFormat.Pptx)` çağırın.  
- **Geliştirme için lisansa ihtiyacınız var mı?** Test için ücretsiz 30‑günlük deneme sürümü çalışır; kalıcı bir lisans değerlendirme filigranlarını kaldırır.

## Pie of Pie Grafiği Nedir?
**Pie of Pie grafiği**, bir veya daha fazla küçük dilimi ayrı, bağlantılı bir pasta grafiğine izole eden iki seviyeli bir pasta görselleştirmesidir; bu sayede okunması daha kolay olur. Aspose.Slides bu grafik türünü kutudan çıkar çıkmaz destekler ve bölme boyutu, konumu ve etiket biçimlendirmesini kontrol etmenizi sağlar.

## Neden Aspose.Slides ile PowerPoint'e Grafik Ekleyelim?
Aspose.Slides, Microsoft Office yüklü olmadan PowerPoint dosyaları oluşturabilir, düzenleyebilir ve işleyebilir. **50+ giriş ve çıkış formatını** destekler, tipik sunucu donanımında **500 slayta kadar** sunumları bir saniyeden kısa sürede işler ve grafik stilizasyonu, veri etiketleri ve düzen üzerinde **tam API kontrolü** sağlar—otomatik raporlama hatları için mükemmeldir.

## Önkoşullar

- **Java Development Kit (JDK) 16+** yüklü.  
- **IntelliJ IDEA**, **Eclipse** veya **NetBeans** gibi bir IDE.  
- Bağımlılık yönetimi için Maven veya Gradle (aşağıdaki bölümlere bakın).  
- Temel Java bilgisi ve proje oluşturma konusundaki aşinalık.

## Aspose.Slides for Java Kurulumu

### Kurulum Bilgileri

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Doğrudan İndirme:** En son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisans Edinme Adımları
- **Ücretsiz Deneme:** Tüm özellikleri keşfetmek için 30‑günlük deneme sürümüyle başlayın.  
- **Geçici Lisans:** Uzatılmış değerlendirme için geçici bir anahtar isteyin.  
- **Satın Alma:** Üretim kullanımında değerlendirme filigranlarını kaldırmak için kalıcı bir lisans edinin.

### Temel Başlatma ve Kurulum
`Presentation` PowerPoint dosyaları oluşturmak için ana nesnedir ve `Chart` bir slayt içindeki grafik şekli temsil eder.

```java
Presentation presentation = new Presentation();
```  

Bu, slaytlar ve grafikler için hazır boş bir sunum oluşturur.

## Uygulama Kılavuzu

### Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Nasıl Eklenir?

Yeni bir `Presentation` yükleyin, bir slayt ekleyin ve `PieOfPie` türünde bir `Chart` ekleyin. API çağrı zinciri özlüdür: grafiği oluşturun, seri verilerini doldurun, etiket görünürlüğünü ayarlayın, ikincil pasta boyutunu yapılandırın ve sonunda kaydedin. Tüm süreç genellikle 20 satırın altında bir kodla tamamlanır, bu da otomatik rapor üretimi için idealdir.

### 'Pie of Pie' Grafiği Oluşturma

#### Genel Bakış
İlk slaytta bir Pie of Pie grafiği oluşturacağız, en küçük dilimleri ayıracağız ve her bölümü değerine göre etiketleyeceğiz.

#### Adım 1: Presentation Sınıfının Bir Örneğini Oluşturun
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Bu, sonraki tüm slaytlar ve grafikler için kapsayıcıyı başlatır.

#### Adım 2: İlk Slayta 'Pie of Pie' Grafiği Ekleyin
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Burada `ChartType.PieOfPie` belirtiyoruz ve grafiğin slayt tuvalindeki konumunu (X, Y) ve boyutunu (genişlik, yükseklik) tanımlıyoruz.

#### Adım 3: Serinin Veri Etiketlerini Değerleri Göstercek Şekilde Ayarlayın
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
`showValue` etkinleştirildiğinde, her dilim sayısal değerini gösterir; bu, hızlı veri yorumlaması için esastır.

#### Adım 4: İkincil Pasta Boyutunu ve Yüzdeye Göre Bölmeyi Yapılandırın
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Bu seçenekler, grafiğin ne kadarının ikincil pasta için ayrılacağını ve yüzde eşiğine göre hangi dilimlerin taşınacağını belirlemenizi sağlar.

#### Adım 5: Sunumu PPTX Formatında Diske Kaydedin
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro ipucu:** Platforma özgü ayırıcıları önlemek için mutlak bir yol veya Java’nın `Paths.get()` metodunu kullanın.

## Yaygın Sorunlar ve Çözümler

`License` sınıfı, değerlendirme kısıtlamalarını kaldırmak için bir lisans dosyası yükler.

- **Lisans uyarısı eksik:** Grafikte “Evaluation Only” görürseniz, `License license = new License(); license.setLicense("Aspose.Slides.lic");` ile geçerli bir lisans dosyası uyguladığınızdan emin olun.  
- **Yanlış dilim bölmesi:** `splitBy` özelliğinin `SplitBy.Percentage` olarak ayarlandığını ve `secondPieSize` değerinin 0 ile 100 arasında olduğunu doğrulayın.  
- **Veri görüntülenmiyor:** Grafiğin serisinin en az bir veri noktasına sahip olduğunu doğrulayın; aksi takdirde grafik boş renderlanır.

## Sıkça Sorulan Sorular

`IChart` bir slayta eklenebilen bir grafik nesnesini temsil eder.

**S: Tek bir sunumda birden fazla grafik oluşturabilir miyim?**  
C: Evet, her slayt veya konum için yeni bir `IChart` örneği oluşturun; API dosya başına sınırsız grafik nesnesine izin verir.

`SaveFormat.Pdf` kaydetme için PDF çıktı formatını belirtir.

**S: Aspose.Slides PDF olarak kaydetmeyi de destekliyor mu?**  
C: Kesinlikle – aynı slayt destesi PDF olarak dışa aktarmak için `presentation.save("output.pdf", SaveFormat.Pdf)` çağırın.

`IPortion` bir pasta grafiğinin tek bir dilimini temsil eder.

**S: Pie of Pie grafiği kaç veri noktasını en fazla işleyebilir?**  
C: Kütüphane, seriye başına **10.000** veri noktasına kadar destek verir; sınırlama yalnızca mevcut bellekle ilgilidir.

**S: Tek tek dilimlerin renklerini özelleştirmek mümkün mü?**  
C: Evet, `chart.getChartData().getSeries().get_Item(0).getPortions()` üzerinden her `IPortion`a erişip `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))` ile renk ayarlayabilirsiniz.

**S: Oluşturulan PPTX'i bir web uygulamasına nasıl gömebilirim?**  
C: Dosyayı kaydettikten sonra, `HttpServletResponse` ile `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation` kullanarak doğrudan istemciye akıtabilirsiniz.

## Sonuç

Artık Aspose.Slides for Java ile bir Pie of Pie grafiği oluşturarak **PowerPoint'e grafik eklemek** için eksiksiz, üretim‑hazır bir tarife sahipsiniz. Farklı bölme eşiklerini, etiket formatlarını ve renk şemalarını deneyerek marka yönergelerinize uyum sağlayın. Sonra, yığılmış çubuk veya radar gibi diğer grafik türlerini keşfederek otomatik slayt destelerinizi daha da zenginleştirin.

---

**Son Güncelleme:** 2026-07-17  
**Test Edilen Versiyon:** Aspose.Slides for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Dinamik Grafik Oluşturma Java – Aspose.Slides için PowerPoint Grafik Öğreticileri](/slides/java/charts-graphs/)
- [Aspose.Slides for Java ile PowerPoint'e Pasta Grafiği Nasıl Eklenir](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}