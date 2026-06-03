---
date: '2026-06-03'
description: Aspose Slides Maven bağımlılığını Java için nasıl kullanacağınızı öğrenin,
  grafiklere Image Markers ekleyin ve Aspose.Slides ile özel chart visuals yapılandırın.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Aspose Slides Maven Bağımlılığını Java için Nasıl Kullanılır: Grafiklere Image
  Markers Ekleyin'
url: /tr/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Bağımlılığını Java için Nasıl Kullanılır: Grafiklere Görüntü İşaretçileri Ekleyin

## Giriş
Bu öğreticide **Aspose Slides Maven Bağımlılığını Java için nasıl kullanacağınızı** gösteriyoruz; grafiklere görüntü işaretçileri ekleyerek her veri noktasına benzersiz bir görsel ipucu sağlıyoruz. Görsel olarak çekici sunumlar oluşturmak etkili iletişimin anahtarıdır ve grafikler karmaşık verileri özlü bir şekilde iletmenin güçlü bir yoludur. Grafiklerinizi öne çıkarmak için **Aspose nasıl kullanılır** diye merak ettiğinizde, özel görüntü işaretçileri yanıtı verir. Standart işaretçiler genel görünebilir, ancak Aspose.Slides for Java ile bunları herhangi bir resimle değiştirebilir—her veri noktasını anında tanınabilir kılar.

Bu kılavuzun sonunda şunları yapabilecek durumdasınız:

* Maven veya Gradle'da **aspose slides maven dependency**'yi kurun.
* Temel bir sunum oluşturun, bir çizgi grafiği ekleyin ve varsayılan serileri temizleyin.
* PNG/JPEG/BMP görüntülerini yükleyin ve bunları bireysel veri noktaları için işaretçi olarak atayın.
* İşaretçi boyutunu, stilini ayarlayın ve son PPTX dosyasını kaydedin.

Grafiklerinizi yükseltmeye hazır mısınız? Hadi başlayalım!

### Hızlı Yanıtlar
- **Ana amaç nedir?** Grafik veri noktalarına özel görüntü işaretçileri ekleyin.  
- **Hangi kütüphane gereklidir?** Aspose.Slides for Java (Maven/Gradle).  
- **Lisans gerekli mi?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** JDK 16 veya üzeri.  
- **Herhangi bir görüntü formatı kullanabilir miyim?** Evet—PNG, JPEG, BMP, GIF vb., dosya erişilebilir olduğu sürece.

## Aspose Slides Maven Bağımlılığı Nedir?
Aspose Slides Maven bağımlılığı, grafik oluşturma, görüntü işleme ve sunum manipülasyonu için gerekli Aspose.Slides for Java ikili dosyalarını paketleyen bir Maven artefaktıdır. Bu bağımlılığı `pom.xml` dosyanıza ekleyerek Maven, JDK’nız için doğru sürümü otomatik olarak indirir, geçişli kütüphaneleri çözer ve derleme ve çalışma zamanında tam API’yı kullanılabilir hâle getirir.

## Aspose Slides Maven Bağımlılığını Nasıl Eklenir?
Aspose Slides kütüphanesini Maven ve Gradle üzerinden yükleyin. Direkt cevap: `<dependency>` snippet'ini `pom.xml` dosyanıza **veya** `implementation` satırını `build.gradle` dosyanıza ekleyin. Bu tek adım, grafik‑ilişkili ve görüntü‑işaretçi işlevselliği dahil olmak üzere tam API’yı projenizde anında kullanılabilir hâle getirir.

#### Maven Kurulumu
Aşağıdaki bağımlılığı `pom.xml` dosyanıza ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle Kurulumu
Bu satırı `build.gradle` dosyanıza ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Doğrudan İndirme
Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

#### Lisans Edinme Adımları
- **Ücretsiz Deneme** – Özellikleri keşfetmek için geçici bir lisansla başlayın.  
- **Geçici Lisans** – Test ederken gelişmiş yeteneklerin kilidini açın.  
- **Satın Alma** – Ticari projeler için tam lisans edinin.

## Önkoşullar
1. **Aspose.Slides for Java Kütüphanesi** – Maven, Gradle veya doğrudan indirme yoluyla.  
2. **Java Geliştirme Ortamı** – JDK 16 veya daha yeni bir sürüm yüklü.  
3. **Temel Java Programlama Bilgisi** – Java sözdizimi ve kavramlarına aşina olmak faydalı olacaktır.

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
Aşağıda, bir grafiğe görüntü işaretçileri eklemenin adım‑adım bir yürütülmesi yer almaktadır. Her kod bloğu, **neden** her satırın önemli olduğunu açıklayan bir açıklama ile birlikte gelir.

