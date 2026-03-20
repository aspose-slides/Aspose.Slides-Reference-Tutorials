---
date: '2026-03-20'
description: Aspose.Slides kullanarak Java sunumlarına grafik eklemeyi öğrenin ve
  sunum grafik dosyalarını hızlı bir şekilde oluşturun.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Aspose.Slides ile Java Sunumlarına Grafik Nasıl Eklenir
url: /tr/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak Sunuma Grafik Ekleme

## Giriş

Dinamik sunumlar oluşturmak ve verileri etkili bir şekilde iletmek, günümüzün hızlı tempolu iş ortamında çok önemlidir. Finansal bir rapor, bir pazarlama sunumu ya da bir proje durum güncellemesi hazırlıyor olun, slaytlarınıza **grafik eklemeyi bilmek** izleyici katılımını büyük ölçüde artırabilir. Bu öğreticide, adım adım 3D yığılmış sütun grafiği eklemeyi, verilerini yapılandırmayı ve son dosyayı kaydetmeyi—tümü Aspose.Slides for Java ile—öğreneceksiniz.

### Hızlı Yanıtlar
- **Temel kütüphane nedir?** Aspose.Slides for Java  
- **Hangi grafik türü gösterilmektedir?** 3D Stacked Column  
- **Sunum grafik dosyalarını programlı olarak oluşturabilir miyim?** Yes, using the API methods shown below  
- **Hangi Java sürümü önerilir?** JDK 16 or later  
- **Üretim için lisansa ihtiyacım var mı?** A valid Aspose.Slides license is required for commercial use  

## Aspose.Slides'ta “grafik ekleme” nedir?

Aspose.Slides for Java, Microsoft Office olmadan PowerPoint dosyaları oluşturmanıza, düzenlemenize ve dışa aktarmanıza olanak tanıyan zengin bir nesne seti sunar. Grafik eklemek, bir `Presentation` nesnesi oluşturmak, bir grafik şekli eklemek ve yerleşik çalışma kitabı aracılığıyla verileri beslemek kadar basittir.

## Java sunumlarına neden grafik eklenir?

- **Görsel etki:** Grafikler, ham sayıları anında anlaşılır görsellere dönüştürür.  
- **Otomasyon:** Raporları anında oluşturun—planlı e‑posta özetleri veya gösterge tabloları için idealdir.  
- **Tutarlılık:** Oluşturulan tüm sunumlarda aynı stil ve marka kimliğini kullanın.  
- **Taşınabilirlik:** Tek bir metod çağrısıyla PPTX, PDF veya görüntü formatına dışa aktarın.

## Önkoşullar

- **Kütüphaneler ve Bağımlılıklar:** Aspose.Slides for Java kurulmuş olmalıdır.  
- **Ortam Kurulumu:** Java ortamında çalışın (JDK 16 veya daha yeni sürüm önerilir).  
- **Bilgi Temeli:** Temel Java programlama kavramlarına aşina olmak faydalı olacaktır.

## Aspose.Slides for Java Kurulumu

### Kurulum

Aspose.Slides'ı projenize entegre etmek için aşağıdaki seçeneklerden birini izleyin.

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

**Doğrudan İndirme**: Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

### Lisans Edinme
- **Ücretsiz Deneme:** Özellikleri keşfetmek için ücretsiz deneme ile başlayın.  
- **Geçici Lisans:** Uzun vadeli testler için geçici bir lisans edinin.  
- **Satın Alma:** Ticari kullanım için tam lisans alın.

Kurulum tamamlandıktan sonra, tüm grafikle ilgili işlemler için giriş noktası olan `Presentation` sınıfını örnekleyebilirsiniz.

## Uygulama Kılavuzu

### 3D yığılmış sütun ile bir sunuma grafik ekleme

#### Genel Bakış
Aspose.Slides ile sıfırdan bir sunum oluşturmak oldukça basittir. Bu bölümde, sunumumuzun ilk slaytına bir 3D yığılmış sütun grafiği ekleyeceğiz.

**Adımlar:**

1. **Presentation Nesnesini Başlat**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
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

2. **Parametreleri Açıklayın**  
   - `ChartType.StackedColumn3D`: Grafik türünü belirtir.  
   - Konum ve boyut `(0, 0, 500, 500)`: Grafiğin slaytta nerede görüneceğini belirler.

