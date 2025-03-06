---
title: Java Slaytlarında Döndürme Açısını Ayarlama
linktitle: Java Slaytlarında Döndürme Açısını Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile Java slaytlarınızı optimize edin. Metin öğeleri için dönüş açılarını ayarlamayı öğrenin. Kaynak koduyla adım adım kılavuz.
weight: 17
url: /tr/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Döndürme Açısını Ayarlamaya Giriş

Bu eğitimde Aspose.Slides for Java kütüphanesini kullanarak grafik ekseni başlığındaki metnin dönüş açısının nasıl ayarlanacağını inceleyeceğiz. Döndürme açısını ayarlayarak grafiğinizin eksen başlıklarının görünümünü sunum ihtiyaçlarınıza daha iyi uyacak şekilde özelleştirebilirsiniz.

## Önkoşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin kurulu ve kurulu olduğundan emin olun. Kütüphaneyi Aspose web sitesinden indirebilir ve belgelerinde verilen kurulum talimatlarını takip edebilirsiniz.

## 1. Adım: Bir Sunu Oluşturun

Öncelikle yeni bir sunum oluşturmanız veya mevcut bir sunumu yüklemeniz gerekiyor. Bu örnekte yeni bir sunum oluşturacağız:

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Slayta Grafik Ekleme

Daha sonra slayda bir grafik ekleyeceğiz. Bu örnekte kümelenmiş bir sütun grafiği ekliyoruz:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Adım 3: Eksen Başlığı için Döndürme Açısını Ayarlayın

Eksen başlığının dönüş açısını ayarlamak için grafiğin dikey eksen başlığına erişmeniz ve dönüş açısını ayarlamanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

Bu kod parçacığında döndürme açısını 90 dereceye ayarlıyoruz, bu da metni dikey olarak döndürecektir. Açıyı istediğiniz değere ayarlayabilirsiniz.

## 4. Adım: Sunuyu Kaydetme

Son olarak sunuyu bir PowerPoint dosyasına kaydedin:

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
// Belgeler dizininin yolu.
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

Bu eğitimde Aspose.Slides for Java'yı kullanarak grafik ekseni başlığındaki metnin dönüş açısını nasıl ayarlayacağınızı öğrendiniz. Bu özellik, görsel olarak çekici sunumlar oluşturmak için grafiklerinizin görünümünü özelleştirmenize olanak tanır. Grafiklerinizde istediğiniz görünümü elde etmek için farklı dönüş açılarıyla denemeler yapın.

## SSS'ler

### Bir slayttaki diğer metin öğelerinin dönüş açısını nasıl değiştirebilirim?

Benzer bir yaklaşım kullanarak şekiller veya metin kutuları gibi diğer metin öğelerinin dönüş açısını değiştirebilirsiniz. Öğenin metin biçimine erişin ve dönüş açısını gerektiği gibi ayarlayın.

### Yatay eksen başlığındaki metni de döndürebilir miyim?

Evet, döndürme açısını ayarlayarak yatay eksen başlığındaki metni döndürebilirsiniz. Döndürme açısını dikey metin için 90 derece veya yatay metin için 0 derece gibi istediğiniz değere ayarlamanız yeterlidir.

### Grafik başlıkları için başka hangi biçimlendirme seçenekleri mevcuttur?

Aspose.Slides for Java grafik başlıkları için yazı tipi stilleri, renkler ve hizalama dahil olmak üzere çeşitli formatlama seçenekleri sunar. Grafik başlıklarını özelleştirmeyle ilgili daha fazla ayrıntı için belgeleri inceleyebilirsiniz.

### Bir grafik ekseni başlığındaki metnin dönüşünü canlandırmak mümkün müdür?

Evet, Aspose.Slides for Java'yı kullanarak grafik ekseni başlıkları da dahil olmak üzere metin öğelerine animasyon efektleri ekleyebilirsiniz. Sunumlarınıza animasyon ekleme hakkında bilgi için belgelere bakın.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
