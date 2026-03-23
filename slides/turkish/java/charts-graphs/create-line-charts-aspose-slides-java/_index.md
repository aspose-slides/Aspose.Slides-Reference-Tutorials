---
date: '2026-03-23'
description: Aspose.Slides for Java'ı kullanarak işaretçili çizgi grafikler oluşturmayı,
  ikinci bir seri eklemeyi ve PowerPoint sunumlarında null verileri nasıl yöneteceğinizi
  öğrenin.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Aspose.Slides for Java Nasıl Kullanılır: Varsayılan İşaretçili Çizgi Grafikler
  Oluşturma'
url: /tr/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Varsayılan İşaretçilerle Çizgi Grafikler Oluşturma – Aspose.Slides for Java

## Giriş
Aspose kullanarak PowerPoint oluşturmayı otomatikleştirmenin **nasıl yapılacağını** merak ediyorsanız, doğru yerdesiniz. Bu öğreticide **işaretçili bir çizgi grafik** oluşturmayı, ikinci bir seri eklemeyi ve boş (null) verileri işlemeyi Aspose.Slides for Java ile adım adım göstereceğiz. Sonunda, PowerPoint’i manuel olarak açmadan profesyonel görünümlü bir grafik üreten, çalıştırmaya hazır bir kod parçacığınız olacak.

### Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (en son sürüm önerilir)  
- **İkinci bir seri ekleyebilir miyim?** Evet – API, birden fazla seriyi kolayca eklemenizi sağlar.  
- **Boş veri noktaları nasıl işlenir?** Hücre değerine `null` koyun; grafik noktayı atlayacaktır.  
- **Maven gerekli mi?** Maven veya Gradle çalışır; aşağıdaki *aspose slides maven* bölümüne bakın.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme yeterlidir; üretim için ticari lisans gerekir.

## Aspose.Slides for Java ile Çizgi Grafik Oluşturma
Grafikleri programatik olarak oluşturmak, saatlerce süren manuel biçimlendirmeyi ortadan kaldırır ve sunumlar arasında tutarlılık sağlar. **PowerPoint grafiği oluşturma** özelliğini bir raporlama aracına ekliyor ya da anında slayt desteleri üretiyor olun, Aspose.Slides Java kodundan tam kontrol sunar.

## Ön Koşullar
Başlamadan önce geliştirme ortamınızın hazır olduğundan emin olun:

1. **Kütüphaneler ve Bağımlılıklar**
   - Aspose.Slides for Java kütüphanesi (versiyon 25.4 önerilir) – bu, *aspose slides maven* senaryosunu kapsar.
   - Java Development Kit (JDK) sürüm 16 veya üzeri.
2. **Ortam Kurulumu**
   - Maven veya Gradle desteği olan bir IDE.
   - Kodu deneme süresi dışında çalıştıracaksanız geçerli bir Aspose lisans dosyası.
3. **Bilgi Gereksinimleri**
   - Temel Java programlama bilgisi.
   - Maven veya Gradle yapı dosyalarına aşinalık.

## Aspose.Slides for Java Kurulumu
### Maven
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
`build.gradle` dosyanıza şunu ekleyin:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Doğrudan İndirme
Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

