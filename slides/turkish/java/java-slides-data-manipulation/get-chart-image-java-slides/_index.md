---
title: Java Slaytlarında Grafik Görüntüsü Alın
linktitle: Java Slaytlarında Grafik Görüntüsü Alın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak Java Slides'ta grafik görsellerini nasıl elde edeceğinizi öğrenin. Bu adım adım kılavuz, kusursuz entegrasyon için kaynak kodu ve ipuçları sağlar.
weight: 19
url: /tr/java/data-manipulation/get-chart-image-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik Görüntüsü Alın


## Java Slaytlarında Grafik Görüntüsü Alma Konusuna Giriş

Aspose.Slides for Java, PowerPoint sunumlarıyla programlı olarak çalışmanıza olanak tanıyan güçlü bir kütüphanedir. Bu kütüphaneyle, grafikler de dahil olmak üzere sunumlardan çeşitli öğeler oluşturabilir, değiştirebilir ve çıkarabilirsiniz. Yaygın gereksinimlerden biri slaytlardan grafik görüntüleri elde etmektir ve bu kılavuzda bunun nasıl yapılacağını göstereceğiz.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi indirildi ve projenizde yapılandırıldı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## 1. Adım: Projenizi Kurun

Tercih ettiğiniz Entegre Geliştirme Ortamında (IDE) bir Java projesi oluşturarak başlayın. Aspose.Slides for Java kütüphanesini projenizin bağımlılıklarına eklediğinizden emin olun.

## Adım 2: Sunumu Başlatın

Başlamak için bir PowerPoint sunumunu başlatmanız gerekir. Bu örnekte, belge dizininizde "test.pptx" adında bir PowerPoint dosyanız olduğunu varsayıyoruz.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3. Adım: Grafik Ekleyin ve Resmi Alın

Daha sonra bir slayta grafik ekleyebilir ve görselini alabilirsiniz. Bu örnekte kümelenmiş bir sütun grafiği ekleyeceğiz.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

Bu kod parçacığında sunumun ilk slaydında kümelenmiş bir sütun grafiği oluşturup ardından küçük resmini elde ediyoruz. Resim belirtilen dizine "image.png" olarak kaydedilir.

## Java Slaytlarında Grafik Görüntüsü Almak İçin Kaynak Kodunu Tamamlayın

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Aspose.Slides for Java kullanarak Java Slides'tan grafik görüntüleri elde etmek basit bir işlemdir. Sağlanan kodla, bu işlevselliği Java uygulamalarınıza kolayca entegre ederek PowerPoint sunumlarıyla etkili bir şekilde çalışmanıza olanak tanıyabilirsiniz.

## SSS'ler

### Aspose.Slides for Java'yı nasıl yüklerim?

 Aspose.Slides for Java'yı yüklemek basittir. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/) ve belgelerde verilen kurulum talimatlarını izleyin.

### Grafiği, görüntüsünü almadan önce özelleştirebilir miyim?

Evet, grafiğin görüntüsünü almadan önce grafiğin görünümünü, verilerini ve diğer özelliklerini özelleştirebilirsiniz. Aspose.Slides for Java, grafik özelleştirmesi için kapsamlı seçenekler sunar.

### Aspose.Slides for Java başka hangi özellikleri sunuyor?

Aspose.Slides for Java, PowerPoint sunumlarıyla çalışmak için slayt oluşturma, metin işleme, şekil düzenleme ve çok daha fazlasını içeren çok çeşitli özellikler sunar. Detaylı bilgi için dokümanları inceleyebilirsiniz.

### Aspose.Slides for Java ticari kullanıma uygun mu?

Evet, Aspose.Slides for Java ticari amaçlarla kullanılabilir. Hem bireysel geliştiricilere hem de işletmelere hitap eden lisanslama seçenekleri sunar.

### Grafik görselini farklı bir formatta kaydedebilir miyim?

 Kesinlikle! Grafik görselini, uygun dosya uzantısını belirterek, JPEG veya GIF gibi çeşitli formatlarda kaydedebilirsiniz.`ImageIO.write` yöntem.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
