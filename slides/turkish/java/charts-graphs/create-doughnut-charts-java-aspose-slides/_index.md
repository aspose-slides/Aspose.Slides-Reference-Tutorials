---
date: '2026-03-07'
description: Aspose.Slides kullanarak Java’da donut grafik oluşturmayı öğrenin. Bu
  adım adım rehber, Maven Aspose Slides bağımlılık kurulumunu, grafik yapılandırmasını
  ve sunumları kaydetmeyi kapsar.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Aspose.Slides Rehberi ile Java'da Donut Grafik Oluşturma
url: /tr/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides ile Java'da Doughnut Chart Oluşturma Rehberi

## Giriş

Programatik olarak **doughnut chart** oluşturmak, ham sayıları anında bir hikâye anlatan göz alıcı bir görsele dönüştürebilir. Java'da **Aspose.Slides**, bu süreci basitleştirir ve PowerPoint'i hiç açmadan sunuma hazır grafikler oluşturmanıza olanak tanır. Bu öğreticide, **create doughnut chart java** adım adım nasıl yapılacağını öğreneceksiniz — Maven Aspose Slides bağımlılığını kurmaktan serileri, kategorileri özelleştirmeye ve son olarak sunumu kaydetmeye kadar.

Bu rehberin sonunda, raporlar, gösterge panelleri veya otomatik slayt desteleri için mükemmel olan dinamik doughnut chart'ları herhangi bir PPTX dosyasına gömebileceksiniz.

### Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.Slides for Java  
- **Ana görev?** Create doughnut chart java in a PPTX file  
- **Kütüphane nasıl eklenir?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java sürümü?** JDK 16 or higher  
- **Renkleri ve etiketleri özelleştirebilir miyim?** Yes, the API provides full formatting control  

## Doughnut Chart Nedir ve Neden Kullanılır?

Doughnut chart, boş bir ortası olan bir pie chart varyasyonudur ve birden fazla veri serisini konsantrik halkalar halinde göstermeye olanak tanır. Bu, bir bütünün parçalarını çeşitli kategorilerde karşılaştırmak için idealdir — örneğin bölgelere göre satışları birden fazla çeyrek boyunca veya departmanlar arasındaki bütçe tahsislerini düşünün.

## Java için Aspose.Slides Neden Kullanılmalı?

- **Office kurulumu gerekmez** – herhangi bir sunucuda PPTX dosyaları oluşturun.  
- **Zengin API** – grafik türleri, veri noktaları ve stil üzerinde tam kontrol.  
- **Yüksek performans** – büyük sunumlar için optimize edilmiştir.  
- **Çapraz platform** – Windows, Linux ve macOS'ta çalışır.

## Ön Koşullar

- **Gerekli Kütüphaneler:**  
  - Aspose.Slides for Java version 25.4 or later.  

- **Ortam Kurulumu:**  
  - JDK 16 or higher.  
  - Your favorite IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Bilgi Ön Koşulları:**  
  - Basic Java programming.  
  - Familiarity with Maven or Gradle for dependency management.

## Maven Aspose Slides Bağımlılığı

Aşağıdaki Maven bağımlılığını `pom.xml` dosyanıza ekleyin. Bu, kütüphaneyi projenize çekmek için gereken **maven aspose slides dependency**'dir.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Gradle tercih ediyorsanız, aşağıdaki eşdeğer kod parçacığını kullanın.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ayrıca JAR dosyasını doğrudan resmi sürüm sayfasından indirebilirsiniz:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Lisans Edinme

Değerlendirme filigranını kaldırmak ve tam özellik setini açmak için:

- **Ücretsiz deneme** – start with a temporary license.  
- **Geçici lisans** – request one from the [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Ticari lisans** – purchase for production use.

Lisansı kodunuzda uygulayın:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Uygulama Kılavuzu

### Sunumu Başlatma ve Doughnut Chart Ekleme

İlk olarak, bir sunum oluşturun veya yükleyin ve ilk slayta bir doughnut chart ekleyin.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Grafik Veri Çalışma Kitabını Yapılandırma ve Mevcut Verileri Temizleme

Sonra, grafiği destekleyen çalışma kitabını alın ve varsayılan serileri veya kategorileri temizleyin.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Grafiğe Seri Ekleme

Şimdi 15'e kadar seri ekleyeceğiz. Her seri özelleştirilebilir — burada patlama, doughnut‑hole boyutu ve ilk dilim açısını ayarlıyoruz.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Kategoriler ve Veri Noktaları Ekleme

15 kategori oluşturacağız ve her seriyi bir veri noktasıyla dolduracağız. Son seri özel etiket biçimlendirmesi alır.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
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

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Sunumu Kaydetme

Son olarak, güncellenen sunumu diske yazın.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Yaygın Sorunlar ve Çözümler

- **Lisans bulunamadı** – Verify the path to `license.lic` is correct and the file is readable.  
- **Grafik boş görünüyor** – Ensure you cleared existing series/categories before adding new ones.  
- **Yanlış renkler** – Check that `FillType.Solid` is set for both fill and line formats.  
- **Çok sayıda seriyle performans** – Limit the number of series/categories or reuse the workbook cells.

## Sıkça Sorulan Sorular

**S: Önceden var olan bir PPTX dosyası olmadan doughnut chart oluşturabilir miyim?**  
A: Evet, boş bir slayt destesiyle başlamak için `new Presentation()` örneğini oluşturun.

**S: Aspose.Slides PDF'ye dışa aktarmayı destekliyor mu?**  
A: Kesinlikle. Grafik oluşturduktan sonra `pres.save("output.pdf", SaveFormat.Pdf);` çağrısını yapın.

**S: Doughnut hole boyutunu nasıl değiştiririm?**  
A: Değeri 0‑100 arasında olan `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` kullanın.

**S: Son seriye değil, tüm serilere veri etiketleri eklemek mümkün mü?**  
A: Evet, etiket‑biçimlendirme bloğunu `if (i == ...)` koşulunun dışına taşıyıp her `dataPoint`'e uygulayın.

**S: Hangi Java sürümleri destekleniyor?**  
A: Aspose.Slides 25.4, JDK 16 ve üzerini destekler. Daha eski JDK'lar uygun sınıflandırıcıyı gerektirir.

---

**Son Güncelleme:** 2026-03-07  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}