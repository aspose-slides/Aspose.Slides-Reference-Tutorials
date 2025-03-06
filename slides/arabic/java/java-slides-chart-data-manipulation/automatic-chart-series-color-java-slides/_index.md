---
title: لون سلسلة الرسم البياني التلقائي في شرائح جافا
linktitle: لون سلسلة الرسم البياني التلقائي في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات ديناميكية بألوان متسلسلة تلقائية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تعزيز تصورات البيانات الخاصة بك دون عناء.
weight: 14
url: /ar/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة إلى لون سلسلة المخططات التلقائية في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء عرض تقديمي لـ PowerPoint باستخدام مخطط باستخدام Aspose.Slides لـ Java وتعيين ألوان التعبئة التلقائية لسلسلة المخططات. يمكن أن تجعل ألوان التعبئة التلقائية مخططاتك أكثر جاذبية من الناحية المرئية وتوفر لك الوقت من خلال السماح للمكتبة باختيار الألوان لك.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، سنقوم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint وإضافة شريحة إليه.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

بعد ذلك، سنقوم بإضافة مخطط عمودي متفاوت المسافات إلى الشريحة. سنقوم أيضًا بتعيين السلسلة الأولى لإظهار القيم.

```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// قم بتعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## الخطوة 3: تعبئة بيانات المخطط

الآن، سنقوم بملء المخطط بالبيانات. سنبدأ بحذف السلسلة والفئات الافتراضية التي تم إنشاؤها ثم نضيف سلسلة وفئات جديدة.

```java
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

## الخطوة 4: تعبئة بيانات السلسلة

سنقوم بملء بيانات السلسلة لكل من السلسلة 1 والسلسلة 2.

```java
// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);
// الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## الخطوة 5: تعيين لون التعبئة التلقائية للسلسلة

الآن، لنقم بتعيين ألوان التعبئة التلقائية لسلسلة المخططات. وهذا سيجعل المكتبة تختار الألوان لنا.

```java
// ضبط لون التعبئة التلقائي للسلسلة
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## الخطوة 6: احفظ العرض التقديمي

وأخيرًا، سنقوم بحفظ العرض التقديمي مع المخطط في ملف PowerPoint.

```java
// حفظ العرض التقديمي مع الرسم البياني
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل للون سلسلة الرسم البياني التلقائي في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
try
{
	// الوصول إلى الشريحة الأولى
	ISlide slide = presentation.getSlides().get_Item(0);
	// إضافة مخطط بالبيانات الافتراضية
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// ضبط لون التعبئة التلقائي للسلسلة
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// خذ سلسلة الرسم البياني الثانية
	series = chart.getChartData().getSeries().get_Item(1);
	// الآن ملء بيانات السلسلة
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// تحديد لون التعبئة للسلسلة
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// حفظ العرض التقديمي مع الرسم البياني
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء عرض تقديمي لبرنامج PowerPoint باستخدام مخطط باستخدام Aspose.Slides لـ Java وتعيين ألوان التعبئة التلقائية لسلسلة المخططات. يمكن للألوان التلقائية أن تعزز المظهر المرئي لمخططاتك وتجعل عروضك التقديمية أكثر جاذبية. يمكنك أيضًا تخصيص المخطط حسب الحاجة لمتطلباتك المحددة.

## الأسئلة الشائعة

### كيف أقوم بتعيين ألوان التعبئة التلقائية لسلسلة المخططات في Aspose.Slides لـ Java؟

لتعيين ألوان التعبئة التلقائية لسلسلة المخططات في Aspose.Slides لـ Java، استخدم الكود التالي:

```java
// ضبط لون التعبئة التلقائي للسلسلة
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

سيسمح هذا الرمز للمكتبة باختيار الألوان تلقائيًا لسلسلة المخططات.

### هل يمكنني تخصيص ألوان الرسم البياني إذا لزم الأمر؟

 نعم، يمكنك تخصيص ألوان الرسم البياني حسب الحاجة. في المثال المقدم، استخدمنا ألوان التعبئة التلقائية، ولكن يمكنك تعيين ألوان محددة عن طريق تعديل`FillType` و`SolidFillColor` خصائص شكل السلسلة.

### كيف يمكنني إضافة سلسلة أو فئات إضافية إلى المخطط؟

 لإضافة سلسلة أو فئات إضافية إلى المخطط، استخدم`getSeries()` و`getCategories()` طرق الرسم البياني`ChartData` هدف. يمكنك إضافة سلاسل وفئات جديدة عن طريق تحديد بياناتها وتسمياتها.

### هل من الممكن مواصلة تنسيق الرسم البياني والتسميات؟

نعم، يمكنك أيضًا تنسيق المخطط والسلسلة والتسميات حسب الحاجة. يوفر Aspose.Slides for Java خيارات تنسيق شاملة للمخططات، بما في ذلك الخطوط والألوان والأنماط والمزيد. يمكنك استكشاف الوثائق لمزيد من التفاصيل حول خيارات التنسيق.

### أين يمكنني العثور على مزيد من المعلومات حول العمل مع Aspose.Slides لـ Java؟

 لمزيد من المعلومات والوثائق التفصيلية حول Aspose.Slides for Java، يمكنك زيارة الوثائق المرجعية[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
