---
"date": "2025-04-17"
"description": "Java için Aspose.Slides kullanarak Pasta Pastası grafiğinin nasıl oluşturulacağını ve özelleştirileceğini öğrenin. Bu kılavuz kurulum, uygulama ve pratik uygulamaları kapsar."
"title": "Java'da Aspose.Slides ile Pasta Grafiği Pastası Oluşturun Kapsamlı Bir Kılavuz"
"url": "/tr/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides ile Pasta Grafiği Oluşturma: Kapsamlı Bir Kılavuz

## Tablolar ve Grafikler

### giriiş

Veri görselleştirmede, pasta grafikleri bir veri kümesindeki oranları temsil etmenin sezgisel bir yoludur. Ancak, bazı bölümlerin diğerlerinden önemli ölçüde daha küçük olduğu karmaşık veri kümeleriyle uğraşırken, geleneksel pasta grafikleri karmaşık ve yorumlanması zor hale gelebilir. Pasta Pasta grafikleri, küçük dilimleri ikincil bir grafiğe bölerek okunabilirliği artırarak bu sorunu çözer.

Bu eğitimde, Java için Aspose.Slides kullanarak bir Pasta Grafiği Pastası oluşturmayı ve düzenlemeyi öğreneceksiniz. Ortamınızı kurmayı, grafiği oluşturmayı, veri etiketleri ve bölünmüş konumlar gibi özellikleri özelleştirmeyi ve sununuzu PPTX biçiminde kaydetmeyi ele alacaksınız. Sonunda, bu özellikleri pratik uygulamalar ve performans ipuçlarıyla ustalaşmış olacaksınız.

**Ne Öğreneceksiniz:**
- Java için Aspose.Slides Kurulumu
- Pasta Grafiği Pastası Oluşturma
- Veri etiketleri ve bölünmüş yapılandırmalar gibi grafik özelliklerini özelleştirme
- Sununuzu diske kaydetme

Başlamaya hazır mısınız? Önce ön koşullara bakalım!

## Ön koşullar

Pasta Grafiğimizi oluşturmadan önce şunlara sahip olduğunuzdan emin olun:

### Gerekli Kitaplıklar, Sürümler ve Bağımlılıklar:
- **Java için Aspose.Slides**:PowerPoint sunumlarını programlı olarak yönetmek için gereklidir.

### Çevre Kurulum Gereksinimleri:
- Makinenize yüklenmiş bir Java Geliştirme Kiti (JDK). JDK 16 veya üzerini kullanmanızı öneririz.
- IntelliJ IDEA, Eclipse veya NetBeans gibi bir Entegre Geliştirme Ortamı (IDE).

### Bilgi Ön Koşulları:
- Java programlamanın temel anlayışı
- Bağımlılık yönetimi için Maven veya Gradle'a aşinalık

## Java için Aspose.Slides Kurulumu

### Kurulum Bilgileri:

**Usta:**
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

**Doğrudan İndirme**: En son sürümü şu adresten indirebilirsiniz: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

### Lisans Alma Adımları:
- **Ücretsiz Deneme**: Tüm özellikleri keşfetmek için 30 günlük deneme sürümüyle başlayın.
- **Geçici Lisans**:Uzun süreli değerlendirme için geçici lisans talebinde bulunun.
- **Satın almak**: Eğer Aspose.Slides ihtiyaçlarınızı karşılıyorsa bir lisans satın almayı düşünebilirsiniz.

### Temel Başlatma ve Kurulum

Kütüphaneyi projenize kurduğunuzda, bir örnek oluşturarak başlatın `Presentation` sınıf:

```java
Presentation presentation = new Presentation();
```

Bu, slaytlarınıza çeşitli grafikler eklemek için ortamı hazırlar. Şimdi, Pasta of Pasta Grafiğimizi uygulamaya geçelim.

## Uygulama Kılavuzu

### 'Pasta Pastası' Grafiği Oluşturma

#### Genel bakış
Bir örnek oluşturarak başlayacağız `Presentation` ve ilk slayta bir Pasta Pastası grafiği ekleyin. Bu grafik, daha küçük segmentleri ikincil bir pastaya ayırarak verileri etkili bir şekilde görselleştirecek ve okunabilirliği artıracaktır.

#### Adım 1: Sunum Sınıfının Bir Örneğini Oluşturun
```java
// Yeni bir sunum oluştur
ePresentation presentation = new Presentation();
```
Bu kod, grafiklerimizi ekleyeceğimiz sunumumuzu başlatır.

#### Adım 2: İlk Slayda 'Pasta Pastası' Grafiği Ekleyin
```java
// İlk slayda (50, 50) konumuna (500x400) boyutunda bir Pasta Pastası grafiği ekleyin
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Burada grafik türünü belirtiyoruz (`PieOfPie`) ve slayt üzerindeki konumu ve boyutları.

#### Adım 3: Serinin Değerlerini Göstermek İçin Veri Etiketlerini Ayarlayın
```java
// Değerleri görüntülemek için veri etiketlerini yapılandırın
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Bu adım, pasta grafiğimizin her bir segmentinin karşılık gelen değerini göstermesini sağlayarak verilerin hızlı yorumlanmasına yardımcı olur.

#### Adım 4: İkinci Pasta Boyutunu Yapılandırın ve Yüzdeye Göre Bölme Yapın
```java
// İkincil pastanın boyutunu ayarlayın
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Pastayı yüzdeye göre böl
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Bölme konumunu ayarlayın
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Bu yapılandırmalar, grafiğinizin nasıl bölüneceğini ve daha küçük segmentlerin nasıl görüntüleneceğini özelleştirmenize olanak tanır ve izleyiciler için netliği artırır.

#### Adım 5: Sunumu PPTX Formatında Diske Kaydedin
```java
// Çıktı dizinini tanımla
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Sunuyu kaydet\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}