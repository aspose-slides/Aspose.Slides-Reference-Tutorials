---
"date": "2025-04-17"
"description": "Java için Aspose.Slides kullanarak profesyonel sunumlar oluşturmayı öğrenin. Bu kılavuz, ortamınızı kurmayı, yığılmış sütun grafikleri eklemeyi ve bunları netlik için özelleştirmeyi kapsar."
"title": "Aspose.Slides ile Java'da Yığılmış Sütun Grafiklerinde Ustalaşın Kapsamlı Bir Kılavuz"
"url": "/tr/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides ile Yığılmış Sütun Grafiklerinde Ustalaşın: Kapsamlı Bir Kılavuz

## giriiş

Aspose.Slides for Java'nın gücüyle içgörülü veri görselleştirmelerini birleştirerek sunumlarınızı yükseltin. İster iş raporları hazırlıyor olun ister proje istatistiklerini sergiliyor olun, yığılmış sütun grafikleriyle profesyonel görünümlü slaytlar oluşturmak kolaydır.

Bu eğitimde, dinamik sunumlar oluşturmak ve görsel olarak çekici yığılmış sütun grafikleri eklemek için Aspose.Slides for Java'yı nasıl kullanacağınızı keşfedeceğiz. Bu kılavuzun sonunda, şunlar için gereken becerilere sahip olacaksınız:
- Aspose.Slides'ı kullanmak için ortamınızı ayarlayın
- Sıfırdan bir sunum oluşturun
- Yüzdelik yığılmış sütun grafikleri ekleyin ve özelleştirin
- Netlik için grafik eksenlerini ve veri etiketlerini biçimlendirin

Haydi, hedef kitlenizi büyüleyecek sunumlar oluşturmaya başlayalım.

## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- **Java Geliştirme Kiti (JDK):** Sürüm 8 veya üzeri.
- **İDE:** IntelliJ IDEA veya Eclipse gibi herhangi bir Entegre Geliştirme Ortamı.
- **Maven/Gradle:** Bağımlılıkları yönetmek için (isteğe bağlı ancak önerilir).
- **Temel Java Bilgisi:** Java programlama kavramlarına aşinalık.

## Java için Aspose.Slides Kurulumu
Başlamak için projenize Aspose.Slides kütüphanesini eklemeniz gerekir. İşte nasıl:

**Usta:**
Bu bağımlılığı şuna ekleyin: `pom.xml` dosya:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Bunu da ekleyin `build.gradle` dosya:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme:**
Alternatif olarak, en son JAR'ı şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

### Lisans Edinimi
Aspose.Slides özelliklerini keşfetmek için ücretsiz denemeyle başlayabilirsiniz. Değerlendirme sınırlamalarını kaldırmak için geçici veya satın alınmış bir lisans edinmeyi düşünün.
- **Ücretsiz Deneme:** Anında maliyet ödemeden sınırlı özelliklere erişin.
- **Geçici Lisans:** İstek yoluyla [Aspose'un sitesi](https://purchase.aspose.com/temporary-license/).
- **Satın almak:** Tam erişim için satın alma sayfasını ziyaret edin.

### Temel Başlatma
Java uygulamanızda Aspose.Slides'ı şu şekilde başlatabilirsiniz:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Bir Presentation sınıfı örneği oluşturun
        Presentation presentation = new Presentation();
        
        // Sunum nesnesi üzerinde işlemler gerçekleştirin
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Uygulama Kılavuzu

### Bir Sunum Oluşturma ve Slayt Ekleme
**Genel Bakış:**
Basit bir sunum oluşturarak başlayın ve başlangıç slaydını kullanın. Bu, daha fazla geliştirme için temelinizdir.

#### Adım 1: Sunum Nesnesini Başlat
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Yeni bir sunum örneği oluşturun
        Presentation presentation = new Presentation();
        
        // İlk slayta referans (otomatik oluşturuldu)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Adım 2: Sunumu Kaydedin
```java
// Sunumu bir dosyaya kaydedin
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Bir Slayda Yüzde Yığılmış Sütun Grafiği Ekleme
**Genel Bakış:**
Kolay veri karşılaştırması sağlayan yüzdelik yığılmış sütun grafiği ekleyerek slaydınızı geliştirin.

#### Adım 1: Slaydı Başlatın ve Erişin
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Bir sonraki adımda grafik eklemeye devam edin
    }
}
```

#### Adım 2: Slayda Grafik Ekle
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Grafik Eksen Sayı Biçimini Özelleştirme
**Genel Bakış:**
Daha iyi okunabilirlik için grafiğinizin dikey ekseninin sayı biçimini özelleştirin.

#### Adım 1: Grafik Ekle ve Erişim
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Adım 2: Özel Sayı Biçimini Ayarlayın
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Grafiğe Seri ve Veri Noktaları Ekleme
**Genel Bakış:**
Tablonuzu veri serileriyle doldurarak bilgilendirici ve görsel olarak çekici hale getirin.

#### Adım 1: Sunumu ve Grafiği Başlatın
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Adım 2: Veri Serilerini Ekleyin
```java
// Mevcut serileri temizleyin ve yenilerini ekleyin
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Gerektiğinde daha fazla veri noktası ekleyin
```

### Biçimlendirme Serisi Dolgu Rengi
**Genel Bakış:**
Her serinin dolgu rengini biçimlendirerek grafiğinizin estetiğini artırın.

#### Adım 1: Grafiği Başlatın ve Erişim Sağlayın
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Adım 2: Dolgu Renklerini Ayarlayın
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Farklı renklerle diğer seriler için tekrarlayın
```

### Veri Etiketlerini Biçimlendirme
**Genel Bakış:**
Veri etiketlerinizin biçimini özelleştirerek daha okunaklı hale getirin.

#### Adım 1: Grafik Serilerine ve Veri Noktalarına Erişim
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Adım 2: Veri Etiketlerini Özelleştirin
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Çözüm
Bu kılavuzu takip ederek, Java için Aspose.Slides'ı nasıl kuracağınızı ve yüzdelik yığılmış sütun grafikleriyle dinamik sunumlar nasıl oluşturacağınızı öğrendiniz. Renkleri ve etiketleri ihtiyaçlarınıza uyacak şekilde ayarlayarak grafiklerinizi daha da özelleştirin.

Keyifli kodlamalar!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}