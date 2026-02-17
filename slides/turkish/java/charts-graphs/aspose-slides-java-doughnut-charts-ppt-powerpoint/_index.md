---
date: '2026-02-17'
description: Aspose.Slides for Java kullanarak PowerPoint'te halka grafik oluşturmayı
  ve grafik veri noktalarını programlı olarak eklemeyi öğrenin. Kolay adımları ve
  kod örneklerini izleyin.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Aspose.Slides for Java ile PowerPoint'te halka grafiği oluştur
url: /tr/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java ile Donut Grafikli PowerPoint Oluşturma

## Giriş
Etkileyici sunumlar oluşturmak çoğu zaman yalnızca metin ve görsellerden daha fazlasını gerektirir; grafikler, verileri etkili bir şekilde görselleştirerek hikâye anlatımını büyük ölçüde güçlendirebilir. Ancak birçok geliştirici, dinamik grafik özelliklerini programlı olarak PowerPoint dosyalarına entegre etmekte zorlanır. Bu öğreticide **Aspose.Slides for Java** kullanarak **donut grafikli PowerPoint** oluşturmayı göstereceğiz—esneklik ve kullanım kolaylığını bir araya getiren güçlü bir araç.

**Öğrenecekleriniz:**
- Aspose.Slides for Java ile bir sunumu nasıl başlatacağınızı
- Slaytlarınıza donut grafik eklemek için adım‑adım kılavuz
- Veri noktalarını yapılandırma ve etiket özelliklerini özelleştirme
- Değiştirilmiş sunumu yüksek doğrulukla kaydetme

Bu özellikleri nasıl kullanarak sunumlarınızı geliştirebileceğinizi keşfedelim. Başlamadan önce temel Java programlama kavramlarına aşina olduğunuzdan emin olun.

## Hızlı Yanıtlar
- **Donut grafikli PowerPoint'i hangi kütüphane oluşturur?** Aspose.Slides for Java
- **Grafik veri noktalarını programlı olarak ekleyebilir miyim?** Evet, grafik API'si kullanılarak
- **Üretim için lisansa ihtiyacım var mı?** Geçerli bir Aspose.Slides lisansı gereklidir
- **Hangi Java sürümleri destekleniyor?** Java 8 ve sonrası (JDK 16 sınıflandırıcısı gösterilmiştir)
- **Kaç seriyi ekleyebilirim?** Örnek 15 seriye kadar ekliyor, ihtiyacınıza göre ayarlayabilirsiniz

## PowerPoint'te donut grafik nedir?
Donut grafik, ortası boş bir pasta grafiği çeşididir ve birden fazla veri serisini kompakt, görsel olarak çekici bir şekilde göstermenizi sağlar. Tasarımı temiz tutarken parça‑bütün ilişkilerini göstermek için idealdir.

## Aspose.Slides for Java ile donut grafik oluşturmanın avantajları
- **Grafik görünümü, veri ve düzeni üzerinde tam kontrol** – PowerPoint açmadan
- **COM etkileşimi yok** – Java destekleyen herhangi bir platformda çalışır
- **Büyük sunumlar üretmek veya web servisleriyle bütünleştirmek için yüksek performans**
- **Patlama, delik boyutu, dilim açıları ve etiket biçimlendirme** gibi zengin özelleştirme seçenekleri

## Ön Koşullar
- Java programlama temelleri.
- IntelliJ IDEA veya Eclipse gibi bir IDE.
- Bağımlılık yönetimi için Maven veya Gradle.
- Geçerli bir Aspose.Slides for Java lisansı (ücretsiz deneme mevcut).

## Aspose.Slides for Java Kurulumu
Projenize uygun bağımlılık yöneticisini seçin.

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

Doğrudan indirmek isterseniz, [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) sayfasını ziyaret edin.

