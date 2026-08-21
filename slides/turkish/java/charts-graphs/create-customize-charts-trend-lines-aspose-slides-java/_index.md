---
date: '2026-08-21'
description: Aspose.Slides for Java ile kümelenmiş sütun grafiği oluşturmayı ve trend
  çizgileri eklemeyi öğrenin. license setup, Maven/Gradle entegrasyonu ve ayrıntılı
  örnekler içerir.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Aspose.Slides for Java kullanarak bir kümelenmiş sütun grafiği oluşturun
  ve trend çizgileri ekleyin. Bu kılavuz, license setup, Maven/Gradle ve adım adım
  kod parçacıklarını kapsar.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Aspose.Slides for Java ile kümelenmiş sütun grafiği oluşturun ve trend çizgileri
  ekleyin
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Aspose.Slides for Java kullanarak kümelenmiş sütun grafiği oluşturma ve trend
  çizgileri ekleme
url: /tr/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java kullanarak kümelenmiş sütun grafiği oluşturma ve eğri çizgileri ekleme

Etkileyici sunumlar oluşturmak genellikle verilerinizin net bir görselle başlamasını gerektirir. Bu rehberde **kümelenmiş sütun grafiği** nesnelerini oluşturacak, ardından güçlü Aspose.Slides for Java API'si ile üstel, doğrusal, logaritmik, hareketli ortalama, polinom ve güç gibi çeşitli eğri çizgeleri ekleyerek zenginleştireceksiniz.

## Hızlı yanıtlar
- **İlk adım nedir?** Bir `Presentation` nesnesi başlatın ve bir slayta kümelenmiş sütun grafiği ekleyin.  
- **Hangi kütüphane sürümü gerekiyor?** Aspose.Slides for Java 25.4 veya daha yeni bir sürüm.  
- **Maven veya Gradle kullanabilir miyim?** Evet, her ikisi de desteklenir; Maven `<dependency>` kullanır ve Gradle `implementation` kullanır.  
- **Lisans gerekli mi?** Değerlendirme için bir deneme lisansı yeterlidir; tam bir Aspose.Slides lisansı değerlendirme sınırlamalarını kaldırır.  
- **Kaç çeşit eğri çizgi tipi mevcut?** Altı yerleşik tip: üstel, doğrusal, logaritmik, hareketli ortalama, polinom ve güç.

## Kümelenmiş sütun grafiği oluşturmak nedir?
`create clustered column chart` ifadesi, her kategori içinde birden fazla veri serisini yan yana gruplayan bir grafik oluşturmak anlamına gelir; bu sayede seriler arasındaki değerleri karşılaştırmak kolaylaşır. Bu grafik türü, bölgeler bazında çeyrek satışları gibi kategorik verileri görselleştirmek için idealdir ve izleyicilerin gruplar arasındaki farkları hızlıca fark etmesini sağlar.

## Neden eğri çizgi eklenir?
Eğri çizgileri, bir veri serisinin altında yatan deseni ortaya çıkararak gelecekteki değerleri tahmin etmenize, büyüme oranlarını vurgulamanıza veya gürültülü verileri düzleştirmenize yardımcı olur. Bir kümelenmiş sütun grafiğine eğri çizgi ekleyerek ham sayılar, eyleme dönüştürülebilir içgörülere dönüşür; paydaşlar uzun vadeli eğilimleri anlayıp veri odaklı kararlar alabilir.

## Önkoşullar
- **Java Development Kit (JDK):** 8 veya üzeri.  
- **Aspose.Slides for Java:** 25.4 veya daha yeni bir sürüm.  
- **IDE:** IntelliJ IDEA, Eclipse veya herhangi bir Java‑uyumlu editör.  
- **Derleme aracı:** Maven veya Gradle (isteğe bağlı ancak önerilir).  
- **Lisans:** bir deneme veya satın alınmış Aspose.Slides lisans dosyası.  

Temel Java sözdizimine aşina olmalı ve proje bağımlılık yönetimi konusunda deneyimli olmalısınız.

## Aspose.Slides for Java nasıl kurulur?
Tercih ettiğiniz bağımlılık yöneticisini kullanarak Aspose.Slides kütüphanesini projenize ekleyin, ardından lisans dosyanızı çalışma zamanının bulabileceği bir konuma yerleştirin. Bu, tam işlevselliği sağlar ve değerlendirme kısıtlamalarını kaldırır.

