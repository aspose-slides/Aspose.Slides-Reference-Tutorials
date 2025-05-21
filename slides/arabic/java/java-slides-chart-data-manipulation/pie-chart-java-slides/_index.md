---
"description": "تعلّم كيفية إنشاء مخططات دائرية رائعة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لمطوري جافا."
"linktitle": "مخطط دائري في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط دائري في شرائح Java"
"url": "/ar/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط دائري في شرائح Java


## مقدمة لإنشاء مخطط دائري في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنشرح كيفية إنشاء مخطط دائري في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. سنزودك بإرشادات خطوة بخطوة وشيفرة مصدر جافا لمساعدتك على البدء. يفترض هذا الدليل أنك قد قمتَ بإعداد بيئة التطوير الخاصة بك باستخدام Aspose.Slides لجافا.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا وتهيئتها في مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

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

// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation presentation = new Presentation();
```

أنشئ كائن عرض تقديمي جديد لتمثيل ملف PowerPoint الخاص بك. استبدل `"Your Document Directory"` مع المسار الفعلي الذي تريد حفظ العرض التقديمي فيه.

## الخطوة 3: إضافة شريحة

```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```

احصل على الشريحة الأولى من العرض التقديمي حيث تريد إضافة مخطط دائري.

## الخطوة 4: إضافة مخطط دائري

```java
// إضافة مخطط دائري بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

أضف مخططًا دائريًا إلى الشريحة في الموضع والحجم المحددين.

## الخطوة 5: تعيين عنوان الرسم البياني

```java
// تعيين عنوان الرسم البياني
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

حدّد عنوانًا للمخطط الدائري. يمكنك تخصيص العنوان حسب الحاجة.

## الخطوة 6: تخصيص بيانات الرسم البياني

```java
// تعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// حذف السلسلة والفئات المولدة افتراضيًا
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// إضافة فئات جديدة
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// إضافة سلسلة جديدة
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// ملء بيانات السلسلة
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

خصّص بيانات الرسم البياني بإضافة فئات وسلاسل، وضبط قيمها. في هذا المثال، لدينا ثلاث فئات وسلسلة واحدة مع نقاط بيانات مقابلة.

## الخطوة 7: تخصيص قطاعات المخطط الدائري

```java
// تعيين ألوان القطاع
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

خصّص مظهر كل قطاع في المخطط الدائري. يمكنك تغيير الألوان وأنماط الحدود والخصائص المرئية الأخرى.

## الخطوة 8: تخصيص تسميات البيانات

```java
// تخصيص تسميات البيانات
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// تخصيص تسميات البيانات لنقاط البيانات الأخرى بطريقة مماثلة
```

خصّص تسميات البيانات لكل نقطة بيانات في المخطط الدائري. يمكنك التحكم في القيم المعروضة على المخطط.

## الخطوة 9: إظهار خطوط القائد

```java
// إظهار خطوط القائد للرسم البياني
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

تمكين خطوط القادة لربط تسميات البيانات بالقطاعات المقابلة لها.

## الخطوة 10: ضبط زاوية دوران المخطط الدائري

```java
// تعيين زاوية الدوران لقطاعات مخطط الفطيرة
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

اضبط زاوية دوران قطاعات المخطط الدائري. في هذا المثال، ضبطناها على ١٨٠ درجة.

## الخطوة 11: حفظ العرض التقديمي

```java
// احفظ العرض التقديمي باستخدام مخطط الفطيرة
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

احفظ العرض التقديمي مع المخطط الدائري في الدليل المحدد.

## كود المصدر الكامل للمخطط الدائري في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation presentation = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide slides = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// عنوان مخطط الإعداد
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// تعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// حذف السلسلة والفئات المولدة افتراضيًا
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// إضافة فئات جديدة
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// إضافة سلسلة جديدة
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// لا يعمل في الإصدار الجديد
// إضافة نقاط جديدة وتعيين لون القطاع
// series.IsColorVaried = صحيح؛
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// تعيين حدود القطاع
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// تعيين حدود القطاع
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// تعيين حدود القطاع
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// إنشاء تسميات مخصصة لكل فئة من الفئات للسلسلة الجديدة
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(صحيح)؛
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// إظهار خطوط القائد للرسم البياني
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// ضبط زاوية الدوران لقطاعات المخطط الدائري
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// حفظ العرض التقديمي مع الرسم البياني
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## خاتمة

