---
date: '2026-07-08'
description: Aspose.Slides for Java kullanarak pie chart PowerPoint sunumları eklemeyi
  öğrenin. Profesyonel pie chart'ları oluşturmak ve özelleştirmek için bu step‑by‑step
  rehberi izleyin.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Aspose.Slides for Java kullanarak pie chart PowerPoint ekleyin. Bu
  öğretici, pie chart'ları programlı olarak oluşturma ve özelleştirme yöntemlerini
  gösterir; otomatik raporlar için mükemmeldir.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Aspose.Slides for Java ile Pie Chart PowerPoint ekleme – Hızlı Rehber
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Aspose.Slides for Java ile PowerPoint'e pie chart ekleme
url: /tr/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java ile Pasta Grafik PowerPoint Ekle

## Giriş

Eğer **pasta grafik PowerPoint** slaytlarını manuel olarak PowerPoint açmadan eklemeniz gerekiyorsa, doğru yerdesiniz. Bu rehberde Aspose.Slides for Java kurulumunu, bir pasta grafiği oluşturmayı ve her dilimi özelleştirmeyi adım adım göstereceğiz—otomatik raporlama, gösterge panoları veya kişiselleştirilmiş sunumlar için mükemmel. Sonunda, birkaç saniye içinde şık bir pasta grafik PowerPoint dosyası üreten yeniden kullanılabilir bir Java kod parçacığına sahip olacaksınız.

### Hızlı Yanıtlar
- **Grafiği oluşturan kütüphane nedir?** Aspose.Slides for Java (en son sürüm).  
- **Head‑less çalıştırabilir miyim?** Evet—Office kurulumu gerektirmez.  
- **Hangi Java sürümü optimal?** En iyi performans ve GC iyileştirmeleri için JDK 16+.  
- **Bir dilimi nasıl patlatırım?** `IDataPoint` üzerinde `setExplosion` çağırın ve piksel offseti ayarlayın.  
- **Üretim için lisansa ihtiyacım var mı?** Geliştirme için bir deneme yeterli; kalıcı lisans tüm değerlendirme sınırlamalarını kaldırır.

## Aspose.Slides for Java kullanarak pasta grafik PowerPoint eklemenin nedeni

Arka uç hizmetlerinizden doğrudan güncel görsel raporlar üretebilir, manuel kopyala‑yapıştır hatalarını ortadan kaldırabilir ve marka tutarlı stil garantisi sağlayabilirsiniz. Aspose.Slides **70+ grafik türünü** destekler ve **10.000+ slayt** içeren sunumları, dosyanın tamamını belleğe yüklemeden işleyebilir; bu da büyük ölçekli otomasyon için idealdir.

## Önkoşullar

- **Aspose.Slides for Java** – öğreticide referans verilen sürüm 25.4 (yazım anındaki en son sürüm).  
- **Java Development Kit** – JDK 16 veya daha yenisi önerilir.  
- **Maven** veya **Gradle** bağımlılık yönetimi için.  

## Aspose.Slides for Java Kurulumu

