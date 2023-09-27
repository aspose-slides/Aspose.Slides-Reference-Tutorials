---
title: Java Slaytlarındaki Grafik Varlıkları
linktitle: Java Slaytlarındaki Grafik Varlıkları
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java Slides grafikleri oluşturmayı ve özelleştirmeyi öğrenin. Sunumlarınızı güçlü grafik varlıklarıyla geliştirin.
type: docs
weight: 13
url: /tr/java/data-manipulation/chart-entities-java-slides/
---

## Java Slaytlarındaki Grafik Varlıklarına Giriş

Grafikler sunumlardaki verileri görselleştirmek için güçlü araçlardır. İster iş raporları, ister akademik sunumlar, ister başka herhangi bir içerik türü oluşturuyor olun, grafikler bilgilerin etkili bir şekilde iletilmesine yardımcı olur. Aspose.Slides for Java, grafiklerle çalışmak için güçlü özellikler sunarak onu Java geliştiricilerinin tercihi haline getiriyor.

## Önkoşullar

Grafik varlıkları dünyasına dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java Geliştirme Kiti (JDK) yüklü
- Aspose.Slides for Java kütüphanesi indirildi ve projenize eklendi
- Java programlamayla ilgili temel bilgiler

Şimdi Aspose.Slides for Java'yı kullanarak grafikler oluşturmaya ve özelleştirmeye başlayalım.

## Adım 1: Sunum Oluşturma

İlk adım, grafiğinizi ekleyeceğiniz yeni bir sunum oluşturmaktır. İşte bir sunum oluşturmak için bir kod pasajı:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Grafik Ekleme

Sununuzu hazırladıktan sonra grafik eklemenin zamanı geldi. Bu örnekte işaretçiler içeren basit bir çizgi grafiği ekleyeceğiz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
// İlk slayda erişim
ISlide slide = pres.getSlides().get_Item(0);

// Örnek grafiğin eklenmesi
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 3. Adım: Grafik Başlığını Özelleştirme

İyi tanımlanmış bir grafiğin bir başlığı olmalıdır. Grafiğimize bir başlık koyalım:

```java
// Grafik Başlığını Ayarlama
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Adım 4: Izgara Çizgilerini Biçimlendirme

Grafiğinizin büyük ve küçük ızgara çizgilerini biçimlendirebilirsiniz. Dikey eksen ızgara çizgileri için bazı biçimlendirmeler ayarlayalım:

```java
// Değer ekseni için Ana kılavuz çizgileri formatını ayarlama
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Değer ekseni için ikincil kılavuz çizgileri formatını ayarlama
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Adım 5: Değer Eksenini Özelleştirme

Değer ekseninin sayı formatı, maksimum ve minimum değerleri üzerinde kontrol sizdedir. Bunu nasıl özelleştireceğiniz aşağıda açıklanmıştır:

```java
// Değer ekseni numarası formatının ayarlanması
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Grafiğin maksimum ve minimum değerlerinin ayarlanması
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Adım 6: Değer Ekseni Başlığı Ekleme

Grafiğinizi daha bilgilendirici hale getirmek için değer eksenine bir başlık ekleyebilirsiniz:

```java
// Değer ekseni başlığını ayarlama
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Adım 7: Kategori Eksenini Biçimlendirme

Genellikle veri kategorilerini temsil eden kategori ekseni de özelleştirilebilir:

```java
// Kategori ekseni için Ana kılavuz çizgileri formatını ayarlama
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//Kategori ekseni için İkincil kılavuz çizgileri formatını ayarlama
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Adım 8: Efsane Ekleme

Göstergeler, grafiğinizdeki veri serilerini açıklamaya yardımcı olur. Efsaneleri kişiselleştirelim:

```java
// Efsane Metin Özelliklerini Ayarlama
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Çakışan grafik olmadan grafik göstergelerini göster ayarla
chart.getLegend().setOverlay(true);
```

## Adım 9: Sunumu Kaydetme

Son olarak sunumunuzu grafikle birlikte kaydedin:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarındaki Grafik Varlıkları İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Sunumu somutlaştırma// Sunumu somutlaştırma
Presentation pres = new Presentation();
try
{
	// İlk slayda erişim
	ISlide slide = pres.getSlides().get_Item(0);
	// Örnek grafiğin eklenmesi
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Grafik Başlığını Ayarlama
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Değer ekseni için Ana kılavuz çizgileri formatını ayarlama
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Değer ekseni için ikincil kılavuz çizgileri formatını ayarlama
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Değer ekseni numarası formatının ayarlanması
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Grafiğin maksimum ve minimum değerlerinin ayarlanması
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Değer Ekseni Metin Özelliklerini Ayarlama
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Değer ekseni başlığını ayarlama
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Değer ekseni çizgi biçiminin ayarlanması: Artık Eski
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Kategori ekseni için Ana kılavuz çizgileri formatını ayarlama
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//Kategori ekseni için İkincil kılavuz çizgileri formatını ayarlama
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Kategori Ekseni Metin Özelliklerini Ayarlama
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Kategori Başlığını Ayarlama
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Kategori ekseni etiket konumunun ayarlanması
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Kategori ekseni etikel dönüş açısının ayarlanması
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Efsane Metin Özelliklerini Ayarlama
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Çakışan grafik olmadan grafik göstergelerini göster ayarla
	chart.getLegend().setOverlay(true);
	// İlk seriyi ikincil değer ekseninde çizme
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Grafiğin arka duvar rengini ayarlama
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Çizim alanı rengini ayarlama
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Sunumu Kaydet
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu makalede Aspose.Slides for Java'yı kullanarak Java Slides'daki grafik varlıklarının dünyasını keşfettik. Sunumlarınızı geliştirmek için grafikleri nasıl oluşturacağınızı, özelleştireceğinizi ve değiştireceğinizi öğrendiniz. Grafikler yalnızca verilerinizi görsel olarak çekici kılmakla kalmaz, aynı zamanda hedef kitlenizin karmaşık bilgileri daha kolay anlamasına da yardımcı olur.

## SSS'ler

### Grafik türünü nasıl değiştiririm?

 Grafik türünü değiştirmek için`chart.setType()` yöntemini seçin ve istediğiniz grafik türünü belirtin.

### Bir grafiğe birden fazla veri serisi ekleyebilir miyim?

 Evet, kullanarak bir grafiğe birden fazla veri serisi ekleyebilirsiniz.`chart.getChartData().getSeries().addSeries()` yöntem.

### Grafik renklerini nasıl özelleştiririm?

Izgara çizgileri, başlık ve göstergeler gibi çeşitli grafik öğeleri için dolgu formatını ayarlayarak grafik renklerini özelleştirebilirsiniz.

### 3D grafikler oluşturabilir miyim?

 Evet, Aspose.Slides for Java, 3D grafiklerin oluşturulmasını destekler. Ayarlayabilirsiniz`ChartType` oluşturmak için bir 3B grafik türüne gidin.

### Aspose.Slides for Java en son Java sürümleriyle uyumlu mu?

Evet, Aspose.Slides for Java, en yeni Java sürümlerini destekleyecek şekilde düzenli olarak güncellenir ve çok çeşitli Java ortamlarında uyumluluk sağlar.