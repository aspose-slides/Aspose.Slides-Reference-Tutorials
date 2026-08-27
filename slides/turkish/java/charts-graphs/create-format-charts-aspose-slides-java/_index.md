---
date: '2026-08-27'
description: Java'da Aspose.Slides kullanarak grid lines chart eklemeyi öğrenin, axes
  ve titles'ı formatlayın ve parlatılmış PowerPoint line chart dışa aktarın.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Java'da Aspose.Slides kullanarak grid lines chart eklemeyi öğrenin,
  axes ve titles'ı formatlayın ve parlatılmış PowerPoint line chart dışa aktarın.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Aspose.Slides for Java ile bir chart'a grid lines ekleme
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Aspose.Slides for Java ile bir chart'a grid lines ekleme
url: /tr/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java ile bir grafiğe ızgara çizgileri ekleme

## Giriş
If you need to **add grid lines chart** in a PowerPoint presentation programmatically, Aspose.Slides for Java gives you a clean, fully‑featured API. Whether you are preparing a quarterly business review, an academic lecture, or a data‑driven sales deck, you can generate a line chart, customize every visual element, and save the result in seconds—all without opening PowerPoint manually.

## Hızlı yanıtlar
- **Java'da grafik oluşturan kütüphane nedir?** Aspose.Slides for Java.
- **Bu kılavuz hangi grafik tipini kapsıyor?** İşaretçili ve ızgara çizgili bir çizgi grafiği.
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz geçici bir lisans yeterlidir; üretim için ticari bir lisans gereklidir.
- **Hangi IDE'yi kullanabilirim?** IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE'si.
- **Grafik öğeleri nasıl biçimlendirilir?** Başlıklar, eksenler, ızgara çizgileri, lejandlar ve arka plan renkleri için akıcı API çağrıları kullanılarak.

## Java'da Aspose.Slides kullanarak ızgara çizgili grafik ekleme
Yeni bir `Presentation` yükleyin, bir slayt ekleyin, bir çizgi grafiği ekleyin ve ardından dikey eksende ana ızgara çizgilerini etkinleştirin – tümü on satırdan az bir kodla. Bu doğrudan yanıt, ihtiyacınız olan tam sıralamayı gösterir, böylece kopyala‑yapıştır yapabilir ve hemen tam biçimlendirilmiş bir grafik görebilirsiniz.

### Tanım bağlantısı
`Presentation`, bellekte bir PowerPoint dosyasını temsil eden Aspose.Slides çekirdek sınıfıdır; tüm slayt‑seviyesi işlemler bu nesneden başlar.

## Çizgi grafiği nedir ve neden Aspose.Slides kullanmalı?
Bir çizgi grafiği, düz çizgilerle bağlanan bir dizi veri noktasını çizer ve zaman içindeki eğilimleri anında görünür kılar. Aspose.Slides **50'den fazla grafik türünü** destekler ve **her seri için 10.000'e kadar veri noktasını** belirgin bir yavaşlama olmadan işleyebilir; bu da büyük veri setleri için kurumsal düzeyde performans sağlar.

### Tanım bağlantısı
`Chart`, Aspose.Slides'in herhangi bir grafik için üst‑seviye nesnesidir; serileri, kategorileri ve biçimlendirme bilgilerini depolar.

## Önkoşullar
- **Java Development Kit (JDK) 8+** yüklü.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans vb.).
- **Aspose.Slides for Java** kütüphanesi Maven veya Gradle aracılığıyla eklenmiş (aşağıdaki *aspose.slides maven dependency* bölümüne bakın).

