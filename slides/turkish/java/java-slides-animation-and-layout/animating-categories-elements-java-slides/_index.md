---
title: Java Slaytlarında Kategori Öğelerini Hareketlendirme
linktitle: Java Slaytlarında Kategori Öğelerini Hareketlendirme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile Java sunumlarınızı optimize edin. PowerPoint slaytlarındaki kategori öğelerini adım adım nasıl canlandıracağınızı öğrenin.
weight: 10
url: /tr/java/animation-and-layout/animating-categories-elements-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Kategori Öğelerini Hareketlendirme


## Java Slaytlarındaki Kategori Öğelerini Animasyona Giriş

Bu eğitimde, Aspose.Slides for Java'yı kullanarak Java slaytlarındaki kategori öğelerini canlandırma sürecinde size rehberlik edeceğiz. Bu adım adım kılavuz, bu animasyon efektini elde etmenize yardımcı olacak kaynak kodunu ve açıklamaları sağlayacaktır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.Slides for Java API kuruldu.
- Bir grafik içeren mevcut bir PowerPoint sunumu. Bu grafiğin kategori öğelerini canlandıracaksınız.

## 1. Adım: Aspose.Slides Kitaplığını İçe Aktarın

Başlamak için Aspose.Slides kütüphanesini Java projenize aktarın. Kütüphaneyi indirip projenizin sınıf yoluna ekleyebilirsiniz. Gerekli bağımlılıkları kurduğunuzdan emin olun.

## 2. Adım: Sunuyu Yükleyin

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 Bu kodda, animasyon yapmak istediğiniz grafiği içeren mevcut bir PowerPoint sunumunu yüklüyoruz. Yer değiştirmek`"Your Document Directory"` belge dizininizin gerçek yolu ile.

## Adım 3: Grafik Nesnesine Referans Alın

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

Sunumun ilk slaytında grafik nesnesine bir referans elde ederiz. Slayt indeksini ayarlayın (`get_Item(0)`) ve şekil indeksi (`get_Item(0)`) özel grafiğinize erişmek için gerektiği gibi.

## Adım 4: Kategorilerin Öğelerini Canlandırın

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

Grafikteki kategorilerin öğelerini canlandırıyoruz. Bu kod, grafiğin tamamına bir solma efekti ekler ve ardından her kategorideki her öğeye bir "Görünme" efekti ekler. Efekt türünü ve alt türünü gerektiği gibi ayarlayın.

## Adım 5: Sunuyu Kaydetme

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 Son olarak, animasyonlu grafikle birlikte değiştirilen sunumu yeni bir dosyaya kaydedin. Yer değiştirmek`"AnimatingCategoriesElements_out.pptx"` İstediğiniz çıktı dosyası adı ile.


## Java Slaytlarındaki Kategori Öğelerini Canlandırmak İçin Tam Kaynak Kodu
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Grafik nesnesinin referansını alın
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Kategori öğelerini canlandırın
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Sunum dosyasını diske yazın
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Aspose.Slides for Java'yı kullanarak bir Java slaytındaki kategori öğelerini başarılı bir şekilde canlandırdınız. Bu adım adım kılavuz, PowerPoint sunumlarınızda bu animasyon efektini elde etmek için size gerekli kaynak kodunu ve açıklamaları sağlamıştır. Animasyonlarınızı daha da özelleştirmek için farklı efektler ve ayarlarla denemeler yapın.

## SSS'ler

### Animasyon efektlerini nasıl özelleştirebilirim?

 Animasyon efektlerini değiştirerek özelleştirebilirsiniz.`EffectType` Ve`EffectSubtype` Grafik öğelerine efektler eklerken parametreler. Mevcut animasyon efektleri hakkında daha fazla ayrıntı için Aspose.Slides for Java belgelerine bakın.

### Bu animasyonları diğer grafik türlerine uygulayabilir miyim?

Evet, kodu canlandırmak istediğiniz belirli grafik öğelerini hedefleyecek şekilde değiştirerek benzer animasyonları diğer grafik türlerine uygulayabilirsiniz. Döngü yapısını ve parametrelerini buna göre ayarlayın.

### Aspose.Slides for Java hakkında nasıl daha fazla bilgi edinebilirim?

 Kapsamlı belgeler ve ek kaynaklar için şu adresi ziyaret edin:[Java API Referansı için Aspose.Slides](https://reference.aspose.com/slides/java/) . Ayrıca kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
