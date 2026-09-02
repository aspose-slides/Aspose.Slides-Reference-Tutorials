---
date: '2026-09-02'
description: Aspose.Slides for Java kullanarak PowerPoint'te hun grafiği oluşturmayı
  öğrenin. Bu adım adım rehber, grafik verilerini ayarlamayı, renkleri özelleştirmeyi
  ve sunumu dışa aktarmayı kapsar.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Aspose.Slides for Java kullanarak PowerPoint'te hun grafiği oluşturmayı
  öğrenin. Bu rehber, veri ayarları, renk özelleştirmesi ve son sunumun dışa aktarılması
  konularında size yol gösterir.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Aspose.Slides for Java ile PowerPoint'te hun grafiği oluşturun
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Aspose.Slides for Java ile PowerPoint'te hun grafiği oluşturun
url: /tr/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Aspose.Slides for Java ile funnel chart oluşturma

## Giriş
Etkileyici sunumlar oluşturmak, veri görselleştirme, tasarım ve hikâye anlatımını birleştiren bir sanattır. Çok aşamalı bir süreci anında netleştiren güçlü bir görsel, funnel chart'tır. Satış hunisi, dönüşüm akışı ya da üretim darboğazını göstermeniz gerekse, iyi tasarlanmış bir funnel chart ham sayıları sezgisel bir anlatıma dönüştürür. Bu öğreticide, Aspose.Slides for Java kullanarak PowerPoint'te **funnel chart oluşturmayı** programlı bir şekilde öğrenecek, verilerini yapılandıracak, her segmentin rengini özelleştirecek ve tamamlanmış sunumu dışa aktaracaksınız.

**Öğrenecekleriniz**
- Maven veya Gradle projesine Aspose.Slides for Java ekleme  
- Bir `Presentation` nesnesi oluşturma ve slaytlarına erişme  
- Funnel chart ekleme, kategorileri tanımlama ve seri verilerini doldurma  
- Her funnel dilimini katı doldurma veya marka‑özel renklerle stil verme  
- Sunumu PPTX dosyası olarak kaydetme veya bir slaytı resim olarak dışa aktarma  

## Hızlı cevaplar
- **Java veri görselleştirme için birincil kütüphane nedir?** Aspose.Slides for Java.  
- **PowerPoint'te funnel chart nasıl oluşturulur?** Hedef slaytta `slide.addChart(ChartType.Funnel, …)` çağrısı yapılır.  
- **Hangi API chart'ın veri kaynağını ayarlar?** `IChartDataWorkbook` ve `chart.getChartData()` birlikte kullanılır.  
- **Her funnel segmenti için renk özelleştirilebilir mi?** Evet—`FillFormat.setFillType(FillType.Solid)` ayarlanır ve bir `java.awt.Color` atanır.  
- **Üretim kullanımında lisans gerekir mi?** Ticari dağıtımlar için satın alınmış bir Aspose.Slides lisansı gereklidir.

## Java veri görselleştirme nedir?
Java veri görselleştirme, ham verileri doğrudan Java uygulamalarından grafikler, çizelgeler veya etkileşimli görseller haline getirme pratiğidir. Aspose.Slides for Java, geliştiricilerin PowerPoint'i manuel olarak açmadan 100'den fazla chart türü—funnel chart dahil—oluşturmasını sağlayan lider bir kütüphanedir; 500 slayta kadar sunumu desteklerken bellek kullanımını düşük tutar.

## PowerPoint'te funnel chart neden kullanılır?
Funnel chart'lar, ardışık aşamalardaki düşüş oranlarını anında gösterir ve satış hunileri, dönüşüm analizleri veya süreç verimliliği incelemeleri için idealdir. Aspose.Slides, düzen, segment renkleri ve veri etiketleri üzerinde piksel‑tam kontrol sunar; böylece marka tutarlılığını korur ve PowerPoint UI'da chart düzenleme zahmetinden kaçınırsınız.

## Önkoşullar

### Gerekli kütüphaneler, sürümler ve bağımlılıklar
Aspose.Slides for Java'yi projenize eklemek için uygun Maven veya Gradle koordinatlarını ekleyin. Kütüphane Java 8‑21 ile çalışır ve harici yerel bağımlılık gerektirmez.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

JAR dosyasını doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden de indirebilirsiniz.

### Ortam kurulum gereksinimleri
JDK 8 veya daha yeni bir sürümün kurulu olduğundan ve `JAVA_HOME`'un doğru JDK dizinine işaret ettiğinden emin olun. Aspose.Slides, Windows, macOS ve Linux dahil JDK'yı destekleyen tüm işletim sistemlerinde çalışır.

### Bilgi önkoşulları
Java sözdizimi, nesne‑yönelimli programlama ve bir sunum dosyası kavramına temel aşinalık faydalı olur; ancak kod parçacıkları her deneyim seviyesindeki geliştirici için tam açıklamalıdır.

## Aspose.Slides for Java kurulumu

