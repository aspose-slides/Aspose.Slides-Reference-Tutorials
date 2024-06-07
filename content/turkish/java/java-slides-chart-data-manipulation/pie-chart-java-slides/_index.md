---
title: Java Slaytlarında Pasta Grafiği
linktitle: Java Slaytlarında Pasta Grafiği
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarında çarpıcı Pasta Grafikleri oluşturmayı öğrenin. Java geliştiricileri için kaynak kodu içeren adım adım kılavuz.
type: docs
weight: 23
url: /tr/java/chart-data-manipulation/pie-chart-java-slides/
---

## Aspose.Slides Kullanarak Java Slaytlarında Pasta Grafiği Oluşturmaya Giriş

Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumunda Pasta Grafiğinin nasıl oluşturulacağını göstereceğiz. Başlamanıza yardımcı olmak için size adım adım talimatlar ve Java kaynak kodu sağlayacağız. Bu kılavuz, Aspose.Slides for Java ile geliştirme ortamınızı zaten kurduğunuzu varsaymaktadır.

## Önkoşullar

 Başlamadan önce projenizde Aspose.Slides for Java kütüphanesinin kurulu ve yapılandırılmış olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Aspose.Slides kütüphanesinden gerekli sınıfları içe aktardığınızdan emin olun.

## Adım 2: Sunumu Başlatın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// PPTX dosyasını temsil eden Sunum sınıfını somutlaştırın
Presentation presentation = new Presentation();
```

 PowerPoint dosyanızı temsil edecek yeni bir Sunum nesnesi oluşturun. Yer değiştirmek`"Your Document Directory"` sunuyu kaydetmek istediğiniz asıl yolla.

## 3. Adım: Slayt Ekleme

```java
// İlk slayda erişin
ISlide slide = presentation.getSlides().get_Item(0);
```

Sununun ilk slaydını Pasta Grafiğini eklemek istediğiniz yere alın.

## Adım 4: Pasta Grafiği Ekleme

```java
//Varsayılan verileri içeren pasta grafiği ekleme
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Slayta belirtilen konum ve boyutta bir Pasta Grafiği ekleyin.

## Adım 5: Grafik Başlığını Ayarlayın

```java
// Grafik başlığını ayarla
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Pasta Grafiği için bir başlık belirleyin. Başlığı gerektiği gibi özelleştirebilirsiniz.

## Adım 6: Grafik Verilerini Özelleştirin

```java
// Değerleri gösterecek ilk seriyi ayarlayın
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;

// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Varsayılan oluşturulan serileri ve kategorileri silin
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Yeni kategoriler ekleme
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Yeni seriler ekleniyor
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Seri verilerini doldurma
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Kategorileri ve serileri ekleyerek ve değerlerini ayarlayarak grafik verilerini özelleştirin. Bu örnekte, karşılık gelen veri noktalarına sahip üç kategorimiz ve bir serimiz var.

## Adım 7: Pasta Grafiği Sektörlerini Özelleştirin

```java
// Sektör renklerini ayarlayın
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Her sektörün görünümünü özelleştirin
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Sektör sınırını özelleştirin
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Diğer sektörleri de benzer şekilde özelleştirin
```

Pasta Grafiğindeki her sektörün görünümünü özelleştirin. Renkleri, kenarlık stillerini ve diğer görsel özellikleri değiştirebilirsiniz.

## Adım 8: Veri Etiketlerini Özelleştirin

```java
// Veri etiketlerini özelleştirin
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Diğer veri noktaları için veri etiketlerini benzer şekilde özelleştirin
```

Pasta Grafiğindeki her veri noktası için veri etiketlerini özelleştirin. Grafikte hangi değerlerin görüntüleneceğini kontrol edebilirsiniz.

## Adım 9: Lider Çizgileri Göster

```java
// Grafiğin lider çizgilerini göster
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Veri etiketlerini karşılık gelen sektörlere bağlamak için öncü çizgileri etkinleştirin.

## Adım 10: Pasta Grafiği Döndürme Açısını Ayarlayın

```java
// Pasta Grafiği sektörleri için dönüş açısını ayarlayın
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Pasta Grafiği sektörleri için dönüş açısını ayarlayın. Bu örnekte 180 dereceye ayarladık.

## Adım 11: Sunuyu Kaydetme

