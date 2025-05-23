---
"description": "Java Slaytları'nda Aspose.Slides for Java'yı kullanarak harici çalışma kitaplarını nasıl ayarlayacağınızı ve grafik verilerini nasıl güncelleyeceğinizi öğrenin. PowerPoint otomasyon becerilerinizi geliştirin."
"linktitle": "Java Slaytlarında Grafik Verilerini Güncelleştiren Harici Çalışma Kitabını Ayarla"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafik Verilerini Güncelleştiren Harici Çalışma Kitabını Ayarla"
"url": "/tr/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik Verilerini Güncelleştiren Harici Çalışma Kitabını Ayarla


## Java Slaytlarında Grafik Verilerini Güncelleyerek Harici Çalışma Kitabı Ayarlamaya Giriş

Bu kapsamlı kılavuzda, Java Slides'da Aspose.Slides for Java API'sini kullanarak güncellenmiş grafik verileriyle harici bir çalışma kitabı ayarlama sürecinde size yol göstereceğiz. Bu güçlü kitaplık, PowerPoint sunumlarını programatik olarak düzenlemenize olanak tanır ve grafik verilerini harici bir kaynaktan güncelleme gibi görevleri otomatikleştirmeyi kolaylaştırır. Bu eğitimin sonunda, adım adım talimatlar ve eşlik eden Java koduyla bu görevi nasıl başaracağınıza dair net bir anlayışa sahip olacaksınız.

## Ön koşullar

Uygulamaya geçmeden önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Java için Aspose.Slides: Java için Aspose.Slides kütüphanesi yüklü olmalıdır. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

2. Java Geliştirme Ortamı: Sisteminizde bir Java geliştirme ortamının kurulu olduğundan emin olun.

## Adım 1: Yeni Bir Sunum Oluşturun

Başlamak için Aspose.Slides for Java kullanarak yeni bir PowerPoint sunumu oluşturalım. Bunu yapmak için Java kodu şu şekildedir:

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Bir Grafik Ekleyin

Şimdi, sunumumuza bir grafik ekleyelim. Bu örnekte bir Pasta grafiği oluşturacağız:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Adım 3: Harici Çalışma Kitabını Ayarla

Burada harici çalışma kitabını grafiğimiz için veri kaynağı olarak ayarlıyoruz. Şimdilik mevcut olmasa bile harici çalışma kitabının URL'sini sağlamanız gerekir:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://yol/yok/var", false);
```

## Adım 4: Sunumu Kaydedin

Son olarak sunumu güncellenmiş grafik verileriyle kaydedin:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Güncelleme Tablosu Verileriyle Harici Çalışma Kitabı Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://yol/yok/var", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Tebrikler! Java Slides'da Aspose.Slides for Java kullanarak güncellenmiş grafik verileriyle harici bir çalışma kitabı ayarlamayı öğrendiniz. Bu, PowerPoint sunumlarınızdaki grafikleri harici veri kaynaklarından dinamik olarak güncellemek için inanılmaz derecede yararlı olabilir.

## SSS

### Grafik için harici çalışma kitabı verilerini nasıl güncelleyebilirim?

Grafik için harici çalışma kitabı verilerini güncellemek için, belirtilen URL'deki harici çalışma kitabındaki verileri değiştirmeniz yeterlidir. Sunuyu bir sonraki açışınızda, Java için Aspose.Slides güncellenmiş verileri harici çalışma kitabından alır ve grafiği buna göre günceller.

### Harici çalışma kitabı olarak yerel bir dosyayı kullanabilir miyim?

Evet, URL yerine dosya yolunu sağlayarak harici çalışma kitabı olarak yerel bir dosya kullanabilirsiniz. Sadece dosya yolunun doğru olduğundan ve Java uygulamanızdan erişilebilir olduğundan emin olun.

### Aspose.Slides for Java ile harici çalışma kitaplarını kullanmanın herhangi bir sınırlaması var mı?

Harici çalışma kitaplarını kullanmak güçlü bir özellik olsa da, harici çalışma kitabının verilerinin kullanılabilirliğinin sağlanan URL veya dosya yolundaki erişilebilirliğine bağlı olduğunu unutmayın. Veri alma sorunlarını önlemek için sunuyu açtığınızda harici veri kaynağının kullanılabilir olduğundan emin olun.

### Harici çalışma kitabını ayarladıktan sonra grafik görünümünü özelleştirebilir miyim?

Evet, harici çalışma kitabını ayarladıktan sonra bile grafiğin başlığı, etiketleri, renkleri ve daha fazlası dahil olmak üzere görünümünü özelleştirebilirsiniz. Java için Aspose.Slides, ihtiyaçlarınızı karşılamak için kapsamlı grafik biçimlendirme seçenekleri sunar.

### Aspose.Slides for Java için daha fazla doküman ve kaynağı nerede bulabilirim?

Ayrıntılı belgeler ve ek kaynaklar için Java için Aspose.Slides belgelerini şu adreste ziyaret edin: [Burada](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}