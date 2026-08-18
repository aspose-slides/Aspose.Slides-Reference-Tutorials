---
date: '2026-06-03'
description: aspose slides maven dependency ile grafik eklemeyi, veri etiketlerini
  yapılandırmayı ve Java sunumlarında dinamik grafikler oluşturmayı öğrenin.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Sunumlarda Grafik Ekleyin ve Yapılandırın
  Aspose.Slides for Java Kullanarak'
url: /tr/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Sunumlarda Aspose.Slides for Java Kullanarak Grafik Ekleme ve Yapılandırma

## Giriş
**aspose slides maven dependency**, Java geliştiricilerinin PowerPoint dosyalarını hiç PowerPoint açmadan programlı olarak oluşturmasına, değiştirmesine ve zenginleştirmesine olanak tanır. Birçok iş ve akademik senaryoda, grafikleri manuel olarak eklemek zaman alıcı ve hataya açıktır. Bu öğreticide, adım adım bir Bubble Chart eklemeyi, veri etiketlerini çalışma sayfası hücrelerine bağlamayı ve sonucu kaydetmeyi gösteriyoruz — tüm bunlar aspose slides maven dependency'yi temiz, tekrarlanabilir bir şekilde kullanarak.

**Neler Öğreneceksiniz**
- aspose slides maven dependency ile grafik ekleme
- Maven veya Gradle kullanarak bir Java projesi kurma
- Mevcut bir sunumu yükleme ve Bubble Chart ekleme
- Hücre referansları kullanarak veri etiketlerini yapılandırma (add data labels chart)
- Güncellenmiş dosyayı daha sonra dağıtım için kaydetme
- Dinamik grafik oluşturma ve sunum grafik iş akışları oluşturma gibi gerçek dünya kullanım senaryoları

## Hızlı Yanıtlar
- **Grafik yeteneklerini ekleyen Maven artefaktı hangisidir?** `com.aspose:aspose-slides:25.4` (veya en yeni)  
- **Veri etiketlerini Excel‑stil hücrelere bağlayabilir miyim?** Evet – `ChartDataLabel` ile `setDataLabelFormat` ve hücre referanslarını kullanın.  
- **Üretim için lisans gerekli mi?** Tam lisans değerlendirme filigranını kaldırır ve tüm özelliklerin kilidini açar.  
- **Bu Java 11+ üzerinde çalışır mı?** Kesinlikle; kütüphane Java 8'den Java 21'e kadar uyumludur.  
- **Kaç çeşit grafik destekleniyor?** Balon, Radar ve Stok grafikler dahil olmak üzere 70'ten fazla farklı grafik türü.

## aspose slides maven dependency nedir?
**aspose slides maven dependency**, Java'da PowerPoint (PPTX, PPT, ODP) dosyalarını oluşturmak ve düzenlemek için tam özellikli bir API sağlayan Maven‑uyumlu bir pakettir. Bu bağımlılığı `pom.xml` veya `build.gradle` dosyanıza ekleyerek 70'ten fazla grafik türü, 150+ slayt düzeni ve Office yüklü olmadan şekilleri, animasyonları ve meta verileri manipüle etme yeteneğine erişirsiniz.

## Grafik otomasyonu için aspose slides maven dependency neden kullanılmalı?
Aspose.Slides, standart sunucu donanımında bir saniyeden kısa sürede binlerce slayttan oluşan sunumları işler, **70+ grafik türünü** destekler ve **10.000 slayta** kadar sunumu, dosyanın tamamını belleğe yüklemeden render edebilir. Bu ölçülebilir yetenekler, performans ve ölçeklenebilirliğin tartışılmaz olduğu kurumsal düzeyde dinamik grafik oluşturma senaryoları için idealdir.

## Önkoşullar
- **Java Development Kit (JDK)** 8 veya daha yeni (Java 11+ önerilir).  
- **Maven** 3.6+ **veya** **Gradle** 6+.  
- **Aspose.Slides for Java** kütüphanesi (aspose slides maven dependency, sürüm 25.4 veya üzeri).  
- **Java koleksiyonları** ve **dosya I/O** konusunda temel bilgi.  
- Deneme veya tam lisans dosyası (`license.json`) eğer kodu deneme süresinin ötesinde çalıştırmayı planlıyorsanız.

