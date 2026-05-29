---
date: '2026-05-29'
description: Aspose.Slides Maven kullanarak pie chart oluşturmayı, bir slayta pie
  chart java eklemeyi ve chart verilerini özelleştirmeyi öğrenin. Maven kurulumu ve
  gerçek dünya örnekleriyle adım adım kılavuz.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Aspose ile Pie Chart Oluştur – Maven ile Sunuma Chart Ekle
url: /tr/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java Kullanarak Bir Sunuma Pasta Grafiği Ekleme

## Giriş
Bu rehberde Aspose.Slides Maven ile **create pie chart aspose** oluşturacak ve bunu bir PowerPoint slaytına nasıl gömeceğinizi göreceksiniz. Görsel olarak çekici sunumlar, bilgiyi etkili bir şekilde iletmek için çok önemlidir, özellikle veri görselleştirmesi kritik bir rol oynadığında. Bu süreci **aspose slides maven** ile otomatikleştirmek istiyorsanız doğru yerdesiniz. Bir slayta—özellikle bir pasta grafiği—grafik ekleme ve gerçek dünya senaryoları için özelleştirme adımlarını birlikte inceleyeceğiz.

### Öğrenecekleriniz
- Java'da bir sunum nesnesi nasıl başlatılır.  
- Bir sununun ilk slaytına **add a pie chart java** ekleme adımları.  
- Grafik veri çalışma kitaplarına erişme ve içindeki çalışma sayfalarını listeleme.  

Let's dive into how you can harness Aspose.Slides Java to enhance your presentations with dynamic charts!

## Hızlı Yanıtlar
- **Maven üzerinden grafik ekleyen kütüphane nedir?** aspose slides maven  
- **Hangi grafik türü gösterilmektedir?** Pie chart (add chart to slide)  
- **Gerekli minimum Java sürümü nedir?** JDK 16 or later  
- **Test için lisans gerekli mi?** A free trial works; production needs a license  
- **Maven bağımlılığını nerede bulabilirim?** In the setup section below  

## Aspose Slides Maven Nedir?
Aspose.Slides for Java is a powerful API that lets developers create, modify, and render PowerPoint files programmatically. The Maven package (`aspose-slides`) simplifies dependency management, allowing you to focus on building and customizing slides—like adding a pie chart—without dealing with low‑level file handling.

## Bir Slayta Grafik Eklemek İçin Aspose.Slides Maven Neden Kullanılmalı?
Using Aspose.Slides Maven lets you generate charts directly from Java code without manual PowerPoint editing. It provides full programmatic control over chart types, data sources, and styling, ensuring consistent branding and accuracy. The Maven artifact also handles all required dependencies, simplifying builds and enabling seamless integration into CI/CD pipelines.

## Önkoşullar
- **Aspose.Slides for Java** sürüm 25.4 veya üzeri (Maven/Gradle).  
- JDK 16+ yüklü.  
- Bir IDE (IntelliJ IDEA, Eclipse vb.).  
- Temel Java bilgisi ve Maven veya Gradle konusunda aşinalık.

