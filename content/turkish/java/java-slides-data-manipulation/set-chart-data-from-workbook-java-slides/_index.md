---
title: Java Slaytlarında Çalışma Kitabından Grafik Verilerini Ayarlama
linktitle: Java Slaytlarında Çalışma Kitabından Grafik Verilerini Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides'ı kullanarak Java Slides'ta bir Excel çalışma kitabından grafik verilerini nasıl ayarlayacağınızı öğrenin. Dinamik sunumlar için kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 15
url: /tr/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Java Slaytlarında Çalışma Kitabından Grafik Verilerini Ayarlamaya Giriş

Aspose.Slides for Java, geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. PowerPoint slaytlarını oluşturmak, değiştirmek ve yönetmek için kapsamlı özellikler sağlar. Sunumlarla çalışırken yaygın bir gereksinim, grafik verilerinin Excel çalışma kitabı gibi harici bir veri kaynağından dinamik olarak ayarlanmasıdır. Bu derste Java kullanarak bunu nasıl başaracağımızı göstereceğiz.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
- Aspose.Slides for Java kütüphanesi projenize eklendi.
- Grafik için kullanmak istediğiniz verileri içeren bir Excel çalışma kitabı.

## 1. Adım: Bir Sunu Oluşturun

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

Aspose.Slides for Java'yı kullanarak yeni bir PowerPoint sunumu oluşturarak başlıyoruz.

## 2. Adım: Grafik Ekleme

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Daha sonra sunumdaki slaytlardan birine bir grafik ekliyoruz. Bu örnekte pasta grafik ekliyoruz ancak siz ihtiyaçlarınıza uygun grafik türünü seçebilirsiniz.

## 3. Adım: Grafik Verilerini Temizle

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Excel çalışma kitabındaki yeni verilere hazırlamak için grafikteki mevcut verileri temizliyoruz.

## Adım 4: Excel Çalışma Kitabını Yükleyin

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

 Grafik için kullanmak istediğimiz verileri içeren Excel çalışma kitabını yüklüyoruz. Yer değiştirmek`"book1.xlsx"` Excel dosyanızın yolu ile birlikte.

## Adım 5: Çalışma Kitabı Akışını Grafik Verilerine Yazma

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Excel çalışma kitabı verilerini bir akışa dönüştürüp grafik verilerine yazıyoruz.

## Adım 6: Grafik Veri Aralığını Ayarlayın

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Grafik için veri olarak kullanılması gereken Excel çalışma kitabından hücre aralığını belirtiriz. Verileriniz için aralığı gerektiği gibi ayarlayın.

## Adım 7: Grafik Serisini Özelleştirin

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

İhtiyaçlarınıza uyacak şekilde grafik serisinin çeşitli özelliklerini özelleştirebilirsiniz. Bu örnekte grafik serisi için çeşitli renkleri etkinleştiriyoruz.

## Adım 8: Sunuyu Kaydetme

```java
pres.save(outPath, SaveFormat.Pptx);
```

Son olarak, güncellenmiş grafik verilerinin bulunduğu sunumu belirtilen çıktı yoluna kaydediyoruz.

## Java Slaytlarındaki Çalışma Kitabından Grafik Verilerini Ayarlamak İçin Tam Kaynak Kodu

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
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

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak Java Slides'da bir Excel çalışma kitabından grafik verilerinin nasıl ayarlanacağını öğrendik. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodu örneklerini kullanarak dinamik grafik verilerini PowerPoint sunumlarınıza kolayca entegre edebilirsiniz.

## SSS'ler

### Sunumumdaki grafiğin görünümünü nasıl özelleştirebilirim?

Renkler, yazı tipleri, etiketler ve daha fazlası gibi özellikleri değiştirerek grafiğin görünümünü özelleştirebilirsiniz. Grafik özelleştirme seçenekleri hakkında ayrıntılı bilgi için Aspose.Slides for Java belgelerine bakın.

### Grafik için farklı bir Excel dosyasındaki verileri kullanabilir miyim?

Evet, çalışma kitabını koda yüklerken doğru dosya yolunu belirterek herhangi bir Excel dosyasındaki verileri kullanabilirsiniz.

### Aspose.Slides for Java ile başka ne tür grafikler oluşturabilirim?

Aspose.Slides for Java, çubuk grafikler, çizgi grafikler, dağılım grafikleri ve daha fazlası dahil olmak üzere çeşitli grafik türlerini destekler. Veri temsili ihtiyaçlarınıza en uygun grafik türünü seçebilirsiniz.

### Çalışan bir sunumda grafik verilerini dinamik olarak güncellemek mümkün müdür?

Evet, temel çalışma kitabını değiştirerek ve ardından grafik verilerini yenileyerek bir sunumdaki grafik verilerini dinamik olarak güncelleştirebilirsiniz.

### Aspose.Slides for Java ile çalışmak için daha fazla örneği ve kaynağı nerede bulabilirim?

 Ek örnekleri ve kaynakları inceleyebilirsiniz.[Web sitesi](https://www.aspose.com/). Ayrıca Aspose.Slides for Java belgeleri, kütüphaneyle çalışma konusunda kapsamlı rehberlik sağlar.