## Aspose.Slides kullanarak bir slayta grafik nasıl eklenir?
Hedef sunumu yükleyin, istenen slayta yeni bir grafik şekli oluşturun ve grafik türünü (bu örnekte Bubble) belirtin. Kütüphane referans alındıktan sonra tüm işlem **üç kısa kod satırı** içinde gerçekleştirilebilir; bu da hızlı prototipleme ve üretim hatları için mükemmeldir.

### Adım 1: aspose slides maven dependency ekleyin
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Bu snippet'ler tam Aspose.Slides API'sini — grafik desteği dahil — doğrudan Maven Central'dan çeker.

### Adım 2: Sunumu yükleyin ve Bubble Chart ekleyin
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Adım 3: Grafiğin veri serilerini ve etiketlerini yapılandırın
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Adım 4: Değiştirilen sunumu kaydedin
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Hücre referansları kullanarak veri etiketleri nasıl yapılandırılır?
Veri etiketleri, Excel'in “Hücreye Bağla” özelliğini taklit ederek dış hücre değerlerine bağlanabilir. Bu yaklaşım sabit değerleri ortadan kaldırır ve **dinamik grafik oluşturma** sağlar; etiket içeriği, temel veri değiştiğinde otomatik olarak güncellenir. Her etiketi belirli bir çalışma kitabı hücresine bağlayarak, kaynak verideki herhangi bir değişikliğin sunumda anında yansıtılmasını sağlarsınız; bu da bakım çabasını azaltır ve eski bilgiler riskini en aza indirir.

### Doğrudan Cevap
`chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` çağrısını yapın ve `"Sheet1!A2"` gibi bir hücre adresi referansı içeren `DataLabelFormat` nesnesi geçin. Aspose.Slides, çalışma zamanında referansı çözer ve hücrenin mevcut değerini grafik etiketine ekler.

### Adım‑adım
1. Etiketlemek istediğiniz seriyi belirleyin.  
2. Her veri noktası için `IDataLabel` nesnesini alın.  
3. `CellReference` için yapılandırılmış `DataLabelFormat` ile `setDataLabelFormat` kullanın.  
4. İsteğe bağlı olarak yazı tipi, renk ve görüntüleme seçeneklerini özelleştirin.

## Değiştirilen sunumu nasıl kaydedilir?
Kaydetme, bellekteki `Presentation` nesnesini bir dosya yolu ya da çıktı akışına yazan tek bir metod çağrısıdır. Ayrıca `SaveFormat` enum'ını kullanarak çıkış formatını (PPTX, PDF, ODP) seçebilirsiniz. Bu işlem sonucu doğrudan diske akıtarak, `Presentation` örneği kapandığında ya da kapsam dışına çıktığında tüm yerel kaynakları otomatik olarak serbest bırakır; bu da büyük sunumlarda bellek kullanımını düşük tutar.

### Doğrudan Cevap
`presentation.save("output.pptx", SaveFormat.Pptx)` çağrısını yapın; kütüphane sonucu doğrudan diske akıtarak, `Presentation` örneği kapandığında tüm yerel kaynakları otomatik olarak serbest bırakır.

## Pratik Uygulamalar
1. **İş Raporları:** Veritabanı dökümünden çeyrek dönem satış grafiklerini otomatik olarak oluşturun.  
2. **Akademik Dersler:** Her ders oturumunda canlı araştırma verilerini slaytlara çekin.  
3. **Satış Sunumları:** Müşteri‑özel performans panolarını anında oluşturun.  
4. **Proje Yönetimi:** Dinamik veri etiketli Gantt‑stil zaman çizelgelerini görselleştirin.  
5. **Pazarlama Analitiği:** Yeni metrikler geldikçe güncellenen kampanya KPI'larını sunumlara gömün.

## Performans Düşünceleri
- **Bellek Yönetimi:** Yerel belleği hızlıca serbest bırakmak için try‑with‑resources veya açıkça `presentation.dispose()` kullanın.  
- **Büyük Veri Setleri:** 10.000'den fazla veri noktasını işlerken, tüm veri setini Java nesnelerine yüklemek yerine `ChartDataWorkbook` üzerinden doldurun.  
- **İş Parçacığı Güvenliği:** Her iş parçacığı kendi `Presentation` örneğiyle çalışmalı; API paylaşılan nesneler arasında iş parçacığı güvenli değildir.  

