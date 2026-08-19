---
date: '2026-07-08'
description: Aspose kullanarak Java ile PowerPoint'te bir doughnut chart oluşturmayı
  öğrenin. Bu adım adım kılavuz, chart data points programlı olarak eklemeyi, labels
  özelleştirmeyi ve PPTX'i high fidelity ile kaydetmeyi gösterir.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Aspose kullanarak Java ile PowerPoint'te bir doughnut chart oluşturabilirsiniz.
  Bu öğreticiyi izleyerek data points ekleyin, labels özelleştirin ve PPTX'i high
  fidelity ile kaydedin.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Aspose Kullanımı: PowerPoint''te (Java) Doughnut Chart Oluşturma'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Aspose ile PowerPoint'te (Java) Doughnut Chart Oluşturma
url: /tr/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint'te Aspose ile Halka Grafik Oluşturma Nasıl Kullanılır (Java)

## Giriş
İkna edici sunumlar oluşturmak genellikle sadece metin ve görsellerden daha fazlasını gerektirir; grafikler, verileri etkili bir şekilde görselleştirerek hikâye anlatımını önemli ölçüde artırabilir. **Aspose nasıl kullanılır** grafik oluşturma, PowerPoint'i hiç açmadan programatik kontrol sağlar. Bu öğreticide, bir halka grafik oluşturmayı, veri noktalarını yapılandırmayı ve yüksek kaliteli bir PPTX kaydetmeyi adım adım gösteriyoruz. Sadece temel Java bilgisine ve birkaç dakikalık kurulum süresine ihtiyacınız olacak.

`Aspose.Slides for Java` Microsoft Office olmadan PowerPoint dosyalarının oluşturulmasını, manipüle edilmesini ve dönüştürülmesini sağlayan bir Java kütüphanesidir.

## Hızlı Yanıtlar
- **PowerPoint'te halka grafik oluşturan kütüphane nedir?** Aspose.Slides for Java  
- **Grafik veri noktalarını programlı olarak ekleyebilir miyim?** Evet, grafik API'si kullanılarak  
- **Üretim için lisansa ihtiyacım var mı?** Geçerli bir Aspose.Slides lisansı gereklidir  
- **Hangi Java sürümleri destekleniyor?** Java 8 ve üzeri (JDK 16 sınıflandırıcısı gösterilmiştir)  
- **Kaç seriyi ekleyebilirim?** Örnek, en fazla 15 seri ekliyor, ancak ihtiyacınıza göre ayarlayabilirsiniz  

## PowerPoint'te halka grafik nedir?
A halka grafik, bir pasta grafik benzeri dairesel bir grafiktir ancak ortası boştur, bu sayede birden fazla seri aynı anda gösterilebilir. Parça‑bütün ilişkilerini vurgular ve görsel düzeni kompakt ve okunması kolay tutar.

## Neden Aspose.Slides for Java ile halka grafikler oluşturmalısınız?
Aspose.Slides for Java, 50'den fazla giriş ve çıkış formatını destekler ve tüm dosyayı belleğe yüklemeden 500 MB'a kadar sunumlar oluşturabilir. Herhangi bir Java platformunda grafik görünümü, veri ve düzen üzerinde tam programatik kontrol sağlar, COM etkileşimini ortadan kaldırır ve tipik bir sunucuda 100 grafik‑zengin slaytı iki saniyeden kısa sürede işleyebilir.

## Önkoşullar
- Java programlama temelleri.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Bağımlılık yönetimi için Maven veya Gradle.  
- Geçerli bir Aspose.Slides for Java lisansı (ücretsiz deneme mevcuttur).

## Aspose.Slides for Java Kurulumu
Projenize uygun bağımlılık yöneticisini seçin.

