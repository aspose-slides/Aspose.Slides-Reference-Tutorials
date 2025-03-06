---
title: الرسم البياني الدائري في شرائح جافا
linktitle: الرسم البياني الدائري في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات دائرية مذهلة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع الكود المصدري لمطوري Java.
type: docs
weight: 23
url: /ar/java/chart-data-manipulation/pie-chart-java-slides/
---

## مقدمة لإنشاء مخطط دائري في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنوضح كيفية إنشاء مخطط دائري في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. سنزودك بتعليمات خطوة بخطوة وكود مصدر Java لمساعدتك على البدء. يفترض هذا الدليل أنك قمت بالفعل بإعداد بيئة التطوير الخاصة بك باستخدام Aspose.Slides for Java.

## المتطلبات الأساسية

 قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides for Java وتكوينها في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: استيراد المكتبات المطلوبة

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

تأكد من استيراد الفئات الضرورية من مكتبة Aspose.Slides.

## الخطوة 2: تهيئة العرض التقديمي

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation presentation = new Presentation();
```

 قم بإنشاء كائن عرض تقديمي جديد لتمثيل ملف PowerPoint الخاص بك. يستبدل`"Your Document Directory"` بالمسار الفعلي الذي تريد حفظ العرض التقديمي فيه.

## الخطوة 3: إضافة شريحة

```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```

احصل على الشريحة الأولى من العرض التقديمي حيث تريد إضافة المخطط الدائري.

## الخطوة 4: إضافة مخطط دائري

```java
// أضف مخططًا دائريًا يحتوي على البيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

أضف مخططًا دائريًا إلى الشريحة في الموضع والحجم المحددين.

## الخطوة 5: تعيين عنوان المخطط

```java
// تعيين عنوان الرسم البياني
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

تعيين عنوان للمخطط الدائري. يمكنك تخصيص العنوان حسب الحاجة.

## الخطوة 6: تخصيص بيانات الرسم البياني

```java
//قم بتعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// حذف السلسلة والفئات الافتراضية التي تم إنشاؤها
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// إضافة فئات جديدة
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// إضافة سلسلة جديدة
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// تعبئة بيانات السلسلة
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

قم بتخصيص بيانات المخطط عن طريق إضافة الفئات والسلاسل وتعيين قيمها. في هذا المثال، لدينا ثلاث فئات وسلسلة واحدة مع نقاط البيانات المقابلة.

## الخطوة 7: تخصيص قطاعات المخطط الدائري

```java
// ضبط ألوان القطاع
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// تخصيص مظهر كل قطاع
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// تخصيص حدود القطاع
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// تخصيص القطاعات الأخرى بطريقة مماثلة
```

تخصيص مظهر كل قطاع في المخطط الدائري. يمكنك تغيير الألوان وأنماط الحدود والخصائص المرئية الأخرى.

## الخطوة 8: تخصيص تسميات البيانات

```java
// تخصيص تسميات البيانات
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// قم بتخصيص تسميات البيانات لنقاط البيانات الأخرى بطريقة مماثلة
```

قم بتخصيص تسميات البيانات لكل نقطة بيانات في المخطط الدائري. يمكنك التحكم في القيم التي يتم عرضها على الرسم البياني.

## الخطوة 9: إظهار خطوط القائد

```java
// إظهار الخطوط الرئيسية للمخطط
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

تمكين الخطوط الرئيسية من ربط تسميات البيانات بالقطاعات المقابلة لها.

## الخطوة 10: ضبط زاوية دوران المخطط الدائري

```java
// اضبط زاوية الدوران لقطاعات المخطط الدائري
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

اضبط زاوية الدوران لقطاعات المخطط الدائري. في هذا المثال، قمنا بضبطها على 180 درجة.

## الخطوة 11: احفظ العرض التقديمي

