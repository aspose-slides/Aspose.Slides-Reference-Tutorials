---
date: '2026-02-06'
description: Aspose Slides sunumunu başlatmayı ve .NET'te Aspose.Slides for Java kullanarak
  gruplanmış sütun grafiğini özelleştirmeyi öğrenin. Veri görselleştirmesini geliştirmek
  için bu adım adım rehberi izleyin.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Aspose Slides ile Sunumu Başlat: .NET Grafikler'
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak .NET Sunumlarında Grafik Oluşturma

## Giriş
Bu öğreticide **presentation Aspose Slides** başlatacak ve .NET slaytlarınıza dinamik, özelleştirilebilir grafikler yerleştirmeyi öğreneceksiniz. Görsel veriler—kümeleme sütun grafikleri gibi—izleyicilerinizin trendleri anında kavramasını sağlar ve Aspose.Slides for Java, .NET ortamını hedefleseniz bile tam programatik kontrol sunar. Kütüphaneyi kurma, yeni bir sunum oluşturma, bir grafik ekleme, verileri doldurma ve negatif değerleri renklendirme gibi biçimlendirme ipuçlarını uygulama adımlarını göstereceğiz.

**Öğrenecekleriniz**
- Aspose.Slides for Java'ı bir .NET projesinde nasıl kuracağınız.  
- **presentation Aspose Slides** başlatmayı ve bir grafik eklemeyi.  
- **kümeleme sütun grafiği** serilerini ve kategorilerini özelleştirmeyi.  
- Grafiğin veri çalışma kitabını yönetmeyi ve koşullu biçimlendirme uygulamayı.  

### Hızlı Cevaplar
- **İlk adım nedir?** Bir `Presentation` nesnesi başlatmak.  
- **Örnekte hangi grafik türü kullanılıyor?** `ClusteredColumn`.  
- **Negatif değerleri farklı biçimlendirebilir miyim?** Evet, koşullu doldurma renkleri kullanarak.  
- **Test için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme lisansı yeterlidir.  
- **Hangi Maven artefaktı gerekli?** `com.aspose:aspose-slides:25.4` `jdk16` sınıflandırıcısı ile.

## “initialize presentation Aspose Slides” nedir?
Bir sunumu başlatmak, kaydetmeden önce manipüle edebileceğiniz bellek içi bir PPTX dosyası oluşturur. Aspose.Slides dosya formatını soyutlayarak, düşük seviyeli OPC yapılarıyla uğraşmadan slayt, şekil ve grafik eklemenizi sağlar.

## Neden bir kümeleme sütun grafiği özelleştirilmeli?
Kümeleme sütun grafikleri, birden fazla veri serisini kategoriler arasında karşılaştırmak için idealdir. Renkleri, veri noktalarını ve etiketleri özelleştirerek, negatif değerleri kırmızı, pozitifleri yeşil vurgulamak gibi önemli içgörüleri öne çıkarabilir, slaytlarınızı daha etkileyici hâle getirebilirsiniz.

