---
title: Java Slaytlarında Harici Çalışma Kitabını Ayarlama
linktitle: Java Slaytlarında Harici Çalışma Kitabını Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'ta harici çalışma kitaplarını nasıl ayarlayacağınızı öğrenin. Excel veri entegrasyonuyla dinamik sunumlar oluşturun.
type: docs
weight: 19
url: /tr/java/data-manipulation/set-external-workbook-java-slides/
---

## Java Slaytlarında Harici Çalışma Kitabı Ayarlamaya Giriş

Bu eğitimde Aspose.Slides kullanarak Java Slides'ta harici bir çalışma kitabının nasıl ayarlanacağını inceleyeceğiz. Harici bir Excel çalışma kitabındaki verilere başvuran bir grafik içeren bir PowerPoint sunumunun nasıl oluşturulacağını öğreneceksiniz. Bu kılavuzun sonunda, harici verileri Java Slaytlar sunumlarınıza nasıl entegre edeceğiniz konusunda net bir anlayışa sahip olacaksınız.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
- Aspose.Slides for Java kütüphanesi projenize eklendi.
- Sununuzda başvurmak istediğiniz verileri içeren bir Excel çalışma kitabı.

## 1. Adım: Yeni Bir Sunu Oluşturun

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Aspose.Slides'ı kullanarak yeni bir PowerPoint sunumu oluşturarak başlıyoruz.

## 2. Adım: Grafik Ekleme

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Daha sonra sunuma bir pasta grafiği ekliyoruz. Grafik türünü ve konumunu gerektiği gibi özelleştirebilirsiniz.

## 3. Adım: Harici Çalışma Kitabına Erişin

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Harici çalışma kitabına erişmek için şunu kullanırız:`setExternalWorkbook` yöntemini kullanın ve verileri içeren Excel çalışma kitabının yolunu sağlayın.

## Adım 4: Grafik Verilerini Bağlayın

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Seriler ve kategoriler için hücre referanslarını belirterek grafiği harici çalışma kitabındaki verilere bağlarız.

## Adım 5: Sunuyu Kaydetme

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Son olarak, harici çalışma kitabı referansıyla birlikte sunuyu PowerPoint dosyası olarak kaydediyoruz.

## Java Slaytlarında Harici Çalışma Kitabını Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides kullanarak Java Slides'ta harici bir çalışma kitabının nasıl ayarlanacağını öğrendik. Artık Excel çalışma kitaplarındaki verilere dinamik olarak başvuran, slaytlarınızın esnekliğini ve etkileşimini artıran sunumlar oluşturabilirsiniz.

## SSS'ler

### Aspose.Slides for Java'yı nasıl yüklerim?

Aspose.Slides for Java, kütüphaneyi Java projenize ekleyerek kurabilirsiniz. Kütüphaneyi Aspose web sitesinden indirebilir ve belgelerde verilen kurulum talimatlarını takip edebilirsiniz.

### Harici çalışma kitaplarıyla farklı grafik türlerini kullanabilir miyim?

Evet, Aspose.Slides tarafından desteklenen çeşitli grafik türlerini kullanabilir ve bunları harici çalışma kitaplarındaki verilere bağlayabilirsiniz. Seçtiğiniz grafik türüne bağlı olarak süreç biraz değişebilir.

### Harici çalışma kitabımın veri yapısı değişirse ne olur?

Harici çalışma kitabınızın verilerinin yapısı değişirse grafik verilerinin doğru kalmasını sağlamak için Java kodunuzdaki hücre referanslarını güncellemeniz gerekebilir.

### Aspose.Slides en son Java sürümleriyle uyumlu mu?

Aspose.Slides for Java, en son Java sürümleriyle uyumluluğun sağlanması amacıyla düzenli olarak güncellenmektedir. Optimum performans ve uyumluluk için güncellemeleri kontrol ettiğinizden ve kitaplığın en son sürümünü kullandığınızdan emin olun.

### Aynı harici çalışma kitabına başvuran birden fazla grafik ekleyebilir miyim?

Evet, sununuza hepsi aynı harici çalışma kitabına başvuran birden fazla grafik ekleyebilirsiniz. Oluşturmak istediğiniz her grafik için bu eğitimde özetlenen adımları tekrarlamanız yeterlidir.