### Lisans Edinimi
Aspose.Slides özelliklerini keşfetmek için ücretsiz bir deneme ile başlayabilirsiniz. Uzun vadeli kullanım için bir lisans satın alın veya [Aspose'un web sitesinden](https://purchase.aspose.com/temporary-license/) geçici bir lisans talep edin. Ortamınızı ayarlama ve Aspose.Slides'i uygulamanıza başlatma talimatlarını izleyin.

## Aspose.Slides for Java ile donut grafikli PowerPoint nasıl oluşturulur
Aşağıda eksiksiz, adım‑adım bir kılavuz yer alıyor. Her kod bloğu, hemen öncesinde açıklanmıştır, böylece ne olduğunu tam olarak bilirsiniz.

### Adım 1: Sunumu başlatma
Mevcut bir PPTX dosyasını yükleyin veya yenisini oluşturun. Bu, slayt koleksiyonunu sonraki değişiklikler için hazırlar.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Adım 2: Slayta donut grafik ekleme
Grafik şekli ekleyin, varsayılan serileri/kategorileri temizleyin ve temel görsel özellikleri ayarlayın.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Adım 3: Grafik veri noktalarını ekleme ve etiketleri özelleştirme
Kategorileri doldurun, her seri için veri noktaları ekleyin ve etiket görünümünü ince ayarlayın. İşte **add chart data points** anahtar kelimesinin devreye girdiği kısım.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Adım 4: Güncellenen sunumu kaydetme
Değişiklikleri yeni bir PPTX dosyasına kalıcı olarak kaydedin.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Pratik Uygulamalar
Donut grafikler çeşitli gerçek‑dünya senaryolarında kullanılabilir:
- **Finansal Raporlar:** Bütçe tahsislerini veya harcama dağılımlarını görselleştirin.
- **Pazar Analizi:** Rakipler arasındaki pazar payı dağılımını gösterin.
- **Anket Sonuçları:** Kategorik anket verilerini kompakt bir biçimde sunun.
- **Gösterge Paneli Oluşturma:** Veritabanı sorgularıyla birleştirerek canlı güncellenen slaytlar üretin.

## Performans Düşünceleri
- **Kaynakları serbest bırakın**: İşiniz bittiğinde `pres.dispose()` çağırarak yerel belleği boşaltın.
- **Grafik sayısını sınırlayın**: Yüzlerce grafik eklemek bellek kullanımını artırabilir; gerekirse toplu işleyin.
- **Akış kullanın**: Büyük veri setleri için, verileri bellekteki diziler yerine doğrudan akışlardan doldurun.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|------|
| **Grafik boş görünüyor** | Veri hücreleri doğru şekilde doldurulmamış | `workBook.getCell(...)` referanslarının doğru satır/sütun indekslerine işaret ettiğini doğrulayın. |
| **Etiketler çakışıyor** | Sınırlı alanda çok fazla kategori | `DoughnutHoleSize` değerini artırın veya `FirstSliceAngle` ayarını değiştirin. |
| **OutOfMemoryError** | Kaynakları serbest bırakmadan büyük sunumlar | Kaydetme sonrası `pres.dispose()` çağırın ve JVM yığın boyutunu artırmayı düşünün. |

## Sık Sorulan Sorular

**S: Aspose.Slides for Java'yi ticari uygulamalarda kullanabilir miyim?**  
C: Evet, ancak geçerli bir ticari lisansa ihtiyacınız var. Değerlendirme için ücretsiz bir deneme mevcuttur.

**S: 15'ten fazla seri ekleyebilir miyim?**  
C: “Donut Grafik Ekle” adımındaki döngü sınırını artırın ve veri çalışma kitabınızın yeterli satıra sahip olduğundan emin olun.

**S: Oluşturduktan sonra donut delik boyutunu değiştirmek mümkün mü?**  
C: Evet, kaydetmeden önce istediğiniz noktada `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` çağırabilirsiniz.

**S: Grafiği PPTX yerine bir görüntü olarak dışa aktarabilir miyim?**  
C: Kesinlikle. `chart.getImage()` metodunu kullanarak döndürülen `java.awt.image.BufferedImage`'ı tercih ettiğiniz formatta kaydedin.

**S: Aspose.Slides animasyonlu grafikleri destekliyor mu?**  
C: Animasyon, `ISlide.getTimeline()` API'si ile eklenebilir, ancak bu öğreticinin kapsamı dışındadır.

## Sonuç
Artık Aspose.Slides for Java ile **donut grafikli PowerPoint** dosyaları oluşturmak, **grafik veri noktalarını eklemek**, etiketleri özelleştirmek ve performans konularını yönetmek için eksiksiz, üretim‑hazır bir yönteme sahipsiniz. Farklı renkler, veri kaynakları ve grafik türleriyle deneyler yaparak sunumlarınızı gerçekten öne çıkarın.

---

**Son Güncelleme:** 2026-02-17  
**Test Edilen Sürüm:** Aspose.Slides for Java 25.4 (JDK 16 sınıflandırıcısı)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}