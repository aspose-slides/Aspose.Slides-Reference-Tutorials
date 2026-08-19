---
date: '2026-07-17'
description: Aspose Slides for Java kullanarak PowerPoint'te sunburst charts eklemeyi
  öğrenin. Adım adım kılavuz, kurulum, grafik oluşturma, özelleştirme ve gerçek dünya
  kullanım örneklerini kapsar.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Aspose Slides for Java kullanarak PowerPoint'te sunburst charts ekleyin.
  Bu öğreticiyi izleyerek kütüphaneyi kurun, bir grafik oluşturun, veri noktalarını
  özelleştirin ve gerçek projelere uygulayın.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: PowerPoint'te Aspose (Java) ile Sunburst Charts Nasıl Eklenir
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: PowerPoint'te Aspose (Java) ile Sunburst Charts Nasıl Eklenir
url: /tr/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose (Java) ile PowerPoint'e Güneş Patlaması Grafikleri Nasıl Eklenir

## Giriş

PowerPoint sunumuna bir güneş patlaması grafiği eklemek, düz bir veri tablosunu anında etkileyici bir görsel hiyerarşiye dönüştürebilir. Bu öğreticide, Aspose.Slides for Java kullanarak PowerPoint'te **güneş patlaması grafikleri eklemeyi** öğreneceksiniz, ortam kurulumundan renk ve etiket ayarlarına kadar. İster bir satış kontrol paneli, bir proje‑görev dağılımı ya da eğitim amaçlı bir slayt seti oluşturuyor olun, aşağıdaki adımlar size üretim‑hazır bir çözüm sunacak.

**Öğrenecekleriniz**
- Maven veya Gradle projesinde Aspose.Slides'ı nasıl yapılandırılır
- Yeni bir sunum nasıl oluşturulur ve bir güneş patlaması grafiği nasıl eklenir
- Veri noktaları, etiketler ve dolgu renkleri nasıl özelleştirilir
- Güneş patlaması grafiklerinin öne çıktığı gerçek dünya senaryoları

Haydi başlayalım ve ham hiyerarşi verilerini cilalı bir PowerPoint görseline dönüştürmenin ne kadar kolay olduğunu görelim.

## Hızlı Yanıtlar
- **Ana kütüphane?** Aspose.Slides for Java  
- **Desteklenen grafik türü?** Sunburst (radial hierarchical)  
- **Minimum Java sürümü?** JDK 16  
- **Tipik uygulama süresi?** Temel bir grafik için 10‑15 dakika  
- **Üretim için lisans gerekli mi?** Evet, geçerli bir Aspose lisansı  

## Güneş Patlaması Grafiği Nedir?
Güneş patlaması grafiği, hiyerarşik verileri merkezi bir noktadan dışa doğru halka hâlinde iç içe yerleştirerek görselleştiren bir radyal diyagramdır. Organizasyon yapıları, ürün kategorileri veya dosya sistemi ağaçları gibi çok seviyeli ilişkileri göstermek için mükemmeldir. Her konsantrik halka hiyerarşinin bir seviyesini temsil eder ve her segmentin büyüklüğü nicel değerini yansıtarak izleyicilerin hem yapıyı hem de büyüklüğü hızlıca kavramasını sağlar.

## Aspose.Slides for Java Neden Kullanılmalı?
Aspose.Slides, **50+ grafik türünü** destekler ve **10.000 slayta kadar** sunumları, dosyanın tamamını belleğe yüklemeden işleyebilir; bu da kurumsal ölçekli raporlamada yüksek performans sağlar. Çapraz platform çalışır, kapsamlı bir API kapsamı sunar ve değerlendirme sınırlamalarını kaldıran sağlam lisans seçenekleri içerir; bu da onu üretim ortamları için ideal kılar.

## Önkoşullar
- **Java Development Kit (JDK)** 16 veya daha yeni  
- **IDE** – IntelliJ IDEA, Eclipse veya herhangi bir Java‑uyumlu editör  
- Java sözdizimi ve Maven/Gradle yapı araçları hakkında temel bilgi  

## Aspose.Slides for Java Kurulumu

