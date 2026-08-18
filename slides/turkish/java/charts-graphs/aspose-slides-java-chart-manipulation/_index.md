---
date: '2026-06-08'
description: Aspose.Slides ile Java’da PowerPoint grafiği oluşturmayı, Maven bağımlılığını
  ayarlamayı, bir clustered column chart eklemeyi ve PPTX olarak kaydetmeyi öğrenin.
keywords:
- java create powerpoint chart
- maven dependency aspose slides
- chart manipulation in presentations
- java presentation library
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to java create powerpoint chart with Aspose.Slides, set up
    the Maven dependency, add a clustered column chart, and save as PPTX.
  headline: Java create powerpoint chart using Aspose.Slides
  type: TechArticle
- questions:
  - answer: Use the `ChartType` enum (e.g., `ChartType.Pie`, `ChartType.Line`) when
      calling `addChart`.
    question: How do I add other chart types?
  - answer: Yes, modify the series’ fill format or the chart’s palette via the `IChart`
      API.
    question: Can I customize chart colors?
  - answer: Verify that the output directory path is correct, exists, and is writable.
      Also ensure no other process holds a lock on the file.
    question: My presentation won’t save—what’s wrong?
  - answer: Process slides in batches, dispose of each `Presentation` after use, and
      consider increasing the JVM heap size if needed.
    question: How can I handle very large presentations efficiently?
  - answer: A free trial is available for evaluation, but a purchased license is required
      for commercial deployment.
    question: Is Aspose.Slides free for commercial projects?
  type: FAQPage
title: Java ile Aspose.Slides kullanarak PowerPoint grafiği oluşturma
url: /tr/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java ile Aspose.Slides kullanarak PowerPoint grafik oluşturma

## Giriş
Bu rehberde Aspose.Slides for Java ile **java create powerpoint chart** sorunsuz bir şekilde oluşturacaksınız. Maven veya Gradle paketini kurmaktan, bir `Presentation` başlatmaya, bir kümeleme sütun grafiği eklemeye, çizim alanını ince ayarlamaya ve sonunda sonucu bir PPTX dosyası olarak kaydetmeye kadar adımları göstereceğiz. Sonunda, ister bir iş raporu ister otomatik slayt oluşturucu geliştirin, herhangi bir Java projesinde çalışacak hazır bir kod parçacığına sahip olacaksınız.

**Öğrenecekleriniz**
- Aspose.Slides için Maven bağımlılığını nasıl ekleyeceğinizi  
- **java create powerpoint chart** nasıl yapılır ve bir kümeleme sütun grafiği nasıl eklenir  
- Çizim alanını (konum, boyut, düzen hedefi) nasıl ayarlayacağınızı  
- **save presentation as pptx** nasıl yapılır ve kaynakların düzgün temizlenmesi  

Ham verileri göz alıcı slaytlara dönüştürmeye hazır mısınız? Hadi başlayalım!

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (Maven veya Gradle üzerinden temin edilebilir).  
- **Hangi grafik türü gösteriliyor?** Kümeleme sütun grafiği.  
- **Dosyayı nasıl kaydederim?** `presentation.save("output.pptx", SaveFormat.Pptx)` çağrısını yapın.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme çalışır; üretim için tam lisans gereklidir.  
- **Çizim alanını değiştirebilir miyim?** Evet – X, Y, genişlik, yükseklik ayarlayın ve bir düzen hedef tipi seçin.

## java create powerpoint chart nedir?
`java create powerpoint chart` programmatically bir grafik nesnesi oluşturmayı, verilerle doldurmayı ve bir Java kütüphanesi kullanarak bir PowerPoint slaytına yerleştirmeyi ifade eder. Aspose.Slides, Open XML formatını soyutlayarak dosya iç detayları yerine görsel tasarıma odaklanmanızı sağlar.

## Neden Aspose.Slides ile kümeleme sütun grafiği ekleyelim?
Kümeleme sütun grafiği, birden fazla veri serisini yan yana karşılaştırmak için mükemmeldir. İş raporları, kontrol panelleri ve sunumlarda yaygın olarak kullanılır. Aspose.Slides, PowerPoint'i manuel olarak açmadan renkler, işaretçiler, eksenler ve düzen üzerinde tam kontrol sağlar. Kategoriler arasındaki trendleri vurgulamanıza olanak tanır, böylece paydaşlar için veri içgörüleri daha net olur. Aspose.Slides ile serilerin biçimlendirmesini, eksen ölçeklendirmesini ve veri etiketlerini programmatically ayarlayabilir, grafiğin kurumsal marka ve görsel standartlarınıza uygun olmasını sağlayabilirsiniz.

## Önkoşullar
- **Aspose.Slides for Java** (sürüm 25.4 veya daha yeni).  
- **JDK 16** veya üzeri.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Temel Java bilgisi.

