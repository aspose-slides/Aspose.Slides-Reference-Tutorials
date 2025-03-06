---
title: Java Slaytlarında Grafik Alma Aralığı
linktitle: Java Slaytlarında Grafik Alma Aralığı
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java API'yi kullanarak Java Slides'ta grafik aralıklarını nasıl alacağınızı öğrenin. Etkili grafik verilerine erişim için kaynak kodlu adım adım kılavuz.
weight: 16
url: /tr/java/data-manipulation/chart-get-range-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java Slaytlarında Grafik Alma Aralığına Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java API'sini kullanarak Java Slides'ta bir grafiğin aralığını nasıl elde edebileceğinizi keşfedeceğiz. Ayrıntılı kaynak kodu örnekleriyle süreç boyunca size yol göstereceğiz. Java Slaytlar sunumunuzdaki bir grafiğin aralığına erişmek istiyorsanız, nasıl yapılacağını öğrenmek için aşağıdaki adımları takip edin.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Ortamı Ayarlama

Kod yazmaya başlamadan önce Aspose.Slides for Java kütüphanesinin projenizin sınıf yoluna eklendiğinden emin olun. Kütüphaneyi önkoşullar bölümünde verilen bağlantıdan indirebilirsiniz.

## Adım 2: Sunum Oluşturma

Başlamak için Aspose.Slides'ı kullanarak bir sunum oluşturacağız. Bir sunum nesnesi oluşturma kodu:

```java
// Belgeler dizininin yolu.
Presentation pres = new Presentation();
```

## 3. Adım: Grafik Ekleme

Daha sonra sunuma bir grafik ekleyeceğiz. Bu örnekte kümelenmiş bir sütun grafiği oluşturacağız. İşte grafiği ekleme kodu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 400, 300);
```

## Adım 4: Aralığı Alma

 Şimdi grafiğin aralığını elde edeceğimiz kısım geliyor. biz kullanacağız`getChartData().getRange()` bunu başarmanın yöntemi:

```java
String result = chart.getChartData().getRange();
```

## Adım 5: Sonucun Görüntülenmesi

Grafik aralığını görmek için sonucu yazdıralım:

```java
System.out.println("GetRange result : " + result);
```

## Java Slaytlarında Grafik Alma Aralığı İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 400, 300);
	String result = chart.getChartData().getRange();
	System.out.println("GetRange result : " + result);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu kılavuzda, Aspose.Slides for Java API'sini kullanarak Java Slides'ta bir grafiğin aralığını nasıl elde edeceğimizi öğrendik. Ortamı ayarlamayı, sunum oluşturmayı, grafik eklemeyi ve aralığı elde etmeyi ele aldık. Grafik aralıklarına etkili bir şekilde erişmek için artık bu bilgiyi Java Slaytlar projelerinizde kullanabilirsiniz.

## SSS'ler

### Aspose.Slides for Java'yı nasıl indirebilirim?

 Aspose.Slides for Java'yı Aspose web sitesinden bu bağlantıyı kullanarak indirebilirsiniz:[Java için Aspose.Slides'ı indirin](https://releases.aspose.com/slides/java/).

### Aspose.Slides for Java'yı ücretsiz kullanabilir miyim?

Aspose.Slides for Java ticari bir kütüphanedir ancak özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz. Ancak üretim amaçlı kullanım için lisans satın almanız gerekecektir.

### Aspose.Slides for Java'nın desteklediği başka grafik türleri var mı?

Evet, Aspose.Slides for Java; çubuk grafikler, pasta grafikler, çizgi grafikler ve daha fazlası dahil olmak üzere çeşitli grafik türlerini destekler. Desteklenen grafik türlerinin tam listesi için belgeleri inceleyebilirsiniz.

### Aspose.Slides for Java'yı kullanarak grafiğin görünümünü özelleştirebilir miyim?

Evet, Aspose.Slides for Java API'sini kullanarak grafiklerin görünümünü, renkleri, yazı tiplerini ve stilleri değiştirerek özelleştirebilirsiniz. Ayrıntılı özelleştirme seçenekleri için belgelere bakın.

### Aspose.Slides for Java için daha fazla kaynağı ve belgeyi nerede bulabilirim?

 Aspose.Slides for Java'ya ilişkin kapsamlı belgeleri ve kaynakları şu sitede bulabilirsiniz:[Aspose.Slides for Java Belgelendirmesi](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
