---
title: Java Slaytlarında Bireysel Açıklamalar için Yazı Tipi Özellikleri
linktitle: Java Slaytlarında Bireysel Açıklamalar için Yazı Tipi Özellikleri
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak, Java Slides'daki ayrı açıklamalar için özel yazı tipi stilleri, boyutları ve renkleri ile PowerPoint sunumlarınızı geliştirin.
weight: 12
url: /tr/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java Slaytlarında Bireysel Açıklamalar için Yazı Tipi Özelliklerine Giriş

Bu eğitimde, Aspose.Slides for Java kullanarak Java Slides'ta tek bir gösterge için yazı tipi özelliklerinin nasıl ayarlanacağını keşfedeceğiz. Yazı tipi özelliklerini özelleştirerek, PowerPoint sunumlarınızda efsanelerinizi görsel olarak daha çekici ve bilgilendirici hale getirebilirsiniz.

## Önkoşullar

 Başlamadan önce Aspose.Slides for Java kütüphanesinin projenize entegre olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Slides for Java Belgelendirmesi](https://reference.aspose.com/slides/java/).

## 1. Adım: Sunumu Başlatın ve Grafik Ekleyin

Öncelikle bir PowerPoint sunumu başlatıp ona bir grafik ekleyerek başlayalım. Bu örnekte örnek olarak kümelenmiş sütun grafiğini kullanacağız.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Kodun geri kalanı buraya gelecek
} finally {
    if (pres != null) pres.dispose();
}
```

 Yer değiştirmek`"Your Document Directory"` PowerPoint belgenizin bulunduğu gerçek dizinle.

## Adım 2: Açıklama için Yazı Tipi Özelliklerini Özelleştirin

Şimdi grafikteki tek bir gösterge girişi için yazı tipi özelliklerini özelleştirelim. Bu örnekte ikinci açıklama girişini hedefliyoruz (dizin 1), ancak dizini özel gereksinimlerinize göre ayarlayabilirsiniz.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

İşte her kod satırının yaptığı şey:

- `get_Item(1)` ikinci açıklama girişini alır (dizin 1). Farklı bir açıklama girişini hedeflemek için dizini değiştirebilirsiniz.
- `setFontBold(NullableBool.True)` yazı tipini kalın olarak ayarlar.
- `setFontHeight(20)` yazı tipi boyutunu 20 puntoya ayarlar.
- `setFontItalic(NullableBool.True)` yazı tipini italik olarak ayarlar.
- `setFillType(FillType.Solid)` Açıklama girişi metninin düz bir dolguya sahip olması gerektiğini belirtir.
- `getSolidFillColor().setColor(Color.BLUE)` dolgu rengini mavi olarak ayarlar. Değiştirebilirsin`Color.BLUE` İstediğiniz renk ile.

## 3. Adım: Değiştirilen Sunuyu Kaydetme

Son olarak, değişikliklerinizi korumak için değiştirilen sunuyu yeni bir dosyaya kaydedin.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Yer değiştirmek`"output.pptx"` tercih ettiğiniz çıktı dosyası adı ile.

Bu kadar! Aspose.Slides for Java'yı kullanarak Java Slides sunumundaki bireysel bir gösterge girişinin yazı tipi özelliklerini başarıyla özelleştirdiniz.

## Java Slaytlarında Bireysel Açıklamaya Yönelik Yazı Tipi Özellikleri İçin Tam Kaynak Kodu

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java'yı kullanarak Java Slides'ta tek bir gösterge için yazı tipi özelliklerini nasıl özelleştireceğimizi öğrendik. Yazı tipi stillerini, boyutlarını ve renklerini ayarlayarak PowerPoint sunumlarınızın görsel çekiciliğini ve netliğini artırabilirsiniz.

## SSS'ler

### Yazı tipi rengini nasıl değiştirebilirim?

 Yazı tipi rengini değiştirmek için şunu kullanın:`tf.getPortionFormat().getFontColor().setColor(yourColor)` dolgu rengini değiştirmek yerine. Yer değiştirmek`yourColor` İstenilen yazı tipi rengiyle.

### Diğer gösterge özelliklerini nasıl değiştirebilirim?

Göstergenin konum, boyut ve format gibi diğer çeşitli özelliklerini değiştirebilirsiniz. Göstergelerle çalışmaya ilişkin ayrıntılı bilgi için Aspose.Slides for Java belgelerine bakın.

### Bu değişiklikleri birden fazla gösterge girişine uygulayabilir miyim?

 Evet, açıklama girişleri arasında geçiş yapabilir ve dizini ayarlayarak bu değişiklikleri birden fazla girişe uygulayabilirsiniz.`get_Item(index)` ve özelleştirme kodunun tekrarlanması.

Kaynakları serbest bırakmayı tamamladığınızda sunum nesnesini elden çıkarmayı unutmayın:

```java
if (pres != null) pres.dispose();
```
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
