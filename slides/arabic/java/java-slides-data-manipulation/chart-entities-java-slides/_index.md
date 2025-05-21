---
"description": "تعلم كيفية إنشاء وتخصيص مخططات Java Slides باستخدام Aspose.Slides. حسّن عروضك التقديمية باستخدام كيانات مخططات فعّالة."
"linktitle": "كيانات المخططات في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "كيانات المخططات في شرائح Java"
"url": "/ar/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيانات المخططات في شرائح Java


## مقدمة إلى كيانات المخططات في شرائح Java

تُعد المخططات البيانية أدوات فعّالة لعرض البيانات في العروض التقديمية. سواءً كنت تُنشئ تقارير أعمال، أو عروضًا تقديمية أكاديمية، أو أي نوع آخر من المحتوى، تُساعد المخططات البيانية على إيصال المعلومات بفعالية. يُوفر Aspose.Slides for Java ميزات فعّالة للعمل مع المخططات البيانية، مما يجعله الخيار الأمثل لمطوري Java.

## المتطلبات الأساسية

قبل أن نتعمق في عالم كيانات الرسم البياني، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK)
- تم تنزيل مكتبة Aspose.Slides لـ Java وإضافتها إلى مشروعك
- المعرفة الأساسية ببرمجة جافا

الآن، لنبدأ في إنشاء المخططات وتخصيصها باستخدام Aspose.Slides لـ Java.

## الخطوة 1: إنشاء عرض تقديمي

الخطوة الأولى هي إنشاء عرض تقديمي جديد لإضافة مخططك. إليك مقتطف من الكود لإنشاء عرض تقديمي:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

بعد تجهيز عرضك التقديمي، حان وقت إضافة مخطط. في هذا المثال، سنضيف مخططًا خطيًا بسيطًا مع علامات. إليك كيفية القيام بذلك:

```java
// الوصول إلى الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);

// إضافة مخطط العينة
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## الخطوة 3: تخصيص عنوان الرسم البياني

يجب أن يكون للرسم البياني المُحدَّد جيدًا عنوان. لنضع عنوانًا لرسمنا البياني:

```java
// إعداد عنوان الرسم البياني
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## الخطوة 4: تنسيق خطوط الشبكة

يمكنك تنسيق خطوط الشبكة الرئيسية والفرعية في مخططك البياني. لنبدأ بضبط تنسيق خطوط شبكة المحور الرأسي:

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

يمكنك التحكم بتنسيق الأرقام، والقيم القصوى والدنيا لمحور القيمة. إليك كيفية تخصيصها:

```java
// ضبط تنسيق رقم محور القيمة
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// تعيين الحد الأقصى والحد الأدنى للقيم في المخطط
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

لجعل الرسم البياني الخاص بك أكثر إفادة، يمكنك إضافة عنوان إلى محور القيمة:

```java
// تعيين عنوان محور القيمة
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

// ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## الخطوة 8: إضافة الأساطير

تساعد الأساطير في شرح سلسلة البيانات في مخططك البياني. لنُخصص الأساطير:

```java
// ضبط خصائص نص الأساطير
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// تعيين أساطير عرض الرسم البياني دون تداخل الرسم البياني
chart.getLegend().setOverlay(true);
```

## الخطوة 9: حفظ العرض التقديمي

وأخيرًا، احفظ عرضك التقديمي باستخدام الرسم البياني:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## الكود المصدر الكامل للكيانات البيانية في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// إنشاء عرض تقديمي// إنشاء عرض تقديمي
Presentation pres = new Presentation();
try
{
	// الوصول إلى الشريحة الأولى
	ISlide slide = pres.getSlides().get_Item(0);
	// إضافة مخطط العينة
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// عنوان مخطط الإعداد
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
	// ضبط تنسيق رقم محور القيمة
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// تعيين الحد الأقصى والحد الأدنى للقيم في المخطط
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// تعيين خصائص نص محور القيمة
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// تعيين عنوان محور القيمة
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// ضبط تنسيق خط محور القيمة: غير صالح الآن
	// مخطط. الحصول على المحاور (). الحصول على المحور الرأسي (). المحور الرأسي (). خط المحور (). تعيين العرض (10)؛
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// ضبط تنسيق خطوط الشبكة الرئيسية لمحور الفئة
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// تعيين خصائص نص محور الفئة
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// إعداد الفئة العنوان
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// تعيين موضع تسمية محور الفئة
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// ضبط زاوية دوران محور الفئة القابلة للتسمية
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// ضبط خصائص نص الأساطير
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// تعيين أساطير عرض الرسم البياني دون تداخل الرسم البياني
	chart.getLegend().setOverlay(true);
	// رسم السلسلة الأولى على محور القيمة الثانوية
	// الرسم البياني.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = صحيح؛
	// مخطط ضبط لون الجدار الخلفي
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// ضبط لون منطقة الرسم البياني
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

في هذه المقالة، استكشفنا عالم كيانات المخططات في عروض Java Slides باستخدام Aspose.Slides لـ Java. تعلمت كيفية إنشاء المخططات وتخصيصها ومعالجتها لتحسين عروضك التقديمية. لا تقتصر فائدة المخططات على جعل بياناتك جذابة بصريًا فحسب، بل تساعد جمهورك أيضًا على فهم المعلومات المعقدة بسهولة أكبر.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

لتغيير نوع الرسم البياني، استخدم `chart.setType()` الطريقة وتحديد نوع الرسم البياني المطلوب.

### هل يمكنني إضافة سلاسل بيانات متعددة إلى مخطط؟

نعم، يمكنك إضافة سلاسل بيانات متعددة إلى مخطط باستخدام `chart.getChartData().getSeries().addSeries()` طريقة.

### كيف أقوم بتخصيص ألوان الرسم البياني؟

يمكنك تخصيص ألوان الرسم البياني عن طريق تعيين تنسيق التعبئة لعناصر الرسم البياني المختلفة، مثل خطوط الشبكة والعنوان والأساطير.

### هل يمكنني إنشاء مخططات ثلاثية الأبعاد؟

نعم، يدعم Aspose.Slides لجافا إنشاء مخططات ثلاثية الأبعاد. يمكنك ضبط `ChartType` إلى نوع مخطط ثلاثي الأبعاد لإنشاء واحد.

### هل Aspose.Slides for Java متوافق مع أحدث إصدارات Java؟

نعم، يتم تحديث Aspose.Slides for Java بانتظام لدعم أحدث إصدارات Java ويوفر التوافق عبر مجموعة واسعة من بيئات Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}