**Maven**  
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin (sürümü en son sürümle değiştirin):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle` dosyanıza şu satırı ekleyin:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Doğrudan indirmeyi tercih ediyorsanız, [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) sayfasını ziyaret edin.

### Lisans Alımı
Aspose.Slides özelliklerini keşfetmek için ücretsiz deneme ile başlayabilirsiniz. Uzun vadeli kullanım için bir lisans satın alın veya [Aspose'un web sitesinden](https://purchase.aspose.com/temporary-license/) geçici bir lisans talep edin. Ortamınızı kurmak ve uygulamanızda Aspose.Slides'i başlatmak için verilen talimatları izleyin.

## Aspose.Slides for Java ile PowerPoint'te halka grafik nasıl oluşturulur
Bir halka grafik oluşturmak için, önce bir `Presentation` yükleyin veya oluşturun, `ChartType.Doughnut` tipinde bir grafik şekli ekleyin, varsayılan serileri temizleyin, delik boyutunu ayarlayın ve ardından grafiğin çalışma kitabını kategori adları ve sayısal değerlerle doldurun. Son olarak, etiket biçimlendirmesini ayarlayın ve PPTX'i kaydedin.

### Adım 1: Sunumu Başlatma
Yeni bir sunum oluşturun veya mevcut bir dosyayı açarak slayt koleksiyonunu elde edin.

`Presentation`, bir PowerPoint dosyasını temsil eden temel sınıftır.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Adım 2: Slayta halka grafik ekleme
Bir grafik şekli ekleyin, varsayılan serileri/kategorileri kaldırın ve halka delik boyutu gibi temel görsel ayarları yapılandırın.

`Chart` (veya grafik şekli), bir slayta yerleştirilen grafik nesnesini temsil eder.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Adım 3: Grafik veri noktalarını ekleme ve etiketleri özelleştirme
Kategori adlarını doldurun, her seri için veri noktalarını ekleyin ve etiket biçimlendirmesini (yazı tipi, renk, konum) ince ayar yapın. Bu adım, “grafik veri noktalarını ekleme” yeteneğini gösterir.

`Workbook`, hücrelerin doldurulduğu grafiğin altında yatan elektronik tablo verilerine erişim sağlar.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Adım 4: Güncellenen sunumu kaydetme
Değişiklikleri diskte yeni bir PPTX dosyasına kaydedin.

`save`, sunumu seçilen formatta bir dosyaya yazar.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Pratik Uygulamalar
- **Finansal Raporlar:** bütçe tahsislerini veya harcama dağılımlarını görselleştirme.  
- **Pazar Analizi:** rakipler arasındaki pazar payı dağılımını gösterme.  
- **Anket Sonuçları:** kategorik anket verilerini kompakt bir biçimde sunma.  
- **Gösterge Tablosu Oluşturma:** veritabanı sorgularıyla birleştirerek canlı güncellenen slaytlar üretme.

## Performans Hususları
- **Kaynakları serbest bırak:** Kaydetme sonrası yerel belleği boşaltmak için `pres.dispose()` çağırın.  
- **Grafik sayısını sınırlayın:** Yüzlerce grafik eklemek bellek kullanımını artırabilir; gerekirse toplu işleyin.  
- **Akış kullanın:** Büyük veri setleri için, çalışma kitabını bellek içi diziler yerine doğrudan akışlardan doldurun.  

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **Grafik boş görünüyor** | Veri hücreleri doğru şekilde doldurulmamış | `workBook.getCell(...)`'in doğru satır/sütun indekslerine başvurduğunu doğrulayın. |
| **Etiketler üst üste geliyor** | Sınırlı alanda çok fazla kategori | `DoughnutHoleSize` değerini artırın veya `FirstSliceAngle`'ı ayarlayın. |
| **OutOfMemoryError** | Kaynakları serbest bırakmadan büyük sunumlar | Kaydetme sonrası `pres.dispose()` çağırın ve JVM yığın boyutunu artırmayı düşünün. |

## Sıkça Sorulan Sorular

**Q:** Aspose.Slides for Java'u ticari uygulamalarda kullanabilir miyim?  
**A:** Evet, ancak geçerli bir ticari lisansa ihtiyacınız var. Değerlendirme için ücretsiz bir deneme mevcuttur.

**Q:** 15'ten fazla seri nasıl eklenir?  
**A:** “Add Doughnut Chart” adımındaki döngü limitini artırın ve veri çalışma kitabınızın yeterli satır içerdiğinden emin olun.

**Q:** Oluşturulduktan sonra halka delik boyutu değiştirilebilir mi?  
**A:** Evet, kaydetmeden önce `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` metodunu çağırın.

**Q:** Grafiği PPTX yerine bir görüntü olarak dışa aktarabilir miyim?  
**A:** Kesinlikle. `chart.getImage()` metodunu kullanın ve dönen `java.awt.image.BufferedImage`'ı istediğiniz formatta kaydedin.

**Q:** Aspose.Slides animasyonlu grafikleri destekliyor mu?  
**A:** Animasyon, `ISlide.getTimeline()` API'si aracılığıyla eklenebilir, ancak bu öğreticinin kapsamı dışındadır.

## Sonuç
Artık Aspose.Slides for Java ile **PowerPoint'te halka grafik** dosyaları oluşturmak için eksiksiz, üretim‑hazır bir yönteme sahipsiniz; **grafik veri noktalarını ekleme**, etiketleri özelleştirme ve performans hususlarını yönetme konularını da içerir. Sunumlarınızı gerçekten öne çıkarmak için farklı renkler, veri kaynakları ve grafik tipleriyle denemeler yapın.

---

**Son Güncelleme:** 2026-07-08  
**Test Edilen:** Aspose.Slides for Java 25.4 (JDK 16 sınıflandırıcısı)  
**Yazar:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## İlgili Öğreticiler

- [Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java ile PowerPoint Grafik Verilerini Düzenleme: Kapsamlı Kılavuz](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java ile PowerPoint Grafiklerini Animasyonlu Hale Getirme – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}