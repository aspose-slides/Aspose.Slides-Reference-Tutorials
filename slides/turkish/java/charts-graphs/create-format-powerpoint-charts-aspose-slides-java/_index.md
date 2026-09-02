---
date: '2026-09-02'
description: Aspose.Slides for Java kullanarak bir PowerPoint slaytına kümeleme sütun
  grafiği eklemeyi öğrenin; grafik oluşturma, biçimlendirme ve PPTX olarak kaydetme
  konularını kapsar.
keywords:
- add clustered column chart
- save powerpoint as pptx
- powerpoint chart formatting
- add chart to slide
- java create chart slide
lastmod: '2026-09-02'
og_description: Aspose.Slides for Java kullanarak bir PowerPoint slaytına kümeleme
  sütun grafiği eklemeyi öğrenin; grafik oluşturma, biçimlendirme ve PPTX olarak kaydetme
  konularını kapsar.
og_image_alt: Guide showing how to add a clustered column chart to a PowerPoint slide
  with Aspose.Slides for Java
og_title: Aspose.Slides Java kullanarak PPT'ye kümeleme sütun grafiği ekleyin
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to add clustered column chart to a PowerPoint slide using
    Aspose.Slides for Java, covering chart creation, formatting, and saving as PPTX.
  headline: Add clustered column chart to PPT using Aspose.Slides Java
  type: TechArticle
- questions:
  - answer: Replace `ChartType.ClusteredColumn` with any other enum value such as
      `ChartType.Pie`, `ChartType.Line`, or `ChartType.Bar`.
    question: How do I add different types of charts using Aspose.Slides?
  - answer: Double‑check that you’re using JDK 16 or newer and that the Maven/Gradle
      dependency version matches the library you downloaded.
    question: What should I do if I encounter compilation errors?
  - answer: Yes. Access the chart’s `getChartData()` collection, create series and
      categories, and fill them with values retrieved at runtime.
    question: Can I populate the chart with data from a database?
  - answer: Split the work into multiple `Presentation` instances, reuse chart templates,
      and always dispose of objects promptly.
    question: How can I improve performance for very large presentations?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java PowerPoint automation
- chart formatting
- PPTX
title: Aspose.Slides Java kullanarak PPT'ye kümeleme sütun grafiği ekleyin
url: /tr/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides Java kullanarak PPT'ye kümelenmiş sütun grafik ekleme

## Giriş
Bu rehberde Aspose.Slides for Java ile programlı olarak bir PowerPoint sunumuna **kümelenmiş sütun grafik** ekleyeceksiniz. İş raporları, eğitim sunumları veya pazarlama sunumları oluşturuyor olun, grafik oluşturmayı otomatikleştirmek zaman tasarrufu sağlar ve tutarlılığı garanti eder. Kütüphaneyi kurmayı, bir slayt oluşturmayı, grafiği eklemeyi, çizgi stilleri ve yuvarlatılmış köşeler uygulamayı ve sonunda dosyayı PPTX olarak kaydetmeyi adım adım göstereceğiz. Sonunda **grafiği slayta ekleme** ve hatta **Java tabanlı PowerPoint slaytı oluşturma** iş akışına aşina olacaksınız.

### Hızlı Yanıtlar
- **Başlamak için birincil sınıf nedir?** `Presentation`
- **Hangi grafik türü kullanılıyor?** `ChartType.ClusteredColumn`
- **Yuvarlatılmış köşeler nasıl etkinleştirilir?** `chart.setRoundedCorners(true);`
- **Kaydetmek için önerilen format nedir?** `SaveFormat.Pptx`
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme test için çalışır; üretim için satın alınan bir lisans gereklidir.

## Kümelenmiş sütun grafik nedir?
Kümelenmiş sütun grafik, her kategori için birden fazla veri serisini yan yana gruplar, bu da farklı gruplar arasındaki değerleri karşılaştırmak için idealdir. Aspose.Slides, bu grafik türünü PowerPoint açmadan tamamen kod içinde oluşturmanıza olanak tanır ve renkleri, işaretçileri ve eksen seçeneklerini markanıza uygun şekilde özelleştirebilirsiniz.

