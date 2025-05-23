---
"date": "2025-04-17"
"description": "Özel resim işaretçileri ekleyerek Java için Aspose.Slides'ta grafiklerinizi nasıl geliştireceğinizi öğrenin. Görsel olarak farklı sunumlarla etkileşimi artırın."
"title": "Master Aspose.Slides Java&#58; Grafiklere Resim İşaretleyicileri Ekleme"
"url": "/tr/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java'da Ustalaşma: Grafiklere Resim İşaretçileri Ekleme

## giriiş
Görsel olarak çekici sunumlar oluşturmak etkili iletişimin anahtarıdır ve grafikler karmaşık verileri özlü bir şekilde iletmek için güçlü bir araçtır. Standart grafik işaretçileri bazen verilerinizi öne çıkarmada yetersiz kalabilir. Java için Aspose.Slides ile grafiklerinizi işaretçi olarak özel resimler ekleyerek geliştirebilir, daha ilgi çekici ve bilgilendirici hale getirebilirsiniz.

Bu eğitimde, Java'daki Aspose.Slides kütüphanesini kullanarak grafiklerinize resim işaretleyicileri nasıl entegre edeceğinizi keşfedeceğiz. Bu tekniklerde ustalaşarak, benzersiz görsel öğeleriyle dikkat çeken sunumlar oluşturabileceksiniz.

**Ne Öğreneceksiniz:**
- Java için Aspose.Slides nasıl kurulur
- Temel bir sunum ve grafik oluşturma
- Grafik veri noktalarına görüntü işaretleyicileri ekleme
- En iyi görselleştirme için işaretleyici ayarlarını yapılandırma

Grafiklerinizi yükseltmeye hazır mısınız? Başlamadan önce ön koşullara bir göz atalım!

### Ön koşullar
Bu eğitimi takip etmek için şunlara ihtiyacınız olacak:
1. **Java Kütüphanesi için Aspose.Slides**: Maven veya Gradle bağımlılıkları aracılığıyla edinebilir veya doğrudan Aspose'dan indirebilirsiniz.
2. **Java Geliştirme Ortamı**: Makinenizde JDK 16'nın yüklü olduğundan emin olun.
3. **Temel Java Programlama Bilgisi**:Java söz dizimi ve kavramlarına aşinalık faydalı olacaktır.

## Java için Aspose.Slides Kurulumu
Koda dalmadan önce gerekli kütüphanelerle geliştirme ortamımızı kuralım.

### Maven Kurulumu
Aşağıdaki bağımlılığı ekleyin `pom.xml` dosya:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kurulumu
Bunu da ekleyin `build.gradle` dosya:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en son sürümü şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

#### Lisans Edinme Adımları
- **Ücretsiz Deneme**:Aspose.Slides özelliklerini keşfetmek için geçici bir lisansla başlayın.
- **Geçici Lisans**: Geçici lisans alarak gelişmiş özelliklere erişin.
- **Satın almak**: Uzun süreli kullanım için tam lisans satın almayı düşünebilirsiniz.

### Temel Başlatma ve Kurulum
Başlat `Presentation` Slayt oluşturmaya başlamak için nesne:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Slayt ve grafik ekleme kodunuz buraya gelecek.
    }
}
```

## Uygulama Kılavuzu
Şimdi grafik serilerinize resim işaretçileri ekleme sürecini parçalara ayıralım.

### Bir Grafikle Yeni Bir Sunum Oluşturun
Öncelikle grafiğimizi ekleyebileceğimiz bir slayta ihtiyacımız var:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Sunum nesnesini başlatın
        Presentation presentation = new Presentation();

        // Koleksiyondan ilk slaydı alın
        ISlide slide = presentation.getSlides().get_Item(0);

        // Slayda işaretçilerle varsayılan bir çizgi grafiği ekleyin
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Grafik Verilerine Erişim ve Yapılandırma
Daha sonra, serileri yönetmek için grafiğimizin veri çalışma sayfasına erişeceğiz:

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

        // Mevcut seriyi temizleyin ve yenisini ekleyin
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Grafik Veri Noktalarına Görüntü İşaretleyicileri Ekleyin
Şimdi heyecan verici kısma geçelim: İşaretleyici olarak görseller eklemek:

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

        // Görüntüleri işaretçi olarak yükleyin ve ekleyin
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Veri noktalarını işaretçi olarak görsellerle ekleyin
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

### Grafik Serisi İşaretleyicisini Yapılandırın ve Sunumu Kaydedin
Son olarak, daha iyi görünürlük için işaretçi boyutunu ayarlayalım ve sunumumuzu kaydedelim:

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

        // Görüntüleri işaretçi olarak yükleyin ve ekleyin (yer tutucu yolları kullanarak örnek)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Çözüm
Bu kılavuzu takip ederek, özel resim işaretçileri ekleyerek Aspose.Slides for Java'daki grafiklerinizi nasıl geliştireceğinizi öğrendiniz. Bu yaklaşım, sunumlarınızın etkileşimini ve netliğini önemli ölçüde artırabilir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}