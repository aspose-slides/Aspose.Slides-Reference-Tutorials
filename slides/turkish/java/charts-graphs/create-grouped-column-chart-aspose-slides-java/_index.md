---
date: '2026-09-17'
description: Aspose.Slides for Java kullanarak clustered column chart'ı bir PowerPoint
  sunumuna eklemeyi, PowerPoint grafiğini özelleştirmeyi ve data series chart eklemeyi
  öğrenin.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Aspose.Slides for Java kullanarak bir PowerPoint sunumuna clustered
  column chart eklemeyi, data series ekleme, grouping özelleştirme ve dosyayı PPTX
  olarak kaydetme adımlarını öğrenin.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Aspose.Slides kullanarak PowerPoint'e clustered column chart ekleme
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: PowerPoint'e clustered column chart eklemek için Aspose.Slides for Java kullanımı
url: /tr/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Aspose.Slides for Java kullanarak gruplanmış sütun grafiği ekleme

## Giriş

PowerPoint sunumuna **gruplanmış sütun grafiği** eklemeniz gerektiğinde, net bir görsel ham sayıları anında anlaşılır bir hikayeye dönüştürebilir. Bunu PowerPoint'te manuel olarak yapmak zaman alıcı olabilir, özellikle birçok slaytı programlı olarak oluşturmanız gerektiğinde. **Aspose.Slides for Java** bu zorluğu ortadan kaldırır – sadece birkaç satır kodla PowerPoint grafiği oluşturmanıza, özelleştirmenize ve veri serisi grafiği eklemenize olanak tanır.

Bu öğreticide şunları öğreneceksiniz:
- Aspose.Slides for Java ile yeni bir PowerPoint sunumu başlatma.  
- **Add chart to slide** ve onu gruplanmış sütun grafiği olarak yapılandırma.  
- **Create grouped column chart** ile kategoriler için gruplama seviyeleri tanımlayarak gruplanmış sütun grafiği oluşturma.  
- **Insert data series chart** so your data is displayed correctly.  
- Tamamlanmış sunumu PPTX dosyası olarak kaydetme.

## Hızlı cevaplar
- **Ana sınıf nedir?** `Presentation` from `com.aspose.slides`.  
- **Hangi grafik türü kullanılıyor?** `ChartType.ClusteredColumn`.  
- **Test için lisansa ihtiyacım var mı?** Ücretsiz deneme çalışır, ancak lisans değerlendirme sınırlamalarını kaldırır.  
- **Hangi Java sürümü destekleniyor?** JDK 16 veya daha yenisi (örnek JDK 16 kullanıyor).  
- **Örneği nasıl çalıştırırım?** Maven/Gradle bağımlılığını ekleyin, derleyin ve `main` metodunu çalıştırın.

## “Gruplanmış sütun grafiği ekleme” nedir?
Gruplanmış bir sütun grafiği, her kategori için birden fazla veri serisini yan yana gösterir ve gruplar arasındaki değerleri tek bir görselde karşılaştırmanıza olanak tanır. Çeyrek satışları, anket sonuçları veya aynı kategori içinde birden fazla veri setini karşılaştırmanız gereken herhangi bir senaryo için idealdir.

## Gruplanmış sütun grafiği eklemek için Aspose.Slides neden kullanılmalı?
Otuzlarca slaytı otomatik olarak oluşturabilir, her görsel öğeyi özelleştirebilir ve kodu Java destekleyen herhangi bir işletim sisteminde çalıştırabilirsiniz—Microsoft Office kurulumu gerekmez. Aspose.Slides **50+ grafik türünü** destekler ve **500 slayta kadar** sunumları tüm dosyayı belleğe yüklemeden işleyebilir, bu da büyük ölçekli raporlama hatları için uygundur.