## Kümelenmiş sütun grafik eklemek için Aspose.Slides for Java neden kullanılmalı?
Grafik oluşturma sürecinin tamamını UI etkileşimi olmadan otomatikleştirebilirsiniz, bu sunucu tarafı rapor üretimi için esastır. Aspose.Slides, Java uyumlu herhangi bir işletim sisteminde çalışır, sunumları tamamen yüklemeden 500 slayta kadar işleyebilir ve 50'den fazla yerleşik grafik stili sunar. Bu, COM bağımlılıklarını ortadan kaldırır ve yüksek kaliteli görselleri doğrudan Java'dan gömmeyi sağlar.

## Önkoşullar
- **Aspose.Slides for Java** (v25.4 veya daha yeni) – 50+ grafik türü ve 30+ görüntü formatını destekler.  
- **JDK 16** (veya daha yeni) – en son dil özellikleri için gereklidir.  
- IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE.  

## Aspose.Slides for Java'ı kurma
Kütüphaneyi Maven, Gradle veya doğrudan indirme yoluyla ekleyebilirsiniz.

### Maven Kullanarak
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kullanarak
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan indirme
En son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

#### Lisans edinme adımları
- **Ücretsiz deneme** – zaman sınırlaması olmadan tüm özellikleri test edin.  
- **Geçici lisans** – tam özellikli değerlendirme için Aspose portalından bir tane isteyin.  
- **Satın alma** – üretim kullanımı için kalıcı bir lisans edinin.

## Uygulama rehberi

### Bir sunum oluşturma ve slayt ekleme
`Presentation`, bellekte bir PowerPoint dosyasını temsil eden temel Aspose.Slides nesnesidir. Oluşturduktan sonra slaytlara erişebilir, değiştirebilir veya yeni slayt ekleyebilirsiniz.

#### Genel Bakış
İlk olarak, yeni bir `Presentation` nesnesi oluşturur ve yeni bir dosyayla gelen varsayılan slaytı alırız.

#### Adım adım
**1. Presentation nesnesini başlat**  
```java
Presentation presentation = new Presentation();
```  

**2. İlk slayta eriş**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. Kaynakları serbest bırak**  
```java
if (presentation != null) presentation.dispose();
```  

### Bir slayta grafik ekleme
`IChart`, bir slayta eklenen herhangi bir grafiği temsil eden arayüzdür. `ChartType.ClusteredColumn` belirterek Aspose.Slides'a kümelenmiş sütun grafik oluşturmasını söylersiniz.

#### Genel Bakış
Şimdi az önce hazırladığımız slayta bir **kümelenmiş sütun grafik** gömüyoruz.

#### Adım adım
**1. Presentation nesnesini başlat**  
```java
Presentation presentation = new Presentation();
```  

**2. İlk slayta eriş**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. Kümelenmiş sütun grafik ekle**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. Kaynakları serbest bırak**  
```java
if (presentation != null) presentation.dispose();
```  

### Grafik çizgi stilini biçimlendirme ve yuvarlatılmış köşeleri ayarlama
`Chart`, `getChartFormat()` metodunu sağlar; bu metod bir `ChartFormat` nesnesi döndürür ve çizgi doldurmalarını, tire stillerini ve köşe yuvarlatmalarını ayarlamak için kullanılabilir.
`Chart`, `IChart` arayüzünü uygulayan somut sınıftır ve bir slayttaki grafik nesnesini temsil eder.

#### Genel Bakış
Katı bir çizgi doldurması, tek bir çizgi stili ve yuvarlatılmış köşeler uygulayarak görsel çekiciliği artırın.

#### Adım adım
**1. Presentation nesnesini başlat**  
```java
Presentation presentation = new Presentation();
```  

**2. İlk slayta eriş**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. Kümelenmiş sütun grafik ekle**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. Çizgi formatını katı doldurma türüne ayarla**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```  

**5. Tek çizgi stilini uygula**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```  

**6. Grafik alanı için yuvarlatılmış köşeleri etkinleştir**  
```java
chart.setRoundedCorners(true);
```  

**7. Kaynakları serbest bırak**  
```java
if (presentation != null) presentation.dispose();
```  

