---
"description": "Java için Aspose.Slides'ı kullanarak harici bir çalışma kitabındaki grafik verilerini nasıl düzenleyeceğinizi öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Harici Çalışma Kitabındaki Grafik Verilerini Düzenleme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Harici Çalışma Kitabındaki Grafik Verilerini Düzenleme"
"url": "/tr/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Harici Çalışma Kitabındaki Grafik Verilerini Düzenleme


## Java Slaytlarında Harici Çalışma Kitabında Grafik Verilerini Düzenlemeye Giriş

Bu kılavuzda, Java için Aspose.Slides kullanarak harici bir çalışma kitabındaki grafik verilerinin nasıl düzenleneceğini göstereceğiz. PowerPoint sunumunda grafik verilerinin programatik olarak nasıl değiştirileceğini öğreneceksiniz. Projenizde Java için Aspose.Slides kitaplığının yüklü ve yapılandırılmış olduğundan emin olun.

## Ön koşullar

- Java için Aspose.Slides
- Java geliştirme ortamı

## Adım 1: Sunumu Yükleyin

Öncelikle düzenlemek istediğimiz verinin bulunduğu grafiğin bulunduğu PowerPoint sunumunu yüklememiz gerekiyor. Değiştir `"Your Document Directory"` sunum dosyanızın gerçek yolunu içerir.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Adım 2: Tabloya Erişim

Sunum yüklendikten sonra, sunum içindeki grafiğe erişmemiz gerekir. Bu örnekte, grafiğin ilk slaytta olduğunu ve o slayttaki ilk şekil olduğunu varsayıyoruz.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Adım 3: Grafik Verilerini Değiştirin

Şimdi grafik verilerini değiştirelim. Grafikteki belirli bir veri noktasını değiştirmeye odaklanacağız. Bu örnekte, ilk serideki ilk veri noktasının değerini 100 olarak ayarladık. Bu değeri gerektiği gibi ayarlayabilirsiniz.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Adım 4: Sunumu Kaydedin

Grafik verilerinde gerekli değişiklikleri yaptıktan sonra, değiştirilen sunumu yeni bir dosyaya kaydedin. Gereksinimlerinize göre çıktı dosyası yolunu ve biçimini belirtebilirsiniz.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Adım 5: Temizleme

Herhangi bir kaynağı serbest bırakmak için sunum nesnesini elden çıkarmayı unutmayın.

```java
if (pres != null) pres.dispose();
```

Artık PowerPoint sunumunuzdaki harici bir çalışma kitabındaki grafik verilerini Aspose.Slides for Java kullanarak başarıyla düzenlediniz. Bu kodu özel ihtiyaçlarınıza uyacak şekilde özelleştirebilir ve Java uygulamalarınıza entegre edebilirsiniz.

## Tam Kaynak Kodu

```java
        // Dikkat edin, harici çalışma kitabına giden yol sunumda neredeyse hiç kaydedilmiyor
        // bu nedenle lütfen örneği çalıştırmadan önce externalWorkbook.xlsx dosyasını Data/Chart dizininden D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ kopyalayın
        // Belgeler dizinine giden yol.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Çözüm

Bu kapsamlı kılavuzda, Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki harici çalışma kitaplarındaki grafik verilerinin nasıl düzenleneceğini inceledik. Adım adım talimatları ve kaynak kodu örneklerini izleyerek, grafik verilerini kolaylıkla programatik olarak değiştirmek için bilgi ve beceriler kazandınız.

## SSS

### Farklı bir grafik veya slayt nasıl belirtebilirim?

Farklı bir grafiğe veya slayta erişmek için, ilgili dizini değiştirin. `getSlides().get_Item()` Ve `getShapes().get_Item()` yöntemler. İndekslemenin 0'dan başladığını unutmayın.

### Aynı sunum içerisinde birden fazla grafikteki verileri düzenleyebilir miyim?

Evet, aynı sunum içerisinde birden fazla grafikteki verileri, her grafik için grafik verisi değiştirme adımlarını tekrarlayarak düzenleyebilirsiniz.

### Harici bir çalışma kitabındaki verileri farklı bir biçimde düzenlemek istersem ne olur?

Uygun Aspose.Cells sınıflarını ve bu formattaki verileri okumak ve yazmak için kullanılan yöntemleri kullanarak kodu farklı harici çalışma kitabı formatlarını işleyecek şekilde uyarlayabilirsiniz.

### Bu süreci birden fazla sunum için nasıl otomatikleştirebilirim?

Birden fazla sunumu işlemek için bir döngü oluşturabilir, her birini yükleyebilir, istediğiniz değişiklikleri yapabilir ve değiştirilen sunumları tek tek kaydedebilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}