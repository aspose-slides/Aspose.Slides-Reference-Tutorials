---
title: كيانات الرسم البياني في شرائح جافا
linktitle: كيانات الرسم البياني في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعلم كيفية إنشاء مخططات Java Slides وتخصيصها باستخدام Aspose.Slides. قم بتحسين العروض التقديمية الخاصة بك باستخدام كيانات الرسم البياني القوية.
type: docs
weight: 13
url: /ar/java/data-manipulation/chart-entities-java-slides/
---

## مقدمة لكيانات المخطط في شرائح جافا

تعد المخططات أدوات قوية لتصور البيانات في العروض التقديمية. سواء كنت تقوم بإنشاء تقارير أعمال أو عروض تقديمية أكاديمية أو أي شكل آخر من أشكال المحتوى، فإن المخططات تساعد في نقل المعلومات بشكل فعال. يوفر Aspose.Slides for Java ميزات قوية للعمل مع المخططات، مما يجعله خيارًا مفضلاً لمطوري Java.

## المتطلبات الأساسية

قبل أن نتعمق في عالم كيانات المخطط، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت مجموعة أدوات تطوير Java (JDK).
- تم تنزيل Aspose.Slides لمكتبة Java وإضافتها إلى مشروعك
- المعرفة الأساسية ببرمجة جافا

الآن، لنبدأ في إنشاء المخططات وتخصيصها باستخدام Aspose.Slides لـ Java.

## الخطوة 1: إنشاء عرض تقديمي

الخطوة الأولى هي إنشاء عرض تقديمي جديد حيث يمكنك إضافة المخطط الخاص بك. فيما يلي مقتطف من التعليمات البرمجية لإنشاء عرض تقديمي:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

بمجرد أن يصبح العرض التقديمي جاهزًا، فقد حان الوقت لإضافة مخطط. في هذا المثال، سنقوم بإضافة مخطط خطي بسيط مع علامات. وإليك كيف يمكنك القيام بذلك:

```java
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);

// إضافة نموذج الرسم البياني
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## الخطوة 3: تخصيص عنوان المخطط

يجب أن يكون للمخطط المحدد جيدًا عنوان. دعونا نضع عنوانًا لمخططنا:

```java
// تحديد عنوان الرسم البياني
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## الخطوة 4: تنسيق خطوط الشبكة

يمكنك تنسيق خطوط الشبكة الرئيسية والثانوية للمخطط الخاص بك. لنقم بتعيين بعض التنسيق لخطوط شبكة المحور الرأسي:

```java
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور القيمة
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// ضبط تنسيق خطوط الشبكة الثانوية لمحور القيمة
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## الخطوة 5: تخصيص محور القيمة

يمكنك التحكم في تنسيق الأرقام والحد الأقصى والحد الأدنى لقيم محور القيمة. وإليك كيفية تخصيصه:

```java
// تحديد تنسيق رقم محور القيمة
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// تحديد الحد الأقصى للرسم البياني والحد الأدنى للقيم
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## الخطوة 6: إضافة عنوان محور القيمة

لجعل المخطط الخاص بك أكثر إفادة، يمكنك إضافة عنوان إلى محور القيمة:

```java
// تحديد عنوان محور القيمة
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## الخطوة 7: تنسيق محور الفئة

يمكن أيضًا تخصيص محور الفئة، الذي يمثل عادةً فئات البيانات:

```java
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور الفئة
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## الخطوة 8: إضافة الأساطير

تساعد وسائل الإيضاح في شرح سلسلة البيانات في المخطط الخاص بك. دعونا تخصيص الأساطير:

```java
// ضبط خصائص نص وسائل الإيضاح
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// قم بتعيين إظهار وسائل إيضاح المخطط دون تداخل المخطط
chart.getLegend().setOverlay(true);
```

## الخطوة 9: حفظ العرض التقديمي

وأخيرًا، احفظ عرضك التقديمي بالمخطط:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لكيانات المخطط في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// إنشاء مثيل للعرض التقديمي// إنشاء العرض التقديمي
Presentation pres = new Presentation();
try
{
	// الوصول إلى الشريحة الأولى
	ISlide slide = pres.getSlides().get_Item(0);
	// إضافة نموذج الرسم البياني
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// تحديد عنوان المخطط
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// ضبط تنسيق خطوط الشبكة الرئيسية لمحور القيمة
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// ضبط تنسيق خطوط الشبكة الثانوية لمحور القيمة
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// تحديد تنسيق رقم محور القيمة
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// تحديد الحد الأقصى للرسم البياني والحد الأدنى للقيم
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// ضبط خصائص نص محور القيمة
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// تحديد عنوان محور القيمة
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// تحديد تنسيق خط محور القيمة: أصبح الآن عفا عليه الزمن
	// Chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// ضبط تنسيق خطوط الشبكة الرئيسية لمحور الفئة
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// ضبط خصائص نص محور الفئة
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// تحديد عنوان الفئة
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// تحديد موضع تسمية محور الفئة
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// ضبط زاوية دوران تسمية محور الفئة
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// ضبط خصائص نص وسائل الإيضاح
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// قم بتعيين إظهار وسائل إيضاح المخطط دون تداخل المخطط
	chart.getLegend().setOverlay(true);
	// رسم السلسلة الأولى على محور القيمة الثانوية
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// تحديد لون الجدار الخلفي للمخطط
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// تحديد لون منطقة الأرض
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// حفظ العرض التقديمي
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذه المقالة، اكتشفنا عالم كيانات المخطط في Java Slides باستخدام Aspose.Slides for Java. لقد تعلمت كيفية إنشاء المخططات وتخصيصها ومعالجتها لتحسين عروضك التقديمية. لا تجعل الرسوم البيانية بياناتك جذابة بصريًا فحسب، بل تساعد أيضًا جمهورك على فهم المعلومات المعقدة بسهولة أكبر.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع المخطط؟

 لتغيير نوع المخطط، استخدم`chart.setType()` الطريقة وحدد نوع المخطط المطلوب.

### هل يمكنني إضافة سلسلة بيانات متعددة إلى مخطط؟

 نعم، يمكنك إضافة سلاسل بيانات متعددة إلى مخطط باستخدام`chart.getChartData().getSeries().addSeries()` طريقة.

### كيف يمكنني تخصيص ألوان المخطط؟

يمكنك تخصيص ألوان المخطط عن طريق تعيين تنسيق التعبئة لعناصر المخطط المختلفة، مثل خطوط الشبكة والعنوان ووسائل الإيضاح.

### هل يمكنني إنشاء مخططات ثلاثية الأبعاد؟

 نعم، يدعم Aspose.Slides for Java إنشاء مخططات ثلاثية الأبعاد. يمكنك ضبط`ChartType` إلى نوع مخطط ثلاثي الأبعاد لإنشاء واحد.

### هل Aspose.Slides for Java متوافق مع أحدث إصدارات Java؟

نعم، يتم تحديث Aspose.Slides for Java بانتظام لدعم أحدث إصدارات Java وتوفير التوافق عبر مجموعة واسعة من بيئات Java.