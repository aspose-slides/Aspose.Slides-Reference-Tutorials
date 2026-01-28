---
date: '2026-01-17'
description: Aspose.Slides ile Java’da gruplanmış sütun grafik nasıl oluşturulur öğrenin.
  Bu adım adım kılavuz, grafiği nasıl ekleyeceğinizi, renkleri nasıl ayarlayacağınızı
  ve sunumu nasıl kaydedeceğinizi gösterir.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Java'da Aspose.Slides ile kümelenmiş sütun grafiği nasıl oluşturulur
url: /tr/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides ile kümeleme sütun grafiği nasıl oluşturulur

## Giriş
Görsel olarak etkileyici veri temsilleri oluşturmak, etkili iş sunumları için gereklidir ve **kümeleme sütun grafiği nasıl oluşturulur** konusunu programlı olarak öğrenmek, saatlerce manuel çalışmadan tasarruf etmenizi sağlar. Bu adım‑adım kılavuz, **Aspose.Slides for Java** kullanarak kümeleme sütun grafiklerini hızlı bir şekilde oluşturma ve biçimlendirme sürecini basitleştirir, sunumlarınızı profesyonel görsellerle zahmetsizce zenginleştirir.

Kütüphaneyi kurmaktan grafiği eklemeye, seri renklerini özelleştirmeye ve son dosyayı kaydetmeye kadar ihtiyacınız olan her şeyi adım adım anlatacağız.

### Neler Başaracaksınız
- Aspose.Slides for Java'yı kurun ve yapılandırın  
- **Kümeleme sütun grafiği oluşturun** yeni bir sunumda  
- Seri dolgu renklerini otomatik olarak uygulayın  
- Sunumu diske kaydedin  

Grafiğimizi oluşturmadan önce gereksinimlerle başlayalım!

## Hızlı Yanıtlar
- **Birincil sınıf nedir?** `Presentation` from `com.aspose.slides`  
- **Bir grafik nasıl eklenir?** Use `addChart(ChartType.ClusteredColumn, ...)` on a slide’s shape collection  
- **Renkleri otomatik olarak ayarlayabilir miyim?** Yes, call `setAutomaticSeriesColor(true)` on each series  
- **Kaydetmek için hangi format kullanılır?** `SaveFormat.Pptx` (PowerPoint)  
- **Lisans gerekli mi?** A trial works for testing; a full license is required for production  

## Önkoşullar
Başlamadan önce gerekli araç ve bilgiye sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar
Aspose.Slides for Java kütüphanesine ihtiyacınız olacak. JDK16 desteğiyle 25.4 sürümünü kullandığınızdan emin olun.

### Ortam Kurulum Gereksinimleri
Geliştirme ortamınız Java'yı (tercihen JDK16) desteklemeli ve Maven veya Gradle kullanarak projeler oluşturabilmelidir.

### Bilgi Önkoşulları
Temel Java programlaması, Maven/Gradle aracılığıyla kütüphanelerle çalışma ve PowerPoint sunumlarını anlama konularına aşina olmak faydalı olacaktır.

