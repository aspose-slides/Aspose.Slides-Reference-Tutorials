---
title: Java Slaytlarındaki Veri Noktasındaki Grafik İşaretleyici Seçenekleri
linktitle: Java Slaytlarındaki Veri Noktasındaki Grafik İşaretleyici Seçenekleri
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Özel Grafik İşaretleyici Seçenekleri ile Java Slaytlarınızı optimize edin. Aspose.Slides for Java'yı kullanarak veri noktalarını görsel olarak geliştirmeyi öğrenin. Adım adım rehberlik ve SSS'leri keşfedin.
weight: 14
url: /tr/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarındaki Veri Noktasındaki Grafik İşaretleyici Seçenekleri


## Java Slaytlarındaki Veri Noktasındaki Grafik İşaretleyici Seçeneklerine Giriş

Etkili sunumlar oluşturmaya gelince, veri noktalarındaki grafik işaretleyicilerini özelleştirme ve değiştirme yeteneği büyük fark yaratabilir. Aspose.Slides for Java ile grafiklerinizi dinamik ve görsel olarak ilgi çekici öğelere dönüştürme gücüne sahipsiniz.

## Önkoşullar

Kodlama kısmına geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java Geliştirme Ortamı
- Aspose.Slides for Java Kütüphanesi
- Java Entegre Geliştirme Ortamı (IDE)
- Örnek Sunum Belgesi (örneğin, "Test.pptx")

## 1. Adım: Ortamı Ayarlama

Öncelikle gerekli araçların kurulu ve hazır olduğundan emin olun. IDE'nizde bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini içe aktarın.

## Adım 2: Sunumu Yükleme

Başlamak için örnek sunum belgenizi yükleyin. Sağlanan kodda belgenin adının "Test.pptx" olduğunu varsayıyoruz.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## 3. Adım: Grafik Oluşturma

Şimdi sunumda bir grafik oluşturalım. Bu örnekte İşaretçili Çizgi Grafiği kullanacağız.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Adım 4: Grafik Verileriyle Çalışmak

Grafik verilerini işlemek için grafik verileri çalışma kitabına erişmemiz ve veri serisini hazırlamamız gerekiyor. Varsayılan seriyi temizleyeceğiz ve özel verilerimizi ekleyeceğiz.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Adım 5: Özel İşaretleyiciler Ekleme

İşte işin heyecan verici kısmı geliyor: veri noktalarındaki işaretleyicileri özelleştirme. Bu örnekte görüntüleri işaretçi olarak kullanacağız.

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

Grafik işaretçilerinizi özelleştirdikten sonra, değişiklikleri çalışırken görmek için sunuyu kaydedin.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Java Slaytlarındaki Veri Noktasındaki Grafik İşaretleyici Seçenekleri İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Varsayılan grafiği oluşturma
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Varsayılan grafik verileri çalışma sayfası dizinini alma
int defaultWorksheetIndex = 0;
//Grafik verileri çalışma sayfasını alma
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
//Buraya yeni noktayı (1:3) ekleyin.
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
//Grafik serisi işaretçisini değiştirme
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Çözüm

Aspose.Slides for Java ile veri noktalarındaki grafik işaretçilerini özelleştirerek sunumlarınızı geliştirebilirsiniz. Bu, izleyicilerinizi büyüleyen görsel olarak büyüleyici ve bilgilendirici slaytlar oluşturmanıza olanak tanır.

## SSS'ler

### Veri noktalarının işaretçi boyutunu nasıl değiştirebilirim?

 Veri noktalarının işaretçi boyutunu değiştirmek için`series.getMarker().setSize()` yöntemi kullanın ve istediğiniz boyutu argüman olarak sağlayın.

### Görselleri özel işaretçiler olarak kullanabilir miyim?

 Evet, görüntüleri veri noktaları için özel işaretleyiciler olarak kullanabilirsiniz. Doldurma türünü şu şekilde ayarlayın:`FillType.Picture` ve kullanmak istediğiniz görüntüyü sağlayın.

### Aspose.Slides for Java dinamik grafikler oluşturmaya uygun mu?

Kesinlikle! Aspose.Slides for Java, sunumlarınızda dinamik ve etkileşimli grafikler oluşturmanız için kapsamlı yetenekler sağlar.

### Aspose.Slides'ı kullanarak grafiğin diğer yönlerini özelleştirebilir miyim?

Evet, Aspose.Slides for Java'yı kullanarak grafiğin başlıklar, eksenler, veri etiketleri ve daha fazlası dahil olmak üzere çeşitli yönlerini özelleştirebilirsiniz.

### Aspose.Slides for Java belgelerine ve indirmelerine nereden erişebilirim?

 Belgeleri şu adreste bulabilirsiniz:[Burada](https://reference.aspose.com/slides/java/) ve şu adresteki kütüphaneyi indirin:[Burada](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
