---
date: '2026-08-06'
description: Aspose.Slides for Java kullanarak legend font color'ı nasıl değiştireceğinizi
  ve chart legend text'i nasıl düzenleyeceğinizi öğrenin. Chart legend'ları hızlı
  bir şekilde customize etmek için step‑by‑step talimatları izleyin.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Aspose.Slides for Java ile legend font color'ı nasıl değiştireceğinizi
  ve chart legend text'i nasıl düzenleyeceğinizi öğrenin. Bu kılavuz, tam adımları
  ve best practices'i gösterir.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Aspose.Slides for Java'da legend font color nasıl değiştirilir
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Aspose.Slides for Java'da legend font color nasıl değiştirilir
url: /tr/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java'da lejand yazı tipi rengini nasıl değiştirirsiniz

## Giriş
Bir grafikte **legend yazı tipi rengini** değiştirmeniz gerekiyorsa, Aspose.Slides for Java size her lejand girişini tam kontrol etme imkanı sunar. Bu öğretici, lejand metin stillerini özelleştirmenizi, kalın veya italik yazı tipleri uygulamanızı ve katı renkler ayarlamanızı adım adım gösterir, böylece grafiğiniz tam istediğiniz gibi görünür. Bu rehberin sonunda, grafik lejand metnini güvenle değiştirebilecek ve değişiklikleri mevcut herhangi bir sunuma entegre edebileceksiniz.

**Öğrenecekleriniz**
- Programatik olarak **legend yazı tipi rengini** değiştirmeyi.
- **Grafik lejand metnini** kalın, italik ve boyut gibi şekillerde **değiştirme** yolları.
- Tek bir sunumda birden fazla grafiğe değişiklikleri uygulama ipuçları.
- Bu adımları daha büyük bir otomasyon iş akışına nasıl entegre edeceğiniz.

## Hızlı cevaplar
- **Tek bir lejand girişinin rengini değiştirebilir miyim?** Evet – girişe indeks üzerinden erişip doldurma formatını katı renk olarak ayarlayabilirsiniz.  
- **Bu API'leri kullanmak için lisansa ihtiyacım var mı?** Üretim için geçici veya ücretli lisans gerekir; değerlendirme için ücretsiz deneme çalışır.  
- **Hangi Java sürümü destekleniyor?** Aspose.Slides for Java 25.4+ JDK 16 ve üzeriyle çalışır.  
- **Değişiklikler diğer grafik öğelerini etkiler mi?** Hayır, lejand biçimlendirmesi veri serisi stilinden izole edilmiştir.  
- **Toplu işleme mümkün mü?** Kesinlikle – slaytları ve grafikleri döngüyle işleyerek tüm sunumda aynı lejand ayarlarını uygulayabilirsiniz.

## Legend yazı tipi rengini değiştirme nedir?
`change legend font color`, Aspose.Slides API'si kullanarak bir grafiğin lejand girişlerinin metin rengini ayarlama programatik işlemini ifade eder. Bu işlem, temel verileri değiştirmeden lejandın görsel görünümünü günceller.

## Grafik lejandlarını neden özelleştirirsiniz?
Aspose.Slides **50+ giriş ve çıkış formatını** destekler ve **500+ slayt** içeren sunumları bellek kullanımını 200 MB'nin altında tutarak işleyebilir. Lejantları özelleştirmek okunabilirliği artırır, marka renklerini güçlendirir ve önemli veri noktalarının öne çıkmasını sağlar—özellikle görsel netliğin karar vermeyi yönlendirdiği iş veya eğitim sunumlarında.

## Önkoşullar
- **Aspose.Slides for Java** kütüphanesi (Version 25.4 veya daha yeni).  
- Java Development Kit (JDK) 16 veya üzeri.  
- IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE.  
- Bağımlılık yönetimi için Maven veya Gradle.  
- Temel Java programlama bilgisi.

## Aspose.Slides for Java'ı Kurma
Grafik lejandlarınızı özelleştirmeye başlamak için, aşağıdaki yöntemlerden birini kullanarak kütüphaneyi projenize ekleyin.