## Yaygın Sorunlar ve Çözümler
- **Sorun:** “Lisans dosyası bulunamadı.”  
  **Çözüm:** `license.json` dosyasını sınıf yoluna yerleştirin ve herhangi bir API kullanımından önce `License license = new License(); license.setLicense("license.json");` kodunu çalıştırın.  
- **Sorun:** Kaydetme sonrası grafik boş görünüyor.  
  **Çözüm:** Grafiğin veri çalışma kitabının sunumla birlikte kaydedildiğinden emin olun (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Sorun:** Veri etiketleri “#REF!” hatası gösteriyor.  
  **Çözüm:** Hücre referans dizesinin tam sayfa adı ve adresiyle eşleştiğini ve referans verilen çalışma kitabının grafiğe ekli olduğunu doğrulayın.  

## Sık Sorulan Sorular

**Q: Balon dışında başka grafik türleri ekleyebilir miyim?**  
A: Evet, `ChartType` enum'ı satır, çubuk, pasta, radar, hisse ve 70'ten fazla ek tür içerir.

**Q: aspose slides maven dependency OpenJDK ile çalışır mı?**  
A: Kesinlikle; OpenJDK 8‑21 ile tam uyumludur ve tüm büyük işletim sistemlerinde çalışır.

**Q: Mevcut bir Excel dosyasından grafik nasıl gömülür?**  
A: `WorkbookFactory.create(new FileInputStream("data.xlsx"))` ile Excel çalışma kitabını yükleyin, ardından grafiğin `ChartDataWorkbook`'unu bu çalışma kitabına bağlayarak hücre referanslarını ayarlayın.

**Q: Bir slaytta kaç grafik olabilir?**  
A: Pratikte sınırlama yoktur — Aspose.Slides, bellek izin verdiği sürece bir slaytta onlarca grafik işleyebilir.

**Q: Son sunumu hangi formatlara dışa aktarabilirim?**  
A: PPTX, PPT, ODP, PDF, XPS, HTML ve PNG, JPEG gibi görüntü formatları desteklenir.

## Kaynaklar
- [Aspose.Slides for Java sürümleri](https://releases.aspose.com/slides/java/) – en yeni kütüphane ikili dosyalarını indirin.  
- [Aspose.Slides Dokümantasyonu](https://reference.aspose.com/slides/java/) – kapsamlı API referansı ve kılavuzlar.  
- [Aspose.Slides for Java İndir](https://releases.aspose.com/slides/java/) – Maven/Gradle paketleri için doğrudan indirme sayfası.  
- [Lisans Satın Al](https://purchase.aspose.com/buy) – tam ticari lisans edinin.  
- [Ücretsiz Deneme](https://releases.aspose.com/slides/java/) – özellikleri değerlendirmek için deneme sürümünü başlatın.  
- [Geçici Lisans](https://purchase.aspose.com/temporary-license/) – uzatılmış değerlendirme için geçici anahtar talep edin.  
- [Aspose Destek Forumu](https://forum.aspose.com/c/slides/11) – topluluktan ve Aspose mühendislerinden yardım alın.

## Sonuç
Artık **aspose slides maven dependency** kullanarak Java sunumlarında grafik ekleme, yapılandırma ve kaydetme konusunda uçtan uca bir kılavuza sahipsiniz. Yukarıdaki adımları izleyerek grafik oluşturmayı otomatikleştirebilir, veri etiketlerini canlı hücre değerlerine bağlayabilir ve ölçekli, profesyonel sunumları üretim ortamında üretebilirsiniz. Diğer grafik türlerini deneyin, animasyon API'lerini keşfedin ve bu iş akışını raporlama hatlarınıza entegre ederek maksimum etkiyi yakalayın.

---  
**Son Güncelleme:** 2026-06-03  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4  
**Yazar:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## İlgili Öğreticiler

- [Aspose.Slides Java ile Sunum Oluşturma ve Yapılandırma: Adım Adım Kılavuz](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Aspose.Slides Maven ile PPTX Java Oluşturma – Otomasyon Kılavuzu](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Aspose.Slides ile Java'da Grafik Oluşturma: Kapsamlı Kılavuz](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}