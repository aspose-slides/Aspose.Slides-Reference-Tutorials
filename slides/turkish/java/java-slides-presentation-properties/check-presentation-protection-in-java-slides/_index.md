---
title: Java Slaytlarında Sunum Korumasını Kontrol Edin
linktitle: Java Slaytlarında Sunum Korumasını Kontrol Edin
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak Java slaytlarında sunum korumasını nasıl kontrol edeceğinizi öğrenin. Bu adım adım kılavuz, yazma ve açma koruması kontrollerine yönelik kod örnekleri sağlar.
weight: 15
url: /tr/java/presentation-properties/check-presentation-protection-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Sunum Korumasını Kontrol Edin


## Java Slaytlarında Sunum Korumasını Kontrol Etmeye Giriş

Bu eğitimde Aspose.Slides for Java kullanarak sunum korumasını nasıl kontrol edeceğimizi inceleyeceğiz. İki senaryoyu ele alacağız: bir sunum için yazma korumasını kontrol etmek ve açık korumayı kontrol etmek. Her senaryo için adım adım kod örnekleri sunacağız.

## Önkoşullar

Başlamadan önce Java projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. Aspose web sitesinden indirebilir ve projenizin bağımlılıklarına ekleyebilirsiniz.

### Maven Bağımlılığı

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 Yer değiştirmek`your_version_here` kullandığınız Aspose.Slides for Java sürümüyle.

## 1. Adım: Yazma Korumasını Kontrol Edin

 Bir sunumun parolayla yazmaya karşı korumalı olup olmadığını kontrol etmek için`IPresentationInfo` arayüz. İşte bunu yapacak kod:

```java
// Kaynak sunumunun yolu
String pptxFile = "path_to_presentation.pptx";

// IPresentationInfo Arayüzü aracılığıyla Yazma Koruması Parolasını Kontrol Edin
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 Yer değiştirmek`"path_to_presentation.pptx"` sunum dosyanızın gerçek yolunu ve`"password_here"` Yazma koruması şifresi ile.

## Adım 2: Açık Korumayı Kontrol Edin

 Bir sunumun açılışta parolayla korunup korunmadığını kontrol etmek için`IPresentationInfo` arayüz. İşte bunu yapacak kod:

```java
// Kaynak sunumunun yolu
String pptFile = "path_to_presentation.ppt";

// IPresentationInfo Arayüzü aracılığıyla Sunum Açık Korumasını Kontrol Edin
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 Yer değiştirmek`"path_to_presentation.ppt"` sunum dosyanızın gerçek yolunu belirtin.

## Java Slaytlarında Sunum Korumasını Kontrol Etmek İçin Tam Kaynak Kodu

```java
//Kaynak sunumunun yolu
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// IPresentationInfo Arayüzü aracılığıyla Yazma Koruması Parolasını Kontrol Edin
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// IProtéctionManager Arayüzü aracılığıyla Yazma Koruması Parolasını Kontrol Edin
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
// IPresentationInfo Arayüzü aracılığıyla Sunum Açık Korumasını Kontrol Edin
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak Java slaytlarında sunum korumasını nasıl kontrol edeceğimizi öğrendik. İki senaryoyu ele aldık: yazma korumasını kontrol etmek ve açık korumayı kontrol etmek. Korumalı sunumları etkili bir şekilde yönetmek için artık bu kontrolleri Java uygulamalarınıza entegre edebilirsiniz.

## SSS'ler

### Aspose.Slides for Java'yı nasıl edinebilirim?

Aspose.Slides for Java'yı Aspose web sitesinden indirebilir veya önkoşullar bölümünde gösterildiği gibi projenize Maven bağımlılığı olarak ekleyebilirsiniz.

### Bir sunum için hem yazma korumasını hem de açık korumayı kontrol edebilir miyim?

Evet, sağlanan kod örneklerini kullanarak bir sunum için hem yazma korumasını hem de açık korumayı kontrol edebilirsiniz.

### Koruma şifresini unutursam ne yapmalıyım?

Bir sunumun koruma parolasını unutursanız onu kurtarmanın yerleşik bir yolu yoktur. Bu gibi durumlarla karşılaşmamak için şifrelerinizin kaydını mutlaka tutun.

### Aspose.Slides for Java en son PowerPoint dosya formatlarıyla uyumlu mu?

Evet, Aspose.Slides for Java, .pptx dosyaları dahil en yeni PowerPoint dosya formatlarını destekler.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