**Lisans Edinme Adımları:**
- Ücretsiz deneme için [free trial page](https://releases.aspose.com/slides/java/) adresini ziyaret edin.
- Geçici bir lisans almak için [temporary license page](https://purchase.aspose.com/temporary-license/) adresine gidin.
- Tam lisans satın almak için [purchase portal](https://purchase.aspose.com/buy) adresini kullanın.

**Temel Başlatma:**
Aspose.Slides’ı Java uygulamanızda nasıl başlatacağınız aşağıda:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Şimdi grafik oluşturma konusuna geçelim!

## Uygulama Kılavuzu
### Özellik 1: Varsayılan İşaretçilerle Grafik Oluşturma
Bu bölüm, trend çizgisindeki bireysel veri noktalarını vurgulamak için ideal olan **işaretçili bir çizgi grafik** oluşturmayı gösterir.

#### Çizgi Grafik Ekleme
İşaretçili bir çizgi grafik eklemek için:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Serileri ve Kategorileri Temizleme
Temiz bir başlangıç yapmak için:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Özellik 2: Seri ve Kategori Ekleme
Seri ve kategori eklemek, grafiğinizi anlamlı verilerle doldurmak için kritiktir.

#### Yeni Bir Seri Oluşturma
"Series 1" adlı yeni bir seri eklemek için:
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Kategorileri ve Veri Noktalarını Doldurma
Kategorileri ve ilgili veri noktalarını eklemek için:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Özellik 3: İkinci Seri Ekleme ve Veri Noktalarını Doldurma
Ek seriler eklemek, görsel analizinizin derinliğini artırır.

#### İkinci Seriyi Oluşturma ve Doldurma
"Series 2" eklemek için:
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Özellik 4: Grafik Açıklamasını (Legend) Yapılandırma
Açıklamayı yapılandırmak, özellikle **ikinci seri eklediğinizde** grafik okunabilirliğini artırır.

#### Açıklama Ayarlarını Düzenleme
Yapılandırmak için:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Özellik 5: Sunumu Kaydetme
Grafiğiniz hazır olduğunda, **PowerPoint grafiği oluşturma** dosyalarını paylaşabilir veya daha sonra düzenleyebilirsiniz.

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Pratik Kullanım Alanları
1. **İş Raporlaması:** Çeyrekler bazında finansal trendleri göstermek için işaretçili bir çizgi grafik kullanın.  
2. **Veri Analizi:** Her işaretçinin bir ölçüm noktasını vurguladığı deneysel verileri görselleştirin.  
3. **Eğitim Materyalleri:** Bir sürecin adım‑adım değişimini gösteren ders slaytları hazırlayın.  
4. **Proje Yönetimi:** Kilit tarihleri belirgin işaretçilerle göstererek zaman çizelgesinde kilometre taşlarını izleyin.  
5. **Pazarlama Sunumları:** Kampanya performansındaki ani yükselişleri net işaretçi sembolleriyle sergileyin.

## Yaygın Sorunlar ve Çözümler
- **Boş veri noktaları hata veriyor:** Hücre değerine `null` gönderin (gösterildiği gibi) – Aspose noktayı otomatik olarak atlayacaktır.  
- **Grafik işaretçisiz görünüyor:** `ChartType.LineWithMarkers` kullandığınızdan emin olun, `ChartType.Line` değil.  
- **Açıklama verilerin üzerine geliyor:** `chart.getLegend().setOverlay(false)` ayarlayarak açıklamayı ayrı tutun.  

## Sık Sorulan Sorular

**S: Bu yaklaşımı bir web hizmetinde grafik üretmek için kullanabilir miyim?**  
C: Kesinlikle. Kütüphane, sunucu‑tarafı uygulamalar dahil her Java ortamında çalışır.

**S: Geliştirme sürümleri için lisans gerekir mi?**  
C: Geliştirme ve test için ücretsiz deneme yeterlidir. Üretim kullanımı için ticari lisans gerekir.

**S: Aspose büyük veri setlerini nasıl yönetir?**  
C: API verileri verimli bir şekilde akış olarak işler; ancak dosya boyutlarını kontrol altında tutmak için veri noktası sayısını makul tutun.

**S: Diğer grafik türleri destekleniyor mu?**  
C: Evet – Aspose.Slides çubuk, pasta, dağılım ve daha birçok grafik türünü destekler.

**S: İşaretçi şekilleri ve renkleri özelleştirilebilir mi?**  
C: Her veri noktasının `Marker` özelliği üzerinden işaretçi biçimini değiştirebilirsiniz.

## Sonuç
Artık **Aspose** kullanarak varsayılan işaretçili bir çizgi grafik oluşturmayı, ikinci bir seri eklemeyi, boş verileri işlemeyi ve sonucu PowerPoint dosyası olarak kaydetmeyi biliyorsunuz. Bu teknikler, rapor üretimini otomatikleştirmenize, veri hikâyesi anlatımını geliştirmenize ve sunumlarınızın tutarlılığını korumanıza yardımcı olur.

Daha derinlemesine bilgi için [official documentation](https://docs.aspose.com/slides/java/) adresini inceleyebilir veya Stack Overflow gibi topluluk forumlarına katılabilirsiniz.

---

**Son Güncelleme:** 2026-03-23  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}