### Maven
pom.xml dosyanıza bu bağımlılığı ekleyin:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` dosyanıza aşağıdakileri ekleyin:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatif olarak, en son sürümü doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisanslama
Aspose.Slides'ı sınırlama olmadan kullanmak için:

- API'yi değerlendirmek için **ücretsiz deneme** sürümüyle başlayın.  
- Uzun vadeli test için [Temporary License](https://purchase.aspose.com/temporary-license/) sayfasından **geçici lisans** talep edin.  
- [Purchase page](https://purchase.aspose.com/buy) üzerinden tam abonelik satın alın.

## Aspose.Slides for Java ile pasta grafik PowerPoint ekleme

Yeni bir sunum yükleyin, bir pasta grafiği ekleyin ve dosyayı kaydedin—tam üç adımda. Bu desen, herhangi bir veri seti boyutu için çalışır ve otomatik olarak onlarca slayt üretmek üzere bir döngü içinde kullanılabilir. Yaklaşım hafiftir, sadece birkaç satır kod ve dış kaynak gerektirmez; bu da hem küçük yardımcı programlar hem de büyük toplu işler için uygundur.

### Adım 1: Sunumu Başlatma
`Presentation` sınıfı bellekte tek bir PowerPoint dosyasını temsil eder. Bir örnek oluşturmak, üzerinde çalışabileceğiniz yeni, boş bir slayt destesi sağlar.
```java
Presentation pres = new Presentation();
```

### Adım 2: Pasta Grafiği Ekleme
İlk slayta bir pasta grafiği ekleyin. Koordinatlar (50, 50) ve boyut (600 × 400), standart 16:9 düzenine uyar ve başlıklar için alan bırakır.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Adım 3: Sunumu Kaydetme
Sunumu diske yazın. `YOUR_OUTPUT_DIRECTORY` ifadesini dosyanın kaydedileceği klasörle değiştirin.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Adım 4: Kaynakları Temizleme
`Presentation` nesnesini serbest bırakarak yerel kaynakları temizleyin ve bellek sızıntılarını önleyin.
```java
if (pres != null) pres.dispose();
```

## Veri noktasının patlamasını ve rengini nasıl özelleştirirsiniz?

Grafiği yükleyin, hedef veri noktasını bulun ve ardından bir patlama offseti ve katı dolgu rengi uygulayın. Bu, dilimin vurgulanmasını sağlar. Bu ayarlamalar, izleyicinin kritik değerlere dikkatini çekmeye ve grafiğin genel okunabilirliğini artırmaya yardımcı olur.

### Adım 1: Mevcut Bir Sunumu Yükleme (veya az önce oluşturduğunuzu yeniden kullanma)
`Presentation` nesnesi mevcut bir PowerPoint dosyasını belleğe yükler ve içeriğini değiştirmenize olanak tanır.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Adım 2: Grafiğe ve Hedef Veri Noktasına Erişim
`IDataPoint` arayüzü, bir grafik serisindeki tek bir veri noktasını (dilim) temsil eder.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Adım 3: Patlamayı ve Rengi Uygulama
`setExplosion(int)` bir dilimin grafik merkezinden piksel cinsinden ne kadar uzaklaştırılacağını ayarlar. Dilimi görsel olarak `setExplosion(20)` ile ayırın ve dolgusunu `setFillType(FillType.Solid)` ve `setSolidFillColor(Color.BLUE)` kullanarak maviye değiştirin.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Adım 4: Kaydet ve Serbest Bırak
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Pratik Uygulamalar
- **Satış Raporları:** En çok satan ürünleri patlatılmış dilimlerle vurgulayın.  
- **Bütçe Analizi:** Bölümlere hızlı görsel karşılaştırma için farklı renkler atayın.  
- **Eğitim Slaytları:** Karmaşık kavramları sindirilebilir grafik bölümlerine ayırın.  

## Performans Düşünceleri
- **Nesneleri hemen serbest bırakın** bellek sızıntılarını önlemek için, özellikle bir döngüde çok sayıda slayt oluştururken.  
- **Yığın kullanımını izleyin** büyük sunumlar için; verileri akış olarak göndermek ve bellek ayak izini düşük tutmak için `OutputStream` kabul eden `Save` aşırı yüklemesini kullanın.  
- **JDK 16+** kullanın; en yeni çöp toplama iyileştirmelerinden faydalanarak 1.000 slaytlık desteler için işleme süresini %30'a kadar azaltabilirsiniz.

## Sonuç
Artık Aspose.Slides for Java kullanarak **pasta grafik PowerPoint** dosyaları eklemek için eksiksiz, üretime hazır bir iş akışına sahipsiniz. Markanıza uygun olması için farklı patlama mesafeleri, renkler ve veri setleriyle deneyler yapın. Hazır olduğunuzda, çubuk, çizgi veya dağılım gibi diğer grafik türlerini keşfederek PowerPoint içinde tam bir analiz panosu oluşturun.

## Sıkça Sorulan Sorular

**S: Aspose.Slides for Java kullanmanın en büyük avantajı nedir?**  
**C:** Microsoft Office kurulu olmadan programatik olarak PowerPoint dosyaları oluşturmanıza, düzenlemenize ve render etmenize olanak tanır; 70+ grafik türü ve 100+ dosya formatını destekler.

**S: Sıfırdan bir PowerPoint dosyası oluşturabilir miyim?**  
**C:** Evet, bir `Presentation` nesnesi oluşturun, slayt, grafik veya şekil ekleyin ve ardından `save` metodunu çağırın—tamamen saf Java kodu ile.

**S: Belirli bir pasta dilimini nasıl patlatırım?**  
**C:** Dilim için `IDataPoint` nesnesini alın ve `setExplosion(pixelOffset)` metodunu çağırın. Offset, dilimin ne kadar dışarı kaydırılacağını belirler.

**S: Oluşturabileceğim slayt sayısında bir sınırlama var mı?**  
**C:** Aspose.Slides, tek bir dosyada **10.000 slayta** kadar sunumu işleyebilir; tüm veriyi belleğe yüklememek için çıktıyı akış olarak göndermeniz yeterlidir.

**S: Daha gelişmiş grafik özelleştirme örneklerini nerede bulabilirim?**  
**C:** Ayrıntılı API referansları ve örnek projeler için resmi [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) sayfasına bakın.

## Kaynaklar
- **Dokümantasyon:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Kütüphane İndirme:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Lisans Satın Al:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Ücretsiz Deneme:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Geçici Lisans:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Destek Forumu:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-07-08  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java Kullanarak PowerPoint'te Grafikleri Canlandırma – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Aspose.Slides for Java Kullanarak PowerPoint'te Grafik Düzenleri Oluşturma ve Doğrulama | SEO-Optimizeli Kılavuz](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}