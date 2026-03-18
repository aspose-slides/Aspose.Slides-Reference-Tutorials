---
date: '2026-03-18'
description: Aspose.Slides ile Java’da gruplanmış sütun grafiği nasıl oluşturulur,
  grafiği nasıl eklenir, renkler nasıl ayarlanır ve sunum PPTX olarak nasıl kaydedilir
  öğrenin. Kod örnekleriyle adım adım rehber.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Java'da Aspose.Slides ile küme sütun grafiği nasıl oluşturulur
url: /tr/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java ile Aspose.Slides kullanarak kümelenmiş sütun grafiği oluşturma

## Giriş
İş etkili sunumlar için görsel olarak etkileyici veri temsilleri oluşturmak çok önemlidir ve **kümelenmiş sütun grafiği nasıl oluşturulur** öğrenmek, manuel çalışmaya harcayacağınız saatleri tasarruf ettirebilir. Bu öğreticide **grafiğin nasıl ekleneceğini**, renklerin otomatik **ayarlanmasını** ve sonunda **sunumu PPTX olarak kaydetmeyi** **Aspose.Slides for Java** kullanarak göreceksiniz. Kütüphaneyi kurmaktan grafiği eklemeye, seri dolgu renklerini özelleştirmeye ve dosyayı kalıcı hale getirmeye kadar ihtiyacınız olan her şeyi adım adım göstereceğiz.

### Neler Başaracaksınız
- Aspose.Slides for Java'ı kurun ve yapılandırın  
- **Kümelenmiş sütun grafiği oluşturun** yeni bir sunumda  
- Serilerin dolgu renklerini otomatik olarak uygulayın (**renklerin nasıl ayarlanacağını**)  
- **Sunumu PPTX olarak kaydedin** diske (**sunumun nasıl kaydedileceği**)  

Grafiği oluşturmaya başlamadan önce önkoşulları halledelim.

## Hızlı Yanıtlar
- **Ana sınıf nedir?** `Presentation` from `com.aspose.slides`  
- **Grafik nasıl eklenir?** Bir slaytın şekil koleksiyonunda `addChart(ChartType.ClusteredColumn, …)` kullanın (**grafiğin nasıl ekleneceği**)  
- **Renkler otomatik olarak ayarlanabilir mi?** Evet, her seri için `setAutomaticSeriesColor(true)` çağırın (**renklerin nasıl ayarlanacağı**)  
- **Kaydetme için hangi format kullanılır?** `SaveFormat.Pptx` (PowerPoint) (**sunumu pptx olarak kaydet**)  
- **Lisans gerekli mi?** Deneme sürümü test için çalışır; üretim için tam lisans gereklidir  

## Önkoşullar
Başlamadan önce gerekli araç ve bilgiye sahip olduğunuzdan emin olun:

### Gerekli Kütüphaneler ve Bağımlılıklar
Aspose.Slides for Java kütüphanesine ihtiyacınız olacak. JDK16 desteğiyle 25.4 sürümünü kullandığınızdan emin olun.

### Ortam Kurulum Gereksinimleri
Geliştirme ortamınız Java'yı (tercihen JDK16) desteklemeli ve Maven veya Gradle kullanarak projeler oluşturabilmelidir.

### Bilgi Önkoşulları
Temel Java programlamaya, Maven/Gradle aracılığıyla kütüphanelerle çalışmaya ve PowerPoint sunumlarını anlamaya aşina olmak faydalı olacaktır.

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
- **Satın Alma**: Sürekli kullanım için tam lisans satın alın.

**Temel Başlatma ve Kurulum**  
Aspose.Slides'ı aşağıdaki gibi başlatın:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Kümelenmiş Sütun Grafiği Nasıl Eklenir
Grafik eklemek ilk işlevsel adımdır. Bu bölüm, API kullanarak **grafiğin nasıl ekleneceğini** açıklar.

### Özellik 1: Kümelenmiş Sütun Grafiği Oluşturma
Aspose.Slides for Java kullanarak bir kümelenmiş sütun grafiği oluşturalım. Bu özellik, slaytlarınıza görsel olarak çekici grafikler eklemenizi kolaylaştırır.

#### Genel Bakış
Bu bölümde yeni bir sunum başlatacağız ve ilk slayta bir kümelenmiş sütun grafiği ekleyeceğiz.

