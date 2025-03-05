---
title: إنشاء مخطط رادار في شرائح جافا
linktitle: إنشاء مخطط رادار في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات رادارية في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides for Java API.
type: docs
weight: 10
url: /ar/java/chart-creation/radar-chart-creating-java-slides/
---

## مقدمة لإنشاء مخطط رادار في شرائح جافا

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط راداري باستخدام Aspose.Slides for Java API. تعتبر المخططات النسيجية مفيدة لتصور البيانات في نمط دائري، مما يسهل مقارنة سلاسل بيانات متعددة. سنقدم تعليمات خطوة بخطوة مع كود مصدر Java.

## المتطلبات الأساسية

 قبل أن نبدأ، تأكد من دمج مكتبة Aspose.Slides for Java في مشروعك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد العرض التقديمي

لنبدأ بإعداد عرض PowerPoint تقديمي جديد وإضافة شريحة إليه.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط الرادار

بعد ذلك، سنضيف مخططًا راداريًا إلى الشريحة. سنحدد موضع المخطط وأبعاده.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## الخطوة 3: إعداد بيانات الرسم البياني

سنقوم الآن بتعيين بيانات المخطط. يتضمن ذلك إنشاء مصنف بيانات وإضافة فئات وإضافة سلسلة.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// تعيين عنوان الرسم البياني
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// حذف السلسلة والفئات الافتراضية التي تم إنشاؤها
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// إضافة فئات جديدة
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// إضافة سلسلة جديدة
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## الخطوة 4: تعبئة بيانات السلسلة

الآن، سنقوم بملء بيانات السلسلة لمخطط الرادار الخاص بنا.

```java
// تعبئة بيانات السلسلة للسلسلة 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// ضبط لون السلسلة
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// تعبئة بيانات السلسلة للسلسلة 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// ضبط لون السلسلة
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## الخطوة 5: تخصيص المحور والأساطير

دعونا نخصص المحور ووسائل الإيضاح لمخطط الرادار الخاص بنا.

```java
// تعيين موقف أسطورة
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// ضبط خصائص نص محور الفئة
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// ضبط خصائص نص وسائل الإيضاح
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// ضبط خصائص نص محور القيمة
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// تحديد تنسيق رقم محور القيمة
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// تحديد قيمة الوحدة الرئيسية للرسم البياني
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## الخطوة 6: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي الذي تم إنشاؤه باستخدام المخطط الراداري

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط نسيجي في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكنك الآن تخصيص هذا المثال بشكل أكبر ليناسب احتياجاتك الخاصة.

## أكمل كود المصدر لإنشاء مخطط الرادار في شرائح Java

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// الوصول إلى الشريحة الأولى
	ISlide sld = pres.getSlides().get_Item(0);
	// إضافة مخطط الرادار
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// إعداد فهرس ورقة بيانات الرسم البياني
	int defaultWorksheetIndex = 0;
	// الحصول على ورقة عمل بيانات المخطط
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// تعيين عنوان الرسم البياني
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// حذف السلسلة والفئات الافتراضية التي تم إنشاؤها
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// إضافة فئات جديدة
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// إضافة سلسلة جديدة
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// الآن ملء بيانات السلسلة
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// ضبط لون السلسلة
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	//الآن ملء بيانات سلسلة أخرى
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// ضبط لون السلسلة
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// تعيين موقف أسطورة
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// ضبط خصائص نص محور الفئة
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// ضبط خصائص نص وسائل الإيضاح
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// ضبط خصائص نص محور القيمة
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// تحديد تنسيق رقم محور القيمة
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// تحديد قيمة الوحدة الرئيسية للرسم البياني
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// حفظ العرض التقديمي الذي تم إنشاؤه
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط نسيجي في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكنك تطبيق هذه المفاهيم لتصور بياناتك وتقديمها بشكل فعال في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تغيير عنوان الرسم البياني؟

لتغيير عنوان المخطط، قم بتعديل السطر التالي:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### هل يمكنني إضافة المزيد من سلاسل البيانات إلى المخطط الراداري؟

نعم، يمكنك إضافة المزيد من سلاسل البيانات باتباع الخطوات الواردة في "الخطوة 3" و"الخطوة 4" لكل سلسلة إضافية تريد تضمينها.

### كيف يمكنني تخصيص ألوان المخطط؟

 يمكنك تخصيص ألوان السلسلة عن طريق تعديل الخطوط التي تحدد اللون`SolidFillColor` خاصية لكل سلسلة. على سبيل المثال:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### كيف يمكنني تغيير تسميات المحاور وتنسيقها؟

راجع "الخطوة 5" لتخصيص تسميات المحاور وتنسيقاتها، بما في ذلك حجم الخط ولونه.

### كيف يمكنني حفظ المخطط بتنسيق ملف مختلف؟

يمكنك تغيير تنسيق الإخراج عن طريق تعديل امتداد الملف في ملف`outPath` المتغير واستخدام المناسب`SaveFormat` . على سبيل المثال، للحفظ بصيغة PDF، استخدم`SaveFormat.Pdf`.