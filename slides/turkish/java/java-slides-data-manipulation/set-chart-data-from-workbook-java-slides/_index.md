---
"description": "Aspose.Slides kullanarak Java Slides'da bir Excel çalışma kitabından grafik verilerinin nasıl ayarlanacağını öğrenin. Dinamik sunumlar için kod örnekleriyle adım adım kılavuz."
"linktitle": "Java Slaytlarında Çalışma Kitabından Grafik Verilerini Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Çalışma Kitabından Grafik Verilerini Ayarlama"
"url": "/tr/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Çalışma Kitabından Grafik Verilerini Ayarlama


## Java Slaytlarında Çalışma Kitabından Grafik Verilerini Ayarlamaya Giriş

Java için Aspose.Slides, geliştiricilerin PowerPoint sunumlarıyla programatik olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. PowerPoint slaytlarını oluşturmak, düzenlemek ve yönetmek için kapsamlı özellikler sunar. Sunumlarla çalışırken sık karşılaşılan bir gereklilik, Excel çalışma kitabı gibi harici bir veri kaynağından grafik verilerini dinamik olarak ayarlamak. Bu eğitimde, Java kullanarak bunu nasıl başaracağımızı göstereceğiz.

## Ön koşullar

Uygulamaya geçmeden önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.
- Aspose.Slides for Java kütüphanesi projenize eklendi.
- Grafikte kullanmak istediğiniz verilerin bulunduğu bir Excel çalışma kitabı.

## Adım 1: Bir Sunum Oluşturun

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Aspose.Slides for Java kullanarak yeni bir PowerPoint sunumu oluşturarak başlayalım.

## Adım 2: Bir Grafik Ekleyin

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Daha sonra sunumdaki slaytlardan birine bir grafik ekliyoruz. Bu örnekte bir pasta grafiği ekliyoruz ancak ihtiyaçlarınıza uygun grafik türünü seçebilirsiniz.

## Adım 3: Grafik Verilerini Temizle

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Excel çalışma kitabından gelecek yeni veriler için hazırlamak amacıyla, grafikteki mevcut verileri temizliyoruz.

## Adım 4: Excel Çalışma Kitabını Yükle

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Grafik için kullanmak istediğimiz verileri içeren Excel çalışma kitabını yüklüyoruz. Değiştir `"book1.xlsx"` Excel dosyanızın yolunu belirtin.

## Adım 5: Çalışma Kitabı Akışını Grafik Verilerine Yazma

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Excel çalışma kitabı verilerini akışa dönüştürüp grafik verilerine yazıyoruz.

## Adım 6: Grafik Veri Aralığını Ayarlayın

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Excel çalışma kitabından grafik için veri olarak kullanılması gereken hücre aralığını belirtiyoruz. Aralığı verileriniz için gerektiği gibi ayarlayın.

## Adım 7: Grafik Serisini Özelleştirin

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Grafik serisinin çeşitli özelliklerini gereksinimlerinize uyacak şekilde özelleştirebilirsiniz. Bu örnekte, grafik serisi için çeşitli renkler etkinleştiriyoruz.

## Adım 8: Sunumu Kaydedin

```java
pres.save(outPath, SaveFormat.Pptx);
```

Son olarak güncellenen grafik verileriyle sunumu belirtilen çıktı yoluna kaydediyoruz.

## Java Slaytlarında Çalışma Kitabından Set Grafik Verileri İçin Tam Kaynak Kodu

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak bir Excel çalışma kitabından Java Slides'ta grafik verilerinin nasıl ayarlanacağını öğrendik. Adım adım kılavuzu izleyerek ve sağlanan kaynak kod örneklerini kullanarak dinamik grafik verilerini PowerPoint sunumlarınıza kolayca entegre edebilirsiniz.

## SSS

### Sunumumdaki grafiğin görünümünü nasıl özelleştirebilirim?

Renkler, yazı tipleri, etiketler ve daha fazlası gibi özellikleri değiştirerek grafiğin görünümünü özelleştirebilirsiniz. Grafik özelleştirme seçenekleri hakkında ayrıntılı bilgi için Aspose.Slides for Java belgelerine bakın.

### Grafik için farklı bir Excel dosyasındaki verileri kullanabilir miyim?

Evet, çalışma kitabını kodda yüklerken doğru dosya yolunu belirterek herhangi bir Excel dosyasındaki verileri kullanabilirsiniz.

### Aspose.Slides for Java ile başka hangi tür grafikler oluşturabilirim?

Java için Aspose.Slides, çubuk grafikler, çizgi grafikler, dağılım grafikleri ve daha fazlası dahil olmak üzere çeşitli grafik türlerini destekler. Veri temsili ihtiyaçlarınıza en uygun grafik türünü seçebilirsiniz.

### Çalışan bir sunumda grafik verilerini dinamik olarak güncellemek mümkün müdür?

Evet, temel çalışma kitabını değiştirip ardından grafik verilerini yenileyerek bir sunumdaki grafik verilerini dinamik olarak güncelleyebilirsiniz.

### Aspose.Slides for Java ile çalışmaya ilişkin daha fazla örnek ve kaynağı nerede bulabilirim?

Ek örnekleri ve kaynakları şu adreste inceleyebilirsiniz: [Aspose web sitesi](https://www.aspose.com/)Ayrıca, Aspose.Slides for Java belgeleri, kütüphaneyle çalışma konusunda kapsamlı rehberlik sağlar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}