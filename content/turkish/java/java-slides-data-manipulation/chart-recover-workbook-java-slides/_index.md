---
title: Grafik Java Slaytlarındaki Çalışma Kitabını Kurtarma
linktitle: Grafik Java Slaytlarındaki Çalışma Kitabını Kurtarma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java Slides'taki grafiklerden çalışma kitaplarını nasıl kurtaracağınızı öğrenin. PowerPoint otomasyonu için adım adım kılavuz.
type: docs
weight: 17
url: /tr/java/data-manipulation/chart-recover-workbook-java-slides/
---

## Java Slaytlarında Grafik Kurtarma Çalışma Kitabına Giriş

Java'da PowerPoint sunumlarıyla çalışırken, çalışma kitabı verilerini bir grafikten kurtarmanız gereken senaryolarla karşılaşabilirsiniz. Bu, özellikle veriye dayalı sunumlarla uğraşırken çok önemli bir görev olabilir. Aspose.Slides for Java bu süreci basitleştirir ve bu kılavuzda size bunun nasıl yapılacağını göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Projenizi Ayarlama

Favori Entegre Geliştirme Ortamınızda (IDE) yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin bağımlılıklarına ekleyin.

## Adım 2: Gerekli Sınıfları İçe Aktarma

Java kodunuzda gerekli sınıfları Aspose.Slides for Java'dan içe aktarın:

```java
import com.aspose.slides.*;
```

## Adım 3: Sunumu Yükleme

Çalışma kitabı verilerini kurtarmak istediğiniz grafiği içeren PowerPoint sunumunu yükleyin:

```java
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = "Path to Output File";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
```

## Adım 4: Grafik Verilerine Erişim

Artık grafik verilerine erişebilir ve çalışma kitabını kurtarabilirsiniz:

```java
try
{
    IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    // Çalışma kitabı verileri üzerinde işlemleri burada gerçekleştirin
    pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Java Slaytlarındaki Grafik Kurtarma Çalışma Kitabı İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = RunExamples.OutPath + "ExternalWB_out.pptx";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
try
{
	IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu kılavuzda, Aspose.Slides for Java kullanarak Java Slides'daki bir grafikten çalışma kitabını kurtarma sürecini anlattık. Bu kitaplık görevi basitleştirerek geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasını kolaylaştırır. Artık veriye dayalı sunumları güvenle yönetebilir ve gerektiğinde çalışma kitabı bilgilerini çıkarabilirsiniz.

## SSS'ler

### Aspose.Slides for Java'yı nasıl yüklerim?

 Aspose.Slides for Java, kütüphaneyi aşağıdaki web sitesinden indirerek kolayca kurulabilir:[Burada](https://releases.aspose.com/slides/java/)Java projenize entegre etmek için sağlanan kurulum talimatlarını izleyin.

### Bir PowerPoint sunumundaki herhangi bir grafikten çalışma kitabı verilerini kurtarabilir miyim?

Evet, Aspose.Slides for Java kütüphanesine sahip olduğunuz ve grafiğe sunum içinden erişilebildiği sürece, PowerPoint sunumundaki herhangi bir grafikten çalışma kitabı verilerini kurtarabilirsiniz. Sağlanan kod pasajı bunun nasıl başarılacağını gösterir.

### Aspose.Slides for Java'yı kullanarak grafik verileriyle çalışmak için ek seçenekler var mı?

Evet, Aspose.Slides for Java, grafik verileriyle çalışmak için çok çeşitli seçenekler sunar. Özel gereksinimlerinizi karşılamak için grafik özelliklerini değiştirebilir, veri noktalarını alabilir ve grafikler üzerinde çeşitli işlemler gerçekleştirebilirsiniz.

### Aspose.Slides for Java profesyonel PowerPoint otomasyonuna uygun mu?

Kesinlikle! Aspose.Slides for Java, PowerPoint görevlerini otomatikleştirmeye yönelik güçlü bir kitaplıktır; bu da onu hem temel hem de ileri düzey profesyonel kullanım örneklerine uygun hale getirir. PowerPoint sunumlarını programlı olarak oluşturmak, değiştirmek ve yönetmek için kapsamlı özellikler sağlar.

### Aspose.Slides for Java ile ilgili diğer belgelere nasıl erişebilirim?

 Aspose.Slides for Java ile ilgili ayrıntılı belgeler ve referanslar için şu adresteki belgeler sayfasını ziyaret edin:[Burada](https://reference.aspose.com/slides/java/).