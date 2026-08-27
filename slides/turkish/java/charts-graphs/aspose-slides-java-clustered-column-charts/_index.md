---
date: '2026-08-27'
description: Aspose.Slides kullanarak Java'da clustered column chart oluşturmayı öğrenin,
  grafiği ekleyin, otomatik seri renklerini ayarlayın ve sunumu PPTX olarak kaydedin.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: Aspose.Slides kullanarak Java'da clustered column chart oluşturmayı
  öğrenin, grafiği ekleyin, otomatik seri renklerini ayarlayın ve sunumu PPTX olarak
  kaydedin—hepsi net adım adım talimatlarla.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: Java ile Aspose.Slides kullanarak clustered column chart oluşturun
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: Java ile Aspose.Slides kullanarak clustered column chart nasıl oluşturulur
url: /tr/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java ile Aspose.Slides kullanarak kümeleme sütun grafiği nasıl oluşturulur

## Giriş
Kümeleme sütun grafiğini programlı olarak oluşturmak, saatlerce süren manuel biçimlendirmeyi tasarruf ettirir ve birden çok sunumda tutarlılığı garanti eder. Bu öğreticide Java ile Aspose.Slides kullanarak **kümeleme sütun grafiği nasıl oluşturulur**, **grafiğin nasıl eklenir**, **renklerin nasıl ayarlanır** ve **sunumun PPTX olarak nasıl kaydedilir** öğreneceksiniz. Kütüphanenin kurulumu, seri dolgu renklerinin özelleştirilmesi ve dosyanın kalıcı hale getirilmesi gibi her şeyi kapsayacağız, böylece zengin veri görselleştirmelerini herhangi bir PowerPoint sunumuna gömebilirsiniz.

