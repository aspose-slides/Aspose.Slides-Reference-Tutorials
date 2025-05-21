---
"description": "تعرّف على كيفية إنشاء مخططات بيانية ديناميكية مع تلوين تلقائي للسلاسل في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. حسّن عروضك المرئية للبيانات بسهولة."
"linktitle": "تلوين سلسلة المخططات تلقائيًا في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تلوين سلسلة المخططات تلقائيًا في شرائح Java"
"url": "/ar/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تلوين سلسلة المخططات تلقائيًا في شرائح Java


## مقدمة إلى تلوين سلسلة المخططات تلقائيًا في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء عرض تقديمي في PowerPoint باستخدام مخطط باستخدام Aspose.Slides لجافا، وتعيين ألوان تعبئة تلقائية لسلسلة المخططات. تُضفي ألوان التعبئة التلقائية على مخططاتك مظهرًا أكثر جاذبية وتوفر عليك الوقت من خلال السماح للمكتبة باختيار الألوان نيابةً عنك.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا في مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، سنقوم بإنشاء عرض تقديمي جديد في PowerPoint وإضافة شريحة إليه.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

بعد ذلك، سنضيف مخططًا عموديًا مجمعًا إلى الشريحة. وسنضبط السلسلة الأولى لعرض القيم.

```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// تعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## الخطوة 3: ملء بيانات الرسم البياني

الآن، سنملأ الرسم البياني بالبيانات. سنبدأ بحذف السلاسل والفئات المُولّدة افتراضيًا، ثم نضيف سلاسل وفئات جديدة.

```java
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// حذف السلسلة والفئات المولدة افتراضيًا
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

## الخطوة 4: ملء بيانات السلسلة

سنقوم بملء بيانات السلسلة لكل من السلسلة 1 والسلسلة 2.

```java
// خذ أول سلسلة مخططات
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## الخطوة 5: تعيين لون التعبئة التلقائي للسلسلة

الآن، لنضبط ألوان التعبئة التلقائية لسلسلة المخططات. هذا سيجعل المكتبة تختار الألوان لنا.

```java
// ضبط لون التعبئة التلقائي للسلسلة
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## الخطوة 6: حفظ العرض التقديمي

وأخيرًا، سنحفظ العرض التقديمي مع الرسم البياني في ملف PowerPoint.

```java
// حفظ العرض التقديمي مع الرسم البياني
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل للون سلسلة المخططات التلقائي في شرائح Java

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
	// تعيين السلسلة الأولى لإظهار القيم
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// ضبط فهرس ورقة بيانات الرسم البياني
	int defaultWorksheetIndex = 0;
	// الحصول على ورقة عمل بيانات الرسم البياني
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// حذف السلسلة والفئات المولدة افتراضيًا
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
	// خذ أول سلسلة مخططات
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// يتم الآن ملء بيانات السلسلة
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// ضبط لون التعبئة التلقائي للسلسلة
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// خذ سلسلة الرسم البياني الثانية
	series = chart.getChartData().getSeries().get_Item(1);
	// يتم الآن ملء بيانات السلسلة
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// تعيين لون التعبئة للسلسلة
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

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء عرض تقديمي في PowerPoint باستخدام مخطط بياني باستخدام Aspose.Slides لجافا، وتعيين ألوان تعبئة تلقائية لسلسلة المخططات. تُحسّن الألوان التلقائية المظهر المرئي لمخططاتك وتجعل عروضك التقديمية أكثر جاذبية. يمكنك تخصيص المخطط حسب احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف أقوم بتعيين ألوان التعبئة التلقائية لسلسلة المخططات في Aspose.Slides لـ Java؟

لتعيين ألوان التعبئة التلقائية لسلسلة المخططات في Aspose.Slides لـ Java، استخدم الكود التالي:

```java
// ضبط لون التعبئة التلقائي للسلسلة
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

سيسمح هذا الكود للمكتبة باختيار الألوان لسلسلة المخططات تلقائيًا.

### هل يمكنني تخصيص ألوان الرسم البياني إذا لزم الأمر؟

نعم، يمكنك تخصيص ألوان المخطط حسب الحاجة. في المثال المقدم، استخدمنا ألوان تعبئة تلقائية، ولكن يمكنك تحديد ألوان محددة بتعديل `FillType` و `SolidFillColor` خصائص تنسيق السلسلة.

### كيف يمكنني إضافة سلاسل أو فئات إضافية إلى الرسم البياني؟

لإضافة سلسلة أو فئات إضافية إلى الرسم البياني، استخدم `getSeries()` و `getCategories()` طرق الرسم البياني `ChartData` يمكنك إضافة سلاسل وفئات جديدة عن طريق تحديد بياناتها وعلاماتها.

### هل من الممكن تنسيق الرسم البياني والعلامات بشكل أكبر؟

نعم، يمكنك تنسيق المخطط والسلسلة والتسميات بشكل إضافي حسب الحاجة. يوفر Aspose.Slides لـ Java خيارات تنسيق شاملة للمخططات، بما في ذلك الخطوط والألوان والأنماط وغيرها. يمكنك الاطلاع على الوثائق لمزيد من التفاصيل حول خيارات التنسيق.

### أين يمكنني العثور على مزيد من المعلومات حول العمل مع Aspose.Slides لـ Java؟

لمزيد من المعلومات والوثائق التفصيلية حول Aspose.Slides for Java، يمكنك زيارة وثائق المرجع [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}