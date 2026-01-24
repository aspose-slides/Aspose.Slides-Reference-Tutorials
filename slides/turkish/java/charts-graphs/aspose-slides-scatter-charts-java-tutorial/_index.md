---
date: '2026-01-24'
description: Aspose.Slides kullanarak Java’da dağılım grafiği oluşturma, veri noktaları
  ekleme ve birden fazla seri dağılım grafiğiyle çalışma için adım adım rehber.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Aspose.Slides ile Java'da Dağılım Grafiği Oluşturma – Özelleştir ve Kaydet
url: /tr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides ile Java Dağılım Grafiği Oluşturma

Bu öğreticide, sıfırdan **create scatter chart java** projeleri oluşturacak, dağılım veri noktaları ekleyecek ve birden fazla seri dağılım grafiğiyle nasıl çalışılacağını öğreneceksiniz—tüm bunlar Aspose.Slides for Java kullanılarak yapılacak. Dizin kurulumunu, sunum başlatmayı, grafik oluşturmayı, veri yönetimini, işaretçi özelleştirmesini ve sonunda sunumu kaydetmeyi adım adım göstereceğiz.

**What You'll Learn**
- Sunum dosyalarını depolamak için bir dizin ayarlama  
- Aspose.Slides kullanarak sunumları başlatma ve manipüle etme  
- Bir slayta dağılım grafiği oluşturma  
- Her seri için veri noktalarını ekleme ve yönetme  
- Seri tiplerini, işaretçileri özelleştirme ve birden fazla seri dağılım grafiğini yönetme  
- Tamamlanmış sunumu kaydetme  

Gereksinimlerle başlayalım.

## Hızlı Yanıtlar
- **What is the primary library?** Aspose.Slides for Java  
- **Which Java version is required?** JDK 8 or higher (JDK 16 recommended)  
- **Can I add more than two series?** Yes – you can add any number of series to a scatter chart  
- **How do I change marker colors?** Use `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Is a license needed for production?** Yes, a commercial license removes evaluation limits  

## Önkoşullar

Bu öğreticiyi takip edebilmek için aşağıdakilere sahip olduğunuzdan emin olun:
- **Aspose.Slides for Java** – sürüm 25.4 veya üzeri.  
- **Java Development Kit (JDK)** – JDK 8 or newer.  
- Temel Java bilgisi ve Maven ya da Gradle hakkında aşinalık.  

## Aspose.Slides for Java Kurulumu

Aspose.Slides'ı projenize aşağıdaki yöntemlerden biriyle entegre edin.

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

Veya en son paketi [Aspose Releases](https://releases.aspose.com/slides/java/) adresinden indirin.

#### Lisans Edinimi
- **Free Trial** – 30‑day evaluation.  
- **Temporary License** – Extended testing.  
- **Commercial License** – Full production use.

Şimdi koda dalalım.

## Uygulama Rehberi

### Adım 1: Dizin Kurulumu
İlk olarak, sunumun hatasız kaydedilebilmesi için çıktı klasörünün mevcut olduğundan emin olun.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Adım 2: Sunum Başlatma
Yeni bir sunum oluşturun ve ilk slaytı alın.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Adım 3: Dağılım Grafiği Ekleme
Slayta yumuşak çizgili bir dağılım grafiği ekleyin.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Adım 4: Grafik Verilerini Yönetme (Temizleme ve Seri Ekleme)
Varsayılan serileri temizleyin ve **multiple series scatter chart** için kendi serimizi ekleyin.

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

### Adım 5: Dağılım Veri Noktaları Ekleme
**add data points scatter** kullanarak her seriyi X‑Y değerleriyle doldurun.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Adım 6: Seri Tiplerini ve İşaretçileri Özelleştirme
Görsel stili ayarlayın—işaretçili düz çizgilere geçin ve farklı işaretçi sembolleri belirleyin.

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

### Adım 7: Sunumu Kaydetme
Dosyayı diske kaydedin.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Pratik Uygulamalar
- **Financial Analysis** – Birden fazla seri dağılım grafiği ile hisse fiyat hareketlerini çizin.  
- **Scientific Research** – Hassas veri temsili için add data points scatter kullanarak deneysel ölçın.  
ınıının; stilleri veri eklemesinden sonra uygulayın.  

## Yaygın Sorunlar ve Çözümler

| Sorun | Çözüm |
|-------|----------|
| **Grafik boş görünüyor** | Veri noktalarının doğru seriye eklendiğini ve çalışma kitabı indekslerinin eşleştiğini doğrulayın. |
| **İşaretçiler görünmüyor** | `series.getMarker().setSize()` değerinin 0'dan büyük bir değere ayarlandığından ve işaretçi sembolünün tanımlı olduğundan emin olun. |
| **Büyük grafiklerde OutOfMemoryError** | Kaydettikten sonra `pres.dispose()` kullanın ve JVM yığın boyutunu (`-Xmx`) artırmayı düşün. Repeat4) for each additional series you need.

### Grafiği bir görüntü olarak dışa akt.

### Aspose.Slides dağılım noktalarında etkileşimli araç ipuçlarını destekliyor mu?
While PowerPoint itself doesn’t provide runtime tooltips, you can embed data labels using `series.getDataPoints().get_Item(i).getLabel().setText("Your text")`.

### Dağılım serisini nasıl canlandırabilirim?
Use `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` to add a simple appear animation.

---

**Son Güncelleme:** 2026-01-24  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}