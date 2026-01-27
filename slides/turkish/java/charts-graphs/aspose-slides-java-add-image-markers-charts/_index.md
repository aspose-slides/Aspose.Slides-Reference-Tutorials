---
date: '2026-01-11'
description: Aspose Slides for Java'ı nasıl kullanacağınızı öğrenin, grafiklere resim
  işaretçileri ekleyin ve özel grafik görselleri için Aspose Slides Maven bağımlılığını
  yapılandırın.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Aspose Slides Java Nasıl Kullanılır - Grafiklere Görsel İşaretçiler Ekle'
url: /tr/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Java Nasıl Kullanılır: Grafiklere Görsel İşaretçiler Ekleyin

## Giriş
Görsel olarak çekici sunumlar oluşturmak etkili iletişimin anahtarıdır ve grafikler, karmaşık verileri özlü bir şekilde iletmek için güçlü bir araçtır. Grafiklerinizi öne çıkarmak için **Aspose nasıl kullanılır** sorusuna yanıt, özel görsel işaretçilerdir. Standart işaretçiler genel görünebilir, ancak Aspose.Slides for Java ile bunları herhangi bir resimle değiştirebilir—her veri noktasını anında tanınabilir kılar.

Bu öğreticide, bir çizgi grafiğine görsel işaretçiler ekleme sürecini baştan sona inceleyeceğiz; **Aspose Slides Maven dependency**'yi kurmaktan görüntüleri yüklemeye ve veri noktalarına uygulamaya kadar. Sonuna kadar **işaretçilerin nasıl ekleneceği**, **grafik serilerine nasıl görüntü ekleneceği** konularında rahat olacaksınız ve çalıştırmaya hazır bir kod örneğine sahip olacaksınız.

**Neler Öğreneceksiniz**
- Aspose.Slides for Java'ı (Maven/Gradle dahil) nasıl kuracağınızı
- Temel bir sunum ve grafik oluşturmayı
- Grafik veri noktalarına görsel işaretçiler eklemeyi
- İşaretçi boyutunu ve stilini optimal görselleştirme için yapılandırmayı

Grafiklerinizi yükseltmeye hazır mısınız? Başlamadan önce ön koşullara göz atalım!

### Hızlı Yanıtlar
- **Temel amaç nedir?** Grafik veri noktalarına özel görsel işaretçiler eklemek.  
- **Hangi kütüphane gereklidir?** Aspose.Slides for Java (Maven/Gradle).  
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gerekir.  
- **Hangi Java sürümü destekleniyor?** JDK 16 veya üzeri.  
- **Herhangi bir görüntü formatı kullanılabilir mi?** Evet—PNG, JPEG, BMP vb., dosya erişilebilir olduğu sürece.

### Önkoşullar
1. **Aspose.Slides for Java Kütüphanesi** – Maven, Gradle ya da doğrudan indirme yoluyla temin edin.  
2. **Java Geliştirme Ortamı** – JDK 16 veya daha yeni bir sürüm kurulu.  
3. **Temel Java Programlama Bilgisi** – Java sözdizimi ve kavramlarına aşina olmak faydalı olacaktır.

## Aspose Slides Maven Bağımlılığı Nedir?
Maven bağımlılığı, Java sürümünüz için doğru ikili dosyaları çeker. `pom.xml` dosyanıza eklemek, kütüphanenin derleme ve çalışma zamanında kullanılabilir olmasını sağlar.

### Maven Kurulumu
Aşağıdaki bağımlılığı `pom.xml` dosyanıza ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kurulumu
`build.gradle` dosyanıza bu satırı ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

#### Lisans Edinme Adımları
- **Ücretsiz Deneme** – özellikleri keşfetmek için geçici bir lisansla başlayın.  
- **Geçici Lisans** – test ederken gelişmiş yeteneklerin kilidini açar.  
- **Satın Alma** – ticari projeler için tam lisans edinin.