## Hızlı cevaplar
- **Sunumlarla çalışmak için birincil sınıf nedir?** `Presentation` from the `com.aspose.slides` package.  
- **Kümeleme sütun grafiği nasıl eklenir?** Call `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **Seri renkleri otomatik olarak ayarlanabilir mi?** Yes—enable `setAutomaticSeriesColor(true)` on each series.  
- **Dosyayı kaydetmek için hangi formatı kullanmalıyım?** `SaveFormat.Pptx` produces a standard PowerPoint file.  
- **Üretim için lisans gerekli mi?** A trial works for development; a full license is needed for commercial use.

## Kümeleme sütun grafiği nedir?
Kümeleme sütun grafiği, her kategori için birden çok veri serisini yan yana gösterir ve gruplar arasındaki değerleri karşılaştırmayı kolaylaştırır. Aspose.Slides bu grafik türünü kutudan çıkar çıkmaz destekler ve her görsel yönü programlı olarak kontrol etmenizi sağlar.

## Aspose.Slides ile kümeleme sütun grafiği neden oluşturulmalı?
Aspose.Slides **50+** giriş ve çıkış formatını destekler ve **yüzlerce slayt** içeren sunumları tüm dosyayı belleğe yüklemeden işleyebilir. Bu verimlilik, sunucuda büyük sunumlar üretirken minimum kaynak tüketimiyle mümkün olur.

## Önkoşullar
- **Java Development Kit** 16 veya daha yeni.  
- **Maven** veya **Gradle**, bağımlılık yönetimi için.  
- Java sözdizimi ve nesne‑yönelimli kavramlara temel aşinalık.  

### Gerekli kütüphaneler ve bağımlılıklar
Aspose.Slides for Java kütüphanesine (sürüm 25.4 veya sonrası) ihtiyacınız var. Kütüphane JDK 16 ile tam uyumludur ve grafik manipülasyonu için zengin bir API sunar.

### Ortam kurulum gereksinimleri
IDE'niz (IntelliJ IDEA, Eclipse, VS Code) Java 16 kodunu derleyebilmeli ve Maven/Gradle bağımlılıklarını çözebilmelidir.

### Bilgi önkoşulları
PowerPoint slayt yapısını ve temel grafik terminolojisini (seriler, kategoriler, veri noktaları) anlamak, örnekleri daha hızlı takip etmenizi sağlar.

## Aspose.Slides for Java kurulumu
Kütüphaneyi projenize aşağıdaki yöntemlerden biriyle entegre edin.

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

**Doğrudan indirme** – resmi sürüm sayfasından JAR dosyasını edinin: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lisans edinme adımları
- **Ücretsiz deneme** – geçici bir lisans dosyası almak için Aspose sitesine kaydolun.  
- **Geçici lisans** – daha büyük test paketleri için 30 günlük lisans isteyin.  
- **Tam lisans** – sınırsız üretim kullanımı için satın alın.

**Temel başlatma ve kurulum**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## Kümeleme sütun grafiği nasıl eklenir?
`Presentation` bir PowerPoint dosyasını bellekte temsil eder.  

**Doğrudan cevap:**  
`Presentation` nesnesi oluşturun, ilk slaytı alın ve `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)` çağrısını yapın. Bu tek çağrı, tam işlevsel bir kümeleme sütun grafiği ekler, veri doldurulmaya hazırdır ve slayt üzerindeki belirtilen koordinatlara yerleştirir.

### Özellik 1: kümeleme sütun grafiği oluştur
`Presentation` sınıfı bir PowerPoint dosyasını bellekte temsil eder ve slaytlara, şekillere ve grafik nesnelerine erişim sağlar.

**Adım 1: sunumu başlat**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**Adım 2: kümeleme sütun grafiği ekle**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**Adım 3: kaynakları temizle**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Grafiğin renkleri nasıl ayarlanır?
`Series` bir grafikteki veri noktalarının koleksiyonunu temsil eder.  

**Doğrudan cevap:**  
Grafik oluşturulduktan sonra `chart.getChartData()` ile grafik verisine erişin ve her `Series` nesnesi üzerinde yineleme yapın. Her seri için `setAutomaticSeriesColor(true)` çağırın. Aspose.Slides, her seri için paletinden farklı ve kontrast bir renk otomatik olarak atar, böylece manuel renk seçimine gerek kalmaz.

### Özellik 2: otomatik seri dolgu rengini ayarla
`IChart` grafik şekli temsil eden arayüzdür; `getChartData()` serileri manipüle etmek için sunar.

**Adım 1: grafiğe eriş ve serileri yinele**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**Adım 2: kaynak yönetimi**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Sunumu PPTX olarak nasıl kaydedilir?
`save` seçilen formatta sunumu bir dosyaya yazar.  

**Doğrudan cevap:**  
`"output/ClusteredColumnChart.pptx"` gibi bir çıktı dosya yolu belirleyin ve `presentation.save(outputPath, SaveFormat.Pptx)` çağrısını yapın. `save` yöntemi, tüm slayt destesi, şekiller, grafikler ve kaynaklar dahil olmak üzere standart bir PPTX dosyasına serileştirir; bu dosya PowerPoint 2010 ve sonrası ile, ayrıca birçok çevrimiçi görüntüleyiciyle açılabilir.

### Özellik 3: sunumu diske kaydet
`SaveFormat.Pptx` ile kaydetmek, PowerPoint 2010 ve sonrası ile uyumlu bir dosya üretir, ayrıca çoğu çevrimiçi görüntüleyicide de çalışır.

**Adım 1: çıktı yolunu tanımla**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**Adım 2: sunumu kaydet**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## Pratik uygulamalar
- **Finansal raporlama** – ürün hatları arasında çeyrek gelirleri karşılaştırın.  
- **Pazarlama analitiği** – kampanya performansını bölge bazında görselleştirin.  
- **Proje yönetimi** – ekipler arasında sprint hızı veya kaynak tahsislerini gösterin.  

## Performans hususları
- `Presentation` nesnelerini zamanında serbest bırakın, yerel kaynakları boşaltmak için.  
- Dosya boyutunu küçültmek için kaydetmeden önce `presentation.getSlides().removeUnusedResources()` kullanın.  
- Bellek kullanımını düşük tutmak için grafik serilerini hafif koleksiyonlarla (ör. `ArrayList<Double>`) doldurun.

## Sonuç
Artık **kümeleme sütun grafiği oluşturmayı**, otomatik **renk ayarlamayı** ve Aspose.Slides for Java kullanarak **sunumu PPTX olarak kaydetmeyi** biliyorsunuz. Bu adımlar, veri odaklı slaytları programlı olarak üretmenizi sağlar, tekrarlayan manuel işleri ortadan kaldırır ve organizasyonunuzda görsel tutarlılığı temin eder.

**Sonraki adımlar:**  
Veri etiketleri, eksen biçimlendirme ve veritabanı ya da CSV dosyalarından dinamik veri bağlama gibi ileri özelleştirmeleri keşfederek sunumlarınızı daha da zenginleştirin.

## Sıkça sorulan sorular
**S: Bu kodu bir web uygulamasında kullanabilir miyim?**  
C: Evet—Aspose.Slides platform‑agnostic bir yapıya sahiptir ve Spring Boot, Jakarta EE gibi herhangi bir Java‑tabanlı sunucu ortamında çalışır.

**S: Kütüphane diğer grafik türlerini destekliyor mu?**  
C: Kesinlikle. `ChartType` enum'ı Pie, Bar, Line, Area, Radar ve daha birçok türü içerir.

**S: Çıktı klasörü mevcut değilse ne olur?**  
C: Klasörün önceden oluşturulduğundan emin olun veya `Files.createDirectories(Paths.get(folder))` kullanarak `FileNotFoundException` hatasından kaçının.

**S: Büyük veri setlerini (binlerce nokta) nasıl yönetirim?**  
C: Serileri akış API'leri veya toplu eklemelerle doldurun ve render hızını artırmak için grafik animasyonunu devre dışı bırakmayı düşünün.

**S: Daha fazla kod örneği nerede bulunabilir?**  
C: Resmi dokümantasyon ve örnek deposunu ziyaret edin: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## Kaynaklar
- **Dokümantasyon:** [Aspose.Slides Dokümantasyonu](https://reference.aspose.com/slides/java/)  
- **Referans:** [Aspose.Slides Referansı](https://reference.aspose.com/slides/java/)  
- **İndirin:** [Aspose.Slides İndirin](https://releases.aspose.com/slides/java/)  
- **Lisans Satın Al:** [Lisans Satın Al](https://purchase.aspose.com/buy)  
- **Ücretsiz Deneme Başlat:** [Ücretsiz Deneme Başlat](https://releases.aspose.com/slides/java/)  
- **Buradan Talep Et:** [Buradan Talep Et](https://purchase.aspose.com/temporary-license/)  
- **Aspose Forum:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-08-27  
**Test Edilen:** Aspose.Slides 25.4 (JDK 16)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [PowerPoint Grafik Oluştur Java – Aspose.Slides Kullanarak Grafiklerle Sunumları Kaydet](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [aspose slides maven bağımlılığı: Aspose.Slides for Java Kullanarak Sunumlarda Grafik Ekle ve Yapılandır](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint grafiğine animasyon ekleme Aspose.Slides for Java ile – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}