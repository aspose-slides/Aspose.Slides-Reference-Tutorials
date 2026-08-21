---
date: '2026-08-21'
description: Aspose.Slides kullanarak Java’da kutu grafiği oluşturmayı, slayta grafik
  eklemeyi ve PowerPoint’te kutu‑ve‑bıyık grafiği üretmeyi öğrenin. Java geliştiricileri
  için idealdir.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Aspose.Slides kullanarak Java’da kutu grafiği oluşturmayı, slayta
  grafik eklemeyi ve PowerPoint’te kutu‑ve‑bıyık grafiği üretmeyi öğrenin. Java geliştiricileri
  için mükemmeldir.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Aspose.Slides for PowerPoint ile Java’da kutu grafiği nasıl oluşturulur
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Aspose.Slides for PowerPoint ile Java’da kutu grafiği nasıl oluşturulur
url: /tr/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java ile Aspose.Slides for PowerPoint kullanarak kutu grafiği (box plot) oluşturma

Bu rehberde Aspose.Slides kullanarak Java ile kutu grafiği oluşturacak ve grafiği doğrudan bir PowerPoint slaytına yerleştireceksiniz. Programatik olarak kutu‑ve‑bıyık (box‑and‑whisker) grafikler oluşturmak, ham istatistiksel verileri Java kodunuzdan çıkmadan net görsel içgörülere dönüştürmenizi sağlar. PowerPoint raporlamasını otomatikleştirmeniz gerekiyorsa, Aspose.Slides for Java güvenilir, yüksek performanslı bir API sunar.

## Neler öğreneceksiniz

- Aspose.Slides for Java için ortamınızı kurma
- Java kullanarak PowerPoint'te kutu‑bıyık grafiği oluşturmak ve **grafiği slayta eklemek** için adımlar
- Aspose.Slides ile çalışırken performansı optimize etmek için en iyi uygulamalar
- Kutu‑ve‑bıyık grafiklerinin gerçek dünya uygulamaları

## Hızlı yanıtlar
- **Java'da kutu grafiği oluşturan kütüphane nedir?** Aspose.Slides for Java.  
- **Hangi grafik türü kullanılır?** `ChartType.BoxAndWhisker`.  
- **Lisans gerekiyor mu?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Birden fazla seri ekleyebilir miyim?** Evet – her veri kümesi için seri‑oluşturma bloğunu tekrarlayın.  
- **Son dosyanın formatı nedir?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Kutu grafiği nedir ve Java'da neden kullanılır?

Kutu‑ve‑bıyık grafiği (genellikle *kutu grafiği* olarak adlandırılır), veri dağılımını—medyan, çeyrekler ve aykırı değerleri—kısa bir biçimde görselleştirir. Java'da bu grafiği programatik olarak oluşturmak, istatistiksel içgörüleri doğrudan PowerPoint sunumlarına gömmenizi sağlar ve manuel grafik oluşturma ihtiyacını ortadan kaldırır. Özellikle sınıflar arasındaki sınav puanları veya bölgeler arasındaki satış rakamları gibi birden çok kategoriye ait dağılımları karşılaştırmak için faydalıdır. Grafiği Java'da üreterek otomatik raporlama hatlarına entegre edebilir, sunumlarınızda her zaman en güncel verileri gösterebilirsiniz.

## Neden Aspose.Slides ile slayta grafik ekleyelim?

Aspose.Slides, düşük seviyeli OpenXML ayrıntılarını soyutlayarak grafik oluşturma, stil verme ve dışa aktarma için akıcı bir API sunar. Bu sayede rapor üretimini otomatikleştirebilir, tutarlı kurumsal kimlik sağlayabilir ve grafikleri daha büyük Java iş akışlarına entegre edebilirsiniz. Kütüphane ayrıca renkler, yazı tipleri ve işaretçiler gibi stil seçeneklerini destekler, böylece kurumsal marka kimliğinize uyum sağlayabilirsiniz. Ayrıca veri bağlama ve grafik yenileme gibi karmaşık görevleri Microsoft Office gerektirmeden halleder.

## Java ile Aspose.Slides kullanarak slayta grafik nasıl eklenir?

Bir `Presentation` nesnesi yükleyin veya oluşturun, `BoxAndWhisker` tipinde bir `Chart` ekleyin, verilerinizi besleyin ve dosyayı kaydedin—tüm bunlar birkaç Java satırı içinde gerçekleşir. API, yerleşim, ölçekleme ve render işlemlerini halleder, böylece XML ile uğraşmanıza gerek kalmaz. Görüntüleyiciler için bağlam sağlamak amacıyla grafik başlıklarını ve eksen etiketlerini programatik olarak da ayarlayabilirsiniz.

