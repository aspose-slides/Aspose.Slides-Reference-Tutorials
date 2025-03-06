---
title: Java Slaytlarında Harici Çalışma Kitabındaki Grafik Verilerini Düzenleme
linktitle: Java Slaytlarında Harici Çalışma Kitabındaki Grafik Verilerini Düzenleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak harici bir çalışma kitabındaki grafik verilerini nasıl düzenleyeceğinizi öğrenin. Kaynak koduyla adım adım kılavuz.
weight: 17
url: /tr/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarında Harici Çalışma Kitabındaki Grafik Verilerini Düzenlemeye Giriş

Bu kılavuzda, harici bir çalışma kitabındaki grafik verilerinin Aspose.Slides for Java kullanılarak nasıl düzenleneceğini göstereceğiz. Bir PowerPoint sunumundaki grafik verilerini programlı olarak nasıl değiştireceğinizi öğreneceksiniz. Projenizde Java için Aspose.Slides kütüphanesinin kurulu ve yapılandırılmış olduğundan emin olun.

## Önkoşullar

- Java için Aspose.Slides
- Java geliştirme ortamı

## 1. Adım: Sunuyu Yükleyin

 Öncelikle verilerini düzenlemek istediğimiz grafiğin bulunduğu PowerPoint sunumunu yüklememiz gerekiyor. Yer değiştirmek`"Your Document Directory"` sunum dosyanızın gerçek yolunu belirtin.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Adım 2: Grafiğe Erişin

Sunum yüklendikten sonra sunum içindeki grafiğe erişmemiz gerekiyor. Bu örnekte grafiğin ilk slaytta olduğunu ve o slayttaki ilk şekil olduğunu varsayıyoruz.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 3. Adım: Grafik Verilerini Değiştirin

Şimdi grafik verilerini değiştirelim. Grafikteki belirli bir veri noktasını değiştirmeye odaklanacağız. Bu örnekte ilk serideki ilk veri noktasının değerini 100 olarak ayarladık. Bu değeri ihtiyacınıza göre ayarlayabilirsiniz.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 4. Adım: Sunuyu Kaydetme

Grafik verilerinde gerekli değişiklikleri yaptıktan sonra değiştirilen sunumu yeni bir dosyaya kaydedin. Gereksinimlerinize göre çıktı dosyası yolunu ve biçimini belirleyebilirsiniz.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Adım 5: Temizleme

Kaynakları serbest bırakmak için sunum nesnesini elden çıkarmayı unutmayın.

```java
if (pres != null) pres.dispose();
```

Artık Aspose.Slides for Java'yı kullanarak PowerPoint sunumunuzdaki harici çalışma kitabındaki grafik verilerini başarıyla düzenlediniz. Bu kodu özel ihtiyaçlarınıza uyacak şekilde özelleştirebilir ve Java uygulamalarınıza entegre edebilirsiniz.

## Kaynak Kodunu Tamamlayın

```java
        // Sunumda harici çalışma kitabına giden yolun neredeyse hiç kaydedilmediğine dikkat edin
        // bu nedenle, örneği çalıştırmadan önce lütfen D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\'dan externalWorkbook.xlsx dosyasını kopyalayın.
        // Belgeler dizininin yolu.
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

Bu kapsamlı kılavuzda, Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki harici çalışma kitaplarındaki grafik verilerinin nasıl düzenleneceğini araştırdık. Adım adım talimatları ve kaynak kodu örneklerini takip ederek, grafik verilerini programlı olarak kolaylıkla değiştirmek için gereken bilgi ve becerileri kazandınız.

## SSS'ler

### Farklı bir grafiği veya slaytı nasıl belirlerim?

 Farklı bir grafiğe veya slayda erişmek için uygun dizini değiştirin.`getSlides().get_Item()` Ve`getShapes().get_Item()`yöntemler. İndekslemenin 0'dan başladığını unutmayın.

### Aynı sunumda birden fazla grafikteki verileri düzenleyebilir miyim?

Evet, her grafik için grafik verileri değiştirme adımlarını tekrarlayarak aynı sunumda birden fazla grafikteki verileri düzenleyebilirsiniz.

### Harici bir çalışma kitabındaki verileri farklı bir biçimde düzenlemek istersem ne olur?

Kodu, farklı harici çalışma kitabı formatlarını işlemek için uygun Aspose.Cells sınıflarını ve bu formattaki verileri okumak ve yazmak için yöntemleri kullanarak uyarlayabilirsiniz.

### Birden fazla sunum için bu süreci nasıl otomatikleştirebilirim?

Birden fazla sunumu işlemek, her birini yüklemek, istediğiniz değişiklikleri yapmak ve değiştirilen sunumları tek tek kaydetmek için bir döngü oluşturabilirsiniz.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