### Maven Bağımlılığı
pom.xml dosyanıza Aspose.Slides Maven artefaktını ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Bağımlılığı
Gradle tercih ediyorsanız, `build.gradle` dosyanıza aşağıdaki satırı ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
En son JAR dosyasını resmi sürüm sayfasından doğrudan indirebilirsiniz: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lisans Alımı
Değerlendirme sınırlamaları olmadan çalıştırmak için bir lisans edinin:
- **Ücretsiz deneme** – hızlı değerlendirme için geçici lisans.  
- **Geçici lisans** – [Aspose web sitesinden](https://purchase.aspose.com/temporary-license) talep edin.  
- **Tam satın alma** – sınırsız üretim kullanımı için bir abonelik satın alın.

### Temel Başlatma
`Presentation` sınıfı, PowerPoint dosyaları oluşturmak veya açmak için giriş noktasıdır.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Uygulama Kılavuzu

### Aspose.Slides for Java kullanarak bir PowerPoint sunumuna nasıl güneş patlaması grafiği eklenir?
Yeni bir `Presentation` yükleyin, bir slayt ekleyin, `ChartType.Sunburst` türünde bir `IChart` ekleyin ve `save` metodunu çağırın. Bu özlü üç adımlı desen, daha fazla özelleştirme için hazır tam işlevsel bir güneş patlaması grafiği oluşturur.

#### Adım 1: Sunumu Başlatın
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Adım 2: Güneş Patlaması Grafiği Ekle
`IChart` arayüzü, herhangi bir slayta yerleştirilebilecek bir grafik nesnesi tanımlar. Burada (100, 100) koordinatlarında ve 450 × 400 point boyutunda bir güneş patlaması grafiği ekliyoruz.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Adım 3: Sunumu Kaydedin
Değişikliklerinizi her zaman `save` metodunu çağırarak kalıcı hale getirin. PPTX, PDF veya 50+ desteklenen çıktı formatından herhangi birini seçebilirsiniz.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Grafikte Veri Noktalarını Değiştir

#### Genel Bakış
Grafiğin veri noktası koleksiyonu aracılığıyla güneş patlamasının her dilimini—etiketleri, renkleri ve görünürlüğü—özelleştirebilirsiniz.

#### Adım 1: Veri Noktaları Koleksiyonuna Erişin
Grafiğin ilk serisi, her dilimi temsil eden `IChartDataPoint` nesnelerinin bir koleksiyonunu tutar.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Adım 2: Belirli Bir Veri Noktası İçin Değeri Göster
İstenen veri noktasında `IsValueShown` özelliğini `true` olarak ayarlayarak sayısal değerini doğrudan dilimde gösterin.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Adım 3: Etiket Biçimlerini Değiştir
Okunabilirliği artırmak için etiket görünürlüğünü, yazı tipi rengini ve arka planı ayarlayın.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Adım 4: Veri Noktaları İçin Dolgu Rengini Ayarla
Bireysel dilimlerin dolgu rengini, marka paletinize uyacak şekilde veya ana segmentleri vurgulamak için özelleştirin.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Adım 5: Değiştirilmiş Sunumu Kaydet
Sunumu tekrar kaydederek özelleştirilmiş grafiği kalıcı hale getirin.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Pratik Uygulamalar
1. **İş Analitiği** – Satışları bölge → ürün hattı → SKU olarak tek bir radyal görünümde görselleştirin.  
2. **Proje Yönetimi** – İş kırılımı yapılarını, aşamalardan görevlere ve alt görevlere derinlemesine gösterin.  
3. **Eğitim** – Bölümler → dersler → modüller gibi müfredat hiyerarşilerini haritalayın.  

## Performans Düşünceleri
- **Bellek Verimliliği:** Aspose.Slides verileri akış olarak işler, bu yüzden birden fazla grafik içeren 500 sayfalık bir sunum bile 200 MB RAM'in altında kalır.  
- **Garbage Collection:** Gereksiz olduğunda slayt nesnelerini (`slide.dispose()`) serbest bırakarak bellek sızıntılarını önleyin.  

## Sıkça Sorulan Sorular

**Q: Güneş patlaması grafiği nedir?**  
**A:** Güneş patlaması grafiği, hiyerarşik verileri konsantrik halkalar içinde görselleştirir; her halka hiyerarşinin bir seviyesini temsil eder.

**Q: Aspose.Slides for Java'ı Maven ile nasıl kurarım?**  
**A:** “Maven Bağımlılığı” bölümünde gösterilen Maven bağımlılığını `pom.xml` dosyanıza ekleyin ve `mvn clean install` komutunu çalıştırın.

**Q: Aspose.Slides ile diğer grafik türlerini özelleştirebilir miyim?**  
**A:** Evet, kütüphane 50'den fazla grafik türünü destekler; sütun, çizgi, pasta ve radar grafikleri dahil.

**Q: Sunumum kaydedilmiyor—ne kontrol etmeliyim?**  
**A:** Dosya yolunun doğru olduğundan, dizinin var olduğundan ve yazma izninizin bulunduğundan emin olun. Ayrıca `Presentation.save()` metodunun çağrıldığını doğrulayın.

**Q: Daha fazla yardım veya örnek nereden bulabilirim?**  
**A:** [Aspose forumunu](https://forum.aspose.com/c/slides/11) ziyaret edin veya resmi [Aspose.Slides referansını](https://reference.aspose.com/slides/java/) inceleyin.

## Kaynaklar
- **Dokümantasyon:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Referans (küçük harf):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Topluluk Forumu:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **İndirilenler:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Son Güncelleme:** 2026-07-17  
**Test Edilen Versiyon:** Aspose.Slides for Java 24.12  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Nasıl Eklenir: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java ile PowerPoint'te Grafikleri Animasyonlu Hale Getirme – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Java'da Aspose.Slides ile Grafik Oluşturma – Grafik Ekleme ve Doğrulama](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}