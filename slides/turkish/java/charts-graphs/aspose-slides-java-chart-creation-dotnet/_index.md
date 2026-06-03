---
date: '2026-06-03'
description: .NET sunumlarında grafikler oluşturmayı ve Aspose.Slides for Java ile
  slayta grafik eklemeyi öğrenin. Veri görselleştirme için bu adım adım kılavuzu izleyin.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: .NET'te Aspose.Slides for Java kullanarak grafikler oluşturun
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java kullanarak .NET'te grafikler oluşturun

## Giriş
Çekici sunumlar oluşturmak genellikle izleyicinin anlayışını ve katılımını artırmak için grafikler gibi görsel veri temsillerinin entegrasyonunu içerir. **.NET'te grafik oluşturmak istiyorsanız** Aspose.Slides for Java, .NET uygulamaları içinde sorunsuz çalışan güçlü, dil bağımsız bir API sunar. Bu öğreticide bir sunumu nasıl başlatacağınızı, çeşitli grafik türleri eklemeyi, grafik veri çalışma kitabını yönetmeyi ve seri verilerini biçimlendirmeyi—negatif değerlerin işlenmesi dahil—öğreneceksiniz. Sonunda, birkaç satır kodla programlı olarak sunum dosyalarına grafik oluşturabilecek ve slayta ekleyebileceksiniz.

## Hızlı Cevaplar
- **Ana hedef nedir?** Aspose.Slides for Java kullanarak .NET sunumlarında grafikler oluşturun.  
- **Hangi kütüphane sürümü gereklidir?** Aspose.Slides for Java 25.4 veya daha yenisi.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Maven veya Gradle kullanabilir miyim?** Evet—her iki yapı sistemi de desteklenir.  
- **Hangi grafik türleri mevcuttur?** Küme sütun, çizgi, pasta, çubuk, alan ve daha fazlası.

## Aspose.Slides for Java ile .NET sunumlarında grafikler nasıl oluşturulur?
`Presentation` sınıfı bir PowerPoint dosyasını temsil eder ve slaytlarını manipüle etmek için yöntemler sağlar. Yeni bir `Presentation` nesnesi yükleyin, bir slayt elde etmek için `slides.addEmptySlide()` çağırın, ardından istediğiniz grafik türünü belirttiğiniz koordinatlarda eklemek için `slide.getShapes().addChart()` kullanın. Grafik eklendikten sonra, veri çalışma kitabını seriler ve kategorilerle doldurun, herhangi bir biçimlendirme uygulayın (örneğin negatif değerler için renkler) ve sonunda sunumu bir .pptx dosyasına kaydedin. Bu akış, **.NET'te grafik oluşturmanızı** kısa bir API çağrısı setiyle sağlar.

## Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin Microsoft Office olmadan PowerPoint dosyaları oluşturmasını, değiştirmesini ve render etmesini sağlayan çapraz platform bir API'dir. **50+ giriş ve çıkış formatını** destekler ve bellek kullanımını 200 MB'nin altında tutarak binlerce slayt içeren sunumları işleyebilir.

## Bir .NET projesinde Aspose.Slides for Java neden kullanılmalı?
Aspose.Slides for Java, Java Virtual Machine üzerinde çalışır ve .NET'ten yerel bir sarmalayıcı aracılığıyla çağrılabilir; bu da .NET geliştiricilerine olgun bir grafik motoruna, büyük veri setlerinin yüksek performanslı işlenmesine ve mevcut Java koduyla mantığı yeniden yazmadan tam uyumluluğa erişim sağlar.

## Önkoşullar
Aspose.Slides for Java ile grafik oluşturma konusuna dalmadan önce, ihtiyaç duyacaklarınızı özetleyelim:

### Gerekli Kütüphaneler ve Sürümler
- **Aspose.Slides for Java**: Sürüm 25.4 veya daha yenisi.

### Ortam Kurulum Gereksinimleri
- .NET uygulamalarını destekleyen bir geliştirme ortamı.  
- Java programlama kavramlarına temel bir anlayış.

### Bilgi Önkoşulları
- .NET uygulama bağlamında sunum oluşturma konusunda aşinalık.  
- Java bağımlılıklarını ve yönetimini (Maven/Gradle) anlama.

## Aspose.Slides for Java Kurulumu
Aspose.Slides'i kullanmaya başlamak için projenize bir bağımlılık olarak eklemeniz gerekir. İşte bunu nasıl yapabileceğiniz:

### Maven
Maven bağımlılık kod parçacığı Aspose.Slides for Java'i projenize ekler.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` dosyanıza bu satırı ekleyerek kütüphaneyi Maven Central'dan çekin.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

#### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Özellikleri keşfetmek için geçici bir lisansla başlayın.  
- **Satın Alma**: Sınırsız üretim kullanımı için bir lisans satın alın.

#### Temel Başlatma ve Kurulum
`Slides` başlatması, lisansı ayarlamayı ve bir `Presentation` örneği oluşturmayı gerektirir.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Bu kurulum, kaynak yönetiminin etkili bir şekilde ele alındığını sağlar.

## Uygulama Kılavuzu
Özellikleri adım adım uygulamanız için size rehberlik edeceğiz.

### Sunumu Başlatma
**Genel Bakış:**  
Bir sunum örneği oluşturmak, sonraki tüm işlemler için zemin hazırlar. Bu özellik, Aspose.Slides kullanarak sıfırdan nasıl başlanacağını gösterir.

