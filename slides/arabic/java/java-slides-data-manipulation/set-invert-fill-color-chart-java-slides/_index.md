---
title: قم بتعيين عكس مخطط ألوان التعبئة في شرائح Java
linktitle: قم بتعيين عكس مخطط ألوان التعبئة في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين ألوان التعبئة المعكوسة لمخططات Java Slides باستخدام Aspose.Slides. قم بتحسين تصورات المخطط الخاص بك باستخدام هذا الدليل التفصيلي والتعليمة البرمجية المصدرية.
weight: 22
url: /ar/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتعيين مخطط ألوان التعبئة العكسية في شرائح Java

في هذا البرنامج التعليمي، سنوضح كيفية تعيين لون التعبئة المعكوس للمخطط في Java Slides باستخدام Aspose.Slides for Java. يعد عكس لون التعبئة ميزة مفيدة عندما تريد تمييز القيم السالبة في مخطط بلون معين. سنقدم تعليمات خطوة بخطوة وكود المصدر لتحقيق ذلك.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Aspose.Slides لمكتبة Java.
2. إعداد بيئة تطوير جافا.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، نحتاج إلى إنشاء عرض تقديمي لإضافة المخطط الخاص بنا إليه. يمكنك استخدام الكود التالي لإنشاء عرض تقديمي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا عموديًا متفاوت المسافات إلى العرض التقديمي. وإليك كيف يمكنك القيام بذلك:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## الخطوة 3: إعداد بيانات المخطط

الآن، لنقم بإعداد بيانات المخطط، بما في ذلك السلاسل والفئات:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// إضافة سلسلة وفئات جديدة
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## الخطوة 4: تعبئة بيانات السلسلة

الآن، دعونا نملأ بيانات السلسلة للمخطط:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## الخطوة 5: تعيين لون التعبئة العكسي

لتعيين لون التعبئة المعكوس لسلسلة المخططات، يمكنك استخدام الكود التالي:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

في الكود أعلاه، قمنا بتعيين السلسلة لعكس لون التعبئة للقيم السالبة وتحديد لون التعبئة المقلوبة.

## الخطوة 6: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي بالمخطط:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لتعيين مخطط ألوان التعبئة العكسية في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// إضافة سلسلة وفئات جديدة
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// خذ سلسلة المخططات الأولى وقم بتعبئة بيانات السلسلة.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## خاتمة

لقد أوضحنا لك في هذا البرنامج التعليمي كيفية تعيين لون التعبئة المعكوس للمخطط في Java Slides باستخدام Aspose.Slides لـ Java. تسمح لك هذه الميزة بتمييز القيم السلبية في المخططات الخاصة بك بلون معين، مما يجعل بياناتك أكثر إفادة من الناحية المرئية.

## الأسئلة الشائعة

في هذا القسم، سنتناول بعض الأسئلة الشائعة المتعلقة بتعيين لون التعبئة المعكوس للمخطط في Java Slides باستخدام Aspose.Slides لـ Java.

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

 يمكنك تثبيت Aspose.Slides لـ Java عن طريق تضمين ملفات Aspose.Slides JAR في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المتوفرة في الوثائق الخاصة ببيئة التطوير الخاصة بك.

### هل يمكنني تخصيص اللون للتعبئة المعكوسة في سلسلة المخططات؟

نعم، يمكنك تخصيص اللون للتعبئة المعكوسة في سلسلة المخططات. في مثال التعليمات البرمجية المقدم،`series.getInvertedSolidFillColor().setColor(Color.RED)` يضبط الخط اللون على اللون الأحمر للتعبئة المقلوبة. يمكنك استبدال`Color.RED` مع أي لون آخر من اختيارك.

### كيف يمكنني تعديل نوع المخطط في Aspose.Slides لـ Java؟

 يمكنك تعديل نوع المخطط عن طريق تغيير`ChartType` المعلمة عند إضافة مخطط إلى العرض التقديمي. في مثال التعليمات البرمجية، استخدمنا`ChartType.ClusteredColumn` . يمكنك استكشاف أنواع المخططات الأخرى مثل المخططات الخطية، والمخططات الشريطية، والمخططات الدائرية، وما إلى ذلك، عن طريق تحديد المخططات المناسبة`ChartType` قيمة التعداد.

### كيف يمكنني إضافة سلسلة بيانات متعددة إلى مخطط؟

 لإضافة سلسلة بيانات متعددة إلى مخطط، يمكنك استخدام`chart.getChartData().getSeries().add(...)` طريقة لكل سلسلة تريد إضافتها. تأكد من توفير نقاط البيانات والتسميات المناسبة لكل سلسلة لملء المخطط الخاص بك بسلاسل متعددة.

### هل هناك طريقة لتخصيص جوانب أخرى من مظهر المخطط؟

نعم، يمكنك تخصيص جوانب مختلفة من مظهر المخطط، بما في ذلك تسميات المحاور والعناوين ووسائل الإيضاح والمزيد باستخدام Aspose.Slides for Java. راجع الوثائق للحصول على إرشادات مفصلة حول تخصيص عناصر المخطط ومظهره.

### هل يمكنني حفظ المخطط بتنسيقات مختلفة؟

 نعم، يمكنك حفظ المخطط بتنسيقات مختلفة باستخدام Aspose.Slides لـ Java. في مثال التعليمات البرمجية المقدم، قمنا بحفظ العرض التقديمي كملف PPTX. يمكنك استخدام مختلفة`SaveFormat` خيارات لحفظه بتنسيقات أخرى مثل PDF أو PNG أو SVG، حسب متطلباتك.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