## Önkoşullar
- **Aspose.Slides for Java** ≥ 25.4  
- .NET geliştirme ortamı (Visual Studio, .NET 6+ önerilir)  
- Temel Java bilgisi (JVM üzerinde çalışan ve .NET'ten JNI veya bir köprü katmanı aracılığıyla çağrılan Java kodu yazacaksınız)

### Gerekli Kütüphaneler ve Sürümler
- **Aspose.Slides for Java**: Sürüm 25.4 veya üzeri.

### Ortam Kurulum Gereksinimleri
- .NET uyumlu bir Java çalışma zamanı (ör. AdoptOpenJDK 16).  
- Bağımlılık yönetimi için Maven veya Gradle.

### Bilgi Önkoşulları
- .NET bağlamında sunum oluşturma konusunda aşinalık.  
- Java proje yapılandırması (Maven/Gradle) hakkında anlayış.

## Aspose.Slides for Java Kurulumu
Kütüphaneyi tercih ettiğiniz derleme aracıyla projenize ekleyin.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Ayrıca resmi sürüm sayfasından en son JAR dosyasını indirebilirsiniz: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Lisans Edinme Adımları
- **Ücretsiz Deneme** – geliştirme için geçici bir lisans dosyası oluşturun.  
- **Satın Alma** – üretim dağıtımları için tam lisans edinin.

#### Temel Başlatma ve Kurulum
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
`try/finally` bloğu, yerel kaynakların serbest bırakılmasını garanti eder, bellek sızıntılarını önler.

## presentation Aspose Slides nasıl başlatılır
Aşağıda yeni bir sunum oluşturmak ve grafiği eklemek için hazırlamak adına somut adımlara dalacağız.

### Sunumu Başlatma

**Genel Bakış:**  
Bir sunum örneği oluşturmak, sonraki tüm işlemler için zemin hazırlar.

#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
```

#### Adım 2: Yeni Bir Presentation Nesnesi Oluşturun
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Bu, sunum nesnesinin kullanım sonrası düzgün bir şekilde temizlenmesini sağlar, bellek sızıntılarını önler.*

## kümeleme sütun grafiği nasıl özelleştirilir
Sunum hazır olduğuna göre, bir kümeleme sütun grafiği ekleyip özelleştirelim.

### Grafiği Slayta Ekleme

**Genel Bakış:**  
Grafik eklemek, slayttaki verileri hayata geçirir.

#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Adım 2: Sunumu Başlat ve Grafiği Ekle
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
*Burada, belirtilen koordinat ve boyutlarda ilk slayta bir kümeleme sütun grafiği ekliyoruz.*

### Grafik Veri Çalışma Kitabını Yönetme

**Genel Bakış:**  
Grafiğin veri çalışma kitabını verimli bir şekilde yönetmek, serileri ve kategorileri sorunsuz bir şekilde manipüle etmenizi sağlar.

#### Adım 1: Gerekli Paketleri İçe Aktarın
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Adım 2: Veri Çalışma Kitabına Eriş ve Temizle
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
*Yeni seriler ve kategoriler eklerken temiz bir sayfa ile başlamanız için çalışma kitabını temizlemek çok önemlidir.*

### Grafiğe Seri ve Kategoriler Ekleme

**Genel Bakış:**  
Bu adım, serileri ve kategorileri yöneterek anlamlı veri noktaları eklemenizi gösterir.

#### Adım 1: Seri ve Kategoriler Ekle
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
*Seri ve kategoriler eklemek, daha düzenli bir veri sunumu sağlar.*

### Seri Verilerini Doldurma ve Biçimlendirme

**Genel Bakış:**  
Grafiğinizi veri noktalarıyla doldurun ve görünümünü biçimlendirerek okunabilirliği artırın, özellikle negatif değerlerle çalışırken.

#### Adım 1: Seri Verilerini Doldur
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
- **Bellek sızıntıları** – `Presentation` nesnesini her zaman gösterildiği gibi bir `try/finally` bloğuna sararak temizlenmesini garanti edin.  
- **Yanlış hücre koordinatları** – Satır ve sütunların sıfır‑tabanlı olduğunu unutmayın; uyumsuz indeksler `NullPointerException` oluşturur.  
- **Lisans bulunamadı** – Lisans dosyasını uygulamanın çalışma dizinine koyun veya yolu `License.setLicense("Aspose.Slides.Java.lic")` ile açıkça ayarlayın.

## Sıkça Sorulan Sorular

**S: Bu yaklaşımı .NET Core ile kullanabilir miyim?**  
C: Evet. Aspose.Slides for Java herhangi bir JVM'de çalışır ve Java kodunu .NET Core'dan IKVM veya JNI gibi bir köprü kullanarak çağırabilirsiniz.

**S: Geliştirme için ücretli lisansa ihtiyacım var mı?**  
C: Geliştirme ve test için ücretsiz deneme lisansı yeterlidir. Üretim dağıtımları için satın alınmış bir lisans gerekir.

**S: Oluşturduktan sonra grafik tipini nasıl değiştiririm?**  
C: Farklı bir grafik tipine geçmek için `chart.getChartData().setChartType(ChartType.Pie)` çağırabilirsiniz.

**S: Veri etiketlerini programlı olarak eklemek mümkün mü?**  
C: Evet. Grafikte değerleri göstermek için `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` kullanın.

**S: Sunumu hangi formatlarda kaydedebilirim?**  
C: Aspose.Slides PPTX, PPT, PDF, XPS ve PNG, JPEG gibi çeşitli görüntü formatlarını destekler.

---

**Son Güncelleme:** 2026-02-06  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16 sınıflandırıcısı)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}