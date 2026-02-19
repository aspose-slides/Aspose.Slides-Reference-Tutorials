---
date: '2026-02-19'
description: Aspose.Slides ile Java’da bir pasta grafiği oluşturmayı, pasta grafiği
  renklerini özelleştirmeyi, grafik serileri eklemeyi, grafik veri çalışma sayfası
  ile çalışmayı ve dönüş açısını ayarlamayı öğrenin.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Java'da Aspose.Slides ile Pasta Grafik Renklerini Özelleştirme – Tam Bir Rehber
url: /tr/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java için Aspose.Slides ile Pasta Grafikler Oluşturma: Tam Bir Eğitim

## Giriş
Dinamik ve görsel açıdan çekici sunumlar oluşturmak, etkili bilgi sunumu için çok önemlidir. Aspose.Slides for Java ile, pasta grafikleri gibi karmaşık grafikleri slaytlarınıza sorunsuz bir şekilde entegre edebilir, **pasta grafik renklerini özelleştirebilir** ve veri görselleştirmesini zahmetsizce artırabilirsiniz. Bu kapsamlı rehber, Aspose.Slides Java kullanarak bir pasta grafiği oluşturma ve özelleştirme sürecini adım adım göstererek yaygın sunum sorunlarını kolayca çözmenize yardımcı olacaktır.

**Ne Öğreneceksiniz:**
- Bir sunumu başlatma ve slayt ekleme.
- Slaytınıza bir pasta grafik oluşturma ve yapılandırma.
- Grafik başlıklarını, veri etiketlerini ayarlama ve **pasta grafik renklerini özelleştirme**.
- Performansı optimize etme ve kaynakları etkili bir şekilde yönetme.
- Maven veya Gradle kullanarak Aspose.Slides'ı Java projelerine entegre etme.

Hadi başlayalım, takip edebilmeniz için gerekli tüm araç ve bilgilere sahip olduğunuzdan emin olun!

## Hızlı Yanıtlar
- **Bir sunumu başlatmak için birincil sınıf nedir?** `Presentation` from `com.aspose.slides`.
- **Bir slayta pasta grafik ekleyen yöntem hangisidir?** `addChart(ChartType.Pie, …)`.
- **Her dilim için farklı renkleri nasıl etkinleştirirsiniz?** Seriler grubunda `setColorVaried(true)` ayarlayın.
- **Pasta grafiğini döndürebilir misiniz?** Evet, grafik nesnesinde `setRotationAngle(double)` kullanın.
- **Üretim kullanımında lisansa ihtiyacım var mı?** Ticari dağıtımlar için bir Aspose.Slides lisansı gereklidir.

## “Pasta grafik renklerini özelleştirme” nedir?
Pasta grafik renklerini özelleştirmek, pastanın her dilimine farklı dolgu renkleri atamak anlamına gelir; bu, okunabilirliği ve görsel etkiyi artırır. Aspose.Slides'te bunu, farklı renkleri etkinleştirerek ve ardından bireysel veri noktaları için katı dolgu renkleri ayarlayarak elde edersiniz.

## Java için Aspose.Slides ile pasta grafik oluşturmayı neden kullanmalısınız?
- **Tam kontrol** grafik görünümü üzerinde, Microsoft Office'e ihtiyaç duymadan.
- **Çapraz platform** uyumluluğu – Windows, Linux ve macOS'ta çalışır.
- **Zengin API** veri bağlama, stil verme ve PPTX, PDF veya görüntülere dışa aktarma için.
- **Lisans esnekliği** – ücretsiz deneme ile başlayın ve tam özellik setine ihtiyacınız olduğunda yükseltin.

## Önkoşullar
Bu eğitime başlamadan önce, aşağıdaki kurulumun hazır olduğundan emin olun:

### Gerekli Kütüphaneler, Sürümler ve Bağımlılıklar
- **Aspose.Slides for Java**: sürüm 25.4 veya üzeri.
- **Java Development Kit (JDK)**: sürüm 16 veya üzeri.

### Ortam Kurulum Gereksinimleri
- Java yüklü ve yapılandırılmış bir geliştirme ortamı.
- IntelliJ IDEA, Eclipse veya NetBeans gibi bir Entegre Geliştirme Ortamı (IDE).

### Bilgi Önkoşulları
- Java programlamaya temel bir anlayış.
- Bağımlılık yönetimi için Maven veya Gradle konusunda aşinalık.

## Aspose.Slides for Java Kurulumu
Java projelerinizde Aspose.Slides'ı kullanmaya başlamak için kütüphaneyi bir bağımlılık olarak eklemeniz gerekir. İşte farklı yapı araçlarıyla bunu nasıl yapabileceğiniz:

