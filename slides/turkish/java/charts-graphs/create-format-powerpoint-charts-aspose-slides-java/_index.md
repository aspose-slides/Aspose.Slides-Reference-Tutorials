---
date: '2026-03-15'
description: Aspose.Slides for Java kullanarak bir PowerPoint slaytına kümelenmiş
  sütun grafiği eklemeyi öğrenin; grafiği slayta ekleme adımlarını ve Java ile verimli
  bir şekilde PowerPoint slaytı oluşturmayı kapsar.
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: Aspose.Slides Java kullanarak PPT'ye Küme Sütun Grafiği ekle
url: /tr/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

:** 2026-03-15 => same.

**Tested With:** Aspose.Slides 25.4 for Java (JDK 16) => same.

**Author:** Aspose => same.

Close shortcodes.

Now produce final content with all translations.

Be careful to keep code block placeholders unchanged.

Also ensure markdown formatting preserved.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java kullanarak PPT'ye Kümeleme Sütun Grafiği ekleme

## Giriş
Bu rehberde, Aspose.Slides for Java ile programlı olarak bir PowerPoint sunumuna **kümeleme sütun grafiği** ekleyeceksiniz. İş raporları, eğitim sunumları veya pazarlama sunumları oluşturuyor olun, grafik oluşturmayı otomatikleştirmek zaman tasarrufu sağlar ve tutarlılığı garanti eder. Kütüphaneyi kurma, bir slayt oluşturma, grafiği ekleme, çizgi stilleri ve yuvarlak köşeler uygulama ve sonunda dosyayı kaydetme adımlarını göstereceğiz. Sonunda **grafiği slayta ekleme** ve hatta **Java tabanlı PowerPoint slaytı oluşturma** çözümlerinin tüm iş akışına hâkim olacaksınız.

### Hızlı Yanıtlar
- **Başlamak için birincil sınıf nedir?** `Presentation`
- **Hangi grafik türü kullanılıyor?** `ChartType.ClusteredColumn`
- **Yuvarlak köşeler nasıl etkinleştirilir?** `chart.setRoundedCorners(true);`
- **Kaydetme için önerilen format nedir?** `SaveFormat.Pptx`
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü test için çalışır; üretim için satın alınmış bir lisans gereklidir.

## Kümeleme sütun grafiği nedir?
Kümeleme sütun grafiği, her kategori için birden fazla veri serisini yan yana gruplar, bu da farklı gruplar arasındaki değerleri karşılaştırmak için idealdir. Aspose.Slides, bu grafik türünü PowerPoint açmadan tamamen kod içinde oluşturmanıza olanak tanır.

## Java için Aspose.Slides kullanarak kümeleme sütun grafiği eklemek neden tercih edilmeli?
- **Tam otomasyon** – Manuel UI etkileşimi gerekmez.  
- **Çapraz platform** – Java destekleyen herhangi bir işletim sisteminde çalışır.  
- **Zengin biçimlendirme** – Çizgi stillerini, doldurmaları, yuvarlak köşeleri ve daha fazlasını kontrol edin.  
- **COM bağımlılığı yok** – Office Interop'tan farklı olarak, sunucularda güvenli bir şekilde çalışır.

## Önkoşullar
- **Aspose.Slides for Java** (v25.4 veya daha yeni)  
- **JDK 16** (veya daha yeni)  
- IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE  

## Aspose.Slides for Java Kurulumu
Kütüphaneyi Maven, Gradle veya doğrudan indirme yoluyla ekleyebilirsiniz.

### Maven Kullanarak
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kullanarak
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
En son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

#### Lisans Alma Adımları
- **Ücretsiz Deneme** – Süre sınırlaması olmadan tüm özellikleri test edin.  
- **Geçici Lisans** – Tam özellikli değerlendirme için Aspose portalından talep edin.  
- **Satın Alma** – Üretim kullanımı için kalıcı bir lisans edinin.

## Uygulama Kılavuzu

### Sunum Oluşturma ve Slayt Ekleme
#### Genel Bakış
İlk olarak, yeni bir `Presentation` nesnesi oluşturur ve yeni bir dosyada gelen varsayılan slaytı alırız.

#### Adım Adım
**1. Presentation Nesnesini Başlatma**
```java
Presentation presentation = new Presentation();
```

**2. İlk Slayta Erişim**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Kaynakları Serbest Bırakma**
```java
if (presentation != null) presentation.dispose();
```

