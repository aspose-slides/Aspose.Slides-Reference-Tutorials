---
"date": "2025-04-17"
"description": "Aspose.Slides ile Java'da çarpıcı halka grafikleri oluşturmayı öğrenin. Bu kapsamlı kılavuz, başlatma, veri yapılandırması ve sunumları kaydetmeyi kapsar."
"title": "Aspose.Slides&#58;ı Kullanarak Java'da Halka Grafikleri Oluşturun Kapsamlı Bir Kılavuz"
"url": "/tr/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Kullanarak Java'da Halka Grafikleri Oluşturma: Adım Adım Kılavuz

## giriiş

Günümüzün veri odaklı ortamında, bilgileri etkili bir şekilde görselleştirmek, anlayışı ve etkileşimi geliştirmenin anahtarıdır. Profesyonel çizelgeleri programatik olarak oluşturmak, özellikle Java ile zorlayıcı görünebilirken, bu kılavuz, zahmetsizce Donut çizelgeleri oluşturmak için Java için Aspose.Slides'ı kullanma konusunda size yol gösterecektir.

Geliştiriciler bu adımları izleyerek sunum slaytlarını düzenleme ve veri görselleştirmeyi kusursuz bir şekilde entegre etme konusunda uygulamalı deneyim kazanacaklar.

**Önemli Noktalar:**
- Aspose.Slides Java'yı kullanarak bir Sunum nesnesi başlatın.
- Grafik verilerini yapılandırın ve mevcut serileri veya kategorileri yönetin.
- Grafikleriniz için seriler ve kategoriler ekleyin ve özelleştirin.
- Veri noktalarını etkili bir şekilde biçimlendirin ve görüntüleyin.
- Sunumunuzu çeşitli formatlarda kolaylıkla kaydedin.

Uygulamaya başlamadan önce, başlamak için gereken her şeye sahip olduğunuzdan emin olun.

## Ön koşullar

Bu eğitimi takip edebilmek için şunlara sahip olduğunuzdan emin olun:

- **Gerekli Kütüphaneler:**
  - Aspose.Slides for Java sürüm 25.4 veya üzeri.
  
- **Çevre Kurulumu:**
  - Sisteminizde JDK 16 veya üzeri yüklü.
  - IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE.

- **Bilgi Ön Koşulları:**
  - Java programlama kavramlarının temel düzeyde anlaşılması.
  - Maven veya Gradle projelerinde bağımlılıkları yönetme konusunda deneyim.

## Java için Aspose.Slides Kurulumu

Aspose.Slides'ı projenize entegre etmek için derleme aracınıza bağlı olarak şu adımları izleyin:

**Maven Kurulumu:**
Aşağıdaki bağımlılığı ekleyin `pom.xml` dosya:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle Kurulumu:**
Aşağıdakileri ekleyin: `build.gradle` dosya:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme:**
Alternatif olarak, en son sürümü doğrudan şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

### Lisans Edinme

Aspose.Slides'ı değerlendirme sınırlamaları olmadan kullanmak için:
- **Ücretsiz Deneme:** Tüm özellikleri keşfetmek için geçici bir lisansla başlayın.
- **Geçici Lisans:** Birini şu şekilde edinin: [Aspose web sitesi](https://purchase.aspose.com/temporary-license/).
- **Satın almak:** Devamlı kullanım için satın almayı düşünün.

Lisansınızı Java uygulamanızda şu şekilde uygulayın:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Uygulama Kılavuzu

### Sunum ve Grafik Başlatılıyor

#### Genel bakış
Öncelikle bir sunum nesnesi başlatıp ilk slayda bir Halka grafiği ekleyerek başlayalım.

**Adım 1: Sunumu Başlatın**
Mevcut bir PPTX dosyasını yükleyin veya yeni bir dosya oluşturun:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Adım 2: Çörek Grafiği Ekle**
Belirtilen koordinatlarda ilk slaytta bir grafik oluşturun:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Grafik Veri Çalışma Kitabını Yapılandırma ve Mevcut Serileri/Kategorileri Temizleme

#### Genel bakış
Grafik veri çalışma kitabını yapılandırın ve önceden var olan tüm serileri veya kategorileri kaldırın.

**Adım 1: Grafik Veri Çalışma Kitabına Erişim**
Grafiğinizle bağlantılı çalışma kitabını alın:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Adım 2: Mevcut Serileri ve Kategorileri Temizle**
Hiçbir kalıntı veri noktasının olmadığından emin olun:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Grafiğe Seri Ekleme

#### Genel bakış
Tablonuzu, her biri görünüm ve davranış açısından özelleştirilmiş birden fazla seriyle doldurun.

**Adım 1: Seriyi Tekrarlı Olarak Ekleyin**
Dizi eklemek için endeksler arasında dolaşın:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Seriyi özelleştir
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Grafiğe Kategoriler ve Veri Noktaları Ekleme

#### Genel bakış
Kategorileri yapılandırın ve etiketler için belirli biçimlendirmeyle veri noktaları ekleyin.

**Adım 1: Kategorileri ekleyin**
Her kategori için endeksler arasında dolaşın:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Adım 2: Her Seriye Veri Noktaları Ekleyin**
Mevcut kategori için her seriyi yineleyin:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Veri noktası biçim ayarları
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Son seri için etiket biçimlendirmesi
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Görüntüleme seçeneklerini ayarlayın
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Etiket konumunu ayarlayın
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Sunumu Kaydetme

#### Genel bakış
Grafiğinizi yapılandırdıktan sonra sunumu belirtilen dizine kaydedin.

**Adım 1: Sunumu Kaydedin**
Kullanın `save` değişiklikleri yazma yöntemi:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Artık Aspose.Slides kullanarak Java'da Donut grafiklerinin nasıl oluşturulacağını ve özelleştirileceğini öğrendiniz. Bu adımlar, sunumlarınıza karmaşık veri görselleştirmelerini entegre etmek için bir temel sağlar.

**Sonraki Adımlar:**
- Aspose.Slides'da bulunan farklı grafik türlerini deneyin.
- Marka ihtiyaçlarınıza uyacak renkler, yazı tipleri ve stiller gibi ek özelleştirme seçeneklerini keşfedin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}