## Aspose.Slides for Java Kurulumu
### Maven
Bağımlılığı `pom.xml` dosyanıza ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```

### Gradle
`build.gradle` dosyanıza kütüphaneyi ekleyin:

```gradle
implementation 'com.aspose:aspose-slides:25.4'
```

### Doğrudan İndirme
Alternatif olarak, en son sürümü [Aspose'un resmi sitesinden](https://releases.aspose.com/slides/java/) indirebilirsiniz.

#### Lisans Alımı
Test için ücretsiz deneme veya geçici lisans kullanın. Üretim dağıtımları için tam lisans satın alın.

## Temel Başlatma ve Kurulum
`Presentation` sınıfı PowerPoint dosyaları oluşturmak ve değiştirmek için giriş noktasıdır. Yeni bir Java sınıfı oluşturun ve temel sınıfı içe aktarın:

```java
import com.aspose.slides.Presentation;
```

## Uygulama Kılavuzu
Her adımı net açıklamalarla göstereceğiz.

### Sunum Başlatma ve Slayt Manipülasyonu
#### Tanım Bağlantısı
`Presentation`, Aspose.Slides'ın bellek içinde tüm bir PowerPoint dosyasını temsil eden üst‑seviye nesnesidir.  

#### Genel Bakış
İlk olarak, yeni bir sunum oluşturun ve grafiğin yer alacağı ilk slaytı alın.

**1. Sunumu Oluştur ve Başlat**

```java
Presentation presentation = new Presentation();
```

**2. İlk Slayta Eriş**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Kümeleme Sütun Grafiği Ekle**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **İpucu:** Sunum kullanımını her zaman bir `try‑finally` bloğuna sarın ve `finally` içinde `presentation.dispose()` çağırarak yerel kaynakları serbest bırakın.

### Çizim Alanı Yapılandırması
#### Genel Bakış
Grafiğin çizim alanını ince ayarlayarak verinin slayt içinde nerede görüneceğini kontrol edin.

**1. Konum ve Boyutu Ayarla**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. Düzen Hedef Tipini Tanımla**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### Sunumu Kaydetme
#### Genel Bakış
Grafiği özelleştirdikten sonra, sunumu bir PPTX dosyası olarak kaydedin.

**1. Dosyaya Kaydet**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Uyarı:** Çıktı dizininin mevcut olduğundan ve uygulamanın yazma iznine sahip olduğundan emin olun; aksi takdirde kaydetme işlemi başarısız olur.

## Yaygın Kullanım Senaryoları
- **İş Raporları:** Satış trendlerini ve finansal KPI'ları gömün.  
- **Eğitim Slaytları:** Deney sonuçlarını veya istatistiksel verileri görselleştirin.  
- **Proje Teklifleri:** Kilometre taşlarını ve kaynak tahsislerini vurgulayın.  
- **Pazarlama Sunumları:** Kampanya performansını canlı grafiklerle gösterin.  
- **Etkinlik Planlaması:** Katılımcı demografilerini veya program dağılımını gösterin.

## Performans Düşünceleri
- `Presentation` nesnelerini hafıza sızıntılarını önlemek için hızlıca serbest bırakın.  
- Büyük veri setleri için, tüm veriyi bir anda yüklemek yerine grafik serilerini artımlı olarak doldurun.  
- Grafik oluşturma sırasında yığın kullanımını izlemek için Java’nın yerleşik profil oluşturma araçlarını kullanın.

## Sıkça Sorulan Sorular

**S: Başka grafik türleri nasıl eklenir?**  
C: `addChart` çağrılırken `ChartType` enum'ını (ör. `ChartType.Pie`, `ChartType.Line`) kullanın.

**S: Grafik renklerini özelleştirebilir miyim?**  
C: Evet, serinin doldurma formatını veya grafiğin paletini `IChart` API'si üzerinden değiştirebilirsiniz.

**S: Sunum kaydedilemiyor—ne sorun?**  
C: Çıktı dizin yolunun doğru, mevcut ve yazılabilir olduğunu doğrulayın. Ayrıca başka bir sürecin dosyayı kilitlemediğinden emin olun.

**S: Çok büyük sunumları verimli bir şekilde nasıl yönetebilirim?**  
C: Slaytları partiler halinde işleyin, her `Presentation` kullanım sonrası serbest bırakın ve gerekirse JVM yığın boyutunu artırmayı düşünün.

**S: Aspose.Slides ticari projeler için ücretsiz mi?**  
C: Değerlendirme için ücretsiz bir deneme mevcuttur, ancak ticari dağıtım için satın alınmış bir lisans gereklidir.

## Kaynaklar
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

Bugün Aspose.Slides for Java ile görsel olarak çarpıcı sunumlar oluşturmaya başlayın!

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

## İlgili Eğitimler

- [Java ile Aspose.Slides kullanarak kümeleme sütun grafiği nasıl oluşturulur](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Aspose.Slides for Java kullanarak Sunumlara Grafik Ekleme ve Yapılandırma](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Animasyonlu PowerPoint Java – PowerPoint Grafiklerini Aspose.Slides ile Canlandırma](/slides/java/animations-transitions/animate-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}