**Maven**  
`pom.xml` dosyanıza bu kod parçacığını ekleyin:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle` dosyanıza aşağıdakini ekleyin:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme**  
Bir yapı aracı kullanmak istemiyorsanız, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Aspose.Slides özelliklerini keşfetmek için ücretsiz deneme ile başlayın.  
- **Geçici Lisans**: Sınırlama olmadan uzun süreli kullanım için geçici bir lisans edinin.  
- **Satın Alma**: Uzun vadeli erişime ihtiyacınız varsa satın almayı düşünün.

**Temel Başlatma ve Kurulum**  
Aspose.Slides'ı kullanmaya başlamak için, yeni bir sunum nesnesi oluşturarak projenizi başlatın:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Uygulama Kılavuzu
Şimdi bir pasta grafiği ekleme ve özelleştirme sürecini yönetilebilir adımlara bölelim.

### Sunumu ve Slaytı Başlatma
Yeni bir sunum ayarlayarak ve ilk slaytı erişerek başlayın. Bu, grafik oluşturmak için tuvalinizdir:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Slayta Pasta Grafik Ekleme
Belirtilen konuma varsayılan bir veri kümesiyle pasta grafik ekleyin:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Grafik Başlığını Ayarlama
Başlığı ayarlayarak ve ortalayarak grafiğinizi özelleştirin:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Seri İçin Veri Etiketlerini Yapılandırma
Açıklık için veri etiketlerinin değerleri gösterdiğinden emin olun:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Grafik Veri Çalışma Sayfasını Hazırlama
Mevcut serileri ve kategorileri temizleyerek grafiğinizin veri çalışma sayfasını ayarlayın:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Grafiğe Kategoriler Ekleme
Pasta grafiğiniz için kategorileri tanımlayın:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Seri Ekleme ve Veri Noktalarını Doldurma
Bir seri oluşturun ve veri noktalarıyla doldurun – burada **grafik serileri ekliyoruz**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Seri Renklerini ve Kenarlıklarını Özelleştirme
Renkleri ayarlayarak ve kenarlıkları özelleştirerek görsel çekiciliği artırın – bu doğrudan **pasta grafik renklerini özelleştirir**:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Özel Veri Etiketlerini Yapılandırma
Her veri noktası için etiketleri ince ayar yapın:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Döndürme Açısını Ayarlama ve Sunumu Kaydetme
Pasta grafiğinizi **döndürme açısını ayarlayarak** ve dosyayı kaydederek tamamlayın:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **Tüm dilimler aynı renkte görünüyor** | `setColorVaried(true)` çağrılmadı | Seri grubunda farklı renkleri etkinleştirdiğinizden emin olun. |
| **Veri etiketleri görünmüyor** | `showValue` bayrağı devre dışı | Uygun etiket formatında `setShowValue(true)` çağırın. |
| **Döndürme etkisi yok** | Eski bir Aspose.Slides sürümü kullanılıyor | Sürümü 25.4 veya üzeri olarak yükseltin. |
| **Çalışma zamanında lisans istisnası** | Eksik veya geçersiz lisans dosyası | `Presentation` nesnesini oluşturmadan önce lisansınızı `License license = new License(); license.setLicense("Aspose.Slides.lic");` kodu ile yükleyin. |

## Sıkça Sorulan Sorular

**S: Aspose.Slides Java lisansını nasıl elde edebilirim?**  
C: Aspose web sitesinden ücretsiz deneme talep edebilir, ardından kalıcı bir lisans satın alabilirsiniz. Ortak Sorunlar tablosunda gösterildiği gibi çalışma zamanında yükleyin.

**S: Bu kodu eski JDK sürümleriyle kullanabilir miyim?**  
C: API, JDK 16 veya üzeri gerektirir; eski sürümler desteklenmez.

**S: Grafiği PPTX yerine görüntü olarak dışa aktarmak mümkün mü?**  
C: Evet, render ettikten sonra `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` çağırın.

**S: Pasta grafiğine birden fazla seri eklemem gerekirse?**  
C: Pasta grafikleri genellikle tek bir seri gösterir; birden fazla seri için bunun yerine halka (doughnut) grafiği düşünün.

**S: Kütüphane Linux sunucularda çalışır mı?**  
C: Kesinlikle – Aspose.Slides for Java platform bağımsızdır ve uyumlu bir JDK ile herhangi bir işletim sisteminde çalışır.

---

**Son Güncelleme:** 2026-02-19  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}