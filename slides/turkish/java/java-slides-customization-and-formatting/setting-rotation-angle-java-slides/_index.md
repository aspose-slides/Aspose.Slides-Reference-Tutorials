---
"description": "Java slaytlarınızı Aspose.Slides for Java ile optimize edin. Metin öğeleri için dönüş açılarını ayarlamayı öğrenin. Kaynak kodlu adım adım kılavuz."
"linktitle": "Java Slaytlarında Dönme Açısını Ayarlama"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Dönme Açısını Ayarlama"
"url": "/tr/java/customization-and-formatting/setting-rotation-angle-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Dönme Açısını Ayarlama


## Java Slaytlarında Dönme Açısını Ayarlamaya Giriş

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak bir grafik eksen başlığındaki metin için dönüş açısının nasıl ayarlanacağını inceleyeceğiz. Dönüş açısını ayarlayarak, grafik eksen başlıklarınızın görünümünü sunum ihtiyaçlarınıza daha iyi uyacak şekilde özelleştirebilirsiniz.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin yüklü ve ayarlanmış olduğundan emin olun. Kütüphaneyi Aspose web sitesinden indirebilir ve belgelerinde sağlanan kurulum talimatlarını takip edebilirsiniz.

## Adım 1: Bir Sunum Oluşturun

Öncelikle yeni bir sunum oluşturmanız veya mevcut bir sunumu yüklemeniz gerekir. Bu örnekte yeni bir sunum oluşturacağız:

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Slayda Bir Grafik Ekleyin

Sonra, slayda bir grafik ekleyeceğiz. Bu örnekte, kümelenmiş bir sütun grafiği ekliyoruz:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Adım 3: Eksen Başlığı için Dönüş Açısını Ayarlayın

Eksen başlığı için dönüş açısını ayarlamak için, grafiğin dikey eksen başlığına erişmeniz ve dönüş açısını ayarlamanız gerekir. Bunu şu şekilde yapabilirsiniz:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

Bu kod parçasında, metni dikey olarak döndürecek olan dönüş açısını 90 dereceye ayarlıyoruz. Açıyı istediğiniz değere ayarlayabilirsiniz.

## Adım 4: Sunumu Kaydedin

Son olarak sunumu bir PowerPoint dosyasına kaydedin:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Java Slaytlarında Dönme Açısını Ayarlamak İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Java için Aspose.Slides kullanarak bir grafik ekseni başlığındaki metin için dönüş açısını nasıl ayarlayacağınızı öğrendiniz. Bu özellik, görsel olarak çekici sunumlar oluşturmak için grafiklerinizin görünümünü özelleştirmenize olanak tanır. Grafikleriniz için istediğiniz görünümü elde etmek için farklı dönüş açılarını deneyin.

## SSS

### Slayttaki diğer metin öğelerinin dönüş açısını nasıl değiştirebilirim?

Benzer bir yaklaşım kullanarak şekiller veya metin kutuları gibi diğer metin öğelerinin dönüş açısını değiştirebilirsiniz. Öğenin metin biçimine erişin ve dönüş açısını gerektiği gibi ayarlayın.

### Yatay eksen başlığındaki metni de döndürebilir miyim?

Evet, dönüş açısını ayarlayarak yatay eksen başlığındaki metni döndürebilirsiniz. Dönüş açısını dikey metin için 90 derece veya yatay metin için 0 derece gibi istediğiniz değere ayarlamanız yeterlidir.

### Grafik başlıkları için başka hangi biçimlendirme seçenekleri mevcuttur?

Java için Aspose.Slides, yazı tipi stilleri, renkler ve hizalama dahil olmak üzere grafik başlıkları için çeşitli biçimlendirme seçenekleri sunar. Grafik başlıklarını özelleştirme hakkında daha fazla ayrıntı için belgeleri inceleyebilirsiniz.

### Bir grafik eksen başlığındaki metnin dönüşünü canlandırmak mümkün müdür?

Evet, Aspose.Slides for Java kullanarak grafik eksen başlıkları dahil olmak üzere metin öğelerine animasyon efektleri ekleyebilirsiniz. Sunularınıza animasyon ekleme hakkında bilgi için belgelere bakın.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}