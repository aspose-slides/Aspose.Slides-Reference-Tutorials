---
"description": "تعرّف على كيفية ضبط ألوان التعبئة المعكوسة لرسومات Java Slides باستخدام Aspose.Slides. حسّن عروضك المرئية باستخدام هذا الدليل المفصل وشيفرة المصدر."
"linktitle": "تعيين مخطط لون التعبئة المعكوس في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين مخطط لون التعبئة المعكوس في شرائح Java"
"url": "/ar/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين مخطط لون التعبئة المعكوس في شرائح Java


## مقدمة لتعيين مخطط لون التعبئة المعكوس في شرائح Java

في هذا البرنامج التعليمي، سنوضح كيفية ضبط لون التعبئة العكسي لرسم بياني في شرائح جافا باستخدام Aspose.Slides لجافا. يُعدّ عكس لون التعبئة ميزة مفيدة عند إبراز القيم السالبة في رسم بياني بلون محدد. سنقدم تعليمات خطوة بخطوة وشيفرة المصدر لتحقيق ذلك.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Aspose.Slides لمكتبة Java.
2. تم إعداد بيئة تطوير Java.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، علينا إنشاء عرض تقديمي لإضافة مخططنا إليه. يمكنك استخدام الكود التالي لإنشاء العرض التقديمي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا عموديًا مجمعًا إلى العرض التقديمي. إليك كيفية القيام بذلك:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## الخطوة 3: إعداد بيانات الرسم البياني

الآن، دعنا نقوم بإعداد بيانات الرسم البياني، بما في ذلك السلسلة والفئات:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// إضافة سلاسل وفئات جديدة
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## الخطوة 4: ملء بيانات السلسلة

الآن، دعونا نملأ بيانات السلسلة للرسم البياني:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## الخطوة 5: تعيين لون التعبئة العكسي

لتعيين لون التعبئة المعكوس لسلسلة الرسم البياني، يمكنك استخدام الكود التالي:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

في الكود أعلاه، قمنا بتعيين السلسلة لعكس لون التعبئة للقيم السلبية وتحديد اللون للتعبئة المقلوبة.

## الخطوة 6: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع الرسم البياني:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لمخطط تعيين لون التعبئة المعكوس في شرائح Java

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
// إضافة سلاسل وفئات جديدة
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// خذ سلسلة الرسم البياني الأولى وقم بتعبئة بيانات السلسلة.
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

في هذا البرنامج التعليمي، شرحنا لك كيفية تعيين لون التعبئة المعكوسة لرسم بياني في شرائح جافا باستخدام Aspose.Slides لجافا. تتيح لك هذه الميزة إبراز القيم السالبة في رسومك البيانية بلون محدد، مما يجعل بياناتك أكثر وضوحًا من الناحية البصرية.

## الأسئلة الشائعة

في هذا القسم، سنتناول بعض الأسئلة الشائعة المتعلقة بتعيين لون التعبئة العكسي لمخطط في Java Slides باستخدام Aspose.Slides لـ Java.

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

يمكنك تثبيت Aspose.Slides لجافا عن طريق تضمين ملفات Aspose.Slides JAR في مشروع جافا. يمكنك تنزيل المكتبة من [صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المقدمة في الوثائق الخاصة ببيئة التطوير الخاصة بك.

### هل يمكنني تخصيص اللون للتعبئة المقلوبة في سلسلة الرسم البياني؟

نعم، يمكنك تخصيص لون التعبئة المعكوسة في سلسلة المخططات. في مثال الكود المُقدّم، `series.getInvertedSolidFillColor().setColor(Color.RED)` يُعيّن الخط اللون الأحمر للتعبئة المعكوسة. يمكنك استبدال `Color.RED` مع أي لون آخر من اختيارك.

### كيف يمكنني تعديل نوع الرسم البياني في Aspose.Slides لـ Java؟

يمكنك تعديل نوع الرسم البياني عن طريق تغيير `ChartType` عند إضافة مخطط إلى العرض التقديمي. في مثال الكود، استخدمنا `ChartType.ClusteredColumn`يمكنك استكشاف أنواع أخرى من المخططات مثل المخططات الخطية، والمخططات الشريطية، والمخططات الدائرية، وما إلى ذلك، من خلال تحديد المخططات المناسبة `ChartType` قيمة التعداد.

### كيف يمكنني إضافة سلاسل بيانات متعددة إلى مخطط؟

لإضافة سلاسل بيانات متعددة إلى مخطط، يمكنك استخدام `chart.getChartData().getSeries().add(...)` استخدم طريقة لكل سلسلة ترغب بإضافتها. تأكد من توفير نقاط البيانات والتسميات المناسبة لكل سلسلة لملء مخططك بسلاسل متعددة.

### هل هناك طريقة لتخصيص جوانب أخرى من مظهر الرسم البياني؟

نعم، يمكنك تخصيص جوانب مختلفة من مظهر المخطط، بما في ذلك تسميات المحاور والعناوين والرموز التوضيحية وغيرها باستخدام Aspose.Slides لجافا. راجع الوثائق للحصول على إرشادات مفصلة حول تخصيص عناصر المخطط ومظهره.

### هل يمكنني حفظ الرسم البياني بتنسيقات مختلفة؟

نعم، يمكنك حفظ المخطط بتنسيقات مختلفة باستخدام Aspose.Slides لجافا. في مثال الكود المرفق، حفظنا العرض التقديمي كملف PPTX. يمكنك استخدام تنسيقات مختلفة. `SaveFormat` خيارات لحفظه بتنسيقات أخرى مثل PDF أو PNG أو SVG، اعتمادًا على متطلباتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}