### Sunumu kaydetme
`SaveFormat.Pptx`, modern PowerPoint dosyaları için önerilen formattır; tüm grafik biçimlendirmesini korur ve sonraki düzenlemelere izin verir.

#### Genel Bakış
Son olarak, sunumu PPTX formatında diske yazarız; bu, **PowerPoint'i PPTX olarak kaydet** işlemleri için standarttır.

#### Adım adım
**1. Presentation nesnesini başlat**  
```java
Presentation presentation = new Presentation();
```  

**2. Çıktı dizinini ve dosya adını tanımla**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```  

**3. Sunumu PPTX formatında kaydet**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```  

**4. Kaynakları serbest bırak**  
```java
if (presentation != null) presentation.dispose();
```  

## Pratik uygulamalar
- **İş raporları** – dinamik grafiklerle çeyrek dönem finansal sunumları otomatikleştirin.  
- **Eğitim içeriği** – veritabanından veri çeken ders slaytları oluşturun.  
- **Pazarlama sunumları** – şık, marka uyumlu grafiklerle ürün trendlerini görselleştirin.  

## Performans hususları
- **Kaynak yönetimi** – yerel belleği serbest bırakmak için her zaman `dispose()` çağırın veya try‑with‑resources kullanın.  
- **Bellek optimizasyonu** – büyük veri setlerini daha küçük partilerde işleyin; Aspose.Slides, tam yüklemeden 500 MB'a kadar sunumları işleyebilir.  
- **En iyi uygulamalar** – mümkün olduğunda grafik serileri için değiştirilemez veri yapıları tercih edin; bu, GC baskısını azaltır ve verimliliği artırır.  

## Yaygın sorunlar ve çözümler

| Sorun | Çözüm |
|-------|----------|
| **`NullPointerException` on `getSlides()`** | Sunum nesnesinin slaytlara erişmeden önce başarılı bir şekilde örneklenmiş olduğundan emin olun. |
| **Chart not appearing** | Grafik boyutlarının (x, y, genişlik, yükseklik) slayt sınırları içinde olduğundan ve `ChartType.ClusteredColumn` kullanıldığından emin olun. |
| **License not applied** | `Presentation` nesnesini oluşturmadan önce lisans dosyanızı yükleyin: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Sıkça sorulan sorular

**S: Aspose.Slides kullanarak farklı grafik türleri nasıl eklenir?**  
C: `ChartType.ClusteredColumn` yerine `ChartType.Pie`, `ChartType.Line` veya `ChartType.Bar` gibi başka bir enum değeri kullanın.

**S: Derleme hatalarıyla karşılaşırsam ne yapmalıyım?**  
C: JDK 16 veya daha yeni bir sürüm kullandığınızdan ve Maven/Gradle bağımlılık sürümünün indirdiğiniz kütüphane ile eşleştiğinden emin olun.

**S: Grafiği bir veritabanından veri ile doldurabilir miyim?**  
C: Evet. Grafiğin `getChartData()` koleksiyonuna erişin, seriler ve kategoriler oluşturun ve çalışma zamanında alınan değerlerle doldurun.

**S: Çok büyük sunumlar için performansı nasıl artırabilirim?**  
C: Çalışmayı birden fazla `Presentation` örneğine bölün, grafik şablonlarını yeniden kullanın ve nesneleri her zaman zamanında serbest bırakın.

## Sonuç
Artık Aspose.Slides for Java ile bir PowerPoint slaytına **kümelenmiş sütun grafik** eklemek için eksiksiz, uçtan uca bir tarife sahipsiniz. Diğer grafik türlerini deneyin, canlı veri kaynaklarını bağlayın ve bu mantığı daha büyük raporlama boru hatlarına entegre ederek sunum iş akışınızı otomatikleştirin.

---

**Son Güncelleme:** 2026-09-02  
**Test Edilen:** Aspose.Slides 25.4 for Java (JDK 16)  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Slides for Java kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [PowerPoint Grafik Oluşturma Java – Aspose.Slides Kullanarak Grafiklerle Sunumları Kaydet](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Aspose.Slides for Java kullanarak PowerPoint grafiğine animasyon ekleme – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}