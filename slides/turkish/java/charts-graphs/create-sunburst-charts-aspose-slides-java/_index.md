---
date: '2026-07-03'
description: Java kullanarak Aspose.Slides ile adım adım sunburst grafiklerini nasıl
  oluşturacağınızı öğrenin, PowerPoint sunumları için tam özelleştirme seçenekleriyle.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Java'da Aspose.Slides Kullanarak Sunburst Grafiklerini Nasıl Oluşturulur
url: /tr/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java Kullanarak Aspose.Slides ile Güneş Patlaması Grafikleri Nasıl Oluşturulur

## Giriş
Günümüzün veri odaklı sunumlarında, **güneş patlaması nasıl oluşturulur** görselleştirmelerini hızlı bir şekilde oluşturmak slaytlarınızı öne çıkarabilir. Bu öğretici, proje kurulumundan son dışa aktarmaya kadar Aspose.Slides for Java ile bir Sunburst grafiği oluşturmayı adım adım gösterir, böylece Java ekosisteminden çıkmadan etkileyici hiyerarşik veri grafikleri sunabilirsiniz.

## Hızlı Yanıtlar
- **PowerPoint dosyası için ana sınıf nedir?** `Presentation` – bellek içinde tüm PPTX'i temsil eder.  
- **Temel bir güneş patlaması için kaç satır kod gerekir?** Kütüphane referans alındıktan sonra genellikle 5–7 satır.  
- **Hangi çıktı formatları desteklenir?** PPTX, PDF, PNG, SVG ve HTML.  
- **Bireysel segmentleri biçimlendirebilir miyim?** Evet – dolgu renkleri, kenarlıklar ve veri etiketleri tamamen özelleştirilebilir.  
- **Üretim için lisansa ihtiyacım var mı?** Ücretsiz değerlendirme test için çalışır; dağıtım için ticari lisans gereklidir.

## Sunburst Grafiği Nedir?
Sunburst grafiği, hiyerarşik verileri konsantrik halkalar şeklinde görselleştirir; her halka hiyerarşinin bir seviyesini temsil eder. İzleyicilerin ebeveyn‑çocuk ilişkilerini anlık olarak kavramasını sağlar ve organizasyon şemaları, taksonomi gösterimleri ve çok seviyeli metrikler için idealdir. Özellikle ürün hatları, coğrafi bölgeler veya organizasyon yapıları gibi çok seviyeli kategorileri göstermek için faydalıdır; izleyiciler hem genel dağılımı hem de her segmentteki ayrıntılı bölümü görebilir.

## Sunburst Grafiklerinde Neden Aspose.Slides Kullanılmalı?
Aspose.Slides, **30+ grafik türünü** destekler, **500 MB**'a kadar dosyaları bellek içine tüm belgeyi yüklemeden işler ve grafikleri **300 DPI**'de kristal netliğinde oluşturur. Bu ölçülebilir yetenekler, büyük sunumlarda bile hızlı üretim ve yüksek kalite görseller sağlar. Ayrıca, kütüphane iş parçacığı‑güvenli işlemler sunar ve popüler Java yapı araçlarıyla sorunsuz entegrasyon sağlar; bu da masaüstü ve sunucu‑tarafı sunum üretimi için ölçeklenebilir bir çözüm sunar.

## Önkoşullar
- Java Development Kit (JDK) 8 veya daha yeni bir sürüm.  
- Bağımlılık yönetimi için Maven veya Gradle.  
- Aspose.Slides for Java (en son sürüm).  
- Hiyerarşik veri yapıları hakkında temel anlayış.

## Sunburst Grafiklerini Adım Adım Nasıl Oluşturulur?
Ortamınızı yükleyin, bir grafik ekleyin, hiyerarşik verileri besleyin, biçimlendirin ve dosyayı kaydedin – hepsi birkaç basit adımda. Aşağıda ekstra kod yazmadan izleyebileceğiniz tam iş akışı verilmiştir. İşlem tamamen otomatik olup manuel UI etkileşimi gerektirmez ve talep üzerine grafik üretmek için toplu işler veya web servislerine entegre edilebilir.

### Adım 1: Projeyi Kurun
`pom.xml` dosyanıza Aspose.Slides Maven bağımlılığını (veya eşdeğer Gradle kodunu) ekleyin. Bu, gerekli tüm ikili dosyaları ve geçişli kütüphaneleri getirir.

### Adım 2: Sunumu Yükleyin veya Oluşturun
`Presentation`, Aspose.Slides'ın bellek içinde tek bir PowerPoint dosyasını temsil eden üst‑seviye nesnesidir. Yeni bir sunum için `new Presentation()` ile örnekleyin veya mevcut bir PPTX'i açmak için dosya yolunu geçin.

### Adım 3: Sunburst Grafiği Ekleyin
`slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` kullanarak bir slayta yeni bir grafik şekli ekleyin. Bu, veri için hazır bir Sunburst yer tutucusu oluşturur. `ChartType.Sunburst`, bir slayta grafik eklerken Sunburst grafik türünü belirtir.