```java
// احفظ العرض التقديمي باستخدام المخطط الدائري
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

احفظ العرض التقديمي باستخدام المخطط الدائري في الدليل المحدد.

## أكمل كود المصدر للمخطط الدائري في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation presentation = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide slides = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// إعداد عنوان المخطط
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// قم بتعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// إعداد فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// حذف السلسلة والفئات الافتراضية التي تم إنشاؤها
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// إضافة فئات جديدة
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// إضافة سلسلة جديدة
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// لا يعمل في الاصدار الجديد
// إضافة نقاط جديدة وتحديد لون القطاع
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// تحديد حدود القطاع
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// تحديد حدود القطاع
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// تحديد حدود القطاع
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// قم بإنشاء تسميات مخصصة لكل فئة من الفئات للسلسلة الجديدة
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// إظهار الخطوط القائدة للمخطط
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// ضبط زاوية الدوران لقطاعات الرسم البياني الدائري
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// حفظ العرض التقديمي مع الرسم البياني
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## خاتمة

لقد نجحت في إنشاء مخطط دائري في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكنك تخصيص مظهر المخطط وتسميات البيانات وفقًا لمتطلباتك المحددة. يوفر هذا البرنامج التعليمي مثالاً أساسيًا، ويمكنك تحسين مخططاتك وتخصيصها حسب الحاجة.

## الأسئلة الشائعة

### كيف يمكنني تغيير ألوان القطاعات الفردية في المخطط الدائري؟

 لتغيير ألوان القطاعات الفردية في المخطط الدائري، يمكنك تخصيص لون التعبئة لكل نقطة بيانات. في مثال التعليمات البرمجية المقدم، أوضحنا كيفية تعيين لون التعبئة لكل قطاع باستخدام`getSolidFillColor().setColor()` طريقة. يمكنك تعديل قيم الألوان لتحقيق المظهر المطلوب.

### هل يمكنني إضافة المزيد من الفئات وسلاسل البيانات إلى المخطط الدائري؟

 نعم، يمكنك إضافة فئات وسلاسل بيانات إضافية إلى المخطط الدائري. للقيام بذلك، يمكنك استخدام`getChartData().getCategories().add()` و`getChartData().getSeries().add()` الطرق كما هو موضح في المثال. ما عليك سوى توفير البيانات والتسميات المناسبة للفئات والسلاسل الجديدة لتوسيع المخطط الخاص بك.

### كيف يمكنني تخصيص مظهر تسميات البيانات؟

 يمكنك تخصيص مظهر تسميات البيانات باستخدام`getDataLabelFormat()` الطريقة على تسمية كل نقطة بيانات. في المثال، أوضحنا كيفية إظهار القيمة على تسميات البيانات باستخدام`getDataLabelFormat().setShowValue(true)`. يمكنك تخصيص تسميات البيانات بشكل أكبر من خلال التحكم في القيم التي يتم عرضها وإظهار مفاتيح وسيلة الإيضاح وضبط خيارات التنسيق الأخرى.

### هل يمكنني تغيير عنوان المخطط الدائري؟

 نعم، يمكنك تغيير عنوان المخطط الدائري. في الكود المقدم، قمنا بتعيين عنوان المخطط باستخدام`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . يمكنك استبدال`"Sample Title"` مع نص العنوان المطلوب.

### كيف يمكنني حفظ العرض التقديمي الذي تم إنشاؤه باستخدام المخطط الدائري؟

 لحفظ العرض التقديمي باستخدام المخطط الدائري، استخدم`presentation.save()` طريقة. قم بتوفير مسار الملف والاسم المطلوبين بالإضافة إلى التنسيق الذي تريد حفظ العرض التقديمي به. على سبيل المثال:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

تأكد من تحديد مسار الملف وتنسيقه الصحيحين.

### هل يمكنني إنشاء أنواع أخرى من المخططات باستخدام Aspose.Slides لـ Java؟

نعم، يدعم Aspose.Slides for Java أنواعًا مختلفة من المخططات، بما في ذلك المخططات الشريطية والمخططات الخطية والمزيد. يمكنك إنشاء أنواع مختلفة من المخططات عن طريق تغيير`ChartType` عند إضافة الرسم البياني. راجع وثائق Aspose.Slides للحصول على مزيد من التفاصيل حول إنشاء أنواع مختلفة من المخططات.

### كيف يمكنني العثور على مزيد من المعلومات والأمثلة للعمل مع Aspose.Slides لـ Java؟

 لمزيد من المعلومات والوثائق التفصيلية والأمثلة الإضافية، يمكنك زيارة الموقع[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/). فهو يوفر موارد شاملة لمساعدتك في استخدام المكتبة بشكل فعال.