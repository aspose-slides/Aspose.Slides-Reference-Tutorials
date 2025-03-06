---
title: PowerPoint'te Light Rig Etkili Verilerini Alın
linktitle: PowerPoint'te Light Rig Etkili Verilerini Alın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Bu ayrıntılı, adım adım kılavuzda Aspose.Slides for Java kullanarak hafif teçhizat etkili verilerini PowerPoint sunumlarından nasıl alacağınızı öğrenin.
weight: 25
url: /tr/java/java-powerpoint-shape-formatting-geometry/get-light-rig-effective-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
PowerPoint sunum görevlerinizi Java kullanarak otomatikleştirmek mi istiyorsunuz? Başka yerde arama! Aspose.Slides for Java, geliştiricilerin Microsoft PowerPoint'in yüklü olmasına gerek kalmadan PowerPoint dosyaları oluşturmasına, işlemesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Bu kapsamlı kılavuzda, Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumundan hafif teçhizatla etkili veriler elde etmek için size adım adım yol göstereceğiz. İster deneyimli bir Java geliştiricisi olun ister yeni başlıyor olun, bu eğitim projelerinizde Aspose.Slides'ın tüm potansiyelinden yararlanmanıza yardımcı olacaktır.
## Önkoşullar
Koda dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK 8 veya üzerinin kurulu olduğundan emin olun.
2.  Aspose.Slides for Java: Kütüphaneyi şu adresten indirin:[Burada](https://releases.aspose.com/slides/java/).
3. IDE: Kodlama için IntelliJ IDEA veya Eclipse gibi bir Entegre Geliştirme Ortamı (IDE) kullanın.
4. Sunum Dosyası: Örnek bir PowerPoint dosyası (`Presentation1.pptx`) kodu test etmek için.
## Paketleri İçe Aktar
Öncelikle projemizi kurup gerekli paketleri import edelim. IDE'nizde yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin derleme yoluna ekleyin.
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## Adım 1: Proje Dizinini Ayarlayın
Proje dizininizi kurarak başlayın. Java dosyalarınızı ve PowerPoint sunumunuzu saklayacağınız bir klasör oluşturun (`Presentation1.pptx`).
```java
String dataDir = "Your Document Directory";  // Belge dizininizin gerçek yoluyla değiştirin
```
## 2. Adım: Sunuyu Yükleyin
 Daha sonra, PowerPoint sunumunu kullanarak yükleyeceksiniz.`Presentation` Aspose.Slides'tan sınıf.
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## 3. Adım: İlk Slayta Erişin
Sunum yüklendikten sonra sunumdaki ilk slayda erişin.
```java
try {
    IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
}
```
## Adım 4: Etkili Light Rig Verilerini Alın
İlk slayt ve şekil seçiliyken etkili ışık teçhizatı özelliklerini alın.
```java
System.out.println("= Effective light rig properties =");
System.out.println("Type: " + threeDEffectiveData.getLightRig().getLightType());
System.out.println("Direction: " + threeDEffectiveData.getLightRig().getDirection());
```
## Adım 5: Sunum Nesnesini Atın
Son olarak, kaynakları serbest bırakmak için sunum nesnesini elden çıkardığınızdan emin olun.
```java
} finally {
    if (pres != null) pres.dispose();
}
```
## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundan etkili hafif teçhizat verilerini başarıyla aldınız. Bu eğitim, projenizin kurulumundan hafif donanım özelliklerine erişmeye ve bunları görüntülemeye kadar temel adımları kapsıyordu. Aspose.Slides, PowerPoint dosyalarını programlı olarak değiştirmenize yardımcı olabilecek zengin özellikler sunarak onu geliştiriciler için paha biçilmez bir araç haline getiriyor.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, Java kullanarak PowerPoint dosyalarını oluşturmaya, işlemeye ve dönüştürmeye yönelik güçlü bir kitaplıktır.
### Aspose.Slides'ı Microsoft PowerPoint yüklü olmadan kullanabilir miyim?
Evet, Aspose.Slides'ı Microsoft PowerPoint yüklemeden kullanabilirsiniz.
### Aspose.Slides için nasıl geçici lisans alabilirim?
 adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java belgelerini nerede bulabilirim?
 Dokümantasyon şu adreste mevcuttur:[bu bağlantı](https://reference.aspose.com/slides/java/).
### Aspose.Slides için nasıl destek alabilirim?
 Aspose.Slides destek forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
