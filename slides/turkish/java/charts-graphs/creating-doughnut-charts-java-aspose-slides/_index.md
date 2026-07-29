---
date: '2026-07-27'
description: Aspose.Slides kullanarak Java'da doughnut chart oluşturmayı öğrenin –
  kütüphaneyi kurmak, özelleştirilebilir bir doughnut chart eklemek, delik boyutunu
  ayarlamak ve sunumu kaydetmek için hızlı bir rehber.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Aspose.Slides kullanarak Java'da doughnut chart oluşturmayı öğrenin
  – kütüphaneyi kurmak, özelleştirilebilir bir doughnut chart eklemek, delik boyutunu
  ayarlamak ve sunumu kaydetmek için hızlı bir rehber.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Java ile Doughnut Chart Oluşturma – Adım Adım Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Java ile Doughnut Chart Oluşturma – Adım Adım Aspose.Slides
url: /tr/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides for Presentations Kullanarak Halka Grafikler Nasıl Oluşturulur

## Giriş
Görsel olarak çekici sunumlar oluşturmak, bilgiyi etkili bir şekilde iletmek için esastır. **Create doughnut chart java** modern bir görünümle orantılı verileri göstermeniz gerektiğinde yaygın bir gereksinimdir. Bu öğreticide Aspose.Slides for Java'yi nasıl kuracağınızı, bir halka grafik oluşturacağınızı, delik boyutunu ve renklerini nasıl özelleştireceğinizi ve sonunda sunum dosyasını nasıl kaydedeceğinizi öğreneceksiniz. Sonunda, PowerPoint sunumlarını otomatik olarak üreten herhangi bir Java projesine ekleyebileceğiniz yeniden kullanılabilir bir desen elde edeceksiniz.

**Öğrenecekleriniz:**
- Aspose.Slides for Java kurulumu
- Sunumlarda halka grafiklerin oluşturulması ve yapılandırılması
- Delik boyutu gibi grafik estetiğinin ayarlanması
- Yeni grafiğinizle sunumu kaydetme

Ortamımızı kurarak başlayalım!

## Hızlı Yanıtlar
- **Hangi kütüphane java için donut grafik oluşturur?** Aspose.Slides for Java.
- **Temel bir doughnut grafik için kaç satır kod gerekir?** Sunum oluşturulduktan sonra yaklaşık 8–10 satır.
- **Delik boyutunu değiştirebilir miyim?** Evet, `setHoleSize(double)` metodu %0 ile %100 arasında değer kabul eder.
- **Hangi çıktı formatları destekleniyor?** PPTX, PDF, XPS, PNG, JPEG ve birkaç diğer format (toplam 50+).
- **Üretim için lisansa ihtiyacım var mı?** Sınırsız kullanım için ticari bir lisans gerekir; değerlendirme için ücretsiz deneme sürümü çalışır.

## Aspose.Slides for Java Nedir?
**Aspose.Slides for Java**, geliştiricilerin Microsoft Office olmadan PowerPoint dosyalarını oluşturmasını, değiştirmesini, dönüştürmesini ve render etmesini sağlayan tam yönetilen bir API'dir. 50'den fazla dosya formatını destekler ve bellek kullanımını düşük tutarak binlerce slayt içeren sunumları işleyebilir.

## Sunumlarda donut grafikleri neden kullanmalı?
Halka grafikler, parçanın bütüne oranını gösterirken merkezde etiketler veya görseller için boşluk bırakır. Aspose.Slides tipik bir 2.5 GHz sunucuda **dakikada 500 slayt** kadar halka grafik render edebilir ve **yüzlerce sayfalık sunumları** tüm dosyayı belleğe yüklemeden işleyerek büyük ölçekli raporlama çözümleri için idealdir.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

### Gerekli Kütüphaneler ve Sürümler
Aspose.Slides for Java ile çalışmak için projeye Maven veya Gradle aracılığıyla ekleyin ya da doğrudan indirin.

#### Ortam Kurulum Gereksinimleri
- Çalışan bir Java Development Kit (JDK), tercihen sürüm 8 veya üzeri.
- IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE).

### Bilgi Önkoşulları
Java ve temel programlama kavramlarına aşina olmak faydalıdır. Maven veya Gradle hakkında temel bilgi, kurulum sürecini hızlandırır.

## Aspose.Slides for Java Kurulumu
Aspose.Slides'i projenize birkaç farklı yolla dahil edebilirsiniz:

**Maven:**  
`pom.xml` dosyanıza bu bağımlılığı ekleyin:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
`build.gradle` dosyanıza bunu ekleyin:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme:**  
Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

### Lisans Edinme
- **Ücretsiz Deneme:** Aspose.Slides özelliklerini keşfetmek için deneme sürümünü indirin.  
- **Geçici Lisans:** Sınırlama olmadan genişletilmiş işlevsellik için geçici bir lisans edinin.  
- **Satın Alma:** Sürekli kullanım için bir lisans satın almanız gerekir.

Kütüphaneyi kurup ortamınızı hazırladıktan sonra, donut grafiğimizi uygulamaya geçelim.

## Java'da donut grafik nasıl oluşturulur?
Yeni bir `Presentation` nesnesi yükleyin, bir slayta halka grafik ekleyin, delik boyutunu ayarlayın ve dosyayı kaydedin – tüm bunlar birkaç basit API çağrısı ile yapılır. Bu yaklaşım, grafik verileri, görünümü ve dışa aktarım formatı üzerinde tam kontrol sağlar ve sunucuda Microsoft PowerPoint yüklü olmasına gerek kalmaz.

