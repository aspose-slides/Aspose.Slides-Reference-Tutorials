---
date: '2026-03-04'
description: Aspose.Slides for Java ile bir balon grafiğine özel hata çubukları eklemeyi
  öğrenin. Bu kılavuz, grafiği oluşturmayı, her nokta için hata çubuklarını yapılandırmayı
  ve sunumu kaydetmeyi kapsar.
keywords:
- Bubble Chart Java
- Custom Error Bars Aspose.Slides
- Java Data Visualization
title: Java'da Aspose.Slides Kullanarak Balon Grafiğine Özel Hata Çubukları Nasıl
  Eklenir
url: /tr/java/charts-graphs/create-bubble-chart-error-bars-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java’da Aspose.Slides Kullanarak Balon Grafiğine Özel Hata Çubukları Nasıl Eklenir

Açık ve veri odaklı sunumlar hazırlamak, basit grafiklerin ötesine geçmeyi gerektirebilir. **Balon grafiğine özel hata çubukları eklemeyi** öğrenerek, izleyicilerinize her veri noktasının değişkenliği ve güven aralıkları hakkında bilgi sunabilirsiniz. Bu öğreticide, Aspose.Slides ile bir Java projesi kurmayı, bir slayta balon grafiği eklemeyi, nokta bazında hata çubuklarını yapılandırmayı ve son olarak sonucu PowerPoint dosyası olarak kaydetmeyi göreceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (en son sürüm).  
- **Hangi grafik türü özel hata çubuklarını destekliyor?** Balon grafiği (`ChartType.Bubble`).  
- **Hata çubukları veri noktasına göre ayarlanabilir mi?** Evet – X/Y artı‑eksi değerleri için `ErrorBarsCustomValues` kullanılır.  
- **Lisans gerekli mi?** Test için ücretsiz deneme sürümü yeterlidir; tam lisans değerlendirme sınırlamalarını kaldırır.  
- **Uygulama ne kadar sürer?** Temel bir örnek için yaklaşık 10‑15 dakika.

## Önkoşullar

Başlamadan önce şunların yüklü olduğundan emin olun:

- **Java Development Kit (JDK):** Sürüm 8 ve üzeri.  
- **Aspose.Slides for Java:** Kütüphaneyi projenize ekleyin (aşağıdaki Maven/Gradle kod parçacıklarına bakın).  
- **IDE:** IntelliJ IDEA, Eclipse, NetBeans veya tercih ettiğiniz herhangi bir editör.

### Gerekli Kütüphaneler ve Bağımlılıklar

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ayrıca en son JAR dosyasını resmi sürüm sayfasından indirebilirsiniz: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lisans Edinme

- Tüm özellikleri keşfetmek için ücretsiz deneme sürümüyle başlayın.  
- Sınırsız test için geçici bir lisans isteyin.  
- Üretim kullanımı için tam‑zamanlı bir lisans satın alın.

## Aspose.Slides for Java Kurulumu

Kütüphane sınıf yolunuza eklendikten sonra bir sunum nesnesi başlatın. Bu blok, grafik için temiz bir tuval oluşturur.

```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Uygulama Kılavuzu

### Özellik 1: Slayta Grafik Ekleme ve Balon Grafik Oluşturma

**Neden slayta bir grafik ekleyelim?**  
Grafiği doğrudan slayta yerleştirmek, görsel bağlamı çevredeki metin veya görsellerle bir arada tutar ve sunumu daha bütünlüklü hâle getirir.

#### Adım 1: Gerekli Sınıfları İçe Aktarın
```java
import com.aspose.slides.*;
```

#### Adım 2: İlk Slayta Balon Grafiği Ekleyin
```java
// Access the first slide
ISlide slide = presentation.getSlides().get_Item(0);

// Create a bubble chart on the slide
IChart chart = slide.getShapes().addChart(
    ChartType.Bubble, 50, 50, 400, 300, true);
```
- `ChartType.Bubble` Aspose’a balon grafiği istediğimizi söyler.  
- `(50, 50)` koordinatları ve `(400, 300)` boyutu, grafiği slayt üzerinde güzel bir konuma yerleştirir.

### Özellik 2: Hata Çubuklarını Yapılandırma

Hata çubukları, izleyicilere her noktanın güvenilirliği hakkında görsel bir ipucu verir. Çubukları görünür hâle getirecek ve özel değerler kullanacak şekilde ayarlayacağız.

#### Adım 3: İlk Seriyi Erişin
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Adım 4: Özel Hata Çubuklarını Etkinleştirip Ayarlayın
```java
// Accessing error bar formats
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();

