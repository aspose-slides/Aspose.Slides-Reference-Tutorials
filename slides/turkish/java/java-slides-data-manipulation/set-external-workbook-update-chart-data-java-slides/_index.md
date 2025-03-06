---
title: Java Slaytlarında Harici Çalışma Kitabını Güncelleme Grafiği Verileriyle Ayarlama
linktitle: Java Slaytlarında Harici Çalışma Kitabını Güncelleme Grafiği Verileriyle Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'ta harici çalışma kitaplarını nasıl ayarlayacağınızı ve grafik verilerini nasıl güncelleyeceğinizi öğrenin. PowerPoint otomasyon becerilerinizi geliştirin.
weight: 20
url: /tr/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Güncelleme Grafiği Verileriyle Harici Çalışma Kitabını Ayarlamaya Giriş

Bu kapsamlı kılavuzda, Aspose.Slides for Java API'sini kullanarak Java Slides'ta güncellenmiş grafik verileriyle harici bir çalışma kitabı oluşturma sürecinde size yol göstereceğiz. Bu güçlü kitaplık, PowerPoint sunumlarını programlı olarak değiştirmenize olanak tanıyarak, grafik verilerinin harici bir kaynaktan güncellenmesi gibi görevleri otomatikleştirmeyi kolaylaştırır. Bu eğitimin sonunda, adım adım talimatlar ve eşlik eden Java koduyla bu görevi nasıl başaracağınıza dair net bir anlayışa sahip olacaksınız.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Slides for Java: Aspose.Slides for Java kütüphanesinin kurulu olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

2. Java Geliştirme Ortamı: Sisteminizde bir Java geliştirme ortamının kurulu olduğundan emin olun.

## 1. Adım: Yeni Bir Sunu Oluşturun

Başlamak için Aspose.Slides for Java'yı kullanarak yeni bir PowerPoint sunumu oluşturalım. İşte bunu yapmak için Java kodu:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. Adım: Grafik Ekleme

Şimdi sunumumuza bir grafik ekleyelim. Bu örnekte bir Pasta grafiği oluşturacağız:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## 3. Adım: Harici Çalışma Kitabını Ayarlayın

Burası grafiğimizin veri kaynağı olarak harici çalışma kitabını ayarladığımız yerdir. Şimdilik mevcut olmasa bile, harici çalışma kitabının URL'sini sağlamanız gerekir:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://yol/yok/mevcut", false);
```

## 4. Adım: Sunuyu Kaydetme

Son olarak sunuyu güncellenmiş grafik verileriyle kaydedin:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Güncelleştirme Tablosu Verileriyle Harici Çalışma Kitabını Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://yol/yok/mevcut", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Tebrikler! Aspose.Slides for Java'yı kullanarak Java Slides'ta güncellenmiş grafik verileriyle harici bir çalışma kitabını nasıl ayarlayacağınızı öğrendiniz. Bu, PowerPoint sunumlarınızdaki grafikleri harici veri kaynaklarından dinamik olarak güncellemek için inanılmaz derecede yararlı olabilir.

## SSS'ler

### Grafiğin harici çalışma kitabı verilerini nasıl güncelleyebilirim?

Grafiğe ilişkin harici çalışma kitabı verilerini güncellemek için, harici çalışma kitabındaki verileri belirtilen URL'de değiştirmeniz yeterlidir. Sunumu bir sonraki açışınızda Aspose.Slides for Java, güncellenmiş verileri harici çalışma kitabından getirecek ve grafiği buna göre güncelleyecektir.

### Yerel bir dosyayı harici çalışma kitabı olarak kullanabilir miyim?

Evet, URL yerine dosya yolunu sağlayarak yerel bir dosyayı harici çalışma kitabı olarak kullanabilirsiniz. Dosya yolunun doğru olduğundan ve Java uygulamanızdan erişilebilir olduğundan emin olun.

### Aspose.Slides for Java ile harici çalışma kitaplarını kullanmanın herhangi bir sınırlaması var mı?

Harici çalışma kitaplarını kullanmak güçlü bir özellik olsa da, harici çalışma kitabı verilerinin kullanılabilirliğinin, sağlanan URL'deki veya dosya yolundaki erişilebilirliğe bağlı olduğunu unutmayın. Veri alma sorunlarını önlemek için sunuyu açtığınızda harici veri kaynağının kullanılabilir olduğundan emin olun.

### Harici çalışma kitabını ayarladıktan sonra grafiğin görünümünü özelleştirebilir miyim?

Evet, harici çalışma kitabını ayarladıktan sonra bile grafiğin görünümünü (başlığı, etiketleri, renkleri ve daha fazlasını içerecek şekilde) özelleştirebilirsiniz. Aspose.Slides for Java, ihtiyaçlarınızı karşılayacak kapsamlı grafik formatlama seçenekleri sunar.

### Aspose.Slides for Java için daha fazla belge ve kaynağı nerede bulabilirim?

 Ayrıntılı belgeler ve ek kaynaklar için Aspose.Slides for Java belgelerini ziyaret edin:[Burada](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
