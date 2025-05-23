---
"description": "Java için Aspose.Slides kullanarak Java Slides'ta grafik resimlerinin nasıl elde edileceğini öğrenin. Bu adım adım kılavuz, sorunsuz entegrasyon için kaynak kodu ve ipuçları sağlar."
"linktitle": "Java Slaytlarında Grafik Görüntüsünü Alın"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafik Görüntüsünü Alın"
"url": "/tr/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik Görüntüsünü Alın


## Java Slaytlarında Grafik Görüntüsünü Almaya Giriş

Java için Aspose.Slides, PowerPoint sunumlarıyla programatik olarak çalışmanıza olanak tanıyan güçlü bir kütüphanedir. Bu kütüphaneyle, grafikler de dahil olmak üzere sunumlardan çeşitli öğeler oluşturabilir, düzenleyebilir ve çıkarabilirsiniz. Yaygın bir gereksinim, slaytlardan grafik görüntüleri elde etmektir ve bu kılavuzda tam olarak bunu nasıl yapacağınızı göstereceğiz.

## Ön koşullar

Koda dalmadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Sisteminizde Java Development Kit (JDK) yüklü.
- Projenizde indirilen ve yapılandırılan Java kütüphanesi için Aspose.Slides. Bunu şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Projenizi Kurun

Tercih ettiğiniz Entegre Geliştirme Ortamında (IDE) bir Java projesi oluşturarak başlayın. Projenizin bağımlılıklarına Aspose.Slides for Java kitaplığını eklediğinizden emin olun.

## Adım 2: Sunumu Başlatın

Başlamak için bir PowerPoint sunumu başlatmanız gerekir. Bu örnekte, belge dizininizde "test.pptx" adlı bir PowerPoint dosyanız olduğunu varsayıyoruz.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Adım 3: Bir Grafik Ekleyin ve Görüntüyü Alın

Sonra, bir slayta grafik ekleyebilir ve görüntüsünü alabilirsiniz. Bu örnekte, kümelenmiş bir sütun grafiği ekleyeceğiz.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

Bu kod parçacığında, sunumun ilk slaydında kümelenmiş bir sütun grafiği oluşturuyoruz ve ardından küçük resmini alıyoruz. Resim belirtilen dizine "image.png" olarak kaydedilir.

## Java Slaytlarında Grafik Görüntüsünü Almak İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
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

Java Slaytlarından Aspose.Slides for Java kullanarak grafik görüntüleri elde etmek basit bir işlemdir. Sağlanan kodla, bu işlevselliği Java uygulamalarınıza kolayca entegre edebilir ve PowerPoint sunumlarıyla etkili bir şekilde çalışabilirsiniz.

## SSS

### Java için Aspose.Slides'ı nasıl yüklerim?

Java için Aspose.Slides'ı yüklemek basittir. Kütüphaneyi şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/) ve dokümanlarda verilen kurulum talimatlarını izleyin.

### Grafiğin görüntüsünü almadan önce onu özelleştirebilir miyim?

Evet, grafiğin görüntüsünü, verilerini ve diğer özelliklerini görüntüsünü almadan önce özelleştirebilirsiniz. Java için Aspose.Slides, grafik özelleştirme için kapsamlı seçenekler sunar.

### Aspose.Slides for Java'nın başka hangi özellikleri var?

Java için Aspose.Slides, slayt oluşturma, metin düzenleme, şekil düzenleme ve çok daha fazlası dahil olmak üzere PowerPoint sunumlarıyla çalışmak için geniş bir özellik yelpazesi sunar. Ayrıntılı bilgi için belgeleri inceleyebilirsiniz.

### Aspose.Slides for Java ticari kullanıma uygun mudur?

Evet, Aspose.Slides for Java ticari amaçlar için kullanılabilir. Hem bireysel geliştiricilere hem de işletmelere hitap eden lisanslama seçenekleri sunar.

### Grafik görüntüsünü farklı bir formatta kaydedebilir miyim?

Elbette! Grafik görüntüsünü JPEG veya GIF gibi çeşitli biçimlerde, uygun dosya uzantısını belirterek kaydedebilirsiniz. `ImageIO.write` yöntem.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}