// Making error bars visible
errBarX.setVisible(true);
errBarY.setVisible(true);

// Setting custom value types for more detailed control
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

### Özellik 3: Veri Noktaları İçin Hata Çubuklarını Ayarlama (Nokta Başına Hata Çubuğu)

Şimdi her balon için benzersiz hata marjı değerleri atayacağız; bu **nokta başına hata çubuğu** örneğini gösterir.

#### Adım 5: Veri Noktası Koleksiyonunu Yapılandırın
```java
IChartDataPointCollection points = series.getDataPoints();

// Configuring custom values for error bars
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Loop through each data point
for (int i = 0; i < points.size(); i++) {
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```
*Özel değerler kullanmak, her balon için hata aralığını kesin olarak tanımlamanızı sağlar; bu, bilimsel veya finansal analizlerde kritik öneme sahiptir.*

### Özellik 4: Sunumu Kaydetme

```java
String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";

// Saving the presentation
presentation.save(YOUR_DOCUMENT_DIRECTORY + "/ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

## Pratik Kullanım Alanları

Balon grafiğine özel hata çubukları eklemek, birçok gerçek dünya senaryosunda değerlidir:

1. **Bilimsel Araştırma:** Her deneysel sonucun ölçüm belirsizliğini gösterin.  
2. **İş Analitiği:** Satış veya pazar payı tahmin aralıklarını görselleştirin.  
3. **Eğitim:** Güven aralıkları gibi istatistiksel kavramları anlatın.

## Performans Düşünceleri

- `Presentation` nesnesini mümkün olan en kısa sürede serbest bırakın, böylece yerel kaynaklar temizlenir.  
- Toplu grafik üretimi yapıyorsanız veri noktası sayısını sınırlayın; çok büyük veri kümeleri oluşturma süresini artırabilir.  
- Birden fazla slayt oluştururken aynı grafik nesnelerini yeniden kullanarak yükü azaltın.

## Yaygın Sorunlar ve Çözümleri

| Sorun | Neden | Çözüm |
|-------|-------|------|
| **ErrorBarsCustomValues `null` döndürüyor** | Seri henüz veri noktasına sahip değil. | Önce veri noktalarını ekleyin veya hata çubuklarını yapılandırmadan önce serinin doldurulduğundan emin olun. |
| **Grafik slaytta görünmüyor** | Grafik boyutları slayt sınırları dışına çıkmış. | X/Y koordinatlarını ve genişlik/yüksekliği slayt boyutuna uygun şekilde ayarlayın. |
| **Lisans istisnası** | Geçerli bir lisans olmadan deneme sürümü kullanılıyor. | Sunumu kaydetmeden önce geçici ya da tam bir lisans uygulayın. |

## Sık Sorulan Sorular

**S: Aspose.Slides for Java nedir?**  
C: Microsoft Office olmadan PowerPoint dosyalarını programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan güçlü bir API’dir.

**S: Aspose.Slides’ı lisans olmadan kullanabilir miyim?**  
C: Evet, ücretsiz deneme sürümü geliştirme ve test için çalışır, ancak değerlendirme filigranları ekler ve bazı özellikleri kısıtlar.

**S: Aspose.Slides’ın en son sürümüne nasıl güncellerim?**  
C: Resmi [Aspose releases page](https://releases.aspose.com/slides/java/) adresini kontrol edin ve Maven/Gradle bağımlılığınızı buna göre güncelleyin.

**S: Balon grafiğine neden özel hata çubukları ekleyelim?**  
C: Her veri noktasının değişkenliğini veya güven aralığını göstererek basit bir dağılım görselleştirmesini daha zengin ve bilgilendirici bir hikâyeye dönüştürür.

**S: Başka grafik türlerinde de hata çubuklarını özelleştirebilir miyim?**  
C: Kesinlikle. Aspose.Slides, çizgi, çubuk, sütun ve birçok diğer grafik türü için hata çubuklarını destekler.

---

**Son Güncelleme:** 2026-03-04  
**Test Edilen Sürüm:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}