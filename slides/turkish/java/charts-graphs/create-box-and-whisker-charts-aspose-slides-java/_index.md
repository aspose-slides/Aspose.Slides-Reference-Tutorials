---
date: '2026-03-02'
description: Aspose.Slides for Java kullanarak Java’da kutu grafiği oluşturmayı, slayta
  grafik eklemeyi ve PowerPoint’te kutu‑çubuk grafiği (box‑whisker chart) üretmeyi
  öğrenin.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Aspose.Slides for PowerPoint kullanarak Java’da kutu grafiği oluşturma
url: /tr/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint'te Aspose.Slides for Java Kullanarak Kutu ve Bıyık Grafiklerini Nasıl Oluşturulur

Bu rehberde Aspose.Slides ile **create box plot java** oluşturacak ve ardından grafiği doğrudan bir PowerPoint slaytına yerleştireceksiniz. Görsel açıdan etkileyici veri sunumları oluşturmak, günümüz veri odaklı dünyasında kritik öneme sahiptir ve grafikler bu amaç için temel araçlardır. Java kullanarak PowerPoint içinde kutu ve bıyık grafikleri oluşturmak istiyorsanız, Aspose.Slides kütüphanesi sağlam bir çözüm sunar. Bu öğreticide, Aspose.Slides for Java ile bu grafiklerin oluşturulması ve yapılandırılması adım adım gösterilecektir.

## Öğrenecekleriniz

- Aspose.Slides for Java için ortamınızı kurma
- **add chart to slide** adımlarını ve Java kullanarak PowerPoint'te kutu‑bıyık grafiği oluşturma
- Aspose.Slides ile çalışırken performansı optimize etmek için en iyi uygulamalar
- Kutu‑ve‑bıyık grafiklerinin gerçek dünya uygulamaları

## Hızlı Yanıtlar
- **What library creates a box plot in Java?** Aspose.Slides for Java.
- **Which chart type is used?** `ChartType.BoxAndWhisker`.
- **Do I need a license?** Değerlendirme için ücretsiz deneme çalışır; üretim için ticari bir lisans gereklidir.
- **Can I add multiple series?** Evet – her veri kümesi için seri‑oluşturma bloğunu tekrarlayın.
- **What format is the final file?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Ön Koşullar

Bu öğreticiyi takip edebilmek için aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK)**: JDK 8 veya daha üstü yüklü olmalıdır.
- **Aspose.Slides for Java Library**: Java'da PowerPoint sunumlarını işlemek için gereklidir.
- **IDE**: IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı, kodunuzu yazıp çalıştırmak için.

## Aspose.Slides for Java Kurulumu

Aspose.Slides'ı kullanmak için bağımlılık olarak ekleyin. Bunu Maven, Gradle aracılığıyla ya da doğrudan indirme yoluyla yönetebilirsiniz.

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

`build.gradle` dosyanıza aşağıdakini ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme

Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

#### Lisans Edinme

- **Free Trial**: Özellikleri keşfetmek için ücretsiz deneme ile başlayın.  
- **Temporary License**: Değerlendirme amaçlı geçici bir lisans edinin.  
- **Purchase**: Tam işlevsellik için bir lisans satın almayı düşünün.

Aspose.Slides'ı başlatmak için, kütüphanenin sınıf yolunuzda (classpath) bulunduğundan ve gerekli lisans gereksinimlerini ayarladığınızdan emin olun.

## Uygulama Kılavuzu

Şimdi adım adım koda dalalım. Her blok, kod parçacığından önce açıklanır, böylece ne yaptığını tam olarak bilirsiniz.

### Box plot nedir ve Java'da neden kullanılır?

Kutu‑ve‑bıyık grafiği (genellikle *box plot* olarak adlandırılır) veri dağılımını—medyan, çeyrekler ve aykırı değerleri—kısa bir biçimde görselleştirir. Java'da bu grafiği programlı olarak oluşturmak, istatistiksel içgörüleri doğrudan PowerPoint sunularına yerleştirmenizi sağlar ve manuel grafik oluşturmayı ortadan kaldırır.

### Aspose.Slides ile slayta grafik eklemek neden?

Aspose.Slides, düşük seviyeli OpenXML ayrıntılarını soyutlayarak grafik oluşturma, biçimlendirme ve dışa aktarma için akıcı bir API sunar. Bu sayede rapor üretimini otomatikleştirebilir, tutarlı marka kimliği oluşturabilir ve grafikleri daha büyük Java iş akışlarına entegre edebilirsiniz.

### Adım 1: Sunum Oluşturma veya Açma

İlk olarak, mevcut bir PPTX dosyasını açın veya yeni bir tane başlatın:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro ipucu:** Dosya mevcut değilse, Aspose.Slides sizin için yeni bir boş sunum oluşturur.

### Adım 2: Slayta Kutu‑ve‑Bıyık Grafiği Ekleme

Grafiği, konum ve boyut (puan cinsinden) belirterek ihtiyacınız olan yere yerleştirin:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Adım 3: Mevcut Verileri Temizleme

Yeni verileri eklemeden önce, yer tutucu kategorileri veya serileri temizleyin:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Adım 4: Kategorileri Yapılandırma