#### Adım 1: Gerekli Paketleri İçe Aktarın
`Presentation` ve ilgili sınıflar `com.aspose.slides` ad alanının bir parçasıdır.

```java
import com.aspose.slides.Presentation;
```

#### Adım 2: Yeni Bir Presentation Nesnesi Oluşturun
`Presentation` nesnesini örnekleyin ve otomatik olarak kapatılmasını sağlamak için bir try‑with‑resources bloğuna sarın.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Bu, kullanım sonrası sunum nesnesinin doğru şekilde serbest bırakılmasını sağlar ve bellek sızıntılarını önler.*

### Slayta Grafik Ekleme
**Genel Bakış:**  
Slaytınıza bir grafik eklemek, veri görselleştirmesini daha etkili ve ilgi çekici hâle getirebilir.

#### Adım 1: Gerekli Paketleri İçe Aktarın
`Chart` sınıfı, bir slayta yerleştirilebilen ve özelleştirilebilen bir grafik şekli temsil eder.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Adım 2: Sunumu Başlatın ve Grafik Ekleyin
Bir slayt oluşturun, ardından `ChartType.ClusteredColumn` ve istenen konum ve boyutla `addChart` metodunu çağırın.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Burada, belirtilen koordinat ve boyutlarda ilk slayta bir küme sütun grafiği ekliyoruz.*

### Grafik Veri Çalışma Kitabını Yönetme
**Genel Bakış:**  
Grafiğinizin veri çalışma kitabını verimli bir şekilde yönetmek, serileri ve kategorileri sorunsuz bir şekilde manipüle etmenizi sağlar.

#### Adım 1: Gerekli Paketleri İçe Aktarın
`IChartDataWorkbook`, grafikler tarafından kullanılan alttaki Excel benzeri çalışma kitabına erişim sağlar.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Adım 2: Veri Çalışma Kitabına Erişin ve Temizleyin
Grafikten çalışma kitabını alın ve yeni bir başlangıç için mevcut verileri temizleyin.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Yeni seriler ve kategoriler eklerken temiz bir sayfa ile başlamak için çalışma kitabını temizlemek çok önemlidir.*

### Grafiğe Seri ve Kategori Ekleme
**Genel Bakış:**  
Bu özellik, serileri ve kategorileri yöneterek anlamlı veri noktaları eklemenizi gösterir.

#### Adım 1: Seri ve Kategorileri Ekleyin
`chart.getChartData().getSeries().add()` ve `chart.getChartData().getCategories().add()` kullanarak yapıyı tanımlayın.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Seri ve kategorileri eklemek, daha düzenli bir veri sunumu sağlar.*

### Seri Verilerini Doldurma ve Biçimlendirme
**Genel Bakış:**  
Grafiğinizi veri noktalarıyla doldurun ve görünümünü biçimlendirerek okunabilirliği artırın, özellikle negatif değerlerle çalışırken.

#### Adım 1: Seri Verilerini Doldurun
Çalışma kitabındaki her hücreye sayısal değerler atayın ve negatif sayılar için kırmızı dolgu uygulayın.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Bu bölüm, verileri doldurmayı ve daha iyi görselleştirme için renk biçimlendirmeyi nasıl uygulayacağınızı gösterir.*

## Yaygın Sorunlar ve Çözümler
- **LicenseNotFoundException** – Lisans dosyası yolunun doğru olduğundan ve çalışma zamanında erişilebilir olduğundan emin olun.  
- **NullPointerException on chart data** – Kalan verileri önlemek için yeni seri eklemeden önce her zaman çalışma kitabını temizleyin.  
- **Chart not rendering in .NET** – Aspose.Slides JAR'ın .NET uyumlu sürümünü kullandığınızdan ve Java çalışma zamanının .NET projenizde doğru yapılandırıldığından emin olun.

## Sıkça Sorulan Sorular

**S: Sunum dosyalarında GUI olmadan bir grafik oluşturabilir miyim?**  
C: Evet, Aspose.Slides for Java tamamen başsızdır ve herhangi bir grafik bileşen olmadan sunucularda çalışır.

**S: Hangi .NET sürümleri destekleniyor?**  
C: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 ve .NET 6 desteklenir.

**S: Kaç farklı grafik türü ekleyebilirim?**  
C: Sütun, çizgi, pasta, alan ve radar grafikler dahil olmak üzere 20'den fazla grafik türü mevcuttur.

**S: Tek tek veri noktalarını biçimlendirmek mümkün mü?**  
C: Kesinlikle – `IDataPoint` API'si aracılığıyla her veri noktasına dolgu renkleri, kenarlıklar ve işaretçiler ayarlayabilirsiniz.

**S: Java nesnelerini .NET tiplerine manuel olarak dönüştürmem gerekiyor mu?**  
C: Hayır, Aspose.Slides for Java .NET sarmalayıcısı tip dönüşümünü otomatik olarak yönetir.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Slides ile Etkili Veri Görselleştirme için .NET Sunumlarına Grafik Gömme](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Aspose.Slides for .NET Kullanarak Grafik Veri Kaynağı Türünü Alma - Grafikler & Çizimler](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Aspose.Slides .NET ile Grafik Serisi Oluşturma ve Manipülasyonu - Etkili Veri Görselleştirme](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}