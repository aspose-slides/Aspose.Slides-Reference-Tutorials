---
"date": "2025-04-17"
"description": "Java için Aspose.Slides'ı kullanarak dinamik dağılım grafikleri oluşturmayı öğrenin. Özelleştirilebilir grafik özellikleriyle sunumlarınızı geliştirin."
"title": "Aspose.Slides ile Java'da Dağılım Grafikleri Oluşturun ve Özelleştirin"
"url": "/tr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides ile Java'da Dağılım Grafikleri Oluşturun ve Özelleştirin

Java ile Aspose.Slides'ı kullanarak dinamik dağılım grafikleri ekleyerek sunumlarınızı geliştirin. Bu kapsamlı eğitim, dizinleri ayarlama, sunumları başlatma, dağılım grafikleri oluşturma, grafik verilerini yönetme, seri türlerini ve işaretleyicileri özelleştirme ve çalışmanızı kaydetme konusunda size rehberlik edecektir; hepsi de kolaylıkla.

**Ne Öğreneceksiniz:**
- Sunum dosyalarını depolamak için bir dizin ayarlama
- Aspose.Slides kullanarak sunumları başlatma ve düzenleme
- Slaytlarda dağılım grafikleri oluşturma
- Grafik serilerine veri ekleme ve yönetme
- Grafik serisi türlerini ve işaretleyicilerini özelleştirme
- Sununuzu değişikliklerle kaydetme

Öncelikle gerekli ön koşullara sahip olduğunuzdan emin olarak başlayalım.

## Ön koşullar

Bu eğitimi takip edebilmek için şunlara sahip olduğunuzdan emin olun:
- **Java için Aspose.Slides**: Sürüm 25.4 veya üzeri gereklidir.
- **Java Geliştirme Kiti (JDK)**: JDK 8 veya üzeri gereklidir.
- Temel Java programlama bilgisi ve Maven veya Gradle derleme araçlarına aşinalık.

## Java için Aspose.Slides Kurulumu

Kodlamaya başlamadan önce, aşağıdaki yöntemlerden birini kullanarak Aspose.Slides'ı projenize entegre edin:

### Usta
Bu bağımlılığı şuraya ekleyin: `pom.xml` dosya:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Bu satırı şuraya ekleyin: `build.gradle` dosya:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatif olarak, Java için en son Aspose.Slides'ı şu adresten indirin: [Aspose Sürümleri](https://releases.aspose.com/slides/java/).

#### Lisans Edinimi
- **Ücretsiz Deneme**: Özellikleri keşfetmek için 30 günlük ücretsiz denemeyle başlayın.
- **Geçici Lisans**:Uzun süreli testler için geçici lisans alın.
- **Satın almak**:Tam erişim ve destek için lisans satın alın.

Şimdi, aşağıda gösterildiği gibi gerekli içe aktarımları ekleyerek Aspose.Slides'ı Java uygulamanızda başlatın.

## Uygulama Kılavuzu

### Dizin Kurulumu
Öncelikle sunum dosyalarını depolamak için dizinimizin mevcut olduğundan emin olun. Bu adım dosya kaydetme sırasında hataları önler.

