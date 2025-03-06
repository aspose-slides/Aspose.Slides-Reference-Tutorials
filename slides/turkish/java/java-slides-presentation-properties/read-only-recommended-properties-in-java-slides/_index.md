---
title: Java Slaytlarında Salt Okunur Önerilen Özellikler
linktitle: Java Slaytlarında Salt Okunur Önerilen Özellikler
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak Java PowerPoint sunumlarında Salt Okunur Önerilen özellikleri nasıl etkinleştireceğinizi öğrenin. Gelişmiş sunum güvenliği için kaynak kodu örneklerinin yer aldığı adım adım kılavuzumuzu izleyin.
weight: 17
url: /tr/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Salt Okunur Önerilen Özellikler


## Java Slaytlarında Salt Okunur Önerilen Özellikleri Etkinleştirmeye Giriş

Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumları için Salt Okunur Önerilen özelliklerin nasıl etkinleştirileceğini inceleyeceğiz. Salt Okunur Önerilen özellikler, kullanıcıları herhangi bir değişiklik yapmadan bir sunuyu görüntülemeye teşvik etmek istediğinizde yararlı olabilir. Bu özellikler sunumun salt okunur modda açılması gerektiğini önerir. Bunu başarmak için size Java kaynak koduyla birlikte adım adım bir kılavuz sunacağız.

## Önkoşullar

 Başlamadan önce projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Slides for Java web sitesi](https://products.aspose.com/slides/java/).

## 1. Adım: Yeni Bir PowerPoint Sunusu Oluşturun

Aspose.Slides for Java'yı kullanarak yeni bir PowerPoint sunumu oluşturarak başlayacağız. Zaten bir sunumunuz varsa bu adımı atlayabilirsiniz.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Yukarıdaki kodda, çıktı PowerPoint dosyasının yolunu tanımladık ve yeni bir sunum nesnesi oluşturduk.

## 2. Adım: Salt Okunur Önerilen Özelliği Etkinleştirin

Şimdi sunum için Salt Okunur Önerilen özelliğini etkinleştirelim.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 Bu kod parçacığında şunu kullanıyoruz:`getProtectionManager().setReadOnlyRecommended(true)` Salt Okunur Önerilen özelliğini şu şekilde ayarlama yöntemi:`true`. Bu, birisi sunuyu açtığında, sunuyu salt okunur modda açmasının istenmesini sağlar.

## 3. Adım: Sunuyu Kaydetme

Son olarak sunumu Salt Okunur Önerilen özelliği etkin olarak kaydediyoruz.

## Java Slaytlarında Salt Okunur Önerilen Özellikler İçin Tam Kaynak Kodu

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde Aspose.Slides for Java kullanarak bir PowerPoint sunumu için Salt Okunur Önerilen özelliğini nasıl etkinleştireceğinizi öğrendiniz. Bu özellik, düzenlemeyi kısıtlamak ve izleyicileri sunuyu salt okunur modda kullanmaya teşvik etmek istediğinizde yararlı olabilir. Sunum için bir parola belirleyerek güvenliği daha da artırabilirsiniz.

## SSS'ler

### Salt Okunur Önerilen özelliğini nasıl devre dışı bırakırım?

Salt Okunur Önerilen özelliğini devre dışı bırakmak için aşağıdaki kodu kullanmanız yeterlidir:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Salt Okunur Önerilen sunum için parola ayarlayabilir miyim?

Evet, Aspose.Slides for Java'yı kullanarak Salt Okunur Önerilen sunum için bir şifre belirleyebilirsiniz. Şunu kullanabilirsiniz:`setPassword` sunum için bir şifre belirleme yöntemi. Bir parola ayarlanmışsa, salt okunur modda bile kullanıcıların sunuyu açmak için parolayı girmeleri gerekir.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Değiştirmeyi unutmayın`"YourPassword"` İstediğiniz şifre ile
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
