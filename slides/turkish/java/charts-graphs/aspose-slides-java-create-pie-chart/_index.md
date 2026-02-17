---
date: '2026-02-17'
description: Aspose.Slides for Java kullanarak PowerPoint sunumlarına pasta grafiği
  eklemeyi öğrenin. Profesyonel pasta grafiklerini oluşturmak ve özelleştirmek için
  bu adım adım rehberi izleyin.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Aspose.Slides for Java ile PowerPoint'e pasta grafiği nasıl eklenir
url: /tr/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint'te Aspose.Slides for Java Kullanarak Pasta Grafiklerini Oluşturma ve Özelleştirme

## Giriş

PowerPoint sunumlarınızda verileri etkili bir şekilde görselleştirmekte zorlanıyor musunuz? **Adding a pie chart PowerPoint** slaytı, ham sayıları anında net bir görsel hikayeye dönüştürebilir. Aspose.Slides for Java ile programlı olarak **add pie chart PowerPoint** dosyaları ekleyebilir, PowerPoint'i manuel olarak açmadan tasarım ve veri üzerinde tam kontrol sahibi olabilirsiniz. Bu öğreticide, kütüphaneyi kurmaktan bireysel veri noktalarını özelleştirmeye kadar tüm süreci adım adım göstereceğiz; böylece dakikalar içinde şık, veri odaklı slaytlar sunabilirsiniz.

### Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (latest version).  
- **PowerPoint yüklü olmadan bir grafik oluşturabilir miyim?** Evet, API tamamen çevrim dışı çalışır.  
- **Hangi Java sürümü gereklidir?** JDK 16 veya daha yenisi önerilir.  
- **Bir dilimin rengini nasıl değiştiririm?** Veri noktasında `setFillType` ve `setSolidFillColor` metodlarını kullanın.  
- **Lisans zorunlu mu?** Geliştirme için bir deneme sürümü çalışır; kalıcı bir lisans değerlendirme sınırlamalarını kaldırır.

### Öğrenecekleriniz
- Java ile programlı olarak **add pie chart PowerPoint** nasıl ekleyeceğinizi.  
- Dilim patlaması, renkler ve diğer görsel özellikleri özelleştirmenin yolları.  
- Büyük sunumları işlerken kaynak yönetimi ve performans için en iyi uygulamalar.

## Aspose.Slides for Java Kullanarak PowerPoint'e Pasta Grafiği Neden Eklenir?
Koddan doğrudan bir pasta grafiği gömmek, güncel raporlar oluşturmanıza, aylık gösterge tablolarını otomatikleştirmenize veya anlık olarak kişiselleştirilmiş slayt desteleri yaratmanıza olanak tanır. Manuel kopyala‑yapıştır hatalarını ortadan kaldırır, sunumlar arasında tutarlılığı sağlar ve mevcut Java back‑end'leriyle sorunsuz entegrasyon sunar.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Aspose.Slides for Java library** – öğreticide sürüm 25.4 (yazım anındaki en son sürüm) referans alınmıştır.  
- Uyumlu bir **Java Development Kit (JDK)** – JDK 16+ tercih edilir.  
- **Maven** veya **Gradle** ile bağımlılık yönetimine temel aşinalık.

## Aspose.Slides for Java Kurulumu

Projeye Aspose.Slides kütüphanesini ekleyerek başlayın.

