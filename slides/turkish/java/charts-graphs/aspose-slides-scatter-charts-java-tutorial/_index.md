---
date: '2026-02-24'
description: Aspose.Slides for Java kullanarak dağılım grafiğini nasıl özelleştireceğinizi
  öğrenin. Bu rehber, sunumlarınızda dinamik dağılım grafiklerini oluşturma, stil
  verme ve kaydetme sürecinde size yol gösterir.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Java'da Aspose ile Dağılım Grafiğini Özelleştirme
url: /tr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose ile Dağılım Grafiğini Özelleştirme

Bu öğreticide, güçlü Aspose.Slides for Java kütüphanesi ile **customize scatter chart aspose** nasıl özelleştirileceğini öğreneceksiniz. Projenizi kurma, bir dağılım grafiği oluşturma, seri tiplerini ve işaretçileri ayarlama ve sonunda sunumu kaydetme adımlarını göstereceğiz. Sonunda, programlı olarak profesyonel görünümlü dağılım grafiklerini oluşturabilecek ve her görsel detayı markanıza veya raporlama ihtiyaçlarınıza göre özelleştirebileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (v25.4+).  
- **Hangi Java sürümü destekleniyor?** JDK 8 veya üzeri.  
- **İşaretçi şekillerini değiştirebilir miyim?** Evet – `MarkerStyleType` kullanarak yıldız, daire vb. seçebilirsiniz.  
- **Dosyayı nasıl kaydederim?** `pres.save("output.pptx", SaveFormat.Pptx)` çağırın.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme yeterlidir; üretim için ticari lisans gerekir.

## “customize scatter chart aspose” nedir?
Aspose ile bir dağılım grafiğini özelleştirmek, grafiğin verilerini, görünümünü ve davranışını programlı olarak tanımlamak anlamına gelir—nokta koordinatlarından işaretçi sembollerine kadar—PowerPoint'i manuel olarak açmadan. Bu yaklaşım, otomatik raporlama, veri odaklı sunumlar veya tekrarlanabilir, yüksek kaliteli görselleştirmelere ihtiyaç duyulan tüm senaryolar için idealdir.

## Aspose.Slides ile dağılım grafiklerini neden özelleştirirsiniz?
- **Tam kontrol** – seri tiplerini, işaretçi stillerini, renkleri ve daha fazlasını Java kodu ile değiştirin.  
- **Otomasyon** – panolar veya toplu raporlar için anında onlarca grafik üretin.  
- **Çapraz platform** – Java'yı destekleyen herhangi bir işletim sisteminde çalışır, Office kurulumu gerekmez.  
- **Performans** – büyük veri setlerini verimli şekilde işleyen hafif bir API.

## Önkoşullar

Takip edebilmek için şunlara sahip olun:

- **Aspose.Slides for Java** (v25.4 veya sonrası).  
- **Java Development Kit (JDK)** 8 + yüklü.  
- Bağımlılık yönetimi için Maven veya Gradle (veya JAR'ı manuel olarak indirebilirsiniz).  
- Temel Java bilgisi ve tercih ettiğiniz yapı aracına aşinalık.

## Aspose.Slides for Java'ı Kurma

Kütüphaneyi projenize aşağıdaki yöntemlerden birini kullanarak entegre edin.

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

Veya en son sürümü [Aspose Releases](https://releases.aspose.com/slides/java/) adresinden alın.

#### Lisans Alımı
- **Ücretsiz Deneme** – 30 günlük değerlendirme.  
- **Geçici Lisans** – uzatılmış test süresi.  
- **Tam Lisans** – üretim kullanımı ve premium destek.

## Aspose ile Dağılım Grafiğini Özelleştirme Adım Adım Kılavuzu

### 1️⃣ Sunum dosyalarınız için bir klasör hazırlayın
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Neden önemli:* Çıktı klasörünün var olduğundan emin olmak, PPTX'i daha sonra kaydettiğinizde `FileNotFoundException` oluşmasını önler.

### 2️⃣ Yeni bir sunum oluşturun ve ilk slaytı alın
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Yeni bir `Presentation` size temiz bir tuval sağlar; grafiği yerleştireceğimiz yer ilk slayttır.

### 3️⃣ Yumuşak çizgili bir dağılım grafiği ekleyin
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` yumuşak çizgili bir dağılım grafiği oluşturur, trend görselleştirmesi için mükemmeldir.

### 4️⃣ Varsayılan serileri temizleyin ve kendi serinizi ekleyin
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Varsayılan seriyi kaldırmak, gösterdiğiniz veriler üzerinde tam kontrol sağlar.

### 5️⃣ İlk seriyi veri noktalarıyla doldurun
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` bir X‑değer hücresi ve bir Y‑değer hücresi alır, dağılım grafiğini nokta nokta oluşturur.

### 6️⃣ Seri tipini ve işaretçi görünümünü özelleştirin
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Burada **customize scatter chart aspose** yaparak düz çizgilere geçiyor, işaretçileri büyütüyor ve görsel netlik için farklı semboller (yıldız vs. daire) seçiyoruz.

### 7️⃣ Sunumu kaydedin
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
`Pptx` olarak kaydetmek, tüm grafik özelleştirmelerini korur ve dosyayı paylaşım veya daha fazla düzenleme için hazır hâle getirir.

## Özelleştirilmiş Dağılım Grafiklerinin Yaygın Kullanım Alanları
- **Finansal panolar** – hisse fiyatını hacimle karşılaştırın.  
- **Bilimsel araştırma** – deneysel ölçümleri hata işaretçileriyle gösterin.  
- **Proje yönetimi** – görevler arasında planlanan ve gerçekleşen çabayı karşılaştırın.  

## Performans İpuçları
- `Presentation` nesnesini (`pres.dispose()`) kaydettikten sonra yerel kaynakları serbest bırakmak için yok edin.  
- Büyük veri setleri için, önce çalışma kitabını doldurun ve ardından serileri bağlayın, böylece tekrar eden UI yenilemelerinden kaçının.  
- Birçok seri eklerken tek bir `IChartDataWorkbook` örneğini yeniden kullanın.

## Sık Sorulan Sorular

### İşaretçilerin rengini nasıl değiştiririm?
`series.getMarker().getFillFormat().setFillColor(Color)` kullanın; burada `Color`, `java.awt.Color` sınıfının bir örneğidir (ör. `Color.RED`).

### Bir dağılım grafiğine iki seriden fazla ekleyebilir miyim?
Kesinlikle. Her ek seri için `chart.getChartData().getSeries().add(...)` çağrısını tekrarlayın ve veri noktalarını buna göre doldurun.

### Her seri için özel bir lejand ayarlamak mümkün mü?
Evet. Bir seri oluşturduktan sonra, varsayılan adı geçersiz kılmak için `series.getLegend().setText("Your Legend Text")` çağrısını yapın.

### Grafiği PPTX yerine görüntü olarak nasıl dışa aktarabilirim?
Grafiği yapılandırdıktan sonra `chart.getImage().save("chart.png", ImageFormat.Png)` çağrısını yapın. Bu, bağımsız bir PNG dosyası sağlar.

### Dağılım noktalarını animasyon eklemem gerekirse ne olur?
Aspose.Slides animasyon efektlerini destekler. Grafiğe veya tek tek serilere giriş ya da vurgu animasyonları eklemek için `chart.getTimeline().getMainSequence().addEffect(...)` kullanın.

---

**Son Güncelleme:** 2026-02-24  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16 sınıflandırıcı)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}