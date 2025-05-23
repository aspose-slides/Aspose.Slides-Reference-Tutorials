---
"description": "Aspose.Slides for Java'yı kullanarak Java Slaytlarında bireysel açıklamalar için özel yazı tipleri, boyutlar ve renklerle PowerPoint sunumlarınızı geliştirin."
"linktitle": "Java Slaytlarında Bireysel Efsane için Yazı Tipi Özellikleri"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Bireysel Efsane için Yazı Tipi Özellikleri"
"url": "/tr/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Bireysel Efsane için Yazı Tipi Özellikleri


## Java Slaytlarında Bireysel Efsaneler için Font Özelliklerine Giriş

Bu eğitimde, Java Slaytlarında Aspose.Slides for Java kullanarak tek bir efsane için yazı tipi özelliklerinin nasıl ayarlanacağını inceleyeceğiz. Yazı tipi özelliklerini özelleştirerek, PowerPoint sunumlarınızda efsanelerinizi görsel olarak daha çekici ve bilgilendirici hale getirebilirsiniz.

## Ön koşullar

Başlamadan önce, projenize Aspose.Slides for Java kütüphanesinin entegre olduğundan emin olun. Bunu şuradan indirebilirsiniz: [Java Belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/).

## Adım 1: Sunumu Başlatın ve Grafik Ekleyin

Öncelikle bir PowerPoint sunumu başlatarak ve ona bir grafik ekleyerek başlayalım. Bu örnekte, bir örnek olarak kümelenmiş sütun grafiği kullanacağız.

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

Yer değiştirmek `"Your Document Directory"` PowerPoint belgenizin bulunduğu gerçek dizinle.

## Adım 2: Legend için Yazı Tipi Özelliklerini Özelleştirin

Şimdi, grafikteki bireysel bir gösterge girişi için yazı tipi özelliklerini özelleştirelim. Bu örnekte, ikinci gösterge girişini (indeks 1) hedefliyoruz, ancak dizini özel gereksinimlerinize göre ayarlayabilirsiniz.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

İşte her bir kod satırının yaptığı şey:

- `get_Item(1)` ikinci efsane girişini (indeks 1) alır. Farklı bir efsane girişini hedeflemek için dizini değiştirebilirsiniz.
- `setFontBold(NullableBool.True)` yazı tipini kalın olarak ayarlar.
- `setFontHeight(20)` yazı tipi boyutunu 20 puntoya ayarlar.
- `setFontItalic(NullableBool.True)` yazı tipini italik olarak ayarlar.
- `setFillType(FillType.Solid)` efsane giriş metninin düz bir dolguya sahip olması gerektiğini belirtir.
- `getSolidFillColor().setColor(Color.BLUE)` dolgu rengini maviye ayarlar. Değiştirebilirsiniz `Color.BLUE` İstediğiniz renk ile.

## Adım 3: Değiştirilen Sunumu Kaydedin

Son olarak, değişikliklerinizi korumak için değiştirilmiş sunumu yeni bir dosyaya kaydedin.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Yer değiştirmek `"output.pptx"` Tercih ettiğiniz çıktı dosya adı ile.

İşte bu kadar! Java Slaytlar sunumunda Aspose.Slides for Java kullanarak bireysel bir gösterge girişi için yazı tipi özelliklerini başarıyla özelleştirdiniz.

## Java Slaytlarında Bireysel Efsaneler İçin Yazı Tipi Özelliklerinin Tam Kaynak Kodu

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

Bu eğitimde, Java Slaytlarında Aspose.Slides for Java kullanarak tek bir efsane için yazı tipi özelliklerinin nasıl özelleştirileceğini öğrendik. Yazı tipi stillerini, boyutlarını ve renklerini ayarlayarak PowerPoint sunumlarınızın görsel çekiciliğini ve netliğini artırabilirsiniz.

## SSS

### Yazı rengini nasıl değiştirebilirim?

Yazı tipi rengini değiştirmek için şunu kullanın: `tf.getPortionFormat().getFontColor().setColor(yourColor)` dolgu rengini değiştirmek yerine. Değiştir `yourColor` İstediğiniz yazı rengiyle.

### Diğer efsane özelliklerini nasıl değiştirebilirim?

Efsanenin konum, boyut ve biçim gibi çeşitli diğer özelliklerini değiştirebilirsiniz. Efsanelerle çalışma hakkında ayrıntılı bilgi için Aspose.Slides for Java belgelerine bakın.

### Bu değişiklikleri birden fazla gösterge girişine uygulayabilir miyim?

Evet, efsane girişleri arasında döngü oluşturabilir ve bu değişiklikleri dizini ayarlayarak birden fazla girişe uygulayabilirsiniz. `get_Item(index)` ve özelleştirme kodunu tekrarlamak.

Kaynakları serbest bırakmayı bitirdiğinizde sunum nesnesini elden çıkarmayı unutmayın:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}