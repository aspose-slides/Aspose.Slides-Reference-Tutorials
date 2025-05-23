---
"date": "2025-04-17"
"description": "Aspose.Slides kullanarak Java'da grafiklerle dinamik sunumlar oluşturmayı ve yapılandırmayı öğrenin. Sunumları etkili bir şekilde ekleme, özelleştirme ve kaydetme konusunda ustalaşın."
"title": "Java için Aspose.Slides'ı Kullanarak Grafiklerle Java Sunumları Oluşturun"
"url": "/tr/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java için Aspose.Slides Kullanarak Grafikli Bir Sunum Nasıl Oluşturulur ve Yapılandırılır

## giriiş

Günümüzün hızlı tempolu iş ortamında verileri etkili bir şekilde ileten dinamik sunumlar oluşturmak esastır. İster finansal bir rapor hazırlıyor olun ister proje ölçümlerini sergiliyor olun, grafikler eklemek sunumunuzun etkisini önemli ölçüde artırabilir. Bu eğitim, sunumları programatik olarak işlemek için tasarlanmış güçlü bir kütüphane olan Aspose.Slides for Java kullanarak 3B yığılmış sütun grafiğiyle bir sunum oluşturma ve yapılandırma konusunda size rehberlik eder.

**Ne Öğreneceksiniz:**
- Yeni bir sunum nasıl oluşturulur
- Slaytlara grafik ekleyin ve yapılandırın
- Grafik verilerini ve görünümünü özelleştirin
- Sunumunuzu etkili bir şekilde kaydedin

Java ile görsel olarak ilgi çekici sunumlar oluşturmada ustalaşmaya hazır mısınız? Hadi başlayalım!

## Ön koşullar

Eğitime başlamadan önce şu ön koşulların sağlandığından emin olun:

- **Kütüphaneler ve Bağımlılıklar**: Java için Aspose.Slides'ın kurulu olması gerekir.
- **Çevre Kurulumu**: Java ortamında çalışın (JDK 16 veya üzeri önerilir).
- **Bilgi Tabanı**:Temel Java programlama kavramlarına aşinalık faydalı olacaktır.

## Java için Aspose.Slides Kurulumu

### Kurulum

Aspose.Slides'ı projenize entegre etmek için şu adımları izleyin:

**Usta**

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

**Doğrudan İndirme**: Alternatif olarak, en son sürümü şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

### Lisans Edinimi
- **Ücretsiz Deneme**: Özellikleri keşfetmek için ücretsiz denemeyle başlayın.
- **Geçici Lisans**:Uzun süreli testler için geçici lisans alın.
- **Satın almak**:Ticari kullanım için tam lisans edinin.

Kurulduktan sonra, Java ortamınızda bir örnek oluşturarak kitaplığı başlatın `Presentation` sınıf. Bu, sununuza grafikler ve diğer öğeler eklemek için zemin hazırlar.

## Uygulama Kılavuzu

### Bir Grafikle Bir Sunum Oluşturun ve Yapılandırın

#### Genel bakış
Aspose.Slides ile sıfırdan bir sunum oluşturmak basittir. Bu bölümde, sunumumuzun ilk slaydına 3B yığılmış sütun grafiği ekleyeceğiz.

**Adımlar:**

1. **Sunum Nesnesini Başlat**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Yeni bir Sunum nesnesi başlatın
           Presentation presentation = new Presentation();
           
           // Sunumdaki ilk slayda erişin
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Slayta (0,0) konumuna 3 boyutlu yığılmış sütun grafiği ekleyin
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Parametreleri Açıkla**:
   - `ChartType.StackedColumn3D`: Grafik türünü belirtir.
   - Pozisyon ve boyut `(0, 0, 500, 500)`: Grafiğin slaytta nerede görüneceğini belirler.

### Grafik Verilerini Yapılandır

#### Genel bakış
Grafiğinizi anlamlı kılmak için veri serilerini ve kategorilerini yapılandırın. Bu bölüm, grafiğinize belirli veri noktalarının nasıl ekleneceğini gösterir.

**Adımlar:**

1. **Access Chart'ın Veri Çalışma Kitabı**

   ```java
   public static void configureChartData(IChart chart) {
       // Grafik verilerini içeren çalışma sayfasının dizinini ayarlayın
       int defaultWorksheetIndex = 0;
       
       // Tablonun veri çalışma kitabına erişin
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // İsimleri olan iki seriyi ekle
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Üç kategori ekle
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Grafik için Rotation3D Özelliklerini Ayarla

#### Genel bakış
3D döndürme özellikleriyle grafiğinizin görsel çekiciliğini artırın. Bu özelleştirme, perspektifi ve derinliği ayarlamanıza olanak tanır.

**Adımlar:**

1. **3B Döndürmeleri Yapılandırın**

   ```java
   public static void setRotation3D(IChart chart) {
       // Dik açılı eksenleri etkinleştirin ve X, Y yönlerinde ve derinlik yüzdesinde dönüşleri yapılandırın
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Parametreleri Açıkla**:
   - `setRightAngleAxes(true)`: Eksenlerin dik olmasını sağlar.
   - Döndürme değerleri: 3B görünümün açısını ve derinliğini ayarlar.

### Grafikteki Seri Verilerini Doldur

#### Genel bakış
Grafiğinizi veri noktalarıyla doldurmak analiz için çok önemlidir. Burada, grafiğimizdeki bir seriye belirli değerler ekleyeceğiz.

**Adımlar:**

1. **Veri Noktaları Ekle**

   ```java
   public static void populateSeriesData(IChart chart) {
       // İkinci grafik serisine erişin
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Belirtilen değerlere sahip çubuk serileri için veri noktaları ekleyin
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Grafikte Seri Çakışmalarını Ayarla

#### Genel bakış
Grafiğinizin görünümünü ince ayarlamak okunabilirliği artırabilir. Bu bölüm, daha iyi veri görselleştirmesi için örtüşme özelliğinin nasıl ayarlanacağını ele almaktadır.

**Adımlar:**

1. **Seri Çakışmalarını Ayarla**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Tablodan ikinci seriyi alın ve örtüşmesini 100 olarak ayarlayın
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Sunumu Kaydet

#### Genel bakış
Sunumunuz yapılandırıldıktan sonra, istediğiniz formatta diske kaydedin. Bu adım, tüm değişikliklerin korunmasını sağlar.

**Adımlar:**

1. **Sunumu Kaydet**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Değiştirilen sunumu bir dosyaya kaydedin
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Çözüm

Artık Java için Aspose.Slides kullanarak grafiklerle sunumlar oluşturmayı ve yapılandırmayı öğrendiniz. Bu kılavuz, bir sunumu başlatmayı, 3B yığılmış sütun grafiği eklemeyi, veri serilerini ve kategorileri yapılandırmayı, dönüş özelliklerini ayarlamayı, seri verilerini doldurmayı, seri örtüşmesini ayarlamayı ve son sunumu kaydetmeyi kapsıyordu.

Daha gelişmiş özellikler ve özelleştirme seçenekleri için şuraya bakın: [Java belgeleri için Aspose.Slides](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}