## Önkoşullar

- **Java Development Kit (JDK)**: JDK 8 veya üzeri.  
- **Aspose.Slides for Java Kütüphanesi**: PowerPoint manipülasyonu için gereklidir.  
- **IDE**: IntelliJ IDEA, Eclipse veya herhangi bir Java uyumlu editör.

## Aspose.Slides for Java Kurulumu

Kütüphaneyi Maven, Gradle veya manuel bağımlılık olarak ekleyin.

### Maven

`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

`build.gradle` dosyanıza şunu ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan indirme

Alternatif olarak, en yeni sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

#### Lisans edinme

- **Ücretsiz deneme** – özellikleri ücretsiz keşfedin.  
- **Geçici lisans** – kısa vadeli değerlendirme için kullanın.  
- **Satın al** – üretim iş yükleri için tam işlevselliği açın.

Aspose.Slides'i başlatmak için JAR dosyasının sınıf yolunuzda olduğundan emin olun ve belgelerde açıklandığı gibi lisans dosyasını ayarlayın.

## Uygulama rehberi

Aşağıda adım adım bir yürütme bulunuyor. Her blok, ne yaptığını anlamanız için açıklanmıştır.

### `Presentation` sınıfı nedir?

`Presentation` sınıfı, Aspose.Slides içinde bellekte bir bütün PowerPoint dosyasını temsil eden merkezi nesnedir. Slaytlar, grafikler, şekiller ve diğer slayt öğelerine erişim sağlar; böylece sunumları programatik olarak oluşturabilir, değiştirebilir ve kaydedebilirsiniz. Bu sınıf sayesinde yeni slaytlar ekleyebilir, resimler yerleştirebilir ve slayt sırasını basit API çağrılarıyla yönetebilirsiniz.

### Adım 1: bir sunum oluşturun veya açın

Mevcut bir PPTX dosyasını açın ya da yeni bir tane başlatın:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro tip:** Dosya mevcut değilse Aspose.Slides otomatik olarak yeni bir boş sunum oluşturur.

### Adım 2: slayta kutu‑ve‑bıyık grafiği ekleyin

Grafiği konumlandırmak ve boyutlandırmak için konum ve boyut (puan cinsinden) belirtin:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Adım 3: mevcut verileri temizleyin

Yeni verileri eklemeden önce yer tutucu kategori veya serileri silin:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Adım 4: kategorileri yapılandırın

Her kutunun altında görünecek X‑eksen etiketlerini (kategorileri) ekleyin:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Not:** Etiket metnini veri alanınıza uygun şekilde ayarlayın (ör. “Q1”, “Product A”).

### Adım 5: seriyi oluşturun ve özelleştirin

Şimdi bir seri oluşturun, görsel seçenekleri ayarlayın ve sayısal veri noktalarını besleyin:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

`int[] data` dizisini bir veritabanı, CSV dosyası veya başka bir kaynaktan okunan değerlerle değiştirebilirsiniz.

### Adım 6: sunumu kaydedin

Değişiklikleri yeni bir PPTX dosyasına kaydedin:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Adım 7: kaynakları temizleyin

Yerel kaynakları serbest bırakmak için `Presentation` nesnesini her zaman dispose edin:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Pratik uygulamalar

Kutu‑ve‑bıyık grafikleri istatistiksel analiz ve veri sunumunda vazgeçilmezdir. İşte öne çıkan bazı senaryolar:

1. **Finansal analiz** – gelir dağılımını bölgeler arasında görselleştirin.  
2. **Kalite kontrol** – üretim ölçümlerindeki aykırı değerleri tespit edin.  
3. **Akademik araştırma** – deneysel sonuçların değişkenliğini gösterin.  
4. **Pazar araştırması** – demografik gruplar arasında ürün performansını karşılaştırın.

Bu grafikleri doğrudan PowerPoint sunumlarına yerleştirerek paydaşların karmaşık verileri bir bakışta kavramasını sağlayabilirsiniz.

## Performans değerlendirmeleri

Aspose.Slides, **500+ slayt** ve **100 000+ veri noktası** içeren sunumları tipik bir sunucuda bellek kullanımını 200 MB altında tutarak işleyebilir. Bu sınırlar içinde kalmak için:

- **Bellek yönetimi** – `Presentation` nesnelerini zamanında serbest bırakın.  
- **Veri işleme** – sadece ihtiyacınız olan verileri yükleyin; büyük veri setlerini doğrudan grafik çalışma kitabına beslemekten kaçının.  
- **Tembel yükleme** – birçok slayt üretirken, yalnızca gösterilecek slaytlar için grafik oluşturun.

## Yaygın sorunlar ve çözümler

| Sorun | Neden | Çözüm |
|-------|-------|----------|
| **Grafik boş görünüyor** | Veri hücreleri doğru doldurulmamış | `wb.getCell` referansının doğru satır/sütuna işaret ettiğini ve değerin `null` olmadığını doğrulayın. |
| **Aykırı değerler gösterilmiyor** | `setShowOutlierPoints` `false` olarak ayarlanmış | `series.setShowOutlierPoints(true)` çağrıldığından emin olun. |
| **Bellek sızıntısı** | Sunum serbest bırakılmamış | Kullanımı her zaman `try/finally` içinde sarın ve `dispose()` çağırın. |
| **Yanlış çeyrekler** | Varsayılan `Inclusive` yöntemi kullanılıyor | `setQuartileMethod(QuartileMethodType.Exclusive)` ile `Exclusive` yöntemine geçin. |

## Sıkça sorulan sorular

**S1: Kutu‑ve‑bıyık grafiği nedir?**  
Kutu‑ve‑bıyık grafiği, beş özet istatistiği (minimum, birinci çeyrek, medyan, üçüncü çeyrek ve maksimum) ve olası aykırı değerleri gösteren bir dağılım görselleştirme aracıdır.

**S2: Kutu‑ve‑bıyık grafiğinin görünümünü özelleştirebilir miyim?**  
Evet. Aspose.Slides, renkleri, çizgi stillerini, işaretçi şekillerini değiştirme ve veri etiketleri ekleme gibi formatlama API'leriyle grafiğin görünümünü özelleştirmenize izin verir.

**S3: Tek bir grafikte birden fazla seriyi yönetmek mümkün mü?**  
Kesinlikle. Görselleştirmek istediğiniz her veri kümesi için seri‑oluşturma bloğunu tekrarlayın.

**S4: Verilerin doğru görüntülenmemesi sorununu nasıl çözerim?**  
Verilerin çalışma kitabı hücrelerine doğru yazıldığından ve `setShowMeanLine` gibi görünürlük özelliklerinin etkin olduğundan emin olun.

**S5: Sorun yaşarsam nereden destek alabilirim?**  
Topluluk yardımı için [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) adresini ziyaret edin veya resmi belgelerden faydalanın.

**S6: Aspose.Slides diğer grafik türlerini destekliyor mu?**  
Evet, çizgi, çubuk, pasta, dağılım, radar ve huni gibi 50'den fazla grafik türünü destekler; böylece veriniz için en uygun görselleştirmeyi seçebilirsiniz.

**S7: Başsız (headless) sunucu ortamında grafik oluşturabilir miyim?**  
Kütüphane, UI veya Microsoft Office kurulumu gerektirmeden sunucu tarafı senaryolarında tam olarak çalışır.

## Kaynaklar

- **Dokümantasyon**: Ayrıntılı API referanslarını [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) adresinde keşfedin  
- **İndirme**: Aspose.Slides sürüm sayfasına [Aspose.Slides releases page](https://releases.aspose.com/slides/java/) adresinden ulaşın  
- **Satın alma**: Tam özellikleri açmak için lisans satın alın [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Ücretsiz deneme ve geçici lisans**: Ücretsiz deneme ile başlayın veya geçici lisans isteyin [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Bu kılavuzu izleyerek Java uygulamalarınızda istatistiksel olarak zengin kutu‑ve‑bıyık grafikler oluşturabilir ve doğrudan PowerPoint sunumlarına gömebilirsiniz. Kodlamanın tadını çıkarın!

---

**Son Güncelleme:** 2026-08-21  
**Test Edilen Versiyon:** Aspose.Slides 25.4 (JDK 16 sınıflandırıcı)  
**Yazar:** Aspose

## İlgili Eğitimler

- [Java için Aspose.Slides kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java ile Aspose.Slides kullanarak PowerPoint grafiği oluşturma](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Java için Aspose.Slides ile PowerPoint grafiğine animasyon ekleme – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}