### Presentation Nesnesini Başlatma
`Presentation` sınıfı, Aspose.Slides'in bellek içindeki bir PowerPoint dosyasını temsil eden üst‑seviye nesnesidir.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Bu adım, slayt, şekil ve grafik ekleyebileceğiniz boş bir sunum oluşturur.

### Slayta Donut Grafik Ekleme
`ISlide` tek bir slayt için arayüzdür; ilk slaytı alabilir veya yeni bir tane ekleyebilirsiniz.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
`addChart` metodu bir donut grafik oluşturur; parametreler grafiğin slayt üzerindeki konumunu (X, Y) ve boyutunu (genişlik, yükseklik) tanımlar.

### Donut Delik Boyutunu Yapılandırma
`Chart` sınıfı, grafik yarıçapının yüzde olarak iç yarıçapını kontrol eden `setHoleSize(double)` metodunu sunar.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Delik boyutunu %90 olarak ayarlamak, grafiğin neredeyse tam bir daire gibi görünmesini sağlar; bu, dış segmentleri vurgulamak istediğinizde faydalıdır.

### Sunumu Kaydetme
`presentation.save(String, SaveFormat)` dosyayı seçilen formatta diske yazar.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Örnek, sonucu `DoughnutHoleSize_out.pptx` olarak kaydeder, ancak PDF, PNG veya 50+ desteklenen formatlardan birini de seçebilirsiniz.

### Kaynakları Temizleme
`presentation.dispose()` yerel kaynakları serbest bırakır ve özellikle uzun süre çalışan sunucu uygulamalarında bellek sızıntılarını önler.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Pratik Uygulamalar
Halka grafikler çok yönlüdür. İşte öne çıkan senaryolar:
1. **Bütçe Dağılımı:** Bir bütçenin departmanlar arasında nasıl dağıldığını gösterin.  
2. **Anket Sonuçları:** Çoktan seçmeli soruların yanıtlarını görselleştirin.  
3. **Web Sitesi Trafik Kaynakları:** Trafiğin farklı kanallardan (organik, ücretli, yönlendirme vb.) gelen yüzdesini gösterin.

## Performans Düşünceleri
Aspose.Slides ile çalışırken optimal performans için şu ipuçlarını göz önünde bulundurun:
- `Presentation` nesnelerini işiniz bittiğinde serbest bırakın, böylece yerel bellek boşaltılır.  
- Büyük veri setleri için `FileInputStream`, `ByteArrayOutputStream` gibi akışları kullanın, böylece tüm dosyayı RAM'e yüklemekten kaçınırsınız.  
- Bir döngüde birçok slayt üretirken grafik nesnelerini yeniden kullanın, nesne oluşturma yükünü azaltır.

## Yaygın Sorunlar ve Çözümler
- **Kaydetme sırasında hata:** Çıktı dizininin var olduğunu ve uygulamanın yazma iznine sahip olduğunu doğrulayın.  
- **Grafik verisi eksik:** `setHoleSize` çağırmadan önce grafiğin `ChartData` koleksiyonunu doldurduğunuzdan emin olun.  
- **Bellek dalgalanmaları:** Binlerce slayt içeren sunumlar için `Presentation.setSlideSize`'ı daha küçük bir boyuta ayarlayın ve ara slaytları zamanında serbest bırakın.

## Sıkça Sorulan Sorular

**S: Donut grafik segmentlerinin renklerini ayarlayabilir miyim?**  
C: Evet. `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` metodunu kullanın ve ardından istediğiniz RGB rengi belirtin.

**S: Grafiğime veri etiketleri nasıl eklerim?**  
C: Her segmentin içinde değeri göstermek için `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` metodunu çağırın.

**S: PPTX dışındaki formatlarda grafikleri kaydetmek mümkün mü?**  
C: Kesinlikle. Aspose.Slides PDF, XPS, PNG, JPEG, TIFF ve birçok diğer formatı destekler—toplamda 50'den fazla.

**S: Büyük bir sunumu yüklerken bir istisna ile karşılaşırsam ne yapmalıyım?**  
C: Akış kabul eden `Presentation` yapıcıyı kullanın ve `loadOptions.setLoadFormat(LoadFormat.Pptx)`'i etkinleştirerek dosyayı akış olarak okuyun ve bellek tüketimini azaltın.

**S: Can I automate chart updates with live data sources?**  
C: Evet. Verileri bir veritabanı veya REST API'den alıp `ChartData` koleksiyonunu güncelleyebilir ve sunumu kaydetmeden önce `chart.refresh()` metodunu çağırabilirsiniz.

## Kaynaklar
- **Dokümantasyon:** Ayrıntılı API referanslarını [Aspose.Slides for Java](https://reference.aspose.com/slides/java/) adresinde keşfedin.  
- **İndirme:** En son kütüphane sürümünü [Aspose.Slides releases](https://releases.aspose.com/slides/java/) adresinden alın.  
- **Satın Alma:** Tam erişim için lisansı [Aspose Purchase](https://purchase.aspose.com/buy) adresinden satın alın.  
- **Ücretsiz Deneme:** İndirme sayfalarında bulunan ücretsiz deneme sürümüyle Aspose.Slides'ı test edin.  
- **Geçici Lisans:** Sınırlama olmadan genişletilmiş test için geçici bir lisans edinin.  
- **Destek:** Sorularınız mı var? Yardım için [Aspose Forum](https://forum.aspose.com/c/slides/11) adresini ziyaret edin.

---

**Son Güncelleme:** 2026-07-27  
**Test Edilen Versiyon:** Aspose.Slides for Java 24.12  
**Yazar:** Aspose

## İlgili Eğitimler

- [Java için Aspose.Slides Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java'da Aspose.Slides ile Grafik Oluşturma: Kapsamlı Kılavuz](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}