Her kutunun altında görünecek kategorileri (X‑eksen etiketleri) ekleyin:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Not:** Etiket metnini veri alanınıza uygun şekilde ayarlayın (ör. “Q1”, “Product A”).

### Adım 5: Seriyi Oluşturma ve Özelleştirme

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

### Adım 6: Sunumu Kaydetme

Değişiklikleri yeni bir PPTX dosyasına kaydedin:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Adım 7: Kaynakları Temizleme

`Presentation` nesnesini her zaman dispose ederek yerel kaynakları serbest bırakın:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Pratik Uygulamalar

Kutu‑ve‑bıyık grafikleri istatistiksel analiz ve veri sunumunda vazgeçilmezdir. İşte öne çıktıkları birkaç senaryo:

1. **Financial Analysis** – Gelir dağılımını bölgeler arasında görselleştirin.  
2. **Quality Control** – Üretim ölçümlerindeki aykırı değerleri tespit edin.  
3. **Academic Research** – Deneysel sonuçların değişkenliğini gösterin.  
4. **Market Research** – Demografik gruplar arasında ürün performansını karşılaştırın.

Bu grafikleri PowerPoint sunularına entegre etmek, paydaşların karmaşık verileri bir bakışta kavramasını sağlar.

## Performans Düşünceleri

Aspose.Slides'ı Java'da kullanırken aşağıdaki ipuçlarını aklınızda tutun:

- **Memory Management** – `Presentation` nesnelerini hızlı bir şekilde dispose edin.  
- **Data Handling** – Sadece ihtiyacınız olan verileri yükleyin; büyük veri setlerini doğrudan grafik çalışma kitabına beslemekten kaçının.  
- **Lazy Loading** – Çok sayıda slayt oluşturuyorsanız, yalnızca gösterilecek slaytlar için grafik oluşturmayı düşünün.

## Yaygın Sorunlar ve Çözümler

| Issue | Cause | Solution |
|-------|-------|----------|
| **Grafik boş görünüyor** | Veri hücreleri doğru şekilde doldurulmamış | `wb.getCell`'in doğru satır/sütuna referans verdiğini ve değerin `null` olmadığını doğrulayın. |
| **Aykırı değerler gösterilmiyor** | `setShowOutlierPoints` false olarak ayarlanmış | `series.setShowOutlierPoints(true)` çağrıldığından emin olun. |
| **Bellek sızıntısı** | Presentation dispose edilmemiş | Kullanımı her zaman try/finally içinde sarın ve `dispose()` çağırın. |
| **Yanlış çeyrekler** | Varsayılan `Inclusive` yöntemi kullanılıyor | `setQuartileMethod(QuartileMethodType.Exclusive)` ile `Exclusive`'a geçin. |

## Sıkça Sorulan Sorular

**S1: Kutu‑ve‑bıyık grafiği nedir?**  
Kutu‑ve‑bıyık grafiği, box plot olarak da bilinir, verinin dağılımını beş özet istatistiğe göre gösterir: minimum, birinci çeyrek, medyan, üçüncü çeyrek ve maksimum, ayrıca aykırı değerler.

**S2: Kutu‑ve‑bıyık grafiğinin görünümünü özelleştirebilir miyim?**  
Evet. Aspose.Slides, renkleri, çizgi stillerini, işaretçi şekillerini değiştirebilir ve hatta grafik biçimlendirme API'si aracılığıyla veri etiketleri ekleyebilir.

**S3: Tek bir grafikte birden fazla seriyi yönetmek mümkün mü?**  
Kesinlikle. Görselleştirmek istediğiniz her veri kümesi için seri‑oluşturma bloğunu tekrarlayın.

**S4: Verilerin doğru görüntülenmemesi sorununu nasıl çözerim?**  
Verilerin çalışma kitabı hücrelerine doğru yazıldığından ve `setShowMeanLine` gibi görünürlük özelliklerinin etkin olduğundan emin olun.

**S5: Sorunlarla karşılaştığımda nereden destek alabilirim?**  
Topluluk yardımı için [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) adresini ziyaret edin veya resmi dokümantasyona bakın.

**S6: Aspose.Slides diğer grafik türlerini destekliyor mu?**  
Evet, çizgi, çubuk, pasta, dağılım, radar ve daha birçok grafik türünü destekler.

**S7: Grafikleri başsız (headless) bir sunucu ortamında oluşturabilir miyim?**  
Kütüphane sunucu tarafı senaryolarında tamamen çalışır; UI gerektirmez.

## Kaynaklar

- **Documentation**: Ayrıntılı API referanslarını [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) adresinde keşfedin  
- **Download**: Aspose.Slides sürümlerine [buradan](https://releases.aspose.com/slides/java/) erişin  
- **Purchase**: Tam özellikleri açmak için bir lisans satın alın [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: Ücretsiz deneme ile başlayın veya geçici bir lisans isteyin [buradan](https://releases.aspose.com/slides/java/)

Bu kılavuzu izleyerek, Java uygulamalarınızda programlı olarak içgörülü kutu‑ve‑bıyık grafikler oluşturup doğrudan PowerPoint sunumlarına yerleştirebilecek donanıma sahip oldunuz. Kodlamanın tadını çıkarın!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-03-02  
**Test Edilen Versiyon:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Yazar:** Aspose