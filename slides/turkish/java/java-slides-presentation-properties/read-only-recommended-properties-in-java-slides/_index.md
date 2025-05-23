---
"description": "Java PowerPoint sunumlarında Aspose.Slides for Java kullanarak Salt Okunur Önerilen özelliklerinin nasıl etkinleştirileceğini öğrenin. Gelişmiş sunum güvenliği için kaynak kod örnekleriyle adım adım kılavuzumuzu izleyin."
"linktitle": "Java Slaytlarında Salt Okunur Önerilen Özellikler"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Salt Okunur Önerilen Özellikler"
"url": "/tr/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Salt Okunur Önerilen Özellikler


## Java Slaytlarında Salt Okunur Önerilen Özellikleri Etkinleştirmeye Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumları için Salt Okunur Önerilen özelliklerinin nasıl etkinleştirileceğini inceleyeceğiz. Salt Okunur Önerilen özellikleri, kullanıcıları herhangi bir değişiklik yapmadan bir sunumu görüntülemeye teşvik etmek istediğinizde yararlı olabilir. Bu özellikler, sunumun salt okunur modunda açılması gerektiğini önerir. Bunu başarmanız için size adım adım bir kılavuz ve Java kaynak kodu sağlayacağız.

## Ön koşullar

Başlamadan önce projenizde Aspose.Slides for Java kütüphanesinin kurulu olduğundan emin olun. Bunu şuradan indirebilirsiniz: [Java web sitesi için Aspose.Slides](https://products.aspose.com/slides/java/).

## Adım 1: Yeni bir PowerPoint Sunumu Oluşturun

Aspose.Slides for Java kullanarak yeni bir PowerPoint sunumu oluşturarak başlayacağız. Zaten bir sunumunuz varsa, bu adımı atlayabilirsiniz.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Yukarıdaki kodda, çıktı PowerPoint dosyasının yolunu tanımladık ve yeni bir sunum nesnesi oluşturduk.

## Adım 2: Salt Okunur Önerilen Özelliği Etkinleştir

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

Bu kod parçacığında şunu kullanıyoruz: `getProtectionManager().setReadOnlyRecommended(true)` Salt Okunur Önerilen özelliğini ayarlamak için yöntem `true`Bu, birisi sunuyu açtığında, salt okunur modunda açması istenmesini sağlar.

## Adım 3: Sunumu Kaydedin

Son olarak sunumu Salt Okunur Önerilen özelliği etkinleştirilerek kaydediyoruz.

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

Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumu için Salt Okunur Önerilen özelliğini nasıl etkinleştireceğinizi öğrendiniz. Bu özellik, düzenlemeyi kısıtlamak ve izleyicileri sunumu salt okunur modunda kullanmaya teşvik etmek istediğinizde faydalı olabilir. Sunum için bir parola ayarlayarak güvenliği daha da artırabilirsiniz.

## SSS

### Salt Okunur Önerilen özelliğini nasıl devre dışı bırakabilirim?

Salt Okunur Önerilen özelliğini devre dışı bırakmak için aşağıdaki kodu kullanmanız yeterlidir:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Salt Okunur Önerilen bir sunum için parola ayarlayabilir miyim?

Evet, Aspose.Slides for Java kullanarak Salt Okunur Önerilen bir sunum için bir parola ayarlayabilirsiniz. `setPassword` sunum için bir parola belirleme yöntemi. Bir parola belirlenirse, kullanıcıların sunumu açmak için salt okunur modda bile parolayı girmeleri gerekir.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Değiştirmeyi unutmayın `"YourPassword"` İstediğiniz şifreyle.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}