```java
// Sunuyu Pasta Grafiği ile kaydedin
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Sunuyu Pasta Grafiği ile belirtilen dizine kaydedin.

## Java Slaytlarındaki Pasta Grafiği İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PPTX dosyasını temsil eden Sunum sınıfını somutlaştırın
Presentation presentation = new Presentation();
// İlk slayda erişin
ISlide slides = presentation.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Grafik başlığını ayarlama
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// İlk seriyi Değerleri Göster olarak ayarla
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Varsayılan oluşturulan serileri ve kategorileri silin
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Yeni kategoriler ekleme
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Yeni seriler ekleniyor
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
//Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Yeni versiyonda çalışmıyor
// Yeni noktalar ekleme ve sektör rengini ayarlama
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Sektör sınırının ayarlanması
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Sektör sınırının ayarlanması
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Sektör sınırının ayarlanması
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Yeni seriler için kategorilerin her biri için özel etiketler oluşturun
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Grafik için Lider Çizgiler Gösteriliyor
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Pasta Grafiği Sektörleri için Dönme Açısını Ayarlama
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Sunuyu grafikle kaydet
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Çözüm

Aspose.Slides for Java'yı kullanarak PowerPoint sunumunda başarılı bir şekilde Pasta Grafiği oluşturdunuz. Grafiğin görünümünü ve veri etiketlerini özel gereksinimlerinize göre özelleştirebilirsiniz. Bu eğitimde temel bir örnek verilmektedir ve grafiklerinizi gerektiği gibi daha da geliştirebilir ve özelleştirebilirsiniz.

## SSS'ler

### Pasta Grafiği'nde tek tek sektörlerin renklerini nasıl değiştirebilirim?

 Pasta Grafiğindeki ayrı sektörlerin renklerini değiştirmek için her veri noktasının dolgu rengini özelleştirebilirsiniz. Sağlanan kod örneğinde, her sektör için dolgu renginin nasıl ayarlanacağını gösterdik.`getSolidFillColor().setColor()` yöntem. İstediğiniz görünümü elde etmek için renk değerlerini değiştirebilirsiniz.

### Pasta Grafiğine daha fazla kategori ve veri serisi ekleyebilir miyim?

 Evet, Pasta Grafiğine ek kategoriler ve veri serileri ekleyebilirsiniz. Bunu yapmak için şunları kullanabilirsiniz:`getChartData().getCategories().add()` Ve`getChartData().getSeries().add()` Örnekte gösterildiği gibi yöntemler. Grafiğinizi genişletmek için yeni kategoriler ve seriler için uygun verileri ve etiketleri sağlamanız yeterlidir.

### Veri etiketlerinin görünümünü nasıl özelleştiririm?

 Veri etiketlerinin görünümünü aşağıdakileri kullanarak özelleştirebilirsiniz:`getDataLabelFormat()` Her veri noktasının etiketindeki yöntem. Örnekte, değerin veri etiketlerinde nasıl gösterileceğini şunu kullanarak gösterdik:`getDataLabelFormat().setShowValue(true)`. Hangi değerlerin görüntüleneceğini kontrol ederek, açıklama tuşlarını göstererek ve diğer biçimlendirme seçeneklerini ayarlayarak veri etiketlerini daha da özelleştirebilirsiniz.

### Pasta Grafiğinin başlığını değiştirebilir miyim?

 Evet, Pasta Grafiğinin başlığını değiştirebilirsiniz. Sağlanan kodda, grafiğin başlığını kullanarak ayarladık.`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Değiştirebilirsin`"Sample Title"` İstediğiniz başlık metniyle.

### Oluşturulan sunumu Pasta Grafiği ile nasıl kaydederim?

 Sunuyu Pasta Grafiği ile kaydetmek için`presentation.save()` yöntem. Sunuyu kaydetmek istediğiniz formatın yanı sıra istediğiniz dosya yolunu ve adını da sağlayın. Örneğin:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Doğru dosya yolunu ve biçimini belirttiğinizden emin olun.

### Aspose.Slides for Java'yı kullanarak başka türde grafikler oluşturabilir miyim?

Evet, Aspose.Slides for Java, Çubuk Grafikler, Çizgi Grafikler ve daha fazlası dahil olmak üzere çeşitli grafik türlerini destekler. Değiştirerek farklı türde grafikler oluşturabilirsiniz.`ChartType` Bir grafik eklerken. Farklı türde grafikler oluşturmaya ilişkin daha fazla ayrıntı için Aspose.Slides belgelerine bakın.

### Aspose.Slides for Java ile çalışmaya ilişkin daha fazla bilgi ve örneği nasıl bulabilirim?

 Daha fazla bilgi, ayrıntılı belgeler ve ek örnekler için şu adresi ziyaret edebilirsiniz:[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/). Kütüphaneyi etkili bir şekilde kullanmanıza yardımcı olacak kapsamlı kaynaklar sağlar.