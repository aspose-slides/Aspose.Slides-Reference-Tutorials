---
"description": "Java slaytlarında sunum korumasını Aspose.Slides for Java kullanarak nasıl kontrol edeceğinizi öğrenin. Bu adım adım kılavuz, yazma ve açık koruma kontrolleri için kod örnekleri sağlar."
"linktitle": "Java Slaytlarında Sunum Korumasını Kontrol Etme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Sunum Korumasını Kontrol Etme"
"url": "/tr/java/presentation-properties/check-presentation-protection-in-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Sunum Korumasını Kontrol Etme


## Java Slaytlarında Sunum Korumasını Kontrol Etmeye Giriş

Bu eğitimde, Java için Aspose.Slides kullanarak sunum korumasının nasıl kontrol edileceğini inceleyeceğiz. İki senaryoyu ele alacağız: bir sunum için yazma korumasının ve açık korumasının kontrol edilmesi. Her senaryo için adım adım kod örnekleri sağlayacağız.

## Ön koşullar

Başlamadan önce, Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. Bunu Aspose web sitesinden indirebilir ve projenizin bağımlılıklarına ekleyebilirsiniz.

### Maven Bağımlılığı

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

Yer değiştirmek `your_version_here` Kullandığınız Aspose.Slides for Java sürümüyle.

## Adım 1: Yazma Korumasını Kontrol Edin

Bir sunumun parola ile yazmaya karşı korumalı olup olmadığını kontrol etmek için şunu kullanabilirsiniz: `IPresentationInfo` arayüz. Bunu yapmak için kod şu şekilde:

```java
// Kaynak sunumuna giden yol
String pptxFile = "path_to_presentation.pptx";

// Yazma Koruması Parolasını IPresentationInfo Arayüzü Üzerinden Kontrol Edin
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

Yer değiştirmek `"path_to_presentation.pptx"` sunum dosyanıza giden gerçek yol ve `"password_here"` yazma koruma şifresi ile.

## Adım 2: Açık Korumayı Kontrol Edin

Bir sunumun açılması için bir parola ile korunup korunmadığını kontrol etmek için şunu kullanabilirsiniz: `IPresentationInfo` arayüz. Bunu yapmak için kod şu şekilde:

```java
// Kaynak sunumuna giden yol
String pptFile = "path_to_presentation.ppt";

// Sunumu Kontrol Et IPresentationInfo Arayüzü Üzerinden Açık Koruma
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

Yer değiştirmek `"path_to_presentation.ppt"` sunum dosyanızın gerçek yolunu içerir.

## Java Slaytlarında Sunum Korumasını Kontrol Etmek İçin Tam Kaynak Kodu

```java
//Kaynak sunumu için yol
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Yazma Koruması Parolasını IPresentationInfo Arayüzü Üzerinden Kontrol Edin
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// IProtectionManager Arayüzü Üzerinden Yazma Koruması Parolasını Kontrol Edin
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// Sunumu Kontrol Et IPresentationInfo Arayüzü Üzerinden Açık Koruma
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Çözüm

Bu eğitimde, Java için Aspose.Slides kullanarak Java slaytlarında sunum korumasının nasıl kontrol edileceğini öğrendik. İki senaryoyu ele aldık: yazma korumasını kontrol etme ve açık korumayı kontrol etme. Artık bu kontrolleri, korumalı sunumları etkili bir şekilde işlemek için Java uygulamalarınıza entegre edebilirsiniz.

## SSS

### Java için Aspose.Slides'ı nasıl edinebilirim?

Aspose.Slides for Java'yı Aspose web sitesinden indirebilir veya ön koşullar bölümünde gösterildiği gibi projenize Maven bağımlılığı olarak ekleyebilirsiniz.

### Bir sunum için hem yazma korumasını hem de açık korumasını işaretleyebilir miyim?

Evet, verilen kod örneklerini kullanarak bir sunum için hem yazma korumasını hem de açık korumayı kontrol edebilirsiniz.

### Koruma şifremi unutursam ne yapmalıyım?

Bir sunumun koruma parolasını unutursanız, onu kurtarmanın yerleşik bir yolu yoktur. Bu tür durumlardan kaçınmak için parolalarınızın bir kaydını tuttuğunuzdan emin olun.

### Aspose.Slides for Java en son PowerPoint dosya formatlarıyla uyumlu mudur?

Evet, Aspose.Slides for Java, .pptx dosyaları da dahil olmak üzere en son PowerPoint dosya formatlarını destekler.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}