**Adım 1: Sunumu Başlatma**  
PowerPoint dosyalarıyla çalışmaya başlamak için bir `Presentation` nesnesi oluşturun:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Adım 2: Kümelenmiş Sütun Grafiği Ekleme**  
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

## Grafiğin Renklerini Nasıl Ayarlarsınız
Seri dolgu renklerini otomatik olarak uygulayarak görsel çekiciliği artırın (**renklerin nasıl ayarlanacağını**).

### Özellik 2: Otomatik Seri Dolgu Rengini Ayarla
Her grafiğin seri rengini otomatik olarak ayarlayarak tutarlı bir görünüm elde edin.

#### Genel Bakış
Her grafiğin seri rengini otomatik olarak ayarlayarak tutarlı bir görünüm elde edin.

**Adım 1: Grafik Erişimi ve Seri Döngüsü**  
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
İşiniz bittiğinde sunum nesnesini serbest bırakın:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Sunumu PPTX Olarak Nasıl Kaydedersiniz
Grafik harika göründüğünde dosyayı kalıcı hale getirmek isteyeceksiniz (**sunumun nasıl kaydedileceği**).

### Özellik 3: Sunumu Diske Kaydet
Son olarak, Aspose.Slides kullanarak çalışmanızı kolayca kaydedin.

#### Genel Bakış
Düzenlenmiş sunumlarınızı istediğiniz formatta ve konumda kaydedin.

**Adım 1: Çıktı Yolunu Tanımlama**  
Dosyayı nereye kaydetmek istediğinizi belirtin:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Adım 2: Sunumu Kaydet**  
`Presentation` nesnesinin `save` metodunu kullanın:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Pratik Uygulamalar
- **Finansal Raporlar**: Çeyrek gelirleri net bir şekilde görselleştirin.  
- **Pazarlama Veri Analizi**: Kampanya sonuçlarını etkileyici görsellerle sergileyin.  
- **Proje Yönetimi**: Takım toplantılarında kilometre taşlarını ve ilerlemeyi görsel olarak izleyin.

## Performans Düşünceleri
Aspose.Slides ile çalışırken aşağıdaki en iyi uygulamaları göz önünde bulundurun:

- `Presentation` nesnelerini zamanında serbest bırakarak belleği etkili yönetin.  
- Sunumları kaydederken dosya boyutlarını optimize ederek disk alanını koruyun.  
- Performansı artırmak için grafik serileri için verimli veri yapıları kullanın.

## Sonuç
Tebrikler! Aspose.Slides for Java kullanarak **kümelenmiş sütun grafiği oluşturmayı**, renkleri otomatik **ayarlamayı** ve **sunumu PPTX olarak kaydetmeyi** öğrendiniz. Bu beceri, sunumlarınızı geliştirmenin yanı sıra görsel veri temsili sürecini de kolaylaştırır.

**Sonraki Adımlar:**  
Proje yeteneklerinizi genişletmek için grafik öğelerini özelleştirme, veri etiketleri ekleme veya harici veri kaynaklarıyla entegrasyon gibi ek özellikleri keşfedin.

## SSS Bölümü
1. **Belirli bir JDK sürümü için Aspose.Slides'ı nasıl kurarım?**  
   - Kurulum bölümünde gösterildiği gibi `classifier` belirterek Maven/Gradle bağımlılıklarını kullanın.  
2. **Sunumum doğru kaydedilmezse ne olur?**  
   - Çıktı dizininizde yazma izniniz olduğundan ve dosya yolunun doğru olduğundan emin olun.  
3. **Aspose.Slides for Java ile başka grafik türleri oluşturabilir miyim?**  
   - Kesinlikle! `ChartType` seçeneklerini, Pasta, Çubuk veya Çizgi grafikler gibi inceleyin.  
4. **Grafiğimde büyük veri setlerini nasıl yönetirim?**  
   - Veri yapılarını optimize edin ve görselleştirmeden önce verilerinizi ön işleme almayı düşünün.  
5. **Aspose.Slides for Java kullanımına dair daha fazla örnek nerede bulunur?**  
   - Kapsamlı rehberler ve kod örnekleri için [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) adresini ziyaret edin.

## Kaynaklar
- **Dokümantasyon**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **İndirme**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Satın Alma**: [Buy a License](https://purchase.aspose.com/buy)  
- **Ücretsiz Deneme**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Geçici Lisans**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Destek**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-03-18  
**Test Edilen:** Aspose.Slides 25.4 (JDK16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}