1. **Bağımlılığı ekleyin** – Yukarıdaki Maven veya Gradle snippet'ini kullanın.  
2. **Lisans edinin** –  
   - **Ücretsiz deneme** – Değerlendirme için [Aspose'un web sitesinden](https://purchase.aspose.com/temporary-license/) geçici bir lisans indirin.  
   - **Tam lisans** – Üretim lisansını [satın alma sayfasından](https://purchase.aspose.com/buy) alın.  
3. **Temel başlatma** –  

`Presentation` Aspose.Slides'ın bellek içindeki bir PowerPoint dosyasını temsil eden çekirdek sınıfıdır. Slaytlara, şekillere ve chart nesnelerine erişim sağlar.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Yukarıdaki kod, slayt manipülasyonu için yeni bir `Presentation` örneği oluşturur ve `dispose()` ile kaynakların serbest bırakılmasını garanti eder.

## Uygulama rehberi

Her kod yer tutucusundan önce kısa açıklayıcı metin ekleyerek tam bir funnel chart oluşturmak için gereken tüm özellikleri adım adım inceleyeceğiz.

### Özellik 1: sunum oluşturma

#### Genel Bakış
`Presentation` sınıfının bir örneğini oluşturun. Bu nesne, sonraki tüm işlemler için giriş noktasıdır.

`Presentation` Aspose.Slides'ın slayt koleksiyonunu ve global belge ayarlarını tutan üst‑seviye nesnedir.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Bu snippet boş bir sunum açar; daha sonra `.pptx` dosyası olarak kaydedebilirsiniz.

### Özellik 2: slayta funnel chart ekleme

#### Genel Bakış
İlk slayta bir funnel chart ekleyin, boyutunu tanımlayın ve chart tipini ayarlayın.

`ChartType.Funnel`, Aspose.Slides'ın bar veya line chart yerine funnel‑stil görselleştirme oluşturmasını sağlar.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

`addChart` çağrısı chart şekli oluşturur, `(50, 50)` noktasına konumlandırır ve genişliği `500`, yüksekliği `400` olarak ayarlar.

### Özellik 3: chart verilerini temizleme

#### Genel Bakış
Chart'ı doldurmadan önce şablonda bulunabilecek yer tutucu kategori veya serileri temizleyin.

`chart.getChartData().getCategories().clear()` mevcut tüm kategori girdilerini siler, `chart.getChartData().getSeries().clear()` ise önceden doldurulmuş serileri kaldırır.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Bu, özel verilerinizin tam olarak istediğiniz gibi görünmesini sağlayan temiz bir tablo oluşturur.

### Özellik 4: chart veri çalışma kitabını ayarlama

#### Genel Bakış
`IChartDataWorkbook` nesnesi, chart'ı besleyen ham değerleri depolar. Başlatılması, hücrelere doğrudan veri yazmanıza olanak tanır.

`IChartDataWorkbook`, Aspose.Slides'ın chart serileri ve kategorileri için kullandığı hafif bir bellek içi elektronik tablo gibidir.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Kod, mevcut hücreleri temizler ve yeni girişler için çalışma kitabını hazırlar.

### Özellik 5: chart'a kategori ekleme

#### Genel Bakış
Funnel'ın sol tarafında görünen metin etiketlerini tanımlayın—bunlar sürecinizin her aşamasını temsil eder.

`chart.getChartData().getCategories().add()` belirli bir çalışma kitabı hücresine bağlı yeni bir kategori nesnesi oluşturur.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Burada üç aşama ekliyoruz: “Prospects”, “Qualified Leads” ve “Closed Deals”.

### Özellik 6: chart'a veri serisi ekleme

#### Genel Bakış
Funnel'ı sayısal değerlerle doldurun ve isteğe bağlı olarak her dilime benzersiz bir renk atayın.

`IDataPoint`, bir chart serisi içindeki tek bir veri noktasını temsil eder.  

`chart.getChartData().getSeries().add()` sayısal veri noktalarını tutan bir seri oluşturur; her `IDataPoint` kendi doldurma rengine sahip olabilir.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Döngü, her nokta için katı doldurma ayarlamayı gösterir; marka‑özel `java.awt.Color` sabitleri ya da görsel çeşitlilik için rastgele renkler kullanılabilir.

## Yaygın kullanım durumları ve ipuçları

- **Satış hunisi raporlaması** – Her aşamada kaç lead'in prospect'tan kapalı‑kazanç'a geçtiğini gösterin.  
- **Süreç verimliliği analizi** – Üretim adımları arasındaki malzeme kaybını veya zaman gecikmelerini görselleştirin.  
- **Pazarlama hunisi incelemesi** – Kampanyalar veya trafik kaynakları arasındaki dönüşüm oranlarını karşılaştırın.  

**Pro ipucu:** Rastgele renkler yerine şirketinizin marka paletini (ör. `new Color(0, 112, 192)`) kullanarak sunumu diğer pazarlama varlıklarıyla tutarlı tutun.

## Sıkça Sorulan Sorular

**S: Funnel chart yönünü nasıl değiştiririm?**  
C: `IChart` nesnesindeki `ChartOrientation` özelliğini `ChartOrientation.Vertical` veya `ChartOrientation.Horizontal` olarak ayarlayın.

**S: Chart'ı ekledikten sonra slaytı resim olarak dışa aktarabilir miyim?**  
C: Evet—`pres.getSlides().get_Item(0).getThumbnail(1, 1)` çağrısı ile elde edilen `java.awt.image.BufferedImage`'ı PNG veya JPEG dosyasına yazabilirsiniz.

**S: Üçten fazla kategori eklemem gerekirse?**  
C: `chart.getChartData().getCategories().add(...)` ile ek kategori ekleyin ve her yeni kategori için eşleşen veri noktalarını sağlayın.

**S: Legend (gösterge) gizlenebilir mi?**  
C: `chart.getChartTitle().setVisible(false)` ve `chart.getLegend().setVisible(false)` kullanarak başlık ve göstergeyi kaldırabilirsiniz.

**S: Geliştirme sürümleri için lisans gerekli mi?**  
C: Değerlendirme için geçici bir lisans yeterlidir; üretim dağıtımları için tam ticari lisans gereklidir.

---

**Son güncelleme:** 2026-09-02  
**Test edilen sürüm:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java ile PowerPoint Chart Verilerini Düzenleme: Kapsamlı Kılavuz](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java ile PowerPoint chart'ına animasyon ekleme – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}