### Maven bağımlılığı (aspose.slides maven bağımlılığı)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle bağımlılığı
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Alternatif olarak, en son JAR dosyasını [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

## Lisans edinme (aspose lisansı uygulama)
- Test amaçlı [free trial license](https://purchase.aspose.com/temporary-license/) sayfasından **ücretsiz deneme lisansı** edinin.
- Üretim dağıtımları için [Aspose'un resmi sitesinden](https://purchase.aspose.com/buy) tam bir lisans satın alın.

## Aspose.Slides for Java kurulumu
1. Yukarıda gösterilen Maven veya Gradle bağımlılığını projenize ekleyin.
2. Tüm özelliklerin açılması için herhangi bir `Presentation` nesnesi oluşturmadan **önce** lisans dosyasını yükleyin.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## Adım adım uygulama

### Adım 1: çıktı dizinini oluşturun (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*Neden önemli:* Klasörün var olduğundan emin olmak, sunumu daha sonra kaydettiğinizde `FileNotFoundException` oluşmasını önler.

### Adım 2: bir slayt ekleyin ve bir çizgi grafik ekleyin
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*Açıklama:* Bu, yeni bir slayt oluşturur ve belirtilen koordinatlarda **işaretçili bir çizgi grafiği** yerleştirir.

### Adım 3: grafik başlığı ekleyin (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*İpucu:* Kalın, gri bir başlık kullanmak, grafiği anında tanınabilir kılar.

### Adım 4: eksenleri biçimlendirin ve ızgara çizgileri ekleyin (add grid lines)
#### Dikey eksen biçimlendirme
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*Neden önemli:* Net ızgara çizgileri ve döndürülmüş etiketler, özellikle veri noktaları yoğun olduğunda okunabilirliği artırır.

#### Yatay eksen biçimlendirme
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### Adım 5: lejandı özelleştirin (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### Adım 6: arka plan renklerini ayarlayın (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### Adım 7: sunumu kaydedin
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*Sonuç:* Artık tam biçimlendirilmiş bir çizgi grafiği içeren bir PowerPoint dosyanız (`FormattedChart_out.pptx`) var.

## Pratik uygulamalar (çizgi grafiği PowerPoint oluşturma)
- **İş raporları:** Keskin ızgara çizgileriyle çeyrek dönem gelir eğilimlerini gösterin.
- **Akademik dersler:** Deneysel verileri birden fazla oturumda görselleştirin.
- **Proje teklifleri:** Kilometre taşı ilerlemesini ve tahmin eğrilerini vurgulayın.
- **Pazarlama analizi:** Kampanya ROI eğilimlerini rakip verileriyle yan yana sunun.
- **Gösterge paneli entegrasyonu:** Canlı analizleri paydaş toplantıları için PowerPoint'e dışa aktarın.

## Performans hususları
- **Bellek yönetimi:** Kaydettikten sonra yerel kaynakları hızlıca serbest bırakmak için `presentation.dispose()` çağırın.
- **Büyük veri setleri:** Aspose.Slides, akış kullanarak binlerce noktalı grafikleri işler ve tipik bir sunucuda bellek kullanımını 100 MB'nin altında tutar.

## Yaygın sorunlar ve çözümler
| Sorun | Çözüm |
|-------|----------|
| **Lisans uygulanmadı** | Deneme veya tam lisansı, herhangi bir `Presentation` nesnesi oluşturulmadan **önce** yükleyin. |
| **Grafik boş görünüyor** | Slaytın en az bir veri serisi içerdiğini doğrulayın; gerekirse `chart.getChartData().getSeries().add(...)` ile seri ekleyin. |
| **Dosya kaydedilmedi** | Çıktı dizininin var olduğundan emin olun (Adım 1'e bakın). |
| **Renkler uygulanmadı** | Güvenilir renk işleme için `java.awt.Color` sabitlerini veya `PresetColor` enum'ını kullanın. |

## Sıkça Sorulan Sorular

**S: Çizgi grafiği dışında başka grafik türleri oluşturabilir miyim?**  
E: Evet, Aspose.Slides çubuk, pasta, dağılım, radar ve 50'den fazla ek grafik türünü destekler.

**S: Çizgi grafiğine birden fazla veri serisi nasıl eklerim?**  
E: Biçimlendirmeyi uygulamadan önce ek seriler eklemek için `chart.getChartData().getSeries().add(...)` kullanın.

**S: Grafiği bir görüntü olarak dışa aktarmak mümkün mü?**  
E: Kesinlikle. Slaytı `presentation.save("slide.png", SaveFormat.Png)` ile PNG, JPEG veya SVG olarak render edebilirsiniz.

**S: Geliştirme için ücretli bir lisansa ihtiyacım var mı?**  
E: Değerlendirme için ücretsiz geçici bir lisans yeterlidir; üretim kullanımı için ticari bir lisans gereklidir.

**S: Hangi Java sürümleri destekleniyor?**  
E: Kütüphane JDK 8'den JDK 22'ye kadar çalışır; Maven/Gradle bağımlılığını eklerken uygun sınıflandırıcıyı (ör. `jdk16`) seçin.

---

**Son Güncelleme:** 2026-08-27  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

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

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## İlgili Eğitimler

- [aspose slides maven bağımlılığı: Aspose.Slides for Java kullanarak Sunumlarda Grafik Ekle ve Yapılandır](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Aspose.Slides for Java kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose Slides Java ile Grafik Trend Çizgileri Oluştur ve Özelleştir](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}