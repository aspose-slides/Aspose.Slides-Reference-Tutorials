---
date: '2026-01-17'
description: Aspose.Slides kullanarak Java’da nasıl grafik oluşturulacağını, kümelenmiş
  sütun grafiği eklemeyi ve sunumu pptx olarak kaydetmeyi öğrenin. Java geliştiricileri
  için adım adım rehber.
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: Java'da Aspose.Slides for Java ile Grafik Nasıl Oluşturulur
url: /tr/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides for Java ile grafik nasıl oluşturulur

## Giriş
Profesyonel görünen bir **create chart in java** deneyimi oluşturmak zor olmak zorunda değil. **Aspose.Slides for Java** ile programmatically, grafik ekleyebilir, stil verebilir ve kaydedebilirsiniz—örneğin bir clustered column chart—doğrudan PowerPoint sunumları içinde. Bu öğreticide kütüphaneyi kurmayı, bir sunumu başlatmayı, bir clustered column chart eklemeyi, plot alanını ayarlamayı ve sonunda dosyayı PPTX olarak kaydetmeyi adım adım göstereceğiz. Sonunda, herhangi bir Java projesine ekleyebileceğiniz yeniden kullanılabilir bir kod parçacığına sahip olacaksınız.

**Neler Öğreneceksiniz**
- Aspose.Slides Maven veya Gradle bağımlılığını nasıl kuracağınız  
- **create chart in java** ve bir clustered column chart ekleme  
- Plot alanını (konum, boyut, düzen) nasıl yapılandıracağınız  
- **save presentation as pptx** doğru kaynak yönetimiyle nasıl kaydedeceğiniz  

Verilerinizi görsel olarak anlatmaya hazır mısınız? Hadi başlayalım!

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (Maven/Gradle).  
- **Hangi grafik türü gösteriliyor?** Clustered column chart.  
- **Dosyayı nasıl kaydederim?** `presentation.save(..., SaveFormat.Pptx)` kullanın.  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme çalışır; üretim için tam lisans gerekir.  
- **Plot alanını değiştirebilir miyim?** Evet, X, Y, width, height ve layout target type ayarlayabilirsiniz.

## create chart in java nedir?
Java'da bir grafik oluşturmak, bir kütüphane kullanarak grafik nesneleri üretmek, bunları veriyle doldurmak ve bir belgeye—burada bir PowerPoint slaytına—gömmek anlamına gelir. Aspose.Slides, düşük seviyeli Office Open XML ayrıntılarını soyutlayarak görsel sonuca odaklanmanızı sağlar.

## Aspose.Slides ile clustered column chart neden eklenir?
Bir clustered column chart, birden fazla veri serisini yan yana karşılaştırmak için mükemmeldir. İş raporları, gösterge panelleri ve sunumlarda yaygın olarak kullanılır. Aspose.Slides, PowerPoint'i manuel olarak açmadan renkler, işaretçiler, eksenler ve düzen üzerinde tam kontrol sağlar.

## Ön Koşullar
- **Aspose.Slides for Java** kütüphanesi (sürüm 25.4 veya daha yeni).  
- **JDK 16** (veya daha yenisi) yüklü.  
- IntelliJ IDEA veya Eclipse gibi bir IDE.  
- Java sözdizimi hakkında temel bilgi.

## Aspose.Slides for Java Kurulumu
### Maven
`pom.xml` dosyanıza bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` dosyanıza kütüphaneyi ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternatif olarak, en son sürümü [Aspose's official site](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

#### License Acquisition
Test için ücretsiz deneme veya geçici lisans kullanın. Üretim dağıtımları için tam lisans satın alın.

### Basic Initialization and Setup
Yeni bir Java sınıfı oluşturun ve temel sınıfı içe aktarın:

```java
import com.aspose.slides.Presentation;
```

## Uygulama Kılavuzu
Her adımı net açıklamalarla göstereceğiz.

### Presentation Initialization and Slide Manipulation
#### Genel Bakış
İlk olarak, grafiğin yer alacağı yeni bir sunum oluşturun ve ilk slaytı alın.

**1. Create and Initialize a Presentation**

```java
Presentation presentation = new Presentation();
```

**2. Access the First Slide**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Add a Clustered Column Chart**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **İpucu:** Sunum kullanımını her zaman bir `try‑finally` bloğuna sarın ve `finally` içinde `presentation.dispose()` çağırarak yerel kaynakları serbest bırakın.

### Plot Area Configuration
#### Genel Bakış
Grafiğin plot alanını ince ayar yaparak verinin slayt içinde nerede görüneceğini kontrol edin.

**1. Set Position and Size**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. Define Layout Target Type**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### Presentation Saving
#### Genel Bakış
Grafiği özelleştirdikten sonra sunumu PPTX dosyası olarak kalıcı hale getirin.

**1. Save to File**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Uyarı:** Çıktı dizininin var olduğundan ve uygulamanın yazma iznine sahip olduğundan emin olun; aksi takdirde kaydetme işlemi başarısız olur.

## Yaygın Kullanım Durumları
- **İş Raporları:** Satış trendlerini ve finansal KPI'ları gömün.  
- **Eğitim Slaytları:** Deney sonuçlarını veya istatistiksel verileri görselleştirin.  
- **Proje Teklifleri:** Kilometre taşlarını ve kaynak tahsislerini vurgulayın.  
- **Pazarlama Sunumları:** Kampanya performansını canlı grafiklerle gösterin.  
- **Etkinlik Planlaması:** Katılımcı demografik bilgilerini veya program dağılımını gösterin.

## Performans Düşünceleri
- `Presentation` nesnelerini hafıza sızıntılarını önlemek için hemen serbest bırakın.  
- Büyük veri setleri için, tüm veriyi bir anda yüklemek yerine grafik serilerini artımlı olarak doldurun.  
- Java’nın yerleşik profil oluşturma araçlarını kullanarak grafik oluşturma sırasında yığın kullanımını izleyin.

## Sıkça Sorulan Sorular

**S: Diğer grafik türlerini nasıl eklerim?**  
C: Grafik eklerken `addChart` çağrısında `ChartType` enum'ını (ör. `ChartType.Pie`, `ChartType.Line`) kullanın.

**S: Grafik renklerini özelleştirebilir miyim?**  
C: Evet, serinin dolgu formatını veya grafiğin paletini `IChart` API'si üzerinden değiştirebilirsiniz.

**S: Sunumum kaydedilmiyor—ne yanlış?**  
C: `YOUR_OUTPUT_DIRECTORY`'nin doğru, mevcut ve yazılabilir olduğundan emin olun. Ayrıca olası dosya kilitlerini kontrol edin.

**S: Çok büyük sunumları verimli bir şekilde nasıl yönetebilirim?**  
C: Slaytları partiler halinde işleyin, her `Presentation` kullanımından sonra serbest bırakın ve gerekirse JVM yığın boyutunu artırın.

**S: Aspose.Slides ticari projeler için ücretsiz mi?**  
C: Değerlendirme için ücretsiz bir deneme mevcuttur, ancak ticari dağıtım için satın alınmış bir lisans gereklidir.

## Kaynaklar
- [Dokümantasyon](https://reference.aspose.com/slides/java/)
- [Aspose.Slides İndir](https://releases.aspose.com/slides/java/)
- [Lisans Satın Al](https://purchase.aspose.com/buy)
- [Ücretsiz Deneme](https://releases.aspose.com/slides/java/)
- [Geçici Lisans](https://purchase.aspose.com/temporary-license/)
- [Destek Forumu](https://forum.aspose.com/c/slides/11)

Bugün Aspose.Slides for Java ile görsel olarak çarpıcı sunumlar oluşturmaya başlayın!

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