لقد نجحت في إنشاء مخطط دائري في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يمكنك تخصيص مظهر المخطط وتسميات بياناته وفقًا لاحتياجاتك الخاصة. يقدم هذا البرنامج التعليمي مثالاً أساسيًا، ويمكنك تحسين مخططاتك وتخصيصها حسب الحاجة.

## الأسئلة الشائعة

### كيف يمكنني تغيير ألوان القطاعات الفردية في المخطط الدائري؟

لتغيير ألوان القطاعات الفردية في المخطط الدائري، يمكنك تخصيص لون التعبئة لكل نقطة بيانات. في مثال الكود المرفق، شرحنا كيفية ضبط لون التعبئة لكل قطاع باستخدام `getSolidFillColor().setColor()` الطريقة. يمكنك تعديل قيم الألوان للحصول على المظهر المطلوب.

### هل يمكنني إضافة المزيد من الفئات وسلاسل البيانات إلى المخطط الدائري؟

نعم، يمكنك إضافة فئات وسلاسل بيانات إضافية إلى المخطط الدائري. للقيام بذلك، يمكنك استخدام `getChartData().getCategories().add()` و `getChartData().getSeries().add()` كما هو موضح في المثال. ما عليك سوى توفير البيانات والعلامات المناسبة للفئات والسلاسل الجديدة لتوسيع مخططك.

### كيف يمكنني تخصيص مظهر تسميات البيانات؟

يمكنك تخصيص مظهر تسميات البيانات باستخدام `getDataLabelFormat()` على تسمية كل نقطة بيانات. في المثال، أوضحنا كيفية عرض القيمة على تسميات البيانات باستخدام `getDataLabelFormat().setShowValue(true)`يمكنك تخصيص تسميات البيانات بشكل أكبر عن طريق التحكم في القيم التي يتم عرضها، وإظهار مفاتيح الأسطورة، وضبط خيارات التنسيق الأخرى.

### هل يمكنني تغيير عنوان الرسم البياني الدائري؟

نعم، يمكنك تغيير عنوان المخطط الدائري. في الكود المُرفق، نحدد عنوان المخطط باستخدام `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`.يمكنك استبدال `"Sample Title"` مع نص العنوان المطلوب.

### كيف يمكنني حفظ العرض التقديمي الناتج باستخدام مخطط الفطيرة؟

لحفظ العرض التقديمي باستخدام مخطط الفطيرة، استخدم `presentation.save()` الطريقة. أدخل مسار الملف المطلوب واسمه، بالإضافة إلى التنسيق الذي تريد حفظ العرض التقديمي به. على سبيل المثال:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

تأكد من تحديد مسار الملف والتنسيق الصحيحين.

### هل يمكنني إنشاء أنواع أخرى من الرسوم البيانية باستخدام Aspose.Slides لـ Java؟

نعم، يدعم Aspose.Slides لجافا أنواعًا مختلفة من المخططات، بما في ذلك المخططات الشريطية والخطية وغيرها. يمكنك إنشاء أنواع مختلفة من المخططات بتغيير `ChartType` عند إضافة مخطط بياني. راجع وثائق Aspose.Slides لمزيد من التفاصيل حول إنشاء أنواع مختلفة من المخططات البيانية.

### كيف يمكنني العثور على مزيد من المعلومات والأمثلة للعمل مع Aspose.Slides لـ Java؟

لمزيد من المعلومات والوثائق التفصيلية والأمثلة الإضافية، يمكنك زيارة [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/). إنه يوفر موارد شاملة لمساعدتك على استخدام المكتبة بشكل فعال.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}