## Aspose.Slides for Java Kurulumu
Aspose.Slides'ı projenize entegre etmek için aşağıdaki kurulum talimatlarını izleyin:

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme**  
Doğrudan indirmeyi tercih edenler için, [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresini ziyaret edin.

### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Özellikleri keşfetmek için ücretsiz deneme ile başlayın.  
- **Geçici Lisans**: Sınırlama olmadan test etmek için geçici bir lisans edinin.  
- **Satın Alma**: Sürekli kullanım için tam bir lisans satın alın.

**Temel Başlatma ve Kurulum**  
Aspose.Slides'ı aşağıdaki gibi başlatın:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Uygulama Kılavuzu

### Özellik 1: Kümeleme Sütun Grafiği Oluşturma
Aspose.Slides for Java kullanarak bir kümeleme sütun grafiği oluşturalım. Bu özellik, slaytlarınıza görsel olarak çekici grafikler eklemenizi zahmetsizce sağlar.

#### Genel Bakış
Bu bölümde, yeni bir sunum başlatacak ve ilk slayta bir kümeleme sütun grafiği ekleyeceğiz.

**Adım 1: Sunumu Başlatma**  
`Presentation` nesnesi oluşturarak PowerPoint dosyalarıyla çalışmaya başlayın:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Adım 2: Kümeleme Sütun Grafiği Ekleme**  
Grafiği belirtilen koordinatlarda (100, 50) ve boyutlarda (600 × 400) ekleyin:
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Adım 3: Kaynakları Temizleme**  
Bellek sızıntılarını önlemek için her zaman kaynakları serbest bırakın:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

### Özellik 2: Otomatik Seri Dolgu Rengini Ayarlama
Otomatik seri dolgu renklerini ayarlayarak görsel çekiciliği artırın.

#### Genel Bakış
Her grafiğin serisinin rengini otomatik olarak ayarlayarak tutarlı bir görünüm elde edin.

**Adım 1: Grafiğe Erişme ve Serileri Döngüleme**  
Grafiğinizi oluşturduktan sonra ona erişin ve serileri üzerinde döngü yapın:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Adım 2: Kaynak Yönetimi**  
İşiniz bittiğinde presentation nesnesini serbest bırakın:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

### Özellik 3: Sunumu Diske Kaydetme
Son olarak, Aspose.Slides kullanarak çalışmanızı kolayca kaydedin.

#### Genel Bakış
Düzenlenmiş sunumlarınızı istediğiniz formatta ve konumda kaydedin.

**Adım 1: Çıktı Yolunu Tanımlama**  
Dosyayı nereye kaydetmek istediğinizi belirtin:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Adım 2: Sunumu Kaydetme**  
`Presentation` nesnesinin `save` metodunu kullanın:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Pratik Uygulamalar
- **Finansal Raporlar**: Çeyrek dönem kazançlarını net bir şekilde görselleştirin.  
- **Pazarlama Veri Analizi**: Kampanya sonuçlarını etkileyici görsellerle sergileyin.  
- **Proje Yönetimi**: Takım toplantılarında kilometre taşlarını ve ilerlemeyi görsel olarak izleyin.

## Performans Düşünceleri
Aspose.Slides ile çalışırken aşağıdaki en iyi uygulamaları göz önünde bulundurun:

- `Presentation` nesnelerini zamanında serbest bırakarak belleği etkili bir şekilde yönetin.  
- Sunumları kaydederken dosya boyutlarını optimize ederek disk alanından tasarruf edin.  
- Grafik serileri için verimli veri yapıları kullanarak performansı artırın.

## Sonuç
Tebrikler! Aspose.Slides for Java kullanarak **kümeleme sütun grafiği oluşturma** ve biçimlendirme konusunda bilgi edindiniz. Bu beceri, sunumlarınızı geliştirmekle kalmaz, aynı zamanda görsel veri temsili sürecini de kolaylaştırır.

**Sonraki Adımlar:**  
Grafik öğelerini özelleştirme, veri etiketleri ekleme veya veri kaynaklarıyla entegrasyon gibi ek özellikleri keşfederek projenizin yeteneklerini genişletin.

## SSS Bölümü
1. **Belirli bir JDK sürümü için Aspose.Slides'ı nasıl kurarım?**  
   - Kurulum bölümünde gösterildiği gibi `classifier` belirterek Maven/Gradle bağımlılıklarını kullanın.  

2. **Sunumum doğru kaydedilmezse ne yapmalıyım?**  
   - Çıktı dizinine yazma izninizin olduğundan ve dosya yolunun doğru olduğundan emin olun.  

3. **Aspose.Slides for Java ile başka grafik türleri oluşturabilir miyim?**  
   - Kesinlikle! `ChartType` seçeneklerini inceleyin; Örneğin Pasta, Çubuk veya Çizgi grafikleri.  

4. **Grafiğimde büyük veri setlerini nasıl yönetirim?**  
   - Veri yapılarını optimize edin ve görselleştirmeden önce verilerinizi ön işleme tabi tutmayı düşünün.  

5. **Aspose.Slides for Java kullanımıyla ilgili daha fazla örnek nerede bulunur?**  
   - Kapsamlı kılavuzlar ve kod örnekleri için [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) adresini ziyaret edin.

## Kaynaklar
- **Dokümantasyon**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **İndirme**: [Aspose.Slides'ı İndir](https://releases.aspose.com/slides/java/)  
- **Satın Alma**: [Lisans Satın Al](https://purchase.aspose.com/buy)  
- **Ücretsiz Deneme**: [Ücretsiz Deneme Başlat](https://releases.aspose.com/slides/java/)  
- **Geçici Lisans**: [Buradan Talep Et](https://purchase.aspose.com/temporary-license/)  
- **Destek**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-01-17  
**Test Edilen:** Aspose.Slides 25.4 (JDK16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}