---
"description": "PowerPoint sunumlarınızı Aspose.Slides for Java ile geliştirin. Mevcut grafikleri programatik olarak değiştirmeyi öğrenin. Grafik özelleştirmesi için kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Mevcut Grafik"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Mevcut Grafik"
"url": "/tr/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Mevcut Grafik


## Java Slaytlarında Mevcut Grafiklere Giriş Aspose.Slides for Java kullanılarak

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda var olan bir grafiğin nasıl değiştirileceğini göstereceğiz. Grafik verilerini, kategori adlarını, seri adlarını değiştirme ve grafiğe yeni bir seri ekleme adımlarını ele alacağız. Projenizde Aspose.Slides for Java'nın kurulu olduğundan emin olun.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Projenize Aspose.Slides for Java kütüphanesi dahil edildi.
2. Değiştirmek istediğiniz bir grafik içeren mevcut bir PowerPoint sunumu.
3. Java geliştirme ortamı kuruldu.

## Adım 1: Sunumu Yükleyin

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";

// PPTX dosyasını temsil eden Sunum sınıfını örneklendirin
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Adım 2: Slayt ve Tabloya Erişim

```java
// İlk slayda erişin
ISlide sld = pres.getSlides().get_Item(0);

// Slayttaki tabloya erişin
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Adım 3: Grafik Verilerini ve Kategori Adlarını Değiştirin

```java
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;

// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Grafik kategori adlarını değiştir
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Adım 4: İlk Grafik Serisini Güncelleyin

```java
// İlk grafik serisini ele alalım
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
// İkinci grafik serisini ele alalım
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
// Yeni bir seri ekleniyor
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Üçüncü grafik serisini ele alalım
series = chart.getChartData().getSeries().get_Item(2);

// Seri verilerini doldur
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Adım 7: Grafik Türünü Değiştirin

```java
// Grafik türünü Kümelenmiş Silindir olarak değiştirin
chart.setType(ChartType.ClusteredCylinder);
```

## Adım 8: Değiştirilen Sunumu Kaydedin

```java
// Sunuyu değiştirilmiş grafikle kaydedin
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Tebrikler! Aspose.Slides for Java kullanarak bir PowerPoint sunumunda var olan bir grafiği başarıyla değiştirdiniz. Artık bu kodu kullanarak PowerPoint sunumlarınızdaki grafikleri programatik olarak özelleştirebilirsiniz.

## Java Slaytlarında Mevcut Grafik İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// PPTX dosyasını temsil eden Sunum sınıfını örneklendir// PPTX dosyasını temsil eden Sunum sınıfını örneklendir
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// İlk slideMarker'a erişin
ISlide sld = pres.getSlides().get_Item(0);
// Varsayılan verilerle grafik ekle
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Grafik veri sayfasının indeksini ayarlama
int defaultWorksheetIndex = 0;
// Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Grafik Kategorisi Adını Değiştirme
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
// Şimdi, yeni bir seri ekleniyor
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

Bu kapsamlı eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda mevcut bir grafiği nasıl değiştireceğimizi öğrendik. Adım adım kılavuzu takip ederek ve kaynak kod örneklerini kullanarak, grafikleri özel gereksinimlerinizi karşılayacak şekilde kolayca özelleştirebilir ve güncelleyebilirsiniz. İşte ele aldığımız konuların bir özeti:

## SSS

### Grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirmek için şunu kullanabilirsiniz: `chart.setType(ChartType.ChartTypeHere)` yöntem. Değiştir `ChartTypeHere` İstenilen grafik türüyle, örneğin `ChartType.ClusteredCylinder` Örneğimizde.

### Bir seriye daha fazla veri noktası ekleyebilir miyim?

Evet, bir seriye daha fazla veri noktası ekleyebilirsiniz. `series.getDataPoints().addDataPointForBarSeries(cell)` yöntem. Uygun hücre verilerini sağladığınızdan emin olun.

### Kategori adlarını nasıl güncellerim?

Kategori adlarını kullanarak güncelleyebilirsiniz. `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` yeni kategori adlarını ayarlamak için.

### Dizi adlarını nasıl değiştirebilirim?

Seri adlarını değiştirmek için şunu kullanın: `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` yeni seri adlarını belirlemek için.

### Bir seriyi grafikten kaldırmanın bir yolu var mı?

Evet, bir seriyi grafikten kaldırmak için şunu kullanabilirsiniz: `chart.getChartData().getSeries().removeAt(index)` yöntem, nerede `index` kaldırmak istediğiniz dizinin dizinidir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}