## Önkoşullar
- **Aspose.Slides for Java** kütüphanesi (en son sürüm önerilir).  
- JDK 16 veya üzeri.  
- Maven veya Gradle yapı aracı (veya JAR'ı manuel ekleyebilirsiniz).  
- Java kodunu çalıştırmak için bir IDE veya metin düzenleyici.

## Aspose.Slides for Java kurulumu
Projeye aşağıdaki yapı betiklerinden birini kullanarak kütüphaneyi ekleyin.

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

Alternatif olarak, en son sürümü doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisans edinme
Üretime dağıtmadan önce bir lisans edinin:
- **Free trial** – satın alma yapmadan tüm özellikleri keşfedin.  
- **Temporary license** – kısa bir süre için genişletilmiş yetenekleri değerlendirin.  
- **Full license** – sınırsız kullanımın kilidini açın. [Aspose's purchase page](https://purchase.aspose.com/buy) adresinden edinin.

## Aspose.Slides for Java kullanarak PowerPoint'te gruplanmış sütun grafiği nasıl eklenir?
Yeni bir `Presentation` yükleyin, bir slayt ekleyin, `ChartType.ClusteredColumn` türünde bir `Chart` ekleyin, iç çalışma kitabını kategoriler ve serilerle doldurun ve ardından dosyayı PPTX olarak kaydedin. Bu sıralama, sadece birkaç API çağrısıyla tam işlevsel bir gruplanmış sütun grafiği oluşturur.

### Sunumu başlatma
`Presentation`, bellekte bir PowerPoint dosyasını temsil eden sınıftır ve programlı olarak slayt, şekil ve grafik eklemenize olanak tanır.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Slayta grafik ekleme
`ChartType.ClusteredColumn`, Aspose.Slides'a bir gruplanmış sütun grafiği oluşturmasını söyler.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Grafik veri çalışma kitabını hazırlama
Grafik verilerini dahili bir çalışma kitabında saklar. Temizlemek, özel veri için temiz bir sayfa sağlar.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Gruplama seviyeleriyle kategoriler ekleme
Kategorileri gruplamak, gruplanmış sütun grafiği etkisini oluşturur. Her kategori, eksen etiketlerinde görünen mantıksal bir gruba ait olabilir.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Grafik'e veri serileri ekleme
`Series` nesneleri grafikteki tek tek sütunları temsil eder. Birden fazla seri eklemek, her kategori için yan yana sütunlar oluşturur.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Grafik ile sunumu kaydetme
`Presentation` kaydedildiğinde, herhangi bir PowerPoint görüntüleyicide açılabilen standart bir PPTX dosyası oluşturulur.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Pratik uygulamalar
- **Business reports** – bölgeler arasında çeyrek gelirleri karşılaştırma.  
- **Academic research** – test koşullarına göre gruplanmış deney sonuçlarını gösterme.  
- **Project management** – tek bir slaytta birden fazla ekip için görev tamamlama oranlarını görselleştirme.

## Performans değerlendirmeleri
- **Memory management** – kullanım sonrası büyük çalışma kitaplarını serbest bırakın.  
- **Batch operations** – sıkı döngüler içinde grafiği güncellemekten kaçının; önce verileri toplayın, ardından uygulayın.  
- **Built‑in optimizations** – Aspose.Slides, büyük dosyalar için `Presentation.optimize()` gibi yöntemler sunar, bellek kullanımını **%30** kadar azaltabilir.

## Yaygın tuzaklar ve ipuçları
- **Pitfall:** Mevcut serileri/kategorileri temizlemeyi unutmak, yinelenen verilere yol açabilir.  
  **Tip:** Yeni verileri doldurmadan önce her zaman `clear()` çağırın.  
- **Pitfall:** Yanlış hücre adresi kullanmak (ör. `"c2"` yerine `"C2"`).  
  **Tip:** Hücre referansları büyük/küçük harfe duyarsızdır, ancak okunabilirlik için tutarlı tutun.  
- **Tip:** Anlamlı grup etiketleri oluşturmak için `setGroupingItem` kullanın; bunlar otomatik olarak grafik açıklamasında görünür.

## Sıkça sorulan sorular

**S1: Grafiğime birden fazla seri nasıl ekleyebilirim?**  
C1: `ch.getChartData().getSeries().add()` metodunu tekrar tekrar çağırın, her seri için benzersiz bir ad ve veri noktaları sağlayın.

**S2: Aspose.Slides grafiklerinde yaygın sorunlar nelerdir?**  
C2: Sorunlar genellikle uyumsuz veri aralıkları veya eksik çalışma kitabı hücrelerinden kaynaklanır. Her kategori ve veri noktasının karşılık gelen bir hücresi olduğundan emin olun.

**S3: Aspose.Slides'ı diğer programlama dilleriyle kullanabilir miyim?**  
C3: Evet, Aspose .NET, C++, Python ve daha fazlası için eşdeğer kütüphaneler sunar.

**S4: Mevcut bir grafiği sunumda nasıl güncellerim?**  
C4: Sunumu yükleyin, `slide.getShapes().get_Item(index)` ile grafiği bulun, ardından gerektiği gibi serilerini veya biçimlendirmesini değiştirin.

**S5: Aspose.Slides'ta grafik türleriyle ilgili sınırlamalar var mı?**  
C5: Kütüphane **50'den fazla grafik türünü** destekler ve sürekli yeni türler ekler; en güncel liste için her zaman en son belgeleri kontrol edin.

## Kaynaklar
- **Dokümantasyon:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **İndirme:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Satın Alma:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Ücretsiz deneme:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Geçici lisans:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Destek forumu:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-09-17  
**Test Edilen:** Aspose.Slides for Java 25.4 (JDK 16)  
**Yazar:** Aspose

## İlgili Öğreticiler
- [Java'da Aspose.Slides ile Grafik Oluşturma Kılavuzu](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Aspose.Slides for Java Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java ile PowerPoint grafiğine animasyon ekleme – Adım Adım Kılavuz](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}