## Aspose.Slides for Java Kurulumu
First, include Aspose.Slides in your project via Maven or Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatively, you can [download the latest release](https://releases.aspose.com/slides/java/) directly from Aspose's website.

### Lisans Edinme
Aspose.Slides for Java offers a free trial with a temporary license for testing. For unrestricted production use, purchase a license through the [purchase page](https://purchase.aspose.com/buy).

## Uygulama Kılavuzu
Below we break the solution into two features: adding a pie chart and accessing its data workbook.

### Özellik 1: Sunum Oluşturma ve Grafik Ekleme
#### Genel Bakış
This part shows how to create a new presentation and **add a pie chart** to the first slide.

#### **pie chart aspose** nasıl oluşturulur?
Load the `Presentation` class, add a chart of type `ChartType.Pie`, and save the file. The entire operation requires only three API calls and runs in under a second for a typical 10‑slide deck, making it ideal for automated report generation.

#### Adım‑Adım

**Adım 1: Yeni Bir Presentation Nesnesi Başlatma**  
The `Presentation` class is Aspose.Slides' top‑level object that represents a PowerPoint file in memory.  
```java
Presentation pres = new Presentation();
```
*Creates the `Presentation` instance that will hold all slides.* → *Tüm slaytları tutacak `Presentation` örneğini oluşturur.*

**Adım 2: Pasta Grafiği Ekleme**  
`ChartType.Pie` tells Aspose to render a pie chart.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Places a pie chart at coordinates (50, 50) with a width of 400 and height of 500.* → *Koordinat (50, 50) konumunda, 400 genişlik ve 500 yükseklikte bir pasta grafiği yerleştirir.*

**Adım 3: Kaynakları Serbest Bırakma**  
Calling `dispose()` releases native resources and prevents memory leaks.  
```java
if (pres != null) pres.dispose();
```
*Releases native resources; always call `dispose()` when you’re done.* → *Yerel kaynakları serbest bırakır; işiniz bittiğinde her zaman `dispose()` çağırın.*

### Özellik 2: Grafik Veri Çalışma Kitabına ve Çalışma Sayfalarına Erişim
#### Genel Bakış
Learn how to reach the underlying workbook that stores chart data and iterate through its worksheets.

#### Grafik veri çalışma kitabına nasıl erişilir?
Retrieve the `IChartDataWorkbook` from the chart, then loop through its `Worksheets` collection. This workbook mimics an Excel file, allowing you to read, modify, or add data series programmatically, which the chart will reflect instantly when refreshed during runtime without restarting.

#### Adım‑Adım

**Adım 1: (Tekrar Kullan) Yeni Bir Presentation Nesnesi Başlatma**  
*Same as Feature 1, Step 1.* → *Feature 1, Adım 1 ile aynı.*

**Adım 2: (Tekrar Kullan) Pasta Grafiği Ekleme**  
*Same as Feature 1, Step 2.* → *Feature 1, Adım 2 ile aynı.*

**Adım 3: Grafik Veri Çalışma Kitabını Al**  
`IChartDataWorkbook` is the interface that provides read/write access to the chart’s internal Excel‑like workbook.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Retrieves the `IChartDataWorkbook` linked to the chart.* → *Grafiğe bağlı `IChartDataWorkbook`'u alır.*

**Adım 4: Çalışma Sayfaları Üzerinde Döngü**  
`Worksheet` objects represent individual sheets inside the workbook.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Prints each worksheet’s name, letting you verify the data structure.* → *Her çalışma sayfasının adını yazdırır, veri yapısını doğrulamanızı sağlar.*

**Adım 5: Kaynakları Serbest Bırakma**  
*Same as Feature 1, Step 3.* → *Feature 1, Adım 3 ile aynı.*

## Pratik Uygulamalar
- **Veri Raporlama:** İş zekası için güncel metriklerle slayt destelerini otomatik oluşturma.  
- **Akademik Sunumlar:** Araştırma sonuçlarını manuel grafik oluşturma olmadan görselleştirme.  
- **Pazarlama Materyali:** Ürün performansını veya anket sonuçlarını anında sergileme.

## Performans Düşünceleri
- Aspose.Slides **50+ giriş ve çıkış formatını** işleyebilir ve tüm dosyayı belleğe yüklemeden çok sayfalı sunumları işleyebilir.  
- Slayt ve grafik sayısını makul tutun; her grafik yerel bellek tüketir.  
- `dispose()` her zaman çağrılarak kaynaklar hızlıca serbest bırakılmalıdır.  
- Çalışma kitabı veri işleme optimizasyonu—tek bir grafiğe büyük veri setleri yüklemekten kaçının.

## Sonuç
We’ve covered how **aspose slides maven** enables you to **add chart to slide** programmatically and how to work with the chart’s data workbook. With these building blocks you can automate any reporting workflow that requires a polished PowerPoint output.

### Sonraki Adımlar
- Grafik stil seçeneklerini keşfedin (renkler, lejandlar, veri etiketleri).  
- Grafikleri dinamik olarak doldurmak için harici veri kaynaklarına (CSV, veritabanları) bağlanın.  
- Daha zengin bir anlatım için tek bir sunumda birden fazla grafik türünü birleştirin.

## Sıkça Sorulan Sorular

**S: Aspose.Slides for Java'ı nasıl kurarım?**  
A: Use the Maven or Gradle dependency shown above, or download the library from the releases page.

**S: Aspose.Slides için sistem gereksinimleri nelerdir?**  
A: JDK 16 or later; the library runs on any platform that supports Java.

**S: Pasta grafiği dışında başka grafik türleri ekleyebilir miyim?**  
A: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20 chart types.

**S: Büyük sunumları verimli bir şekilde nasıl yönetmeliyim?**  
A: Dispose of objects promptly, limit high‑resolution images, and reuse chart templates to keep memory usage low.

**S: Aspose.Slides özellikleri hakkında daha fazla detayı nerede bulabilirim?**  
A: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/) for a complete API reference.

**S: Ticari kullanım için lisans gerekli mi?**  
A: A valid license is required for production; a free trial is available for evaluation.

**S: Maven paketi tüm grafik yeteneklerini içeriyor mu?**  
A: Yes, the `aspose-slides` Maven artifact contains the full charting engine.

## Kaynaklar
- Dokümantasyon: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- İndirme: [Latest Releases](https://releases.aspose.com/slides/java/)
- Satın Alma ve Deneme: [Purchase Page](https://purchase.aspose.com/buy)
- Ücretsiz deneme: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Geçici Lisans: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Destek Forumu: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## İlgili Eğitimler

- [Java'da Aspose.Slides ile Pasta Grafik Renklerini Özelleştirme – Tam Kılavuz](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Java'da Aspose.Slides ile Pasta İçinde Pasta Grafiği Oluşturma: Kapsamlı Kılavuz](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Aspose.Slides for Java ile PowerPoint Grafiklerini Canlandırma – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}