### Slayta Grafik Ekleme
#### Genel Bakış
Şimdi hazırladığımız slayta bir **kümeleme sütun grafiği** gömüyoruz.

#### Adım Adım
**1. Presentation Nesnesini Başlatma**
```java
Presentation presentation = new Presentation();
```

**2. İlk Slayta Erişim**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Kümeleme Sütun Grafiği Ekleme**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Kaynakları Serbest Bırakma**
```java
if (presentation != null) presentation.dispose();
```

### Grafik Çizgi Stilini Biçimlendirme ve Yuvarlak Köşeleri Ayarlama
#### Genel Bakış
Katı bir çizgi doldurması, tek bir çizgi stili ve yuvarlak köşeler uygulayarak görsel çekiciliği artırın.

#### Adım Adım
**1. Presentation Nesnesini Başlatma**
```java
Presentation presentation = new Presentation();
```

**2. İlk Slayta Erişim**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Kümeleme Sütun Grafiği Ekleme**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Çizgi Biçimini Katı Doldurma Tipine Ayarlama**
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. Tek Çizgi Stilini Uygulama**
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. Grafik Alanı için Yuvarlak Köşeleri Etkinleştirme**
```java
chart.setRoundedCorners(true);
```

**7. Kaynakları Serbest Bırakma**
```java
if (presentation != null) presentation.dispose();
```

### Sunumu Kaydetme
#### Genel Bakış
Son olarak, sunumu PPTX formatında diske yazarız.

#### Adım Adım
**1. Presentation Nesnesini Başlatma**
```java
Presentation presentation = new Presentation();
```

**2. Çıktı Dizinini ve Dosya Adını Tanımlama**
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. Sunumu PPTX Formatında Kaydetme**
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. Kaynakları Serbest Bırakma**
```java
if (presentation != null) presentation.dispose();
```

## Pratik Uygulamalar
- **İş Raporları** – Dinamik grafiklerle çeyrek dönem finansal sunumları otomatikleştirin.  
- **Eğitim İçeriği** – Veritabanından veri çeken ders slaytları oluşturun.  
- **Pazarlama Sunumları** – Şık grafiklerle ürün trendlerini görselleştirin.

## Performans Düşünceleri
- **Kaynak Yönetimi** – Her zaman `dispose()` çağırın veya try‑with‑resources kullanın.  
- **Bellek Optimizasyonu** – Büyük veri setlerini daha küçük partilerde işleyin.  
- **En İyi Uygulamalar** – Mümkün olduğunda grafik serileri için değişmez veri yapıları tercih edin.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **`NullPointerException` on `getSlides()`** | `Presentation` nesnesinin slaytlara erişmeden önce başarıyla oluşturulduğundan emin olun. |
| **Chart not appearing** | Grafiğin boyutlarının (x, y, genişlik, yükseklik) slayt sınırları içinde olduğundan emin olun. |
| **License not applied** | `Presentation` nesnesini oluşturmadan önce lisans dosyanızı yükleyin: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Sık Sorulan Sorular

**Q: Aspose.Slides kullanarak farklı grafik türleri nasıl eklenir?**  
A: `ChartType.ClusteredColumn` ifadesini `ChartType.Pie`, `ChartType.Line` veya `ChartType.Bar` gibi diğer enum değerleriyle değiştirin.

**Q: Derleme hatalarıyla karşılaşırsam ne yapmalıyım?**  
A: JDK 16 veya daha yeni bir sürüm kullandığınızdan ve Maven/Gradle bağımlılığının yukarıda gösterilen sürümle eşleştiğinden emin olun.

**Q: Grafiği bir veritabanından gelen verilerle doldurabilir miyim?**  
A: Evet. Grafiğin `getChartData()` koleksiyonuna erişin, seriler ve kategoriler oluşturun ve çalışma zamanında alınan değerlerle doldurun.

**Q: Çok büyük sunumlar için performansı nasıl artırabilirim?**  
A: İşi birden fazla `Presentation` örneğine bölün, grafik şablonlarını yeniden kullanın ve nesneleri her zaman hızlı bir şekilde serbest bırakın.

## Sonuç
Artık Aspose.Slides for Java ile bir PowerPoint slaytına **kümeleme sütun grafiği eklemek** için eksiksiz, uçtan uca bir tarifiniz var. Diğer grafik türleriyle deney yapın, canlı veri kaynaklarını bağlayın ve bu mantığı daha büyük raporlama hatlarına entegre ederek sunum iş akışınızı otomatikleştirin.

---

**Last Updated:** 2026-03-15  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}