## Temel Başlatma ve Kurulum
İlk olarak bir `Presentation` nesnesi oluşturun. Bu nesne tüm PowerPoint dosyasını temsil eder ve grafiğimizi tutacaktır.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Uygulama Kılavuzu
Aşağıda, bir grafiğe görsel işaretçiler eklemenin adım adım açıklaması yer almaktadır. Her kod bloğu, **neden** her satırın önemli olduğunu açıklayan bir açıklama ile birlikte verilmiştir.

### Adım 1: Yeni Bir Sunum ve Grafik Oluşturun
İlk slayta varsayılan işaretçilerle bir çizgi grafiği ekliyoruz.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Adım 2: Grafik Verilerine Erişin ve Yapılandırın
Varsayılan serileri temizliyor ve kendi serimizi ekliyoruz, özel veri noktaları için çalışma sayfasını hazırlıyoruz.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Adım 3: Grafik Veri Noktalarına Görsel İşaretçiler Ekleyin
Burada resimler kullanarak **işaretçilerin nasıl ekleneceğini** gösteriyoruz. Yer tutucu yolları, görüntülerinizin gerçek konumlarıyla değiştirin.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Adım 4: İşaretçi Boyutunu Yapılandırın ve Sunumu Kaydedin
Daha iyi görünürlük için işaretçi stilini ayarlıyor ve son PPTX dosyasını yazıyoruz.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Yaygın Sorunlar ve Sorun Giderme
- **FileNotFoundException** – Görüntü yollarının (`YOUR_DOCUMENT_DIRECTORY/...`) doğru olduğundan ve dosyaların mevcut olduğundan emin olun.  
- **LicenseException** – Üretimde herhangi bir API çağrısı yapmadan önce geçerli bir Aspose lisansı ayarladığınızdan emin olun.  
- **İşaretçi Görünmüyor** – `setMarkerSize` değerini artırın veya daha net görüntü için yüksek çözünürlüklü resimler kullanın.

## Sıkça Sorulan Sorular

**S: İşaretçiler için JPEG yerine PNG görüntüleri kullanabilir miyim?**  
**C:** Evet, Aspose.Slides tarafından desteklenen herhangi bir görüntü formatı (PNG, JPEG, BMP, GIF) işaretçi olarak çalışır.

**S: Maven/Gradle paketleri için lisans gerekiyor mu?**  
**C:** Geliştirme ve test için geçici bir lisans yeterlidir; ticari dağıtım için tam lisans gereklidir.

**S: Aynı serideki her veri noktasına farklı görüntüler eklemek mümkün mü?**  
**C:** Kesinlikle. `AddImageMarkers` örneğinde iki resim arasında geçiş yapıyoruz, ancak her nokta için benzersiz bir görüntü yükleyebilirsiniz.

**S: `aspose slides maven dependency` proje boyutunu nasıl etkiler?**  
**C:** Maven paketi, seçilen JDK sürümü için yalnızca gerekli ikili dosyaları içerir, böylece boyut makul kalır. Boyut bir endişe ise **no‑dependencies** sürümünü de kullanabilirsiniz.

**S: Hangi Java sürümleri destekleniyor?**  
**C:** Aspose.Slides for Java, JDK 8'den JDK 21'e kadar destekler. Örnek JDK 16 kullanıyor, ancak sınıflandırıcıyı buna göre ayarlayabilirsiniz.

## Sonuç
Bu kılavuzu izleyerek artık **Aspose nasıl kullanılır** konusunda, grafiklere özel görsel işaretçiler ekleyerek zenginleştirme, **Aspose Slides Maven dependency**'yi yapılandırma ve **grafik serilerine görüntü ekleme** konularında bilgi sahibisiniz. Farklı simgeler, boyutlar ve grafik türleriyle denemeler yaparak gerçekten öne çıkan sunumlar oluşturabilirsiniz.

---

**Son Güncelleme:** 2026-01-11  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}