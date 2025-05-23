---
"description": "Java Slaytlarında Aspose.Slides for Java kullanarak harici çalışma kitaplarının nasıl ayarlanacağını öğrenin. Excel veri entegrasyonuyla dinamik sunumlar oluşturun."
"linktitle": "Java Slaytlarında Harici Çalışma Kitabı Ayarla"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Harici Çalışma Kitabı Ayarla"
"url": "/tr/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Harici Çalışma Kitabı Ayarla


## Java Slaytlarında Harici Çalışma Kitabı Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides kullanarak Java Slides'da harici bir çalışma kitabının nasıl ayarlanacağını inceleyeceğiz. Harici bir Excel çalışma kitabından veri referansı veren bir grafikle bir PowerPoint sunumunun nasıl oluşturulacağını öğreneceksiniz. Bu kılavuzun sonunda, harici verileri Java Slides sunumlarınıza nasıl entegre edeceğiniz konusunda net bir anlayışa sahip olacaksınız.

## Ön koşullar

Uygulamaya geçmeden önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.
- Aspose.Slides for Java kütüphanesi projenize eklendi.
- Sununuzda başvurmak istediğiniz verilerin bulunduğu bir Excel çalışma kitabı.

## Adım 1: Yeni Bir Sunum Oluşturun

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Aspose.Slides kullanarak yeni bir PowerPoint sunumu oluşturarak başlayalım.

## Adım 2: Bir Grafik Ekleyin

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Sonra, sunuma bir pasta grafiği ekliyoruz. Grafik türünü ve konumunu gerektiği gibi özelleştirebilirsiniz.

## Adım 3: Harici Çalışma Kitabına Erişim

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Harici çalışma kitabına erişmek için şunu kullanırız: `setExternalWorkbook` yöntemini kullanın ve verileri içeren Excel çalışma kitabına giden yolu sağlayın.

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

Seriler ve kategoriler için hücre referanslarını belirterek grafiği harici çalışma kitabındaki verilere bağlıyoruz.

## Adım 5: Sunumu Kaydedin

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Son olarak sunuyu harici çalışma kitabı referansıyla birlikte bir PowerPoint dosyası olarak kaydediyoruz.

## Java Slaytlarında Harici Çalışma Kitabı Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
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

Bu eğitimde, Aspose.Slides kullanarak Java Slides'da harici bir çalışma kitabının nasıl ayarlanacağını öğrendik. Artık Excel çalışma kitaplarındaki verilere dinamik olarak başvuran sunumlar oluşturabilir, slaytlarınızın esnekliğini ve etkileşimini artırabilirsiniz.

## SSS

### Java için Aspose.Slides'ı nasıl yüklerim?

Aspose.Slides for Java, kütüphaneyi Java projenize ekleyerek yüklenebilir. Kütüphaneyi Aspose web sitesinden indirebilir ve belgelerde verilen yükleme talimatlarını takip edebilirsiniz.

### Harici çalışma kitaplarında farklı grafik türleri kullanabilir miyim?

Evet, Aspose.Slides tarafından desteklenen çeşitli grafik türlerini kullanabilir ve bunları harici çalışma kitaplarındaki verilere bağlayabilirsiniz. İşlem, seçtiğiniz grafik türüne bağlı olarak biraz farklılık gösterebilir.

### Harici çalışma kitabımın veri yapısı değişirse ne olur?

Harici çalışma kitabınızın verilerinin yapısı değişirse, grafik verilerinin doğru kalmasını sağlamak için Java kodunuzdaki hücre başvurularını güncelleştirmeniz gerekebilir.

### Aspose.Slides en son Java sürümleriyle uyumlu mu?

Aspose.Slides for Java, en son Java sürümleriyle uyumluluğu garantilemek için düzenli olarak güncellenir. En iyi performans ve uyumluluk için güncellemeleri kontrol ettiğinizden ve kütüphanenin en son sürümünü kullandığınızdan emin olun.

### Aynı harici çalışma kitabına referans veren birden fazla grafik ekleyebilir miyim?

Evet, sununuza aynı harici çalışma kitabına başvuran birden fazla grafik ekleyebilirsiniz. Oluşturmak istediğiniz her grafik için bu eğitimde özetlenen adımları tekrarlamanız yeterlidir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}