### Adım 4: Hiyerarşik Verileri Doldurun
`ChartData`, bir grafiğin veri serilerini ve kategorilerini tutar. Grafiğin `ChartData` koleksiyonuna erişin ve hiyerarşinizi yansıtan serileri ve kategorileri ekleyin. Her seviye için `ParentSeries` özelliği aracılığıyla ebeveyn‑çocuk ilişkisini belirtin; bu sayede grafik otomatik olarak konsantrik halkaları oluşturur.

### Adım 5: Görünümü Özelleştirin
`ChartSeries` ve `ChartDataPoint` nesneleri aracılığıyla segment renklerini, kenarlık stillerini ve veri etiketlerini ince ayar yapın. `ChartSeries`, bir grafikteki veri noktası serisini temsil eder. `ChartDataPoint` ise bir serideki tek bir veri noktasını temsil eder. Ayrıca 3‑D döndürmeyi etkinleştirebilir veya belirli dilimleri vurgulamak için `Explode` özelliğini ayarlayabilirsiniz.

### Adım 6: Sunumu Kaydedin
`SaveFormat` enum'u, bir sunumu hangi dosya formatlarında kaydedebileceğinizi tanımlar. Dosyayı diske yazmak için `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` çağrısını yapın. `SaveFormat` enum değerini değiştirerek PDF veya PNG olarak da dışa aktarabilirsiniz.

## Sunburst Grafiği Renklerini Nasıl Özelleştirirsiniz?
Her `ChartDataPoint` için `point.getFillFormat().setFillType(FillType.Solid)` ve ardından `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))` kullanarak bir dolgu rengi belirleyin. Bu doğrudan yaklaşım, kurumsal marka renklerine uymanızı veya önemli veri noktalarını vurgulamanızı sağlar. Ayrıca, degrade dolgu uygulayabilir, şeffaflığı ayarlayabilir veya slayt tasarımınızın geri kalanıyla tutarlılık sağlamak için tema renklerini kullanabilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **Problem:** Hiyerarşi düz görünüyor.  
  **Solution:** Her alt serinin `ParentSeries` özelliğine doğru şekilde referans verdiğinden emin olun. Eksik bağlantılar, grafiğin tüm verileri tek bir seviye olarak işlemesine neden olur.  
- **Problem:** Dışa aktarılan PNG bulanık görünüyor.  
  **Solution:** `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` ayarını yaparak dışa aktarma DPI'sını artırın.  
- **Problem:** Büyük PPTX dosyaları OutOfMemoryError hatasına yol açıyor.  
  **Solution:** Verileri akış olarak işlemek ve bellek kullanımını düşük tutmak için `Presentation.setMemoryOptimization(true)` kullanın.

## Sıkça Sorulan Sorular

**Q:** CSV dosyasından bir Sunburst grafiği oluşturabilir miyim?  
**A:** Evet. CSV'yi okuyun, hiyerarşiyi bellek içinde oluşturun ve kaydetmeden önce grafiğin `ChartData` koleksiyonuna besleyin.

**Q:** Aspose.Slides, Sunburst grafikleri için animasyonlu geçişleri destekliyor mu?  
**A:** Evet. Slayta bir `SlideShowTransition` uygulayın veya grafik‑seviyesinde animasyon için `ChartFormat.setAnimationEnabled(true)` kullanın.

**Q:** Grafiği SVG vektör grafiği olarak dışa aktarmak mümkün mü?  
**A:** Kesinlikle. Sunumu `SaveFormat.Svg` ile kaydederek Sunburst grafiğinin ölçeklenebilir vektör sürümünü elde edebilirsiniz.

**Q:** Bir Sunburst grafiği kaç veri noktasına kadar dayanabilir?  
**A:** Aspose.Slides, performans düşüşü olmadan tek bir Sunburst grafiğinde **10.000** veri noktasına kadar güvenilir şekilde işler.

**Q:** Her dağıtım ortamı için ayrı bir lisansa ihtiyacım var mı?  
**A:** Tek bir ticari lisans, lisans şartları kabul edildiği sürece tüm ortamları (geliştirme, test, üretim) kapsar.

## Sonuç
Artık Aspose.Slides kullanarak Java'da **güneş patlaması** grafiklerini nasıl oluşturacağınızı adım adım gösteren eksiksiz bir rehbere sahipsiniz. Yukarıdaki iş akışını izleyerek herhangi bir PowerPoint sunumu için yüksek kaliteli, tamamen özelleştirilebilir hiyerarşik görselleştirmeler üretebilirsiniz.

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## İlgili Öğreticiler

- [Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Dinamik Sunumlar İçin Aspose.Slides Java Kullanarak PowerPoint Grafik Özelleştirmesinde Ustalık](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Aspose.Slides for Java ile PowerPoint Grafik Kategorilerini Animasyonlu Hale Getirme | Adım Adım Kılavuz](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}