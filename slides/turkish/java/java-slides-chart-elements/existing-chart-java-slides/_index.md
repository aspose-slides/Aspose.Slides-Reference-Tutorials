---
title: Java Slaytlarındaki Mevcut Grafik
linktitle: Java Slaytlarındaki Mevcut Grafik
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile PowerPoint sunumlarınızı geliştirin. Mevcut grafikleri programlı olarak değiştirmeyi öğrenin. Grafik özelleştirmesi için kaynak kodlu adım adım kılavuz.
weight: 12
url: /tr/java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java kullanarak Java Slaytlarındaki Mevcut Grafiğe Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda mevcut bir grafiğin nasıl değiştirileceğini göstereceğiz. Grafik verilerini, kategori adlarını, seri adlarını değiştirme ve grafiğe yeni bir seri ekleme adımlarını izleyeceğiz. Projenizde Aspose.Slides for Java'nın kurulu olduğundan emin olun.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Aspose.Slides for Java kütüphanesi projenize dahil edilmiştir.
2. Değiştirmek istediğiniz grafiğin bulunduğu mevcut bir PowerPoint sunumu.
3. Java geliştirme ortamı kuruldu.

## 1. Adım: Sunuyu Yükleyin

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// PPTX dosyasını temsil eden Sunum sınıfını somutlaştırın
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Adım 2: Slayt ve Grafiğe Erişin

```java
// İlk slayda erişin
ISlide sld = pres.getSlides().get_Item(0);

// Slayttaki grafiğe erişin
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 3. Adım: Grafik Verilerini ve Kategori Adlarını Değiştirin

```java
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;

// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Grafik kategorisi adlarını değiştirme
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## 4. Adım: İlk Grafik Serisini Güncelleyin

```java
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Seri adını güncelle
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Seri verilerini güncelle
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Adım 5: İkinci Grafik Serisini Güncelleyin

```java
// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);

// Seri adını güncelle
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Seri verilerini güncelle
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Adım 6: Grafiğe Yeni Bir Seri Ekleyin

```java
// Yeni bir seri ekleme
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Üçüncü grafik serisini alın
series = chart.getChartData().getSeries().get_Item(2);

// Seri verilerini doldur
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Adım 7: Grafik Türünü Değiştirin

```java
//Grafik türünü Kümelenmiş Silindir olarak değiştirin
chart.setType(ChartType.ClusteredCylinder);
```

## Adım 8: Değiştirilen Sunumu Kaydedin

```java
// Sunuyu değiştirilmiş grafikle kaydedin
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki mevcut bir grafiği başarıyla değiştirdiniz. Artık PowerPoint sunumlarınızdaki grafikleri programlı olarak özelleştirmek için bu kodu kullanabilirsiniz.

## Java Slaytlarındaki Mevcut Grafiğin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PPTX dosyasını temsil eden Örnek Sunum sınıfı// PPTX dosyasını temsil eden Örnek Sunum sınıfı
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// İlk SlideMarker'a erişin
ISlide sld = pres.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik verileri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Grafik Kategori Adını değiştirme
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Şimdi seri verileri güncelleniyor
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Seri adını değiştirme
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// İkinci grafik serisini alın
series = chart.getChartData().getSeries().get_Item(1);
// Şimdi seri verileri güncelleniyor
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Seri adını değiştirme
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Şimdi yeni bir seri ekliyoruz
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// 3. grafik serisini alın
series = chart.getChartData().getSeries().get_Item(2);
// Şimdi seri verileri dolduruluyor
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Sunuyu grafikle kaydet
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Çözüm

Bu kapsamlı eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda mevcut bir grafiğin nasıl değiştirileceğini öğrendik. Adım adım kılavuzu takip ederek ve kaynak kodu örneklerinden yararlanarak, özel gereksinimlerinizi karşılamak için grafikleri kolayca özelleştirebilir ve güncelleyebilirsiniz. İşte ele aldığımız konuların bir özeti:

## SSS'ler

### Grafik türünü nasıl değiştirebilirim?

 Grafik türünü kullanarak değiştirebilirsiniz.`chart.setType(ChartType.ChartTypeHere)` yöntem. Yer değiştirmek`ChartTypeHere` İstenilen grafik türüyle, örneğin`ChartType.ClusteredCylinder` bizim örneğimizde.

### Bir seriye daha fazla veri noktası ekleyebilir miyim?

 Evet, kullanarak bir seriye daha fazla veri noktası ekleyebilirsiniz.`series.getDataPoints().addDataPointForBarSeries(cell)` yöntem. Uygun hücre verilerini sağladığınızdan emin olun.

### Kategori adlarını nasıl güncellerim?

 Kategori adlarını kullanarak güncelleyebilirsiniz.`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` Yeni kategori adlarını ayarlamak için.

### Dizi adlarını nasıl değiştiririm?

 Seri adlarını değiştirmek için şunu kullanın:`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` Yeni seri adlarını ayarlamak için.

### Bir seriyi grafikten kaldırmanın bir yolu var mı?

 Evet, kullanarak bir seriyi grafikten kaldırabilirsiniz.`chart.getChartData().getSeries().removeAt(index)` yöntem, nerede`index`kaldırmak istediğiniz serinin indeksidir.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
