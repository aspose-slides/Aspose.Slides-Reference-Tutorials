---
"description": "Aspose.Slides ile Java Slayt grafikleri oluşturmayı ve özelleştirmeyi öğrenin. Sunumlarınızı güçlü grafik varlıklarıyla geliştirin."
"linktitle": "Java Slaytlarında Grafik Varlıkları"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Grafik Varlıkları"
"url": "/tr/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Grafik Varlıkları


## Java Slaytlarında Grafik Varlıklarına Giriş

Grafikler, sunumlarda verileri görselleştirmek için güçlü araçlardır. İster iş raporları, ister akademik sunumlar veya başka bir içerik biçimi oluşturuyor olun, grafikler bilgileri etkili bir şekilde iletmenize yardımcı olur. Java için Aspose.Slides, grafiklerle çalışmak için sağlam özellikler sunar ve bu da onu Java geliştiricileri için tercih edilen bir seçenek haline getirir.

## Ön koşullar

Grafik varlıklarının dünyasına dalmadan önce, aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Java Geliştirme Kiti (JDK) yüklendi
- Java kütüphanesi için Aspose.Slides indirildi ve projenize eklendi
- Java programlamanın temel bilgisi

Şimdi Aspose.Slides for Java'yı kullanarak grafikler oluşturmaya ve özelleştirmeye başlayalım.

## Adım 1: Bir Sunum Oluşturma

İlk adım, grafiğinizi ekleyeceğiniz yeni bir sunum oluşturmaktır. İşte bir sunum oluşturmak için bir kod parçası:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Adım 2: Grafik Ekleme

Sunumunuz hazır olduğunda, bir grafik ekleme zamanı geldi. Bu örnekte, işaretçilerle basit bir çizgi grafiği ekleyeceğiz. Bunu nasıl yapabileceğinizi burada bulabilirsiniz:

```java
// İlk slayda erişim
ISlide slide = pres.getSlides().get_Item(0);

// Örnek grafiğin eklenmesi
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Adım 3: Grafik Başlığını Özelleştirme

İyi tanımlanmış bir grafiğin bir başlığı olmalıdır. Grafiğimiz için bir başlık belirleyelim:

```java
// Ayar Tablosu Başlığı
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Adım 4: Izgara Çizgilerini Biçimlendirme

Grafiğinizin ana ve alt ızgara çizgilerini biçimlendirebilirsiniz. Dikey eksen ızgara çizgileri için biraz biçimlendirme ayarlayalım:

```java
// Değer ekseni için Ana kılavuz çizgileri biçimini ayarlama
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Değer ekseni için Küçük ızgara çizgileri biçimini ayarlama
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Adım 5: Değer Eksenini Özelleştirme

Sayı biçimi, değer ekseninin maksimum ve minimum değerleri üzerinde kontrole sahipsiniz. İşte bunu nasıl özelleştireceğiniz:

```java
// Değer ekseni sayı biçimini ayarlama
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Grafik maksimum ve minimum değerlerinin ayarlanması
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Adım 6: Değer Eksen Başlığı Ekleme

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
// Kategori ekseni için Ana kılavuz çizgileri biçimini ayarlama
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Kategori ekseni için Küçük ızgara çizgileri biçimini ayarlama
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Adım 8: Efsanelerin Eklenmesi

Efsaneler, grafiğinizdeki veri serilerini açıklamanıza yardımcı olur. Efsaneleri özelleştirelim:

```java
// Efsanelerin Metin Özelliklerini Ayarlama
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Grafik göstergelerini çakışan grafikler olmadan göster
chart.getLegend().setOverlay(true);
```

## Adım 9: Sunumu Kaydetme

Son olarak sunumunuzu grafikle birlikte kaydedin:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Java Slaytlarında Grafik Varlıkları İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Eğer mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Sunumun örneklenmesi// Sunumun örneklenmesi
Presentation pres = new Presentation();
try
{
	// İlk slayda erişim
	ISlide slide = pres.getSlides().get_Item(0);
	// Örnek grafiğin eklenmesi
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Ayar Tablosu Başlığı
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Değer ekseni için Ana kılavuz çizgileri biçimini ayarlama
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Değer ekseni için Küçük ızgara çizgileri biçimini ayarlama
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Değer ekseni sayı biçimini ayarlama
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Grafik maksimum ve minimum değerlerinin ayarlanması
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Değer Eksen Metin Özelliklerini Ayarlama
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
	// Değer ekseni çizgi biçimini ayarlama: Artık kullanımdan kaldırıldı
	// grafik.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Kategori ekseni için Ana kılavuz çizgileri biçimini ayarlama
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Kategori ekseni için Küçük ızgara çizgileri biçimini ayarlama
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Kategori Eksen Metin Özelliklerini Ayarlama
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
	// Kategori ekseni etiket konumunu ayarlama
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Kategori ekseni etiket dönüş açısının ayarlanması
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Efsanelerin Metin Özelliklerini Ayarlama
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Grafik göstergelerini çakışan grafikler olmadan göster
	chart.getLegend().setOverlay(true);
	// İlk seriyi ikincil değer eksenine yerleştirme
	// Grafik.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Grafik arka duvar rengini ayarlama
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Arsa alanı renginin ayarlanması
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

Bu makalede, Java Slides'daki grafik varlıklarının dünyasını Aspose.Slides for Java kullanarak keşfettik. Sunumlarınızı geliştirmek için grafikleri nasıl oluşturacağınızı, özelleştireceğinizi ve düzenleyeceğinizi öğrendiniz. Grafikler yalnızca verilerinizi görsel olarak çekici kılmakla kalmaz, aynı zamanda izleyicilerinizin karmaşık bilgileri daha kolay anlamalarına yardımcı olur.

## SSS

### Grafik türünü nasıl değiştirebilirim?

Grafik türünü değiştirmek için şunu kullanın: `chart.setType()` yöntemini seçin ve istediğiniz grafik türünü belirtin.

### Bir grafiğe birden fazla veri serisi ekleyebilir miyim?

Evet, bir grafiğe birden fazla veri serisi ekleyebilirsiniz. `chart.getChartData().getSeries().addSeries()` yöntem.

### Grafik renklerini nasıl özelleştirebilirim?

Izgara çizgileri, başlık ve açıklamalar gibi çeşitli grafik öğelerinin dolgu biçimini ayarlayarak grafik renklerini özelleştirebilirsiniz.

### 3D grafikler oluşturabilir miyim?

Evet, Java için Aspose.Slides 3D grafiklerin oluşturulmasını destekler. `ChartType` Bir tane oluşturmak için 3 boyutlu bir grafik türüne geçin.

### Aspose.Slides for Java en son Java sürümleriyle uyumlu mu?

Evet, Aspose.Slides for Java, en son Java sürümlerini desteklemek için düzenli olarak güncellenir ve çok çeşitli Java ortamlarıyla uyumluluk sağlar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}