### Maven
Aşağıdaki bağımlılığı `pom.xml` dosyanıza ekleyin:
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
Ayrıca en son JAR dosyasını [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden edinebilirsiniz.

#### Lisans edinme adımları
- **Ücretsiz deneme:** Aspose.Slides özelliklerini keşfetmek için ücretsiz deneme ile başlayın.  
- **Geçici lisans:** Uzatılmış değerlendirme için geçici lisans başvurusu yapın.  
- **Satın alma:** Tam erişim için [Aspose Purchase](https://purchase.aspose.com/buy) adresinden lisans almayı düşünün.

#### Temel başlatma ve kurulum
Kütüphaneyi projenize ekledikten sonra:
1. Java uygulamanızda Aspose.Slides'ı başlatın.  
2. Mevcut bir sunumu yükleyin veya yeni bir tane oluşturun.

## Legend yazı tipi rengini nasıl değiştirirsiniz?
Lejant yazı tipi rengini değiştirmek için, sunumu yükleyin, grafik nesnesini alın, lejantını elde edin ve ardından her lejant girişinin metin formatını doldurma tipini katı olarak ayarlayıp istenen rengi belirleyerek değiştirin. Bu tek işlem, tüm slaytı yeniden çizmeden lejant metin rengini anında günceller. Örnek: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Bu yaklaşım herhangi bir grafik türü için çalışır ve tüm slaytı yeniden render etmeyi gerektirmez.

### Lejant metin özelliklerine erişme ve değiştirme

#### Tanım bağlantısı
`IChart` arayüzü bir slayttaki grafik nesnesini temsil eder ve `getLegend()` yöntemi, `ILegendEntry` öğelerinden oluşan bir koleksiyon içeren bir `ILegend` nesnesi döndürür.

#### Sunumunuza bir grafik ekleme
1. **Sunumu yükleyin:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Küme sütun grafiği ekleyin:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Yazı tipi özelliklerini özelleştirme
3. **Lejant giriş metin formatına erişin:**  
   Burada, `legendEntry` grafiğin lejandındaki tek bir girişi temsil eden bir `ILegendEntry` nesnesidir.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Belirli bir yükseklik ile kalın ve italik stillerini ayarlayın:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Daha iyi görünürlük için doldurma tipini katı renge değiştirin:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Sunumu kaydetme
6. **Değişikliklerinizi kaydedin:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Yaygın tuzaklar ve sorun giderme
- Lejant giriş indeksinin grafiğinizdeki seri sırası ile eşleştiğini doğrulayın.  
- `setSolidFillColor`'ı destekleyen bir kütüphane sürümü kullandığınızdan emin olun (versiyon 20.9'dan itibaren mevcut).

## Pratik uygulamalar
Lejant metnini özelleştirmek birçok gerçek dünya senaryosunda faydalıdır:

1. **İş sunumları:** Lejant renklerini kurumsal marka renkleriyle hizalayarak şık bir görünüm elde edin.  
2. **Eğitim materyalleri:** Zıt lejant renkleri kullanarak ana veri serilerini vurgulayın.  
3. **Pazarlama sunumları:** Performans metriklerini kalın, renkli lejantlarla vurgulayarak paydaşların dikkatini çekin.  

Ayrıca renk değerlerini bir veritabanı veya yapılandırma dosyasından çekerek lejant güncellemelerini otomatikleştirebilirsiniz.

## Performans hususları
Büyük sunumları işlerken şu ipuçlarını aklınızda tutun:

- **Verimli bellek yönetimi:** Kaydettikten sonra yerel kaynakları serbest bırakmak için `presentation.dispose()` çağırın.  
- **Yalnızca gerekli slaytları yükleyin:** Alt küme gerekiyorsa `Presentation.load(String path, LoadOptions options)` ile `LoadOptions.setLoadOnlySlideIds()` kullanın.  
- **Toplu işleme:** API çağrı sayısını azaltmak ve verimliliği artırmak için lejant güncellemelerini slayt başına gruplayın.

## Sonuç
Artık Aspose.Slides for Java kullanarak **legend yazı tipi rengini** ve **grafik lejand metnini** nasıl değiştireceğinizi biliyorsunuz. Bu özelleştirmeler görsel netliği artırır ve verileri daha etkili iletmenize yardımcı olur. Sunumunuzun stil rehberine uygun farklı yazı tipleri, boyutlar ve renklerle denemeler yapın ve gerçek profesyonel sunumlar oluşturmak için diğer grafik stil özelliklerini keşfedin.

**Sonraki adımlar**
- Aynı lejant stilini pasta ve çizgi grafiklerine uygulamayı deneyin.  
- Lejant özelleştirmesini veri etiketi biçimlendirmesiyle birleştirerek tamamen markalı bir grafik oluşturun.  

Sunumlarınızı yükseltmeye hazır mısınız? Yukarıdaki adımları uygulayın ve farkı anında görün!

## SSS Bölümü
1. **Lejant girişinin metin rengini nasıl değiştiririm?**  
   Lejant girişinin metin formatında `getFillFormat().setFillType(FillType.Solid)` ardından `setSolidFillColor(Color.YOUR_COLOR)` kullanın.

2. **Bu değişiklikleri bir sunumdaki tüm lejantlara uygulayabilir miyim?**  
   Evet – her slaytı döngüyle gezerek, her grafiği bulup lejant girişlerini bir döngü içinde güncelleyin.

3. **Metin uzunluğuna göre yazı tipi boyutunu dinamik olarak ayarlamak mümkün mü?**  
   Gerekli boyutu `TextFrame.getTextFrameFormat().getFontHeight()` ile hesaplayıp `setFontHeight(double)` ile ayarlayabilirsiniz.

4. **Lejant giriş indeksleme ile ilgili sorunlarla karşılaşırsam ne yapmalıyım?**  
   Kullandığınız indeksin seri sırası ile eşleştiğini iki kez kontrol edin; indekslerin sıfır tabanlı olduğunu unutmayın.

5. **Daha fazla Aspose.Slides örneği nerede bulunur?**  
   Kapsamlı rehberler ve API referansları için [Aspose Documentation](https://reference.aspose.com/slides/java/) adresini inceleyin.

**Ekstra Soru & Cevap**

**S: Lejant yazı tipi rengini değiştirmek dışa aktarılan PDF dosyalarını etkiler mi?**  
C: Hayır, renk değişikliği Aspose.Slides tarafından desteklenen tüm dışa aktarma formatlarında, PDF ve PPTX dahil, korunur.

**S: Katı renk yerine bir degrade (gradient) kullanabilir miyim?**  
C: Evet – `FillType.Gradient` ayarlayın ve `getGradientStyle()` ile degrade duraklarını yapılandırın.

**S: Bir grafiğin kaç lejand girişi olabilir?**  
C: Bir grafik en fazla 256 lejand girişi içerebilir; bu yalnızca eklediğiniz veri serisi sayısıyla sınırlıdır.

## Kaynaklar
- **Dokümantasyon:** Aspose.Slides özelliklerini kullanma üzerine kapsamlı rehber ([Link](https://reference.aspose.com/slides/java/)).  
- **İndirme:** Aspose.Slides for Java'ın en son sürümüne erişin ([Link](https://releases.aspose.com/slides/java/)).  
- **Satın Alma:** Tam yetenekleri açmak için lisans satın alın ([Link](https://purchase.aspose.com/buy)).  
- **Ücretsiz deneme & geçici lisans:** Ücretsiz denemelerle başlayın ve geçici lisanslar için başvurun ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Destek:** Aspose destek forumunda topluluktan yardım alın ([Link](https://forum.aspose.com/c/slides/11)).

**Son Güncelleme:** 2026-08-06  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4  
**Yazar:** Aspose

## İlgili Öğreticiler

- [PowerPoint Grafiklerini Geliştirme: Yazı Tipi ve Eksen Özelleştirme Aspose.Slides for Java ile](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: Dinamik Metin Çerçeveleri ve Yazı Tipi Özelleştirme Rehberi](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [PowerPoint'te Grafikleri Canlandırma Aspose.Slides for Java ile – Adım Adım Rehber](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}