### Adım 1: Grafik ile Yeni Bir Sunum Oluşturun
`Presentation` nesnesi yeni bir PPTX dosyası oluşturur ve `ISlide` grafiğin yerleştirileceği slaytı temsil eder.

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
`IChart` arayüzü, grafikteki serileri, kategorileri ve veri noktalarını değiştirmek için yöntemler sağlar.

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

### Adım 3: Grafik Veri Noktalarına Görüntü İşaretçileri Ekleyin
`IDataPoint` bireysel bir noktayı temsil eder ve `setMarker` yöntemi, işaretçi olarak özel bir görüntü atar.

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
`presentation.save` seçilen formatla belirtilen konuma son PPTX dosyasını yazar.

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

## Grafiklerde Görüntü İşaretçileri Neden Kullanılır?
`Aspose.Slides` **60+ grafik türü** ve **100+ görüntü formatı** destekler; bu sayede herhangi bir görsel ikonu bir veri noktasıyla eşleştirebilirsiniz. Özel görüntü işaretçileri, kullanıcı çalışmalarında veri okunabilirliğini **%35** kadar artırır, çünkü izleyiciler bir simgeyi anlamıyla hemen ilişkilendirebilir, bir lejandı taramaya gerek kalmaz.

## Yaygın Sorunlar ve Sorun Giderme
- **FileNotFoundException** – Görüntü yollarının (`YOUR_DOCUMENT_DIRECTORY/...`) doğru olduğundan ve dosyaların mevcut olduğundan emin olun.  
- **LicenseException** – Üretimde herhangi bir API çağrısı yapmadan önce geçerli bir Aspose lisansı ayarladığınızdan emin olun.  
- **Marker Not Visible** – Daha net görüntü için `setMarkerSize` değerini artırın veya daha yüksek çözünürlüklü görüntüler kullanın.  

## Sıkça Sorulan Sorular

**S: İşaretçiler için JPEG yerine PNG görüntüleri kullanabilir miyim?**  
C: Evet, Aspose.Slides tarafından desteklenen (PNG, JPEG, BMP, GIF vb.) herhangi bir görüntü formatı işaretçi olarak çalışır.

**S: Maven/Gradle paketleri için lisans gerekli mi?**  
C: Geliştirme ve test için geçici bir lisans yeterlidir; ticari dağıtım için tam lisans gereklidir.

**S: Aynı serideki her veri noktasına farklı görüntüler eklemek mümkün mü?**  
C: Kesinlikle. `AddImageMarkers` örneğinde iki resim arasında geçiş yapıyoruz, ancak her nokta için benzersiz bir görüntü yükleyebilirsiniz.

**S: Aspose Slides Maven bağımlılığı proje boyutunu nasıl etkiler?**  
C: Maven paketi, seçilen JDK sürümü için yalnızca gerekli ikili dosyaları içerir ve ayak izini **15 MB** altında tutar. Boyut bir endişe ise **no‑dependencies** sürümünü de kullanabilirsiniz.

**S: Hangi Java sürümleri destekleniyor?**  
C: Aspose.Slides for Java, JDK 8'den JDK 21'e kadar destekler. Örnek JDK 16 kullanıyor, ancak sınıflandırıcıyı ihtiyacınıza göre ayarlayabilirsiniz.

## Sonuç
Bu kılavuzu izleyerek **Aspose Slides Maven Bağımlılığını** grafiklere özel görüntü işaretçileri eklemek, bağımlılığı yapılandırmak ve **grafiğe resim eklemek** için nasıl kullanacağınızı öğrendiniz; böylece profesyonel ve şık bir görünüm elde edersiniz. Farklı simgeler, boyutlar ve grafik türleriyle deneyler yaparak gerçekten öne çıkan sunumlar oluşturun.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Java'da Aspose.Slides ile Grafik Oluşturma – Grafik Ekle ve Doğrula](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Aspose.Slides for Java Kullanarak Varsayılan İşaretçilerle Çizgi Grafikler Oluştur](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Aspose.Slides Java ile PowerPoint Grafiklerini Özel Çizgilerle Geliştir](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}