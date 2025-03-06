---
title: الرسوم البيانية العادية في شرائح جافا
linktitle: الرسوم البيانية العادية في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: إنشاء مخططات عادية في شرائح Java باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة والكود المصدري لإنشاء المخططات وتخصيصها وحفظها في عروض PowerPoint التقديمية.
weight: 21
url: /ar/java/chart-data-manipulation/normal-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى المخططات العادية في شرائح جافا

في هذا البرنامج التعليمي، سنتعرف على عملية إنشاء مخططات عادية في Java Slides باستخدام Aspose.Slides for Java API. سنستخدم إرشادات خطوة بخطوة مع التعليمات البرمجية المصدر لتوضيح كيفية إنشاء مخطط عمودي متفاوت المسافات في عرض تقديمي لـ PowerPoint.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Aspose.Slides لـ Java API.
2. تم إعداد بيئة تطوير Java.
3. المعرفة الأساسية ببرمجة جافا.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك دليلاً لمشروعك. دعنا نسميه "دليل المستندات الخاص بك" كما هو مذكور في الكود. يمكنك استبدال هذا بالمسار الفعلي لدليل مشروعك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## الخطوة 2: إنشاء عرض تقديمي

الآن، لنقم بإنشاء عرض تقديمي لـ PowerPoint والوصول إلى الشريحة الأولى الخاصة به.

```java
// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation pres = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```

## الخطوة 3: إضافة مخطط

سنضيف مخططًا عموديًا متفاوت المسافات إلى الشريحة ونحدد عنوانه.

```java
// إضافة مخطط بالبيانات الافتراضية
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// إعداد عنوان المخطط
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## الخطوة 4: إعداد بيانات الرسم البياني

بعد ذلك، سنقوم بتعيين بيانات المخطط من خلال تحديد السلسلة والفئات.

```java
// قم بتعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// إعداد فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// حذف السلسلة والفئات الافتراضية التي تم إنشاؤها
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// إضافة فئات جديدة
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## الخطوة 5: تعبئة بيانات السلسلة

الآن، دعونا نملأ نقاط بيانات السلسلة للمخطط.

```java
// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// تعبئة بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// تحديد لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);

// تعبئة بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// تحديد لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## الخطوة 6: تخصيص التسميات

لنقم بتخصيص تسميات البيانات لسلسلة المخططات.

```java
// سوف تظهر التسمية الأولى اسم الفئة
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// إظهار قيمة التسمية الثالثة مع اسم السلسلة والفاصل
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## الخطوة 7: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع المخطط في دليل مشروعك.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط عمودي متفاوت المسافات في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. يمكنك تخصيص هذا المخطط بشكل أكبر وفقًا لمتطلباتك.

## أكمل كود المصدر للمخططات العادية في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation pres = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// إعداد عنوان المخطط
// Chart.getChartTitle().getTextFrameForOverriding().setText("عنوان العينة");
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
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// إضافة فئات جديدة
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// تحديد لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);
// الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// تحديد لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// سيتم عرض التسمية الأولى اسم الفئة
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// إظهار القيمة للتسمية الثالثة
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// حفظ العرض التقديمي مع الرسم البياني
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مخططات عادية في Java Slides باستخدام Aspose.Slides for Java API. لقد مررنا بدليل خطوة بخطوة مع الكود المصدري لإنشاء مخطط عمودي متفاوت المسافات في عرض PowerPoint التقديمي.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

 لتغيير نوع المخطط، قم بتعديل`ChartType`المعلمة عند إضافة الرسم البياني باستخدام`sld.getShapes().addChart()`. يمكنك الاختيار من بين أنواع المخططات المختلفة المتوفرة في Aspose.Slides.

### هل يمكنني تغيير ألوان سلسلة المخططات؟

 نعم، يمكنك تغيير ألوان سلسلة المخططات عن طريق تحديد لون التعبئة لكل سلسلة تستخدمها`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### كيف يمكنني إضافة المزيد من الفئات أو السلاسل إلى المخطط؟

 يمكنك إضافة المزيد من الفئات أو السلاسل إلى المخطط عن طريق إضافة نقاط بيانات وتسميات جديدة باستخدام`chart.getChartData().getCategories().add()` و`chart.getChartData().getSeries().add()` طُرق.

### كيف يمكنني تخصيص عنوان المخطط بشكل أكبر؟

 يمكنك تخصيص عنوان المخطط بشكل أكبر عن طريق تعديل خصائصه`chart.getChartTitle()` مثل محاذاة النص وحجم الخط واللون.

### كيف يمكنني حفظ المخطط بتنسيق ملف مختلف؟

 لحفظ المخطط بتنسيق ملف مختلف، قم بتغيير الملف`SaveFormat` المعلمة في`pres.save()` الطريقة إلى التنسيق المطلوب (على سبيل المثال، PDF، PNG، JPEG).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
