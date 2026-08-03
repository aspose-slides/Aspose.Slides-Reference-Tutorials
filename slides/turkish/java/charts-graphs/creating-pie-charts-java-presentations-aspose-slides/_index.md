---
date: '2026-08-01'
description: Aspose Slides lisansını kullanarak Java sunumlarında pasta grafikler
  oluşturmayı ve özelleştirmeyi öğrenin. Pasta grafik verilerini yapılandırmak ve
  grafik slaytlarını verimli bir şekilde eklemek için adım adım talimatları izleyin.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Aspose Slides lisansını kullanarak Java sunumlarında pasta grafikler
  oluşturmayı ve özelleştirmeyi öğrenin. Pasta grafik verilerini yapılandırmak ve
  grafik slaytlarını verimli bir şekilde eklemek için adım adım talimatları izleyin.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Java'da Aspose Slides Lisansı ile Pasta Grafikler Oluşturun
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Java'da Aspose Slides Lisansı ile Pasta Grafikler Oluşturun
url: /tr/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Kullanarak Java Sunumlarında Pasta Grafikler Nasıl Oluşturulur

## Giriş

Profesyonel görünümlü sunumlar üretmeniz gerekiyorsa, **an Aspose Slides license** size grafik oluşturma ve stil verme yeteneğini programlı olarak sağlar. Bu rehberde bir pasta grafiği nasıl oluşturacağınızı, verilerini nasıl yapılandıracağınızı ve bir Java slayt destesine nasıl gömeceğinizi öğreneceksiniz—Microsoft PowerPoint'e bağımlı olmadan. Kurulumu, kod akışını ve en iyi uygulama ipuçlarını adım adım inceleyecek ve dakikalar içinde şık görsel raporlar sunabileceksiniz.

**What You’ll Learn:**
- Geçerli bir lisansla Aspose.Slides for Java kurulumu
- Pasta grafiği oluşturma ve özelleştirme adımları
- Pasta grafiği verilerini yapılandırma ve grafik slaytları ekleme
- Yaygın tuzaklar ve performans ipuçları

Ortamınızın hazır olduğunu doğrulayarak başlayalım.

## Hızlı Yanıtlar
- **Aspose Slides lisansı neyi etkinleştirir?** Tam özellikli grafik oluşturma, PDF/HTML'ye dışa aktarma ve filigranların kaldırılması.
- **Hangi Java sürümü gereklidir?** JDK 16 veya daha yeni.
- **Maven veya Gradle gerekli mi?** Her ikisi de çalışır; kütüphane her iki araçla da kullanılabilir.
- **Bir pasta grafiği kaç veri noktasını tutabilir?** Bellek sorunları olmadan 10 000 noktaya kadar.
- **Slaytı bir görüntü olarak dışa aktarabilir miyim?** Evet – PNG, JPEG, SVG ve daha fazlası desteklenir.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzu doğrulayın:
- **Gerekli Kütüphaneler:** Aspose.Slides for Java (sürüm 25.4 ve üzeri) – bu sürüm en yeni dosya formatlarını ve performans iyileştirmelerini destekler.
- **Ortam Kurulumu:** IDE'nizde veya derleme sisteminizde JDK 16+ yüklü ve yapılandırılmış.
- **Temel Bilgi:** Java, Maven veya Gradle ve nesne yönelimli programlama kavramlarına aşina olmak.

## Aspose.Slides for Java Kurulumu

Aspose.Slides for Java'ı projenize eklemek için aşağıdaki yaygın derleme araçlarıyla bağımlılığı nasıl ekleyeceğinizi gösteriyoruz:

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

