---
"description": "تعرف على كيفية إنشاء مخططات الرادار في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java API."
"linktitle": "إنشاء مخطط الرادار في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء مخطط الرادار في شرائح Java"
"url": "/ar/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مخطط الرادار في شرائح Java


## مقدمة لإنشاء مخطط راداري في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط راداري باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. تُعدّ المخططات الرادارية مفيدة لعرض البيانات في نمط دائري، مما يُسهّل مقارنة سلاسل بيانات متعددة. سنقدم تعليمات خطوة بخطوة مع شفرة المصدر بلغة جافا.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من دمج مكتبة Aspose.Slides لجافا في مشروعك. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد العرض التقديمي

لنبدأ بإعداد عرض تقديمي جديد في PowerPoint وإضافة شريحة إليه.

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

سنقوم الآن بإعداد بيانات الرسم البياني. يتضمن ذلك إنشاء مصنف بيانات، وإضافة فئات، وإضافة سلاسل.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// تعيين عنوان الرسم البياني
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// حذف السلسلة والفئات المولدة افتراضيًا
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

## الخطوة 4: ملء بيانات السلسلة

الآن، سنقوم بملء بيانات السلسلة لمخطط الرادار الخاص بنا.

```java
// ملء بيانات السلسلة للسلسلة 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// مجموعة ألوان السلسلة
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// ملء بيانات السلسلة للسلسلة 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// مجموعة ألوان السلسلة
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## الخطوة 5: تخصيص المحور والأساطير

دعونا نقوم بتخصيص المحور والأساطير لمخطط الرادار الخاص بنا.

```java
// تعيين موضع الأسطورة
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// تعيين خصائص نص محور الفئة
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// ضبط خصائص نص الأساطير
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// تعيين خصائص نص محور القيمة
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// ضبط تنسيق رقم محور القيمة
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// تعيين قيمة الوحدة الرئيسية للمخطط
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## الخطوة 6: حفظ العرض التقديمي

أخيرًا، احفظ العرض التقديمي الناتج باستخدام مخطط الرادار

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط راداري في عرض تقديمي باوربوينت باستخدام Aspose.Slides لجافا. يمكنك الآن تخصيص هذا المثال بشكل أكبر ليناسب احتياجاتك الخاصة.

## كود المصدر الكامل لإنشاء مخطط الرادار في شرائح Java

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// الوصول إلى الشريحة الأولى
	ISlide sld = pres.getSlides().get_Item(0);
	// إضافة مخطط الرادار
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// ضبط فهرس ورقة بيانات الرسم البياني
	int defaultWorksheetIndex = 0;
	// الحصول على بيانات الرسم البياني في ورقة العمل
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// تعيين عنوان الرسم البياني
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// حذف السلسلة والفئات المولدة افتراضيًا
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
	// يتم الآن ملء بيانات السلسلة
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// مجموعة ألوان السلسلة
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// الآن يتم ملء سلسلة أخرى من البيانات
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// مجموعة ألوان السلسلة
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// تعيين موضع الأسطورة
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// تعيين خصائص نص محور الفئة
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// ضبط خصائص نص الأساطير
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// تعيين خصائص نص محور القيمة
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// ضبط تنسيق رقم محور القيمة
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// تعيين قيمة الوحدة الرئيسية للمخطط
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// حفظ العرض التقديمي المُنشأ
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط راداري في عرض تقديمي باوربوينت باستخدام Aspose.Slides لجافا. يمكنك تطبيق هذه المفاهيم لتصور بياناتك وعرضها بفعالية في تطبيقات جافا.

## الأسئلة الشائعة

### كيف يمكنني تغيير عنوان الرسم البياني؟

لتغيير عنوان الرسم البياني، قم بتعديل السطر التالي:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### هل يمكنني إضافة المزيد من سلسلة البيانات إلى مخطط الرادار؟

نعم، يمكنك إضافة المزيد من سلاسل البيانات من خلال اتباع الخطوات الواردة في "الخطوة 3" و"الخطوة 4" لكل سلسلة إضافية تريد تضمينها.

### كيف أقوم بتخصيص ألوان الرسم البياني؟

يمكنك تخصيص ألوان السلسلة عن طريق تعديل الخطوط التي تحدد `SolidFillColor` خصائص لكل سلسلة. على سبيل المثال:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### كيف يمكنني تغيير تسميات المحور وتنسيقه؟

راجع "الخطوة 5" لتخصيص تسميات المحور وتنسيقه، بما في ذلك حجم الخط ولونه.

### كيف يمكنني حفظ الرسم البياني بتنسيق ملف مختلف؟

يمكنك تغيير تنسيق الإخراج عن طريق تعديل امتداد الملف في `outPath` المتغير واستخدام المناسب `SaveFormat`على سبيل المثال، لحفظ الملف بتنسيق PDF، استخدم `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}