### Grafik Verilerini Yapılandırma

#### Genel Bakış
Grafiğinizi anlamlı kılmak için veri serilerini ve kategorileri yapılandırın. Bu bölüm, grafiğinize belirli veri noktaları eklemeyi gösterir.

**Adımlar:**

1. **Grafiğin Veri Çalışma Kitabına Erişin**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Grafik için Rotation3D Özelliklerini Ayarlama

#### Genel Bakış
Grafiğinizin görsel çekiciliğini 3D dönüş özellikleriyle artırın. Bu özelleştirme, perspektif ve derinliği ayarlamanıza olanak tanır.

**Adımlar:**

1. **3D Dönüşleri Yapılandırın**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Parametreleri Açıklayın**  
   - `setRightAngleAxes(true)`: Eksenlerin dik olmasını sağlar.  
   - Dönüş değerleri: 3D görünümün açı ve derinliğini ayarlar.

### Grafikte Seri Verilerini Doldurma

#### Genel Bakış
Grafiğinizi veri noktalarıyla doldurmak analiz için kritiktir. Burada, grafiğimizdeki bir seriye belirli değerler ekleyeceğiz.

**Adımlar:**

1. **Veri Noktaları Ekle**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
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

### Grafikte Seri Çakışmasını Ayarlama

#### Genel Bakış
Grafiğinizin görünümünü ince ayar yapmak okunabilirliği artırabilir. Bu bölüm, daha iyi veri görselleştirme için çakışma özelliğini nasıl ayarlayacağınızı açıklar.

**Adımlar:**

1. **Seri Çakışmasını Ayarla**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Sunumu Kaydet

#### Genel Bakış
Sunumunuz yapılandırıldıktan sonra, istediğiniz formatta diske kaydedin. Bu adım, tüm değişikliklerin korunmasını sağlar.

**Adımlar:**

1. **Sunumu Kaydet**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|-------|
| **Chart appears flat** | 3D rotation not set | Call `setRotation3D` with appropriate X/Y values. |
| **Data not showing** | Workbook cells not linked | Ensure `fact.getCell` references correct row/column indices. |
| **File not saved** | Incorrect path or missing permissions | Verify `outputFilePath` is writable and folder exists. |

## Sıkça Sorulan Sorular

**Q: PPTX dışındaki formatlarda sunum grafik dosyaları oluşturabilir miyim?**  
A: Evet, Aspose.Slides `SaveFormat` enum'u aracılığıyla PDF, ODP ve görüntü formatlarını destekler.

**Q: Geliştirme ortamında kodu çalıştırmak için lisansa ihtiyacım var mı?**  
A: Geçici veya değerlendirme lisansı geliştirme için yeterlidir, ancak üretim dağıtımları için tam lisans gereklidir.

**Q: Aynı slayta birden fazla grafik eklemek mümkün mü?**  
A: Kesinlikle. `slide.getShapes().addChart` metodunu farklı konum ve boyutlarla birden çok kez çağırın.

**Q: Grafiğin renk paletini nasıl değiştiririm?**  
A: `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` metodunu kullanın ve bir `SolidFillColor` ayarlayın.

**Q: Grafiği bir veritabanı gibi harici bir veri kaynağına bağlayabilir miyim?**  
A: Evet. JDBC ile verileri alın, ardından kaydetmeden önce çalışma kitabı hücrelerini programlı olarak doldurun.

## Sonuç

Artık **grafik ekleme** konusunda Java sunumunda nasıl yapılacağını, verileri yapılandırmayı, 3D dönüşü özelleştirmeyi, seri çakışmasını ayarlamayı ve son dosyayı kaydetmeyi öğrendiniz. Bu bilgi, rapor oluşturmayı otomatikleştirmenizi, tutarlı bir marka kimliği oluşturmanızı ve veri odaklı sunumları manuel çaba olmadan sunmanızı sağlar. Efsane, eksen, tema gibi daha derin özelleştirmeler için resmi belgelerdeki tam yetenekleri keşfedin.

Daha gelişmiş özellikler ve özelleştirme seçenekleri için [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/) adresine bakın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-03-20  
**Test Edilen:** Aspose.Slides for Java 25.4 (JDK 16)  
**Yazar:** Aspose