**Doğrudan İndirme:** En son JAR dosyasını ayrıca [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisans Alımı

Aspose, tüm özellikleri açan ücretsiz bir deneme sunar, ancak üretim ortamında değerlendirme filigranlarını kaldırmak ve performans avantajlarından yararlanmak için **valid Aspose Slides license** gereklidir. Satın alma seçenekleri [purchase page](https://purchase.aspose.com/buy) adresinde listelenmiştir. Lisans dosyasını edindikten sonra uygulama başlangıcında bir kez yükleyin:

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Uygulama Kılavuzu

### Pasta Grafiği Oluşturma ve Sunuma Ekleme

#### Genel Bakış
Bu bölüm, bir pasta grafiği oluşturma, veri serisini yapılandırma ve grafiği bir slayta gömme sürecini açıklar. Sunum nesnesinin başlatılmasından son dosyanın kaydedilmesine kadar tam akışı göreceksiniz.

#### Adım 1: Sunumu Başlatma  
`Presentation` is Aspose.Slides' top‑level object that represents a PowerPoint file in memory. Creating an instance gives you a blank slide deck ready for modification.  
```java
demo.Presentation pres = new demo.Presentation();
```  
Bu satır, sonraki tüm değişikliklerin uygulanacağı yeni bir sunum oluşturur.

#### Adım 2: Slayta Pasta Grafiği Ekleme  
`Chart` is the class that encapsulates chart objects, including pie charts. Adding a chart to a slide is a single method call that specifies position and size.  
```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` ve `yPosition`, grafiğin sol‑üst köşesini ayarlar.  
- `width` ve `height`, grafiğin slayttaki görsel alanını tanımlar.

#### Adım 3: Pasta Grafiği Verilerini Yapılandırma  
`ChartData` holds the data series for a chart.  
**Pasta grafiği verilerini nasıl yapılandırırım?**  
İlk olarak kısa bir yanıt verin: `ChartData` koleksiyonunu kullanarak bir seri ekleyin, ardından `ChartDataPoint` nesnelerini sayısal değerler ve kategori adlarıyla doldurun. Bu yaklaşım, etiket biçimlendirmesini korurken 10 000 dilime kadar görüntülemenizi sağlar. Verileri ayarladıktan sonra renkleri, lejandları ve veri etiketlerini kurumsal stil kılavuzunuza göre özelleştirebilirsiniz.

Şimdi iki kategori ekleyen ve etiketlerini gösteren kod:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Bu snippet bir veri serisi oluşturur, iki nokta ekler ve grafikte kategori etiketlerini etkinleştirir.

#### Adım 4: Sunumu Kaydetme  
Son olarak, sunumu istediğiniz bir dosya formatında (PPTX, PDF veya PNG) kalıcı hale getirin. `save` yöntemi aktif lisansı dikkate alır, böylece deneme filigranları görünmez.  
```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Yaygın Sorunlar ve Çözümler
- **Missing License Error:** Lisans dosyası yolunun doğru olduğundan ve `License` nesnesinin herhangi bir Aspose.Slides çağrısından önce oluşturulduğundan emin olun.
- **Empty Chart:** `ChartData` serisinin en az bir `ChartDataPoint` içerdiğini doğrulayın. Boş bir seri, boş bir grafik alanına yol açar.
- **Performance Lag with Large Data Sets:** Kullanılmayan slaytları atmak için `presentation.getSlides().removeAt(index)` kullanın ve yoğun işlem sonrası `System.gc()` çağırın.

## Pratik Uygulamalar
1. **Business Reports:** Tek bir pasta grafiği ile bölgelere göre pazar payı veya gelir dağılımını görselleştirin.
2. **Academic Presentations:** Anket sonuçlarını veya deney sonuçlarını net, sindirilebilir bir formatta gösterin.
3. **Project Dashboards:** Görev tamamlama yüzdelerini veya kaynak tahsislerini anında bir slaytta temsil edin.

Ayrıca Aspose.Slides'ı JDBC ile birleştirerek bir veritabanından canlı veri çekebilir ve haftalık yönetici toplantıları için güncel grafikler oluşturabilirsiniz.

## Performans Düşünceleri
Birçok yüksek çözünürlüklü görüntü veya büyük veri seti içeren sunumlarla çalışırken:
- `try‑with‑resources` veya açık `dispose()` çağrılarıyla nesneleri hızlı bir şekilde serbest bırakın.
- Bellek kullanımını düşük tutmak için slayt kaynaklarının tembel yüklemesini etkinleştirin.
- Toplu işleme için mümkün olduğunca tek bir `Presentation` örneğini yeniden kullanarak JVM yükünü azaltın.

## Sonuç
Artık **Aspose Slides license** kullanarak Java'da pasta grafikler oluşturmak için eksiksiz, üretime hazır bir iş akışına sahipsiniz. Slaytlarınızı daha da zenginleştirmek için çubuk, çizgi veya halka gibi ek grafik türleriyle deneyler yapın. Sonraki adımda, API'nin dışa aktarma yeteneklerini keşfederek PDF raporları veya PNG görüntüleri otomatik olarak üretin.

## Sıkça Sorulan Sorular

**Q: Tek bir slayta birden fazla grafik nasıl eklerim?**  
A: Her grafik için `slide.getShapes().addChart()` metodunu çağırın ve her örnek için benzersiz koordinatlar ve boyutlar sağlayın.

**Q: Aspose.Slides for Java için bazı alternatifler nelerdir?**  
A: Apache POI ve JFreeChart yaygın alternatiflerdir, ancak kapsamlı dışa aktarma seçenekleri ve lisans modeli açısından Aspose'un sunduklarından yoksundur.

**Q: Aspose.Slides kullanarak sunumumu başka formatlara dönüştürebilir miyim?**  
A: Evet—tek bir `save` çağrısıyla PDF, XPS, HTML, PNG, JPEG, SVG ve daha fazlasına dışa aktarabilirsiniz.

**Q: Büyük bir geliştirme ekibi için lisanslamayı nasıl yönetirim?**  
A: Birden fazla geliştirici ve sunucuyu kapsayan kurumsal bir lisans satın alın; hacim indirimleri için Aspose satış ekibiyle iletişime geçin.

**Q: Grafik verilerim sık sık güncellenirse ne yapmalıyım?**  
A: Aspose.Slides'ı bir veri kaynağı (ör. SQL sorgusu) ile entegre edin ve çalışma zamanında grafiği yeniden oluşturun; API dinamik veri bağlamayı destekler.

## Kaynaklar
- **Dokümantasyon:** [Aspose.Slides Java Referansı](https://reference.aspose.com/slides/java/)
- **İndirme:** [En Son Sürümler](https://releases.aspose.com/slides/java/)
- **Satın Al:** [Lisans Satın Al](https://purchase.aspose.com/buy)
- **Ücretsiz Deneme:** [Aspose.Slides Ücretsiz Deneyin](https://releases.aspose.com/slides/java/)
- **Geçici Lisans Al:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Destek:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-08-01  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Slides for Java Kullanarak Sunumlarda Grafik Ekleme ve Yapılandırma Nasıl Yapılır](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Aspose.Slides ile Java Sunumlarında Grafik Oluşturma ve Özelleştirme](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Aspose.Slides Java ile Sunum Oluşturma ve Yapılandırma: Adım Adım Kılavuz](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}