#### Eğer Dizin Yoksa Oluşturun
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Dizin oluştur
    new File(dataDir).mkdirs();
}
```
Bu kod parçacığı belirtilen bir dizini kontrol eder ve mevcut değilse oluşturur. `File.exists()` varlığını doğrulamak ve `File.mkdirs()` dizinler oluşturmak için.

### Sunum Başlatma

Daha sonra dağılım grafiğini ekleyeceğiniz sunum nesnenizi başlatın.

#### Sununuzu Başlatın
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Burada, `new Presentation()` boş bir sunum oluşturur. Doğrudan üzerinde çalışmak için ilk slayta erişiriz.

### Grafik Oluşturma
Başlattığımız slaydımızda bir dağılım grafiği oluşturmak sıradaki adım.

#### Slayda Dağılım Grafiği Ekle
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Bu kod parçacığı ilk slayta düzgün çizgilere sahip bir dağılım grafiği ekler. Parametreler grafiğin konumunu ve boyutunu tanımlar.

### Grafik Veri Yönetimi
Şimdi mevcut serileri temizleyip yenilerini ekleyerek grafik verilerimizi yönetelim.

#### Grafik Serisini Yönet
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Tabloya yeni seriler ekleniyor
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Bu bölüm mevcut verileri temizler ve dağılım grafiğimize iki yeni seri ekler.

### Dağılım Serileri için Veri Noktası Ekleme
Verilerimizi görselleştirmek için dağılım grafiğindeki her seriye noktalar ekliyoruz.

#### Veri Noktaları Ekle
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Biz kullanıyoruz `addDataPointForScatterSeries()` ilk serimize veri noktaları eklemek için. Parametreler X ve Y değerlerini tanımlar.

### Seri Türü ve İşaretleyici Değişikliği
Her serideki işaretçilerin türünü ve stilini değiştirerek grafiğinizin görünümünü özelleştirin.

#### Seriyi Özelleştir
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// İkinci seriyi değiştirme
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Bu değişiklikler, düz çizgiler ve işaretçiler kullanmak için seri türünü ayarlar. Ayrıca görsel ayrım için işaretçi boyutunu ve sembolünü de ayarladık.

### Sunum Kaydediliyor
Son olarak sunumunuzu yaptığınız tüm değişikliklerle kaydedin.

#### Sununuzu Kaydedin
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Kullanmak `SaveFormat.Pptx` Dosyanızı kaydetmek için PowerPoint biçimini belirtmek için. Bu adım tüm değişiklikleri korumak için çok önemlidir.

## Pratik Uygulamalar
İşte gerçek dünyadan bazı kullanım örnekleri:
1. **Finansal Analiz**: Hisse senedinin zaman içindeki eğilimlerini görüntülemek için dağılım grafiklerini kullanın.
2. **Bilimsel Araştırma**: Analiz için deneysel veri noktalarını temsil eder.
3. **Proje Yönetimi**: Kaynak tahsisini ve ilerleme ölçümlerini görselleştirin.

Aspose.Slides'ı sisteminize entegre etmek, rapor oluşturmayı otomatikleştirmenize, üretkenliği ve doğruluğu artırmanıza olanak tanır.

## Performans Hususları
En iyi performans için:
- Sunuları kaydettikten sonra imha ederek bellek kullanımını yönetin.
- Büyük veri kümeleri için verimli veri yapıları kullanın.
- Döngüler içindeki kaynak yoğun işlemleri en aza indirin.

En iyi uygulamalar, karmaşık grafik işlemlerinde bile sorunsuz yürütmeyi garanti eder.

## Çözüm
Bu eğitimde, dizinleri ayarlamayı, Aspose.Slides sunumlarını başlatmayı, dağılım grafikleri oluşturmayı ve özelleştirmeyi, seri verilerini yönetmeyi, işaretçileri değiştirmeyi ve çalışmanızı kaydetmeyi öğrendiniz. Aspose.Slides yeteneklerini daha fazla keşfetmek için animasyon ve slayt geçişleri gibi daha gelişmiş özelliklere dalmayı düşünün.

**Sonraki Adımlar**: Farklı grafik türlerini deneyin veya bu teknikleri daha büyük bir Java projesine entegre edin.

## SSS

### İşaretçilerin rengini nasıl değiştirebilirim?
İşaretçi rengini değiştirmek için şunu kullanın: `series.getMarker().getFillFormat().setFillColor(ColorObject)`, Neresi `ColorObject` İstediğiniz renktir.

### Bir dağılım grafiğine ikiden fazla seri ekleyebilir miyim?
Evet, yeni seriler ve veri noktaları ekleme sürecini tekrarlayarak ihtiyacınız olduğu kadar çok seri ekleyebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}