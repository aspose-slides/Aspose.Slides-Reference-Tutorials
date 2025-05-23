---
"description": "Java Slaytlarında Aspose.Slides ile çalışma kitaplarını grafiklerden nasıl kurtaracağınızı öğrenin. PowerPoint otomasyonu için adım adım kılavuz."
"linktitle": "Java Slaytlarında Grafik Kurtarma Çalışma Kitabı"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafik Kurtarma Çalışma Kitabı"
"url": "/tr/java/data-manipulation/chart-recover-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik Kurtarma Çalışma Kitabı


## Java Slaytlarında Grafik Kurtarma Çalışma Kitabına Giriş

Java'da PowerPoint sunumlarıyla çalışırken, bir grafikten çalışma kitabı verilerini kurtarmanız gereken senaryolarla karşılaşabilirsiniz. Bu, özellikle veri odaklı sunumlarla uğraşırken önemli bir görev olabilir. Java için Aspose.Slides bu süreci basitleştirir ve bu kılavuzda bunu nasıl yapacağınızı göstereceğiz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.
- Java kütüphanesi için Aspose.Slides. Buradan indirebilirsiniz [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Projenizi Kurma

Favori Entegre Geliştirme Ortamınızda (IDE) yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin bağımlılıklarına ekleyin.

## Adım 2: Gerekli Sınıfları İçe Aktarma

Java kodunuzda, Aspose.Slides for Java'dan gerekli sınıfları içe aktarın:

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
    // Çalışma kitabı verilerinde işlemleri burada gerçekleştirin
    pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Java Slaytlarında Grafik Kurtarma Çalışma Kitabı İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
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

Bu kılavuzda, Java Slaytları'nda Aspose.Slides for Java kullanarak bir grafikten bir çalışma kitabını kurtarma sürecini ele aldık. Bu kitaplık görevi basitleştirerek geliştiricilerin PowerPoint sunumlarıyla programatik olarak çalışmasını kolaylaştırır. Artık, veri odaklı sunumları güvenle işleyebilir ve gerektiğinde çalışma kitabı bilgilerini çıkarabilirsiniz.

## SSS

### Java için Aspose.Slides'ı nasıl yüklerim?

Java için Aspose.Slides, web sitesinden kütüphaneyi indirerek kolayca kurulabilir. [Burada](https://releases.aspose.com/slides/java/)Java projenize entegre etmek için verilen kurulum talimatlarını izleyin.

### PowerPoint sunumundaki herhangi bir grafikten çalışma kitabı verilerini kurtarabilir miyim?

Evet, Aspose.Slides for Java kütüphanesine sahip olduğunuz ve grafiğe sunum içinde erişilebildiği sürece PowerPoint sunumundaki herhangi bir grafikten çalışma kitabı verilerini kurtarabilirsiniz. Sağlanan kod parçacığı bunun nasıl başarılacağını göstermektedir.

### Java için Aspose.Slides'ı kullanarak grafik verileriyle çalışmak için ek seçenekler var mı?

Evet, Java için Aspose.Slides, grafik verileriyle çalışmak için geniş bir seçenek yelpazesi sunar. Grafik özelliklerini düzenleyebilir, veri noktalarını alabilir ve belirli gereksinimlerinizi karşılamak için grafikler üzerinde çeşitli işlemler gerçekleştirebilirsiniz.

### Aspose.Slides for Java profesyonel PowerPoint otomasyonu için uygun mudur?

Kesinlikle! Aspose.Slides for Java, PowerPoint görevlerini otomatikleştirmek için güçlü bir kütüphanedir ve bu da onu hem temel hem de gelişmiş profesyonel kullanım durumları için uygun hale getirir. PowerPoint sunumlarını programatik olarak oluşturmak, değiştirmek ve yönetmek için kapsamlı özellikler sunar.

### Aspose.Slides for Java için daha fazla dokümana nasıl erişebilirim?

Java için Aspose.Slides hakkında ayrıntılı belgeler ve referanslar için şu adresteki belgeler sayfasını ziyaret edin: [Burada](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}