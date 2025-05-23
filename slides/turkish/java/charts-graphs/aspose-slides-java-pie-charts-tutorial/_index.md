---
"date": "2025-04-17"
"description": "Java için Aspose.Slides kullanarak pasta grafiklerinin nasıl oluşturulacağını ve özelleştirileceğini öğrenin. Bu eğitim kurulumdan gelişmiş özelleştirmeye kadar her şeyi kapsar."
"title": "Aspose.Slides ile Java'da Pasta Grafikleri Oluşturma Kapsamlı Bir Kılavuz"
"url": "/tr/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java için Aspose.Slides ile Pasta Grafikleri Oluşturma: Eksiksiz Bir Eğitim

## giriiş
Etkili bilgiler sunmak için dinamik ve görsel olarak çekici sunumlar oluşturmak çok önemlidir. Java için Aspose.Slides ile pasta grafikleri gibi karmaşık grafikleri slaytlarınıza sorunsuz bir şekilde entegre edebilir ve veri görselleştirmesini zahmetsizce geliştirebilirsiniz. Bu kapsamlı kılavuz, Aspose.Slides Java kullanarak pasta grafiği oluşturma ve özelleştirme sürecinde size yol gösterecek ve yaygın sunum zorluklarını kolaylıkla çözecektir.

**Ne Öğreneceksiniz:**
- Bir sunumu başlatma ve slayt ekleme.
- Slaydınızda pasta grafiği oluşturma ve yapılandırma.
- Grafik başlıklarını, veri etiketlerini ve renklerini ayarlama.
- Performansı optimize etmek ve kaynakları etkin bir şekilde yönetmek.
- Maven veya Gradle kullanarak Aspose.Slides'ı Java projelerine entegre etme.

Öncelikle takip etmeniz gereken tüm gerekli araç ve bilgiye sahip olduğunuzdan emin olarak başlayalım!

## Ön koşullar
Bu eğitime başlamadan önce aşağıdaki kurulumların hazır olduğundan emin olun:

### Gerekli Kitaplıklar, Sürümler ve Bağımlılıklar
- **Java için Aspose.Slides**: 25.4 veya üzeri bir sürüme sahip olduğunuzdan emin olun.
- **Java Geliştirme Kiti (JDK)**: Sürüm 16 veya üzeri gereklidir.

### Çevre Kurulum Gereksinimleri
- Java'nın kurulu ve yapılandırılmış olduğu bir geliştirme ortamı.
- IntelliJ IDEA, Eclipse veya NetBeans gibi bir Entegre Geliştirme Ortamı (IDE).

### Bilgi Önkoşulları
- Java programlamanın temel bilgisi.
- Bağımlılık yönetimi için Maven veya Gradle'a aşinalık.

## Java için Aspose.Slides Kurulumu
Java projelerinizde Aspose.Slides kullanmaya başlamak için, kütüphaneyi bir bağımlılık olarak eklemeniz gerekir. Bunu farklı derleme araçlarını kullanarak nasıl yapabileceğiniz aşağıda açıklanmıştır:

**Usta**
Bu parçacığı şuraya ekleyin: `pom.xml` dosya:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Aşağıdakileri ekleyin: `build.gradle` dosya:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme**
Bir derleme aracı kullanmayı tercih etmiyorsanız, en son sürümü şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

### Lisans Edinme Adımları
- **Ücretsiz Deneme**: Aspose.Slides özelliklerini keşfetmek için ücretsiz denemeye başlayın.
- **Geçici Lisans**: Sınırlama olmaksızın uzun süreli kullanım için geçici lisans edinin.
- **Satın almak**: Uzun vadeli erişime ihtiyacınız varsa satın almayı düşünün.

**Temel Başlatma ve Kurulum**
Aspose.Slides'ı kullanmaya başlamak için yeni bir sunum nesnesi oluşturarak projenizi başlatın:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Uygulama Kılavuzu
Şimdi pasta grafiğinin eklenmesi ve özelleştirilmesi sürecini yönetilebilir adımlara bölelim.

### Sunumu ve Slaydı Başlat
Yeni bir sunum ayarlayarak ve ilk slayda erişerek başlayın. Bu, grafikler oluşturmak için tuvalinizdir:
```java
import com.aspose.slides.*;

// Yeni bir sunum örneği oluşturun.
Presentation presentation = new Presentation();
// Sunumdaki ilk slayda erişin.
islide slides = presentation.getSlides().get_Item(0);
```

### Slayda Pasta Grafiği Ekle
Belirtilen konuma varsayılan veri kümesiyle bir pasta grafiği ekleyin:
```java
import com.aspose.slides.*;

// (100, 100) konumuna (400, 400) boyutunda bir pasta grafiği ekleyin.
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Grafik Başlığını Ayarla
Başlığı ayarlayıp ortalayarak grafiğinizi özelleştirin:
```java
import com.aspose.slides.*;

// Pasta grafiğine bir başlık ekleyin.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Seriler için Veri Etiketlerini Yapılandırın
Veri etiketlerinin açıklık açısından değerleri gösterdiğinden emin olun:
```java
import com.aspose.slides.*;

// İlk serideki veri değerlerini göster.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Grafik Veri Çalışma Sayfasını Hazırla
Mevcut serileri ve kategorileri temizleyerek grafiğinizin veri çalışma sayfasını ayarlayın:
```java
import com.aspose.slides.*;

// Grafik veri çalışma kitabını hazırlayın.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Kategorileri Tabloya Ekle
Pasta grafiğiniz için kategorileri tanımlayın:
```java
import com.aspose.slides.*;

// Yeni kategoriler ekleyin.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Seri Ekle ve Veri Noktalarını Doldur
Bir seri oluşturun ve onu veri noktalarıyla doldurun:
```java
import com.aspose.slides.*;

// Yeni bir seri ekleyin ve ismini belirleyin.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Seri Renklerini ve Kenarlıklarını Özelleştir
Renkleri ayarlayarak ve kenarlıkları özelleştirerek görsel çekiciliği artırın:
```java
import com.aspose.slides.*;

// Seri sektörleri için çeşitli renkler ayarlayın.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Farklı renk ve stillere sahip diğer veri noktaları için işlemi tekrarlayın.
```

### Özel Veri Etiketlerini Yapılandırın
Her veri noktası için etiketleri ince ayarlayın:
```java
import com.aspose.slides.*;

// Özel etiketleri yapılandırın.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Etiketler için lider çizgilerini etkinleştirin.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Döndürme Açısını Ayarlayın ve Sunumu Kaydedin
Döndürme açısını ayarlayarak ve sunumu kaydederek pasta grafiğinizi sonlandırın:
```java
import com.aspose.slides.*;

// Dönüş açısını ayarlayın.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Sunumu bir dosyaya kaydedin.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde, Java için Aspose.Slides kullanarak pasta grafikleri oluşturmayı ve özelleştirmeyi öğrendiniz. Bu adımları izleyerek sunumlarınızı görsel olarak çekici veri görselleştirmeleriyle zenginleştirebilirsiniz. Herhangi bir sorunuz varsa veya daha fazla yardıma ihtiyacınız varsa, bize ulaşmaktan çekinmeyin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}