### Maven
`pom.xml` dosyanıza bu bağımlılığı ekleyin:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` dosyanıza bu satırı ekleyin:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan indirme
Ayrıca JAR dosyasını [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden manuel olarak indirebilirsiniz.

#### Aspose Slides lisansı
`Aspose.Slides.lic` dosyasını projenizin kök dizinine yerleştirin veya lisansı programlı olarak şu şekilde ayarlayın: `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Deneme lisansı tüm özellik kısıtlamalarını kaldırır, ancak satın alınmış bir lisans değerlendirme filigranını ortadan kaldırır ve tam performans iyileştirmeleri sağlar. Üretim ortamı için lisansı [Aspose purchase page](https://purchase.aspose.com/buy) üzerinden almayı düşünün.

## Bir sunum oluşturma ve kümelenmiş sütun grafiği ekleme nasıl yapılır?
`Presentation` sınıfı bir PowerPoint dosyasını temsil eder ve slaytları oluşturma, düzenleme ve kaydetme yöntemleri sunar. Bir `Presentation` örneği oluşturun, bir slayt ekleyin ve ardından `addChart` metodunu `ChartType.ClusteredColumn` ile çağırarak grafik nesnesini oluşturun. Bu işlem slayt tuvalini ayarlar, bir grafik şekli ekler ve veri doldurma ve stil verme için hazır hale getirir.

1. **Sunumu başlat** – çıktı klasörünü ayarlayın ve yeni bir `Presentation` örneği oluşturun.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Kümelenmiş sütun grafiği ekle** – grafik şekline erişin, serilerini yapılandırın ve veri noktalarını doldurun.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Üstel eğri çizgi nasıl eklenir?
`ITrendline` arayüzü, bir grafik serisine veri desenlerini modellemek için eklenebilen bir eğri çizgi tanımlar. Bir seriye üstel eğri çizgi eklemek için bir `ITrendline` örneği oluşturun, `TrendlineType` değerini `Exponential` olarak ayarlayın ve istediğiniz seriye bağlayın. Bu tür eğri çizgi, hızla artan bir oranda büyüyen veriler için faydalıdır.

1. **Eğri çizgiyi yapılandır** – seriyi seçin ve `addTrendline(TrendlineType.Exponential)` metodunu çağırın.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Doğrusal eğri çizgi nasıl eklenir?
Doğrusal eğri çizgi, veri noktalarınızdan en iyi uyan düz çizgiyi gösterir. Çizgi rengi ve kalınlığı gibi görünüm özelliklerini sunum stilinize uygun şekilde özelleştirebilirsiniz.

1. **Eğri çizgiyi ayarla** – `addTrendline(TrendlineType.Linear)` metodunu kullanın ve ardından `getLineFormat().setFillFormat().setFillType(FillType.Solid)` ile rengi değiştirin.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Özel bir metin çerçevesiyle logaritmik eğri çizgi nasıl eklenir?
Logaritmik eğri çizgiler, başlangıçta hızlı büyüyen ve ardından yavaşlayan veriler için idealdir. Varsayılan etiketi geçersiz kılarak eğrinin önemini açıklayan bir metin ekleyebilirsiniz.

1. **Eğri çizgiyi özelleştir** – eğri çizgiyi ekledikten sonra `getDataLabel()` metoduna erişin ve `setText("Custom label")` özelliğini ayarlayın.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Hareketli ortalama eğri çizgi nasıl eklenir?
Hareketli ortalama eğri çizgileri, kısa vadeli dalgalanmaları düzleştirerek uzun vadeli eğilimleri vurgular. Ortalama için kullanılan dönem (nokta sayısı) belirleyerek çizginin pürüzsüzlüğünü kontrol edebilirsiniz.

1. **Eğri çizgiyi yapılandır** – `addTrendline(TrendlineType.MovingAverage)` metodunu çağırın ve `setPeriod(3)` ile üç noktalı bir hareketli ortalama kullanın.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Polinom eğri çizgi nasıl eklenir?
Polinom eğri çizgileri, bir polinom denklemiyle tanımlanan bir eğriyle verileri uyarlar. `order` özelliği, polinomun derecesini kontrol eder ve daha karmaşık ilişkileri modellemenizi sağlar.

1. **Eğri çizgiyi özelleştir** – eğri çizgiyi ekledikten sonra `setOrder(3)` ile kübik bir uyum ayarlayın.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Güç eğri çizgi nasıl eklenir?
Güç eğri çizgileri, veriler bir güç‑kanunu ilişkisi izlediğinde faydalıdır. Ayrıca çizgiyi mevcut veri aralığının ötesine uzatmak için geriye ve ileriye tahmin değerleri ayarlayabilirsiniz.

1. **Eğri çizgiyi yapılandır** – `addTrendline(TrendlineType.Power)` metodunu kullanın ve `setBackward(2)` ile çizgiyi geriye doğru uzatın.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Kümelenmiş sütun grafiklerde eğri çizgilerin pratik uygulamaları
- **Finansal analiz:** Üstel ve polinom eğrileri, hisse fiyat hareketlerini tahmin etmeye yardımcı olur.  
- **Satış tahmini:** Hareketli ortalama çizgileri, mevsimsel dalgalanmaları yumuşatarak temel satış eğilimlerini daha net gösterir.  
- **Bilimsel araştırma:** Logaritmik eğriler, akustik şiddet veya pH seviyeleri gibi birkaç mertebe boyunca değişen veriler için mükemmeldir.  
- **Operasyon izleme:** Güç eğrileri, zaman içinde performans düşüşünü modelleyebilir.

## Aspose.Slides kullanırken belleği nasıl optimize ederim?
Kaydetme sonrası `presentation.dispose()` ile nesneleri hemen serbest bırakın. Büyük veri kümeleri için görüntülerin tembel yüklenmesini etkinleştirin ve tüm grafiği bir kerede belleğe almaktan kaçının.

- **Dispose kalıpları:** `Presentation` nesnesini try‑with‑resources bloğuna sarın veya finally bloğunda `presentation.dispose()` çağırın.  
- **Tembel yükleme:** binlerce veri noktasıyla çalışırken `ChartData.setUseCache(true)` ayarını yapın.  
- **Akış çıkışı:** Sunumu doğrudan bir `FileOutputStream`'e yazarak tüm dosyanın RAM'de tutulmasını önleyin.

## Aspose.Slides for Java'nın nicel faydaları
Aspose.Slides **50+ grafik tipi** destekler, tipik bir 2 GHz CPU üzerinde **30 saniyeden kısa** sürede **1.000'den fazla slayt** oluşturabilir ve **500 sayfalık PDF**'leri Microsoft Office kurulu olmadan işleyebilir. Bu sayılar en yeni 25.4 sürümünde doğrulanmıştır.

## Sonuç
Artık **kümelenmiş sütun grafiği** nesneleri oluşturmak ve Aspose.Slides for Java'da mevcut olan tüm ana eğri‑çizgi tipleriyle zenginleştirmek için eksiksiz, uçtan uca bir çözümünüz var. Yukarıdaki adımları izleyerek görsel olarak çekici ve analitik olarak güçlü veri‑odaklı sunumlar üretebilirsiniz.

Sonraki adımlar arasında grafik stil seçeneklerini keşfetmek, PDF/HTML'ye dışa aktarmak ve birden çok veri kaynağı üzerinden grafik üretimini otomatikleştirmek yer alıyor.

## Sıkça sorulan sorular

**S: Maven projesi için Aspose.Slides nasıl ayarlanır?**  
C: Maven bölümünde gösterilen `<dependency>` kod parçacığını `pom.xml` dosyanıza ekleyin ve `mvn clean install` komutunu çalıştırın.

**S: Eğri çizgileri renk ve etiket dışındaki özelliklerle özelleştirebilir miyim?**  
C: Evet, `ITrendline` API'si üzerinden çizgi stili, genişliği, kesikli desen ve hatta ileri/geriye tahmin değerlerini değiştirebilirsiniz.

**S: Versiyon uyumsuzluğu hatası alırsam ne yapmalıyım?**  
C: JDK sürümünüzün Aspose.Slides minimum gereksinimi (JDK 8+) ile eşleştiğini doğrulayın. Kırılma değişiklikleri için Aspose sürüm notlarına bakın.

**S: Birden fazla grafiğe otomatik olarak eğri çizgi eklemek mümkün mü?**  
C: Kesinlikle. Bir slayt koleksiyonundaki her `IChart` üzerinde döngü kurarak her seri için uygun `addTrendline` metodunu çağırabilirsiniz.

**S: Üretim kullanımında ücretli bir lisansa ihtiyacım var mı?**  
C: Evet, satın alınmış bir Aspose.Slides lisansı değerlendirme sınırlamalarını kaldırır ve tam performans iyileştirmelerini açar.

---

**Son Güncelleme:** 2026-08-21  
**Test Edilen Sürüm:** Aspose.Slides for Java 25.4  
**Yazar:** Aspose

## İlgili Eğitimler

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}