---
"description": "Özel Grafik İşaretleyici Seçenekleriyle Java Slaytlarınızı Optimize Edin. Java için Aspose.Slides'ı kullanarak veri noktalarını görsel olarak geliştirmeyi öğrenin. Adım adım rehberliği ve SSS'leri keşfedin."
"linktitle": "Java Slaytlarında Veri Noktasındaki Grafik İşaretleyici Seçenekleri"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Veri Noktasındaki Grafik İşaretleyici Seçenekleri"
"url": "/tr/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Veri Noktasındaki Grafik İşaretleyici Seçenekleri


## Java Slaytlarında Veri Noktalarındaki Grafik İşaretleyici Seçeneklerine Giriş

Etkili sunumlar oluşturmaya gelince, veri noktalarındaki grafik işaretleyicilerini özelleştirme ve düzenleme yeteneği tüm farkı yaratabilir. Java için Aspose.Slides ile grafiklerinizi dinamik ve görsel olarak ilgi çekici öğelere dönüştürme gücüne sahipsiniz.

## Ön koşullar

Kodlama kısmına geçmeden önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Java Geliştirme Ortamı
- Java Kütüphanesi için Aspose.Slides
- Java Entegre Geliştirme Ortamı (IDE)
- Örnek Sunum Belgesi (örneğin, "Test.pptx")

## Adım 1: Ortamı Kurma

Öncelikle gerekli araçların kurulu ve hazır olduğundan emin olun. IDE'nizde bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini içe aktarın.

## Adım 2: Sunumu Yükleme

Başlamak için örnek sunum belgenizi yükleyin. Sağlanan kodda, belgenin "Test.pptx" olarak adlandırıldığını varsayıyoruz.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Adım 3: Bir Grafik Oluşturma

Şimdi sunumda bir grafik oluşturalım. Bu örnekte İşaretçilerle Çizgi Grafiği kullanacağız.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Adım 4: Grafik Verileriyle Çalışma

Grafik verilerini işlemek için grafik veri çalışma kitabına erişmemiz ve veri serisini hazırlamamız gerekir. Varsayılan seriyi temizleyip özel verilerimizi ekleyeceğiz.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Adım 5: Özel İşaretleyiciler Ekleme

İşte heyecan verici kısım geliyor - veri noktalarındaki işaretçileri özelleştirme. Bu örnekte işaretçi olarak görselleri kullanacağız.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Veri noktalarına özel işaretleyiciler ekleme
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Diğer veri noktaları için tekrarlayın
// ...

// Grafik serisi işaretleyici boyutunu değiştirme
series.getMarker().setSize(15);
```

## Adım 6: Sunumu Kaydetme

Grafik işaretleyicilerinizi özelleştirdikten sonra, değişiklikleri uygulamada görmek için sunumu kaydedin.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Veri Noktalarındaki Grafik İşaretleyici Seçenekleri İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Varsayılan grafiği oluşturma
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Varsayılan grafik veri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;
//Grafik veri çalışma sayfasını alma
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Demo serisini sil
chart.getChartData().getSeries().clear();
//Yeni seri ekle
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Resmi ayarla
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Resmi ayarla
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//İlk grafik serisini alın
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Oraya yeni bir nokta (1:3) ekleyin.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Grafik serisi işaretleyicisini değiştirme
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Çözüm

Java için Aspose.Slides ile veri noktalarındaki grafik işaretleyicileri özelleştirerek sunumlarınızı yükseltebilirsiniz. Bu, izleyicilerinizi büyüleyen görsel olarak çarpıcı ve bilgilendirici slaytlar oluşturmanıza olanak tanır.

## SSS

### Veri noktaları için işaretçi boyutunu nasıl değiştirebilirim?

Veri noktaları için işaretleyici boyutunu değiştirmek için şunu kullanın: `series.getMarker().setSize()` yöntemini kullanın ve istediğiniz boyutu argüman olarak belirtin.

### Resimleri özel işaretçi olarak kullanabilir miyim?

Evet, veri noktaları için özel işaretçiler olarak görselleri kullanabilirsiniz. Dolgu türünü şu şekilde ayarlayın: `FillType.Picture` ve kullanmak istediğiniz görseli sağlayın.

### Aspose.Slides for Java dinamik grafikler oluşturmak için uygun mudur?

Kesinlikle! Aspose.Slides for Java, sunumlarınızda dinamik ve etkileşimli grafikler oluşturmak için kapsamlı yetenekler sunar.

### Aspose.Slides'ı kullanarak grafiğin diğer yönlerini özelleştirebilir miyim?

Evet, Aspose.Slides for Java'yı kullanarak başlıklar, eksenler, veri etiketleri ve daha fazlası dahil olmak üzere grafiğin çeşitli yönlerini özelleştirebilirsiniz.

### Aspose.Slides for Java belgelerine ve indirmelere nereden ulaşabilirim?

Belgeleri şu adreste bulabilirsiniz: [Burada](https://reference.aspose.com/slides/java/) ve kütüphaneyi şu adresten indirin: [Burada](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}