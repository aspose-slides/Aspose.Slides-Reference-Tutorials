---
title: Java Slaytlarında Not Slayt Görünümünü Dönüştürme
linktitle: Java Slaytlarında Not Slayt Görünümünü Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak Java Slides'ta not slayt görünümlerini nasıl dönüştüreceğinizi öğrenin. Verimli PowerPoint manipülasyonu için kod örnekleri içeren adım adım kılavuz.
weight: 15
url: /tr/java/presentation-conversion/convert-notes-slide-view-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides Kullanarak Java Slaytlarında Not Slayt Görünümünü Dönüştürmeye Giriş

Günümüzün dijital çağında, PowerPoint sunumlarını programlı olarak değiştirme ve dönüştürme ihtiyacı giderek artıyor. Java geliştiricileri, sunumlarındaki not slayt görünümlerini yönetme ve dönüştürme konusunda kendilerini sıklıkla zorluklarla karşı karşıya bulurlar. Neyse ki Aspose.Slides for Java bu görev için güçlü bir çözüm sunuyor. Bu adım adım kılavuzda, Aspose.Slides kullanarak Java Slaytlar'daki not slayt görünümlerinin nasıl dönüştürüleceğini keşfedeceğiz.

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi projenize eklendi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).

## Adım 1: Java Projenizi Kurma

Başlamak için favori Entegre Geliştirme Ortamınızda (IDE) yeni bir Java projesi oluşturun. Aspose.Slides kütüphanesinin projenizin sınıf yoluna eklendiğinden emin olun.

## Adım 2: Gerekli Kitaplıkları İçe Aktarma

Java sınıfınızda gerekli kitaplıkları aşağıda gösterildiği gibi içe aktarın:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Adım 3: Sunumu Yükleme

Bir PowerPoint sunumuyla çalışmak için onu Java uygulamanıza yüklemeniz gerekir. Bir sunumu yüklemek için aşağıdaki kodu kullanın:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```

 Yer değiştirmek`"Your Document Directory"` sunum dosyanızın gerçek yolunu belirtin.

## 4. Adım: Notes Slayt Görünümüne Dönüştürme

Şimdi sunuyu not slayt görünümüne dönüştürüp TIFF belgesi olarak kaydedelim:

```java
try {
    // Sunuyu TIFF belgesine kaydetme
    pres.save(dataDir + "Tiff_out.tiff", SaveFormat.Tiff);
} finally {
    if (pres != null) pres.dispose();
}
```

 Bu kod parçacığında şunu kullanıyoruz:`save` Sunuyu TIFF dosyası olarak kaydetme yöntemi. İstediğiniz formatı şurada belirtebilirsiniz:`SaveFormat` numaralandırma.

## Java Slaytlarında Notları Slayt Görünümünü Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Bir sunum dosyasını temsil eden bir Sunum nesnesinin örneğini oluşturun
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Default.pptx");
try
{
	// Sunuyu TIFF belgesine kaydetme
	pres.save(dataDir + "Tiff_out.tiff", SaveFormat.Tiff);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides'ı kullanarak Java Slaytlar'daki not slayt görünümlerini dönüştürmek için gerekli adımları ele aldık. Bu adımları izleyerek ve kodu özel ihtiyaçlarınıza göre özelleştirerek, PowerPoint sunumlarını Java uygulamalarınızda programlı bir şekilde verimli bir şekilde değiştirebilir ve dönüştürebilirsiniz.

## SSS'ler

### Bir sunumu dönüştürürken çıktı formatını nasıl özelleştirebilirim?

 Çıkış formatını değiştirerek özelleştirebilirsiniz.`SaveFormat`koddaki numaralandırma. Örneğin sunuyu PDF olarak kaydetmek için şunu kullanın:`SaveFormat.Pdf`.

### Aspose.Slides for Java için lisans satın almam gerekiyor mu?

Evet, Aspose.Slides for Java'yı üretim ortamında kullanmak için geçerli bir lisansa ihtiyacınız olacak. Aspose web sitesinden lisans alabilirsiniz.

### Toplu modda birden fazla sunumu dönüştürebilir miyim?

Evet, Aspose.Slides for Java toplu işlemeyi destekleyerek tek seferde birden fazla sunumu dönüştürmenize olanak tanır. Sunum dosyalarının bir listesini yineleyebilir ve dönüştürme mantığını bunların her birine uygulayabilirsiniz.

### Aspose.Slides PowerPoint'in en son sürümleriyle uyumlu mu?

Aspose.Slides, en son sürümler de dahil olmak üzere çeşitli PowerPoint formatlarıyla çalışacak şekilde tasarlanmıştır. Ancak belirli format uyumluluğu ayrıntıları için belgeleri kontrol etmek her zaman iyi bir uygulamadır.

### Aspose.Slides for Java için daha fazla kod örneğini ve öğreticiyi nerede bulabilirim?

 Çok sayıda kod örneği ve öğreticiyi burada bulabilirsiniz.[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/)Bu güçlü kitaplığın yetenekleri hakkında daha fazla bilgi edinmek için belgeleri inceleyin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