### Maven
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` dosyanıza aşağıdakileri ekleyin:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatif olarak, en son sürümü doğrudan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisanslama
Aspose.Slides'i sınırsız kullanmak için:

- API'yi değerlendirmek üzere bir **free trial** ile başlayın.  
- Uzatılmış testler için [Temporary License](https://purchase.aspose.com/temporary-license/) sayfasından bir **temporary license** talep edin.  
- Tam bir abonelik satın almak için [Purchase page](https://purchase.aspose.com/buy) adresini ziyaret edin.

## Aspose.Slides for Java Kullanarak PowerPoint'e pasta grafiği nasıl eklenir

Aşağıda, bir pasta grafiği oluşturup özelleştirmenin adım adım rehberi yer almaktadır.

### Adım 1: Sunumu Başlatma
İlk olarak yeni bir `Presentation` nesnesi oluşturun. Bu, boş bir PowerPoint dosyasını temsil eder.
```java
Presentation pres = new Presentation();
```

### Adım 2: Pasta Grafiğini Ekleyin
İlk slayta bir pasta grafiği ekleyin. Koordinatlar (50, 50) ve boyut (600 × 400), standart 16:9 slayt için uygundur.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Adım 3: Sunumu Kaydedin
Sunumu diske yazın. `YOUR_OUTPUT_DIRECTORY` ifadesini dosyanın kaydedileceği klasörle değiştirin.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Adım 4: Kaynakları Temizleme
Yerel kaynakları serbest bırakmak için `Presentation` nesnesini dispose edin.
```java
if (pres != null) pres.dispose();
```

## Veri Noktası Patlamasını ve Rengini Özelleştirme

Bireysel dilimleri özelleştirmek, grafiğinizi daha okunabilir hâle getirir; özellikle belirli bir değeri vurgulamak istediğinizde faydalıdır.

### Adım 1: Mevcut Bir Sunumu Yükleyin (veya az önce oluşturduğunuzu yeniden kullanın)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Adım 2: Grafiğe ve Hedef Veri Noktasına Erişin
Burada, ilk seriden ikinci veri noktasını (indeks 1) alıyoruz.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Adım 3: Patlamayı ve Rengi Uygulayın
Dilimi görsel olarak ayırın ve dolgu rengini maviye değiştirin.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Adım 4: Kaydedin ve Serbest Bırakın
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Pratik Uygulamalar
- **Satış Raporları:** En çok satan ürünleri patlamış dilimlerle vurgulayın.  
- **Bütçe Analizi:** Bölümler için farklı renkler atayarak hızlı görsel karşılaştırma sağlayın.  
- **Eğitim Slaytları:** Karmaşık kavramları kolay sindirilebilir grafik segmentlerine bölün.

## Performans Düşünceleri
- **Dispose objects** işlemini zamanında yaparak bellek sızıntılarını önleyin; özellikle bir döngü içinde çok sayıda slayt üretiyorsanız.  
- Büyük sunumlar için **heap kullanımını izleyin**; `Save` metodunun `OutputStream` kabul eden aşırı yüklemelerini kullanarak akış çıkışı düşünün.  
- En yeni çöp toplama iyileştirmelerinden faydalanmak için **JDK 16+** kullanın.

## Sonuç
Artık Aspose.Slides for Java kullanarak **add pie chart PowerPoint** dosyaları oluşturmak ve özelleştirmek için eksiksiz, üretim‑hazır bir iş akışına sahipsiniz. Markanıza uygun olacak şekilde farklı patlama mesafeleri, renkler ve veri setleriyle deneyler yapın. Hazır olduğunuzda, çubuk, çizgi veya dağılım gibi diğer grafik türlerini keşfederek PowerPoint içinde tam bir analiz panosu oluşturabilirsiniz.

## SSS Bölümü
1. **Aspose.Slides for Java kullanmanın temel avantajı nedir?**  
   - PowerPoint dosyalarını programlı olarak oluşturma ve manipüle etme sürecini basitleştirir, geniş bir özellik yelpazesi sunar.  
2. **Aspose.Slides ile diğer grafik türlerini de özelleştirebilir miyim?**  
   - Kesinlikle! Aspose.Slides çubuk, çizgi ve dağılım grafikleri gibi çeşitli grafik türlerini destekler.  
3. **Grafik oluştururken birden fazla slaytı nasıl yönetirim?**  
   - Farklı slaytlara değişiklik uygulamak için `get_Item()` metodunu kullanarak her slaytı indeksle erişin.  
4. **Pasta grafiğim özelleştirme sonrası doğru görüntülenmezse ne yapmalıyım?**  
   - `addChart()` içinde kullanılan koordinat ve boyutları kontrol edin; slayt düzeniniz içinde uygun konumda olduklarından emin olun.  
5. **Aspose.Slides için daha gelişmiş özellikleri nereden bulabilirim?**  
   - Ek işlevler ve seçenekler hakkında bilgi